---
title: "SAP での Bapi の操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAPI, operations
- BAPIs, operations on
- Business Application Programming Interface
- BAPIs
- BAPI, transactions
- BAPI transactions, limitations on
ms.assetid: 6be26641-e8d3-4e11-8d82-4fdb13076580
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8504dd05c671307085d621c474969a70026d2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-bapis-in-sap"></a>SAP での Bapi の操作
ビジネス アプリケーション プログラミング インターフェイス (BAPI) は、外部プロセスによって呼び出すことができる SAP ビジネス オブジェクトのメソッドです。 Bapi のでは、SAP システムでトランザクションです。  
  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]サポートの BAPI は送信方向で呼び出します。 2 つの方法で Bapi を表示します。  
  
-   **RFC として**です。 適切な RFC を呼び出すことによって直接 BAPI を呼び出すことができます。  
  
-   **ビジネス オブジェクトのメソッドとして**です。 アダプターでは、ビジネス オブジェクトのメソッドとして Bapi をサーフェスを使用するときに、メタデータを取得するのに役立つ便利な機能として、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。  
  
> [!IMPORTANT]
>  RFC としてまたはビジネス オブジェクトのメソッドとして、アダプターでの BAPI を呼び出すことができます。アダプターの BAPI の起動方法に関係なく常に呼び出します SAP の BAPI、RFC インターフェイスを使用します。  
  
 アダプターは、BAPI トランザクションをサポートします。 SAP の BAPI のトランザクション モデルでは、作業 (LUW) の 1 つの論理ユニットをいくつかの Bapi を結合することができます。 SAP LUW では、データベースの更新を含むトランザクションに関係するすべての手順で構成されます。  
  
 このセクションのトピックでは、ビジネス オブジェクトとしての Bapi の表示方法と、アダプターによって BAPI トランザクション (LUWs) をサポートする方法について説明します。  
 
  
## <a name="bapi-operations-as-business-object-methods"></a>BAPI 操作 (としてビジネス オブジェクトのメソッド)  
 アダプター サーフェスの Bapi のようにビジネス オブジェクト メソッドを使用する場合は、メタデータを取得するのに役立つ便利な機能として、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。 アダプターは、RFC インターフェイスを使用して SAP システムでの Bapi を常に呼び出します。  
  
 アダプターは、送信操作の適切なビジネス オブジェクトの下の操作として名前によって Bapi を表示します。 ビジネス オブジェクトは、機能グループ アダプターでの BAPI カテゴリ ノードの下で収集されます。 (参照したり、ビジネス オブジェクト、および下での Bapi の検索、 **BAPI**ノードを使用するときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)])。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Bapi で、次をサポートしています。  
  
-   インポートのパラメーター  
  
-   パラメーターをエクスポートします。  
  
-   変化させるパラメーター  
  
-   テーブル パラメーター  
  
 メッセージの構造と Bapi のビジネス オブジェクト メソッドとして表示されるに使用する SOAP アクションの詳細については、次を参照してください。 [BAPI 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)です。  
  
## <a name="bapi-transactions"></a>BAPI のトランザクション  
 呼び出すと、BAPI、SAP システムで、LUW の一部では常にします。 これは、機能は、RFC としてまたはビジネス オブジェクトのメソッドとして、BAPI を呼び出すかどうかに当てはまります。 RFC SDK では、同じ LUW の一部として同じ SAP 接続経由で送信されたすべての Bapi を扱います。 呼び出しの後にコミットするか、接続でトランザクションをロールバックして、[次へ] の BAPI 接続経由で送信された新しい LUW を開始します。  
  
 コミットまたはトランザクションをロールバックするには、BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK を呼び出します。 アダプターは、これら 2 つの Bapi を表示します。  
  
-   RFC 操作として [基準] ノードの下。  
  
-   各ビジネス オブジェクト。  
  
 トランザクションでの Bapi を制御するがすべて送信する (コミットまたはロールバック、トランザクションへの呼び出しを含む) と同じ SAP 接続経由のことを確認します。 これを行うことができます。  
  
-   BizTalk ソリューションを使用して、 **ConnectionState**メッセージ コンテキスト プロパティを同じ接続を使用して、トランザクションでの Bapi を送信することを確認してください。 このプロパティは、アダプターによって提示されるし、BizTalk オーケストレーションでメッセージを送信するための接続を明示的に制御を提供します。  
  
     BizTalk Server を使用したトランザクションの BAPI を実行するため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のメッセージ コンテキスト プロパティをサポートしています。  
  
    |フィールド|Description|  
    |-----------|-----------------|  
    |OPEN|トランザクションの新しいチャネルを開きます。|  
    |再利用します。|トランザクションの既存のチャネルを再利用できます。|  
    |CLOSE|トランザクションをコミットし、既存のチャネルを閉じます。|  
    |中止|トランザクションを中止して、既存のチャネルを閉じます。|  
  
     詳細については、次を参照してください。 [BizTalk Server を使用して SAP での BAPI トランザクションの実行](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)です。  
  
    > [!NOTE]
    >  設定するかどうかを確認、 **EnableBizTalkCompatibilityMode**BizTalk Server を使用してトランザクションを実行するときに、プロパティをバインドします。  
  
-   サービス モデル ソリューションを WCF トランザクションでの Bapi を同じ WCF クライアントを使用して送信されることを保証します。 詳細については、次を参照してください。 [WCF サービスのモデルを使用して SAP での Bapi の呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)です。  
  
-   WCF チャネル モデル ソリューションにより、同じ WCF チャネル経由で送信されるトランザクションでの Bapi です。 詳細については、次を参照してください。 [WCF チャネル モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)です。  
  
### <a name="limitations-on-bapi-transactions"></a>BAPI のトランザクションに関する制限事項  
 BAPI のトランザクションで、次の制限が適用されます。  
  
-   1 つ LUW 内の同じインスタンスで次の 2 つの書き込みアクセスを有効にすることはできません。 たとえば、注文を作成し、同じトランザクションで更新することはできません。  
  
-   トランザクションを使用して、BAPI を実行するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、送信ポートの 1 つのホスト インスタンス上のすべてのメッセージを送信する必要があります。  
  
-   インスタンスが作成された場合、更新、または BAPI の書き込みを使用して、削除、読み取り BAPI は BAPI の書き込みがコミットされるまで、最新のデータを表示できません。  
  
-   呼び出す、LUW 外部のクライアントは、同じ SAP 接続で、LUW を含むすべての Bapi を呼び出す必要があります。  
  
> [!IMPORTANT]
>  Bapi のリリース 3.1 に属しているは、その実装の一部として、COMMIT WORK を呼び出します。 意味これら Bapi ことはできません、LUW での Bapi の他の付属 (トランザクションをコミットする) ためです。 詳細については、SAP のマニュアルを参照してください。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)