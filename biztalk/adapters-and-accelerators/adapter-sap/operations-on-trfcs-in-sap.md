---
title: "SAP の tRFCs に対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e60465716931161e9b9949e16c4630d85c2cfe2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-trfcs-in-sap"></a>SAP の tRFCs に対する操作
トランザクションの Rfc (tRFCs) は、Rfc 作業 (LUW) の論理単位の一部として呼び出されます。 SAP システムを LUW にすべてのビジネスやプログラミング タスクを完了するために必要な手順が含まれます。 TRFC が RFC; を呼び出す方法を表します一意の SAP アーティファクトではありません。  
  
 使用することができます、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] tRFC クライアントと tRFC サーバーの両方です。  
  
-   **TRFC クライアントとして**アダプターを SAP システムで、LUW で単一の RFC を呼び出すアプリケーションを有効にします。 これにより、RFC の 1 回限りののみ実行されます。 トランザクションの動作は限りません。  
  
-   **TRFC サーバーとして**アダプターでは、LUW 内の複数の Rfc を受信することができます。 アダプターは、トランザクションのコンテキストで受信 tRFC の呼び出しをサポートしていますコミットであるし、ロールのバックの動作がサポートされます。  
  
## <a name="trfc-operations"></a>tRFC 操作  
 TRFC、RFC; を起動する方法を意味します。個別の SAP アーティファクトではありません。 そのため、(対象のアダプター メタデータを取得できます)、SAP システム上のすべての RFC は、によって tRFC として提示されるも、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 tRFCs は、RFC 名前によって TRFC メタデータ カテゴリ ノードの下での操作として表示されます。 (参照または tRFCs を検索することができます、 **TRFC**ノードを使用するときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)])。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] TRFCs で、次をサポートしています。  
  
-   インポートのパラメーター  
  
-   パラメーター (変化させるパラメーターの入力側のみがサポートされます) を変更します。  
  
> [!NOTE]
>  tRFCs は、それらの出力値 (エクスポートまたは変更するパラメーター) が返されないように、非同期的に実行されます。  
  
 GUID パラメーターは tRFC 操作のため、アダプターによって確認できます。 この GUID は、SAP トランザクション ID (TID)、tRFC に関連付けられているアダプターによってマップされます。 この GUID パラメーターを使用できます。  
  
-   TRFC クライアント呼び出しで、SAP システムで tRFC を確認します。 これを行う RfcConfirmTransId 操作を呼び出すことによってです。 これは、SAP システムで TID を確認するアダプター側に表示される特別な操作です。  
  
-   TRFC クライアントと tRFC のサーバーのシナリオの両方で、アダプターから tRFC に使用される実際の SAP TID を取得します。 SAP ユーティリティ メソッドを呼び出し、ConvertGuidToTid これを行います。  
  
 これらの操作の詳細については、次を参照してください。[特別な操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)です。 メッセージの構造体と tRFCs のアダプターによって使用される SOAP アクションの詳細については、次を参照してください。 [tRFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)です。  
  
## <a name="invoking-transactional-rfcs-in-an-sap-system"></a>SAP システムでトランザクションの Rfc を呼び出す  
 通常、tRFCs を使用して実行単一 LUW; 内の 1 つまたは複数の RFC 呼び出しただし、SAP RFC SDK での制限により、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] LUW あたり 1 つの tRFC のみをサポートしています。 このため、アダプターは各 tRFC の LUW (SAP TID) を作成します。 このようなクライアントについて SAP RFC の「1 回限り」の実行を保証するためのメカニズムとして、LUW を定義し、コミットとロールバック ベース トランザクションとは限りません。  
  
 次の手順は、RFC 呼び出しを使用してクライアントで実行されるタスクをまとめて、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 これらの手順の一部は、クライアントによって実行される、アダプター、およびいくつかは、アダプターによって実行されます。  
  
1.  TRFC 操作の要求メッセージをアダプターのクライアントに送信します。 アダプターのクライアントは、このメッセージの GUID をオプションで指定できます。  
  
2.  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要求メッセージを受信し、RFC SDK を使用して、SAP システムからトランザクション ID (TID) を取得します。 アダプターはこの GUID を SAP TID; にマップして、要求メッセージに GUID が含まれている場合それ以外の場合、アダプターは新しい GUID を作成し、SAP TID に割り当てる  
  
3.  アダプターでは、TID を使用して、SAP サーバーへの呼び出し tRFC を加えます。 TID の状態マークが付いている**完了**SAP システムでします。  
  
4.  アダプターは、アダプターでクライアントに応答メッセージ (TID にマップ) される GUID を返します。  
  
5.  アダプターのクライアントは、前の手順で返される GUID を持つアダプターの RfcConfirmTransID 操作を呼び出します。  
  
6.  アダプターは、SAP TID を識別する RfcConfirmTransID 要求メッセージ内で、GUID を使用し、SAP システムで tRFC の呼び出しを確認します。 これにより、SAP サーバーをそのデータベースから TID エントリを削除します。  
  
> [!NOTE]
>  tRFC クライアント呼び出しでは、エクスポートまたは変更するパラメーターは返されません。  
  
 詳細については。  
  
-   BizTalk Server を使用して tRFC の呼び出しを参照してください[で BizTalk Server を使用して SAP tRFCs を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)です。  
  
-   モデルを使用して、WCF サービス、tRFC の呼び出しを参照してください[で WCF サービス モデルを使用して SAP tRFCs を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)です。  
  
-   メッセージの構造と、tRFC の呼び出しの SOAP アクションを参照してください[tRFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)です。  
  
## <a name="receiving-inbound-transactional-rfc-calls-from-an-sap-system"></a>SAP システムからの受信側の受信トランザクションの RFC 呼び出し  
 TRFC サーバーとしてアダプターを使用すると、SAP から tRFCs を受信します。 TRFC サーバーとして、アダプターが、tRFC を受信すると、アプリケーションに対応する tRFC 操作を呼び出します。 TRFC サーバーとして動作する、アダプターは、次の機能をサポートします。  
  
-   (SAP TID で識別される)、LUW では、複数 tRFCs (RFC 呼び出し) を含めることができます。  
  
-   アダプターは、各 SAP TID をコミットできるトランザクションを作成します。 アプリケーション コードは、このトランザクションに参加できます。  
  
-   コミットとロールバックはサポートされています。  
  
 このセクションの残りの部分では、tRFC サーバーとして、アダプターの使用に関する全般情報を提供します。 詳細については。  
  
-   BizTalk Server を使用して呼び出しを参照してください受信 tRFC の受信[受信受信 tRFC BizTalk Server を使用して SAP からの呼び出し](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)です。  
  
-   受信 tRFC を受信する WCF サービス モデルを使用して呼び出しを参照してください[WCF サービス モデルを使用して SAP で受信受信 tRFC の呼び出し](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)です。  
  
### <a name="the-tid-database"></a>TID データベース  
 アダプターが SQL Server データベースを使用して tRFC サーバーの役割を果たして、— TID データベース — トランザクション SAP システムから受信した Id を管理します。 たとえば、コミット、ロールバック、SAP システムからの呼び出しを管理し、TID を確認するために、TID データベースを使用します。 アダプターでは、GUID を作成し、TID データベース内の各 SAP TID 関連付けますがも格納されます。  
  
### <a name="prerequisites"></a>前提条件  
 TRFC サーバーとして実行するアダプターの場合、次の項目が該当することを確認する必要があります。  
  
-   RFC は、SAP システムで宣言する必要があります。 これは、アダプターは、SAP システムの RFC を説明するメタデータを取得できるようにします。 RFC は、実際には、アプリケーションで実装されます。  
  
-   アダプターは、SAP ゲートウェイで、RFC 変換先を登録する必要があります。 登録は、プログラム ID と呼ばれる論理名をに基づいてください。 プログラム ID を指定する URI の接続でパラメーターを指定する SAP ゲートウェイ、およびこの登録の SAP サーバー。  
  
-   TID データベースは、SQL Server で作成する必要があります。 これを行うには、セットアップでインストールされている SQL スクリプトを実行する必要があります。 SQL スクリプトが通常にインストールされている\<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、「 [BizTalk Adapter Pack をインストールする](http://msdn.microsoft.com/library/2ae27db5-b11b-42c3-a568-e2331badf80e)です。  
  
-   **TidDatabaseConnectionString** TID データベースの SQL データベース接続文字列に設定するプロパティをバインドする必要があります。 詳細については、 **TidDatabaseConnectionString**バインディング プロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
> [!NOTE]
>  設定、 **TidDatabaseConnectionString** RFC サーバーではなく tRFC サーバーとして機能するアダプターを構成するプロパティをバインドします。 場合、 **TidDatabaseConnectionString** binding プロパティを設定し、接続 URI、RFC 変換先を指定する、アダプターが RFC 転送先からの着信呼び出しの tRFC サーバーとして機能します。 このバインドのプロパティが設定されていない場合、アダプターは、RFC サーバーとして機能します。  
  
### <a name="how-the-adapter-processes-inbound-trfcs"></a>どのアダプター プロセス受信 tRFCs  
 次の手順は、RFC クライアント呼び出しを使用して実行されるタスクをまとめて、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 これらの手順の一部は、クライアントによって実行される、アダプター、およびいくつかは、アダプターによって実行されます。  
  
1.  アダプターに、TID かどうかを確認する、SAP システム コールは使用されています。 アダプターは、SAP システムに適切な応答を返します。 TID が新しい場合は、アダプターは、コミットできるトランザクションを作成します。 このトランザクションは、SAP プログラムは、コミット (コミット動作) を実行するときに、トランザクション的な方法で TID データベースに TID を永続化に使用されます。 受信 tRFCs を処理するアプリケーション コードに公開されるもします。 さらに、アダプターでは、SAP TID に関連付ける GUID を作成します。  
  
2.  SAP システムは、1 つまたは複数のトランザクションの Rfc をアダプターに送信します。 各 tRFC は、アダプターは、アプリケーションに適切な tRFC 操作を呼び出します。 アダプターは、各操作用にアプリケーションを手順 1. で作成されたトランザクションをフローします。 アダプターは、操作の要求メッセージで手順 1. で作成された GUID を渡します。  
  
3.  SAP システムは、LUW (COMMIT WORK) をコミットします。 アダプターは、SAP TID (手順 1. で作成された) に関連付けられているトランザクションをコミットしようとします。  
  
    1.  手順 2. で呼び出しのいずれかの中に (アプリケーション) でトランザクションが中止されたアダプターがトランザクションをコミットしようとするときにエラーが発生します。 SAP に、エラーが返されます。 手順 4 に進みます。  
  
    2.  コミットが成功した場合は、TID が TID データベースに接続してようになりました。 手順 5 に進みます。  
  
4.  エラーが発生した場合の手順 3、または SAP がロールバックそのコミットの代わりに LUW (RESTART_OF_BACKGROUNDTASK) 場合、アダプター トランザクションをロールバックします。 ここでは TID は TID データベースに保存されることです。  
  
5.  SAP システムは、TID を確認します。 アダプター TID データベースから削除 TID (手順 3 が正常に完了し、TID が TID データベースに存在することを想定しています。  
  
> [!NOTE]
>  TRFC サーバー操作中に、TID データベースに接続しようとしてエラーが発生する場合はエラー コードのことを示す SAP からの着信呼び出しによって処理されませんでした、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP に返されます。  
  
### <a name="receiving-idocs-as-a-trfc-server"></a>TRFC サーバーとしての Idoc の受信  
 使用する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC サーバーまたは SAP システムから Idoc を受信する tRFC サーバーのいずれかとして。 どちらの場合に設定する必要があります、 **ReceiveIdocFormat**アダプターが、アプリケーションに IDOC データを出力する式を指定するプロパティをバインドします。 アダプターでの Idoc の受信の詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
## <a name="special-trfc-operations"></a>特殊な tRFC 操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで特定の特別な tRFC 操作も実行できます。 このような 1 つの操作は、RfcConfirmTransID です。  
  
-   **RfcConfirmTransID です。** この操作を呼び出し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を SAP サーバーに tRFC の呼び出しを確認します。 アダプターを使用して、tRFC として、SAP サーバーに Idoc を送信するシナリオでは、RfcConfirmTransID が必要です。 操作が 利用可能な**TRFC**ノードを使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
 メッセージの構造と RfcConfirmTransID 操作の SOAP アクションの詳細については、次を参照してください。 [tRFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)です。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)