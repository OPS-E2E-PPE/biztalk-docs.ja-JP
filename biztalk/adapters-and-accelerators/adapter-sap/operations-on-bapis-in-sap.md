---
title: Sap Bapi に対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI, operations
- BAPIs, operations on
- Business Application Programming Interface
- BAPIs
- BAPI, transactions
- BAPI transactions, limitations on
ms.assetid: 6be26641-e8d3-4e11-8d82-4fdb13076580
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a319626f23b825187d65e01d687be5a1079df53a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993171"
---
# <a name="operations-on-bapis-in-sap"></a>Sap Bapi に対する操作
ビジネス アプリケーション プログラミング インターフェイス (BAPI) は、外部プロセスによって呼び出すことができる SAP ビジネス オブジェクトのメソッドです。 Bapi のでは、SAP システムでトランザクションです。  
  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] BAPI を呼び出す送信方向でサポートしています。 2 つの方法での Bapi が表示されます。  
  
- **RFC として**します。 適切な RFC を呼び出すことによって直接 BAPI を呼び出すことができます。  
  
- **ビジネス オブジェクトのメソッドとして**します。 アダプターのビジネス オブジェクト メソッドとしての Bapi のサーフェスを使用する場合は、メタデータを取得するのに役立つ便利な機能として、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。  
  
> [!IMPORTANT]
>  RFC としてまたはビジネス オブジェクトのメソッドは、アダプターでの BAPI を呼び出すことができます。アダプターの BAPI の起動方法に関係なく常に呼び出します SAP の BAPI RFC インターフェイスを使用します。  
  
 アダプターは、BAPI トランザクションをサポートします。 SAP の BAPI トランザクション モデルでは、いくつかの Bapi を作業 (LUW) の 1 つの論理単位に結合することができます。 SAP、LUW は、データベースの更新を含むトランザクションに関連するすべての手順で構成されます。  
  
 このセクションのトピックでは、ビジネス オブジェクトとしての Bapi の表示方法と、アダプターによって BAPI トランザクション (LUWs) をサポートする方法について説明します。  
 
  
## <a name="bapi-operations-as-business-object-methods"></a>BAPI 操作 (としてビジネス オブジェクト メソッド)  
 ビジネス オブジェクト メソッドを使用する場合は、メタデータを取得するのに役立つ便利なように、アダプター サーフェスの Bapi、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 アダプターは、RFC インターフェイスを使用して SAP システムの Bapi を常に呼び出します。  
  
 アダプターは、名前での Bapi の送信操作の適切なビジネス オブジェクトの下の操作としては表示します。 ビジネス オブジェクトは、アダプターでの BAPI のカテゴリ ノードの下の機能グループによって収集されます。 (参照またはビジネス オブジェクトと Bapi を検索することができます、 **BAPI**ノードを使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)])。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Bapi に対する次のサポートします。  
  
- インポート パラメーター  
  
- パラメーターをエクスポートします。  
  
- 変化するパラメーター  
  
- テーブル パラメーター  
  
  メッセージの構造と Bapi のビジネス オブジェクト メソッドとして表示するための SOAP アクションの詳細については、[BAPI 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)を参照してください。  
  
## <a name="bapi-transactions"></a>BAPI トランザクション  
 BAPI を呼び出すと、LUW で SAP システムの一部では常にします。 これは、機能は、RFC としてまたはビジネス オブジェクトのメソッドとして、BAPI を呼び出すかどうかに当てはまります。 RFC SDK では、同じ LUW の一部として同じ SAP 接続経由で送信されるすべての Bapi を扱います。 呼び出しの後にコミットするか、接続でトランザクションをロールバックして、[次へ] の BAPI 接続経由で送信された新しい LUW を開始します。  
  
 BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK をコミットまたはトランザクションをロールバックして呼び出すことができます。 アダプターでは、これら 2 つの Bapi が表示されます。  
  
- RFC 操作として [基準] ノードの下。  
  
- 各ビジネス オブジェクト。  
  
  トランザクションでの Bapi を制御するには、ことすべて経由送信されます (コミットまたはトランザクションをロールバックする呼び出しを含む)、同じ SAP 接続を確認します。 これを行うことができます。  
  
- BizTalk ソリューションを使用して、 **ConnectionState**メッセージ コンテキスト プロパティを同じ接続を使用して、トランザクションでの Bapi を送信することを確認します。 このプロパティは、アダプターによって提示され、BizTalk オーケストレーションでメッセージを送信するための接続を明示的に制御を提供します。  
  
   BizTalk Server を使用して BAPI トランザクションを実行するため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のメッセージ コンテキスト プロパティがサポートされます。  
  
  |フィールド|説明|  
  |-----------|-----------------|  
  |OPEN|トランザクションの新しいチャネルを開きます。|  
  |再利用します。|トランザクションの既存のチャネルを再利用します。|  
  |CLOSE|トランザクションをコミットし、既存のチャネルを閉じます。|  
  |ABORT|トランザクションを中止し、既存のチャネルを閉じます。|  
  
   詳細については、[で BizTalk Server を使用して SAP の BAPI トランザクションの実行](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)を参照してください。  
  
  > [!NOTE]
  >  設定することを確認、 **EnableBizTalkCompatibilityMode**BizTalk Server を使用してトランザクションを実行するときに、プロパティをバインドします。  
  
- トランザクションでの Bapi を同じ WCF クライアントを使用して送信されるようにすることで WCF サービス モデル ソリューション。 詳細については、[WCF サービス モデルを使用して SAP の Bapi を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)を参照してください。  
  
- WCF チャネル モデル ソリューションにより、同じ WCF チャネル経由で送信されるトランザクションでの Bapi します。 詳細については、[WCF チャネル モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)を参照してください。  
  
### <a name="limitations-on-bapi-transactions"></a>BAPI トランザクションに関する制限事項  
 BAPI トランザクションで、次の制限が適用されます。  
  
- 1 つ LUW 内の同じインスタンスで 2 つの書き込みアクセスを有効にすることはできません。 たとえば、注文を作成するを同じトランザクションで更新することはできません。  
  
- BAPI トランザクションを使用して、実行するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、送信ポートの 1 つのホスト インスタンス上のすべてのメッセージを送信する必要があります。  
  
- インスタンスが作成、更新、または書き込み BAPI を使用して、削除場合、読み取り BAPI は BAPI の書き込みがコミットされるまで、最新のデータを表示できません。  
  
- 呼び出す、LUW 外部クライアントでは、同じ SAP 接続で、LUW を含むすべての Bapi を呼び出す必要があります。  
  
> [!IMPORTANT]
>  Bapi 3.1 のリリースに属しているでは、その実装の一部として、COMMIT WORK を呼び出します。 意味これら Bapi ことはできません、LUW での Bapi の他に含まれています (トランザクションをコミットする) ためです。 詳細については、SAP のマニュアルを参照してください。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)