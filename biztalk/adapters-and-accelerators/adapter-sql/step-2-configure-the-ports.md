---
title: "手順 2: ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e804da96-26ae-482d-b6e1-67af24d639d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c9aaefe0cff41365a587079d0c82629ddddc586
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-configure-the-ports"></a>手順 2: ポートを構成します。
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 15 分  
  
 **目標:**で物理ポートを作成するこの手順で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 オーケストレーションで作成した各論理ポートに対する物理ポートを作成します。 次のポートを作成します。  
  
-   一方向の WCF カスタム受信する受信ポートの変更を通知メッセージ**従業員**SQL Server データベースのテーブルにします。  
  
-   要求-応答の WCF カスタム送信要求メッセージを送信しを起動するための応答を受信ポート、 **UPDATE_EMPLOYEE**ストアド プロシージャに対して、挿入操作を実行して、 **Purchase_Order**テーブル。 オーケストレーションでは、同じ送信ポートを使用して、両方の操作を実行します。 同様に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、両方の操作の単一の送信ポートが使用されます。  
  
-   挿入操作の応答を送信する一方向の送信ポートです。 このチュートリアルでは、電子メールを通じて購買部門に通知する必要があるため、この送信ポートとして作成 SMTP ポートします。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 1: オーケストレーションを展開](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md))。  
  
### <a name="to-create-a-physical-one-way-receive-port"></a>物理的な一方向の受信ポートを作成するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで、左側で、展開**BizTalk Server 管理コンソール**を右クリックして**BizTalk グループ**、順にクリック**更新**です。  
  
3.  展開**BizTalk グループ**、展開**アプリケーション**、展開と**SampleApplication**です。 このチュートリアルでは、すべてのポートと SampleApplication アプリケーション内でアプリケーションを作成します。  
  
4.  "を展開するアダプターの受信メッセージから SQL Server"セクションの指示に従います[wcf-custom アダプタと SQL アダプタを使用してポートを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)です。 名前とポート**NotifyReceivePort**です。  
  
5.  変更の通知を受信するアダプターを構成する次のバインドのプロパティを設定するかどうかを確認、**従業員**テーブル。  
  
    |プロパティのバインド|値|  
    |----------------------|-----------|  
    |**InboundOperationType**|これを設定して**通知**です。|  
    |**NotificationStatement**|これを設定します。<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **注:**する必要があります具体的には、列名を指定、ステートメントで次の Select ステートメントで示すようにします。 また、必要があります常を指定すると、スキーマ名、テーブル名など、`dbo.Employee`です。|  
    |**NotifyOnListenerStart**|これを設定して**True**です。|  
  
     異なるバインディングのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
### <a name="to-create-a-request-response-send-port-for-two-operations"></a>要求-応答送信の 2 つの操作用のポートを作成するには  
  
1.  "を展開するアダプターの送信メッセージを SQL Server"セクションの指示に従います[wcf-custom アダプタと SQL アダプタを使用してポートを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)です。 名前とポート**SQLOutboundPort**です。  
  
2.  実行しているため、2 つの操作を使用して、同じ送信ポート、動的アクション マッピングを使用して、操作のアクションを指定する必要があります。 ポートを構成するときに、**アクション**ボックスで、次のように、アクション マッピングを指定します。  
  
    ```  
    <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
      <Operation Name="UpdateEmp" Action="TypedProcedure/dbo/UPDATE_EMPLOYEE" />  
      <Operation Name="InsertPO" Action="TableOp/Insert/dbo/Purchase_Order" />  
    </BtsActionMapping>  
    ```  
  
     オーケストレーションで要求-応答送信ポートの 2 つの操作を作成することに注意してください: **UpdateEmp**と**InsertPO**です。 そのため、物理ポートの構成では、動的アクション マッピングの同じ操作名を提供します。 上記の例では、アクションを**UpdateEmp**操作が`TypedProcedure/dbo/UPDATE_EMPLOYEE`です。 同様に、アクションを**InsertPO**操作が`TableOp/Insert/dbo/Purchase_Order`です。  
  
3.  応答メッセージにマップするオーケストレーションで作成したマッパーを使用する送信ポートを構成することも必要があります**UPDATE_EMPLOYEE**でストアド プロシージャの挿入操作の要求メッセージを**Purchase_。順序**テーブル。 そのためには次を行います。  
  
    1.  SQLOutboundPort を右クリックして[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、クリックして**プロパティ**です。  
  
    2.  **SQLOutboundPort – 送信ポートのプロパティ**ダイアログ ボックスで、左側のウィンドウからをクリックして**送信マップ**です。  
  
    3.  右側のウィンドウからの**送信マップ**ボックスで、下のセルをクリックして、**マップ**列で、ドロップダウン リストから選択し、**変換 _ 1**です。 これは、BizTalk のオーケストレーションで作成したマップの名前を[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
         **[OK]**をクリックします。  
  
         ![送信マップを構成する](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-010-map-ports.gif "sql_adap_tut_010_map_ports")  
  
### <a name="to-create-an-smtp-send-port"></a>SMTP 送信ポートを作成するには  
  
1.  説明に従い、"の SMTP 送信ポートを構成する方法、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール」セクションで[http://go.microsoft.com/fwlink/?LinkId=141549](http://go.microsoft.com/fwlink/?LinkId=141549)です。 名前とポート**EmailResponse**です。  
  
2.  ポートの構成の一環として、指定の購買部門の電子メール アドレス、**に**プロパティです。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 作成したこのステップでは、WCF カスタムは、SQL Server から通知を受信ポート、SQL Server での操作を実行するための Wcf-custom 送信ポートに送信するため、応答から SQL Server を電子メールとしては購買部門の SMTP ポートを受信します。  
  
## <a name="next-steps"></a>次の手順  
 構成し、」の説明に従って、BizTalk アプリケーションを開始する[手順 3: 構成し、アプリケーションを起動](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 1: オーケストレーションを展開します。](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md)   
 [手順 3: を構成し、アプリケーションを起動](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)   
 [レッスン 5: ソリューションを展開する](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)