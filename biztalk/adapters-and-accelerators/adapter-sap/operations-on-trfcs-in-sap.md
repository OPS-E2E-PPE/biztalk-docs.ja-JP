---
title: SAP の Trfc に対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFCs, invoking transactional RFCs in an SAP System
- TID database
- transactional RFCs
- tRFCs, receiving inbound iransactional RFC calls from an SAP system
- tRFCs
- GUID parameter
- RFCs, processing inbound
- RfcConfirmTransID
- transaction ID (TID)
- tRFC Operations
- IDOCS, receiving IDOCs as a tRFC server
- adapters, operations on tRFCs
- RFC, invoking an RFC
ms.assetid: d6a5c515-d6aa-4b70-9c23-32d1dd94d473
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b99822d838f0681cf9a6ce336ed1a23f4088c659
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996139"
---
# <a name="operations-on-trfcs-in-sap"></a>SAP の Trfc に対する操作
トランザクションの Rfc (Trfc) は、Rfc (LUW) の作業の論理ユニットの一部として呼び出されます。 SAP システムで、LUW にすべてのビジネスやプログラミング タスクを完了するために必要な手順が含まれます。 TRFC を表します。 RFC を呼び出す方法一意の SAP アーティファクトではありません。  
  
 使用することができます、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] tRFC クライアントと tRFC サーバーの両方。  
  
-   **TRFC クライアントとして**、アダプターにより、アプリケーションで、LUW で SAP システムで 1 つの RFC を呼び出す。 これには、RFC の 1 回限りのみの実行が保証されます。 トランザクションの動作は意味しません。  
  
-   **TRFC サーバーとして**アダプターでは、LUW 内で複数の Rfc を受信することができます。 アダプターは、トランザクションのコンテキストで受信 tRFC 呼び出しをサポートしていますコミットとロールバック バック動作がサポートされています。  
  
## <a name="trfc-operations"></a>tRFC 操作  
 TRFC 意味; RFC を呼び出す方法別の SAP アーティファクトではありません。 そのため、すべての RFC (対象のアダプター メタデータを取得できます)、SAP システムでの tRFC として表示されますも、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 Trfc は、RFC 名前によって TRFC メタデータ カテゴリのノードの下での操作として表示されます。 (参照または Trfc を検索することができます、 **TRFC**ノードを使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)])。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Trfc に対する次のサポートします。  
  
-   インポート パラメーター  
  
-   パラメーター (変更するパラメーターの入力側だけがサポートされます) を変更します。  
  
> [!NOTE]
>  Trfc は、それらの出力値 (エクスポートまたは変更するパラメーター) が返されないように、非同期的に実行されます。  
  
 TRFC 操作用のアダプターによって GUID パラメーターが表示されます。 この GUID は、SAP トランザクション ID (TID)、tRFC に関連付けられているアダプターによってマップされます。 この GUID パラメーターを使用できます。  
  
- TRFC クライアント呼び出しでの SAP システムの tRFC を確認します。 RfcConfirmTransId 操作を呼び出してこれを行います。 これは、SAP システムでの TID を確認するアダプターの特別な操作です。  
  
- TRFC クライアントと tRFC サーバー シナリオの両方でアダプターからの tRFC のため実際の SAP TID を取得します。 SAP ユーティリティ メソッドを呼び出し、ConvertGuidToTid これを行います。  
  
  これらの操作の詳細については、次を参照してください。[特別な操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)します。 メッセージの構造と Trfc のアダプターを使用する SOAP アクションの詳細については、次を参照してください。 [tRFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)します。  
  
## <a name="invoking-transactional-rfcs-in-an-sap-system"></a>SAP システムでトランザクションの Rfc を呼び出す  
 1 つの LUW; 内の 1 つまたは複数の RFC 呼び出しを実行する、通常、Trfc を使用します。ただし、SAP の RFC SDK での制限により、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] LUW あたり 1 つの tRFC のみをサポートしています。 このため、アダプターは、各 tRFC の LUW (SAP TID) を作成します。 このようなクライアントの場合は、SAP は、RFC の「1 回限り」の実行を保証するためのメカニズムとして、LUW を定義し、コミットとロールバック ベース トランザクションとは限りません。  
  
 次の手順が、RFC 呼び出しを使用してクライアントで実行されるタスクをまとめて、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 これらの手順の一部は、アダプター クライアントで実行され、一部は、アダプターによって実行されます。  
  
1. TRFC 操作の要求メッセージをアダプターのクライアントに送信します。 アダプターのクライアントでは、このメッセージの GUID を必要に応じて指定できます。  
  
2. [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要求メッセージを受信し、RFC SDK を使用して、SAP システムからトランザクション ID (TID) を取得します。 アダプターはこの GUID を SAP TID; にマップして、要求メッセージに GUID が含まれている場合それ以外の場合、アダプターは新しい GUID を作成して、SAP TID にマップ  
  
3. アダプターでは、TID を使用して、SAP サーバーに呼び出す tRFC を加えます。 TID の状態をマーク**FINISHED** SAP システムにします。  
  
4. アダプターは、アダプターでクライアントに応答メッセージ (TID にマップされて) いる GUID を返します。  
  
5. アダプターのクライアントでは、前の手順で返される GUID を持つアダプターの RfcConfirmTransID 操作を呼び出します。  
  
6. アダプターは、SAP TID を識別するために、RfcConfirmTransID 要求メッセージで、GUID を使用し、SAP システムで tRFC の呼び出しのことを確認します。 これにより、SAP サーバーがそのデータベースから TID エントリを削除します。  
  
> [!NOTE]
>  tRFC クライアント呼び出しでは、エクスポートまたは変更するパラメーターは返されません。  
  
 詳細については。  
  
-   BizTalk Server を使用して tRFC の呼び出しを参照してください[BizTalk Server を使用して SAP の Trfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)します。  
  
-   WCF サービス モデルを使用して tRFC の呼び出しを参照してください[WCF サービス モデルを使用して SAP の Trfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)します。  
  
-   メッセージの構造と、tRFC を呼び出すための SOAP アクションを参照してください[tRFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)します。  
  
## <a name="receiving-inbound-transactional-rfc-calls-from-an-sap-system"></a>SAP システムからの受信側の受信トランザクション RFC 呼び出し  
 TRFC サーバーとして、アダプターを使用すると、Trfc を SAP から受信します。 TRFC サーバーとして、アダプターが受信、tRFC、ときに、アプリケーションに対応する tRFC 操作を呼び出します。 TRFC サーバーとして動作する、アダプターは、次の機能をサポートします。  
  
- (SAP TID で識別される)、LUW は、複数の Trfc (RFC 呼び出し) を含めることができます。  
  
- アダプターでは、各 SAP TID のコミット トランザクションを作成します。 アプリケーション コードは、このトランザクションに参加できます。  
  
- コミットとロールバックはサポートされています。  
  
  このセクションの残りの部分は、tRFC サーバーとして、アダプターを使用する方法の一般的な情報を提供します。 に関する詳細情報。  
  
- 受信 tRFC を受信する BizTalk Server を使用して呼び出しを参照してください[受信受信 tRFC 呼び出し BizTalk Server を使用して SAP から](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)します。  
  
- 受信 tRFC を受信する WCF サービス モデルを使用して呼び出しを参照してください[WCF サービス モデルを使用して SAP で受信受信 tRFC を呼び出す](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)します。  
  
### <a name="the-tid-database"></a>TID データベース  
 アダプターが SQL Server データベースを使用して、tRFC サーバーとして動作する — TID データベース、トランザクション、SAP システムから受信した Id を管理します。 たとえば、TID データベースを使用してコミット、ロールバック、SAP システムからの呼び出しを管理および TID を確認します。 アダプターでは、GUID を作成し、関連付けます TID データベース内の各 SAP TID にも格納されます。  
  
### <a name="prerequisites"></a>前提条件  
 TRFC サーバーとして実行するアダプターの場合に、次の項目が該当することを確認する必要があります。  
  
- SAP システムでは、RFC を宣言する必要があります。 これはので、アダプターは、SAP システムから RFC を記述するメタデータを取得できます。 RFC は、アプリケーションで実際に実装されます。  
  
- アダプターは、SAP ゲートウェイ RFC 転送先に登録する必要があります。 登録は、プログラム ID と呼ばれる論理名をに基づいてください。 プログラム ID を指定する接続 URI のパラメーターを指定する SAP ゲートウェイ、およびこの登録の SAP サーバー。  
  
- TID データベースは、SQL Server で作成する必要があります。 これを行うには、セットアップでインストールする SQL スクリプトを実行する必要があります。 SQL スクリプトは通常にインストールされて\<インストール ドライブ\>: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、「 [BizTalk Adapter Pack をインストールする](http://msdn.microsoft.com/library/2ae27db5-b11b-42c3-a568-e2331badf80e)します。  
  
- **TidDatabaseConnectionString** TID データベースの SQL データベース接続文字列に設定するプロパティをバインドする必要があります。 詳細については、 **TidDatabaseConnectionString**プロパティ、バインドを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
> [!NOTE]
>  設定、 **TidDatabaseConnectionString** RFC サーバーではなく、tRFC サーバーとして機能するアダプターが構成プロパティをバインドします。 場合、 **TidDatabaseConnectionString**プロパティのバインドを設定し、接続 URI で RFC 転送先を指定する、アダプターは RFC 転送先からの着信呼び出しの tRFC サーバーとして機能します。 このバインドのプロパティが設定されていない場合、アダプターが RFC サーバーとして機能します。  
  
### <a name="how-the-adapter-processes-inbound-trfcs"></a>どのアダプター プロセス受信 Trfc  
 次の手順は、RFC クライアント呼び出しを使用して実行されるタスクをまとめて、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 これらの手順の一部は、アダプター クライアントで実行され、一部は、アダプターによって実行されます。  
  
1.  SAP システム コールをな TID かどうかを確認するアダプターには既に使用されています。 アダプターは、SAP システムに適切な応答を返します。 TID が新しい場合は、アダプターをコミットできるトランザクションを作成します。 このトランザクションは、SAP プログラムは、commit (コミット作業) を実行するときに、トランザクション的に TID データベースに TID を永続化に使用されます。 受信 Trfc を処理するアプリケーション コードに公開されることもできます。 さらに、アダプターは、SAP TID に関連付ける GUID を作成します。  
  
2.  SAP システムでは、アダプターを 1 つまたは複数のトランザクションの Rfc を送信します。 各 tRFC、アダプターは、アプリケーションに適切な tRFC 操作を呼び出します。 アダプターは、各操作用のアプリケーションには、手順 1. で作成されたトランザクションをフローします。 アダプターは、操作の要求メッセージでは、手順 1. で作成された GUID を渡します。  
  
3.  SAP システムでは、LUW (COMMIT WORK) をコミットします。 アダプターは、(手順 1. で作成された) SAP TID に関連付けられているトランザクションをコミットしようとします。  
  
    1.  手順 2 での呼び出し中に、(アプリケーション) でトランザクションが中止されて、アダプターがトランザクションをコミットしようとした場合、エラーが発生します。 SAP、エラーが返されます。 手順 4 に進みます。  
  
    2.  コミットが成功した場合、TID の TID データベースになります。 手順 5 に進みます。  
  
4.  エラーが発生した場合の手順 3、または SAP ロールバック、そのコミットではなく LUW (RESTART_OF_BACKGROUNDTASK) 場合、アダプター トランザクションをロールバックします。 ここで TID は TID のデータベースに保持されることはありません。  
  
5.  SAP システムは、TID を確認します。 アダプターは、(手順 3 を正常に完了して TID TID データベースが存在すると仮定 TID データベースから TID を削除します。  
  
> [!NOTE]
>  TRFC サーバー操作中に TID データベースに接続しようとしてエラーが発生する場合、エラー コードがあることを示す SAP からの着信呼び出しによって処理されませんでした、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP に返されます。  
  
### <a name="receiving-idocs-as-a-trfc-server"></a>TRFC サーバーとして Idoc を受信します。  
 使用する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC サーバーまたは SAP システムから Idoc を受信する tRFC サーバーのいずれかとして。 いずれの場合も、設定する必要があります、 **ReceiveIdocFormat**アダプターが、アプリケーションに IDOC データを出力する形式を指定するプロパティをバインドします。 アダプターを使用した Idoc を受信する詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)します。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
## <a name="special-trfc-operations"></a>特別な tRFC 操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで特定の特別な tRFC 操作も実行できます。 このような 1 つの操作では、RfcConfirmTransID です。  
  
- **RfcConfirmTransID します。** この操作を呼び出す、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を SAP サーバーに tRFC の呼び出しを確認します。 RfcConfirmTransID は、アダプターを使用して、tRFC として SAP サーバーに Idoc を送信するシナリオで必要な可能性があります。 操作が 利用可能な**TRFC**ノードを使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
  メッセージの構造と RfcConfirmTransID 操作の SOAP アクションの詳細については、次を参照してください。 [tRFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)します。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)