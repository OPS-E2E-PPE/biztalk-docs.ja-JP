---
title: '手順 2: ポートの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e804da96-26ae-482d-b6e1-67af24d639d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fe05185c625825c795ee89dff10d5be9ae6a68d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973731"
---
# <a name="step-2-configure-the-ports"></a>手順 2: ポートを構成します。
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 15 分  
  
 **目標:** で物理ポートを作成するこの手順で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 オーケストレーションで作成した各論理ポートに対する物理ポートを作成します。 次のポートを作成します。  
  
- Wcf-custom の一方向受信ポートへの変更の通知メッセージを受信する**従業員**SQL Server データベースのテーブル。  
  
- 要求-応答 Wcf-custom 送信要求メッセージを送信し、呼び出しの応答の受信ポートを**UPDATE_EMPLOYEE**ストアド プロシージャに対して、挿入操作を実行して、 **Purchase_Order**テーブル。 オーケストレーションでは、同じ送信ポートを使用して、両方の操作を実行します。 同様に、、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、両方の操作の単一の送信ポートを使用します。  
  
- 挿入操作の応答を送信する一方向の送信ポート。 このチュートリアルで、電子メールを通じて、購買部門に通知する必要があるため、この送信ポートとして作成 SMTP ポートをします。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 1: オーケストレーションを展開](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md))。  
  
### <a name="to-create-a-physical-one-way-receive-port"></a>一方向の物理受信ポートを作成するには  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. 左側にあるコンソール ツリーで [ **BizTalk Server 管理**を右クリックして**BizTalk グループ**、] をクリックし、**更新**します。  
  
3. 展開**BizTalk グループ**、展開**アプリケーション**、展開と**SampleApplication**します。 このチュートリアルでは、すべてのポートと SampleApplication アプリケーション内でアプリケーションを作成します。  
  
4. "を展開するアダプターの受信メッセージから SQL Server"セクションの説明に従い[wcf-custom アダプタと SQL アダプタを使用してポートを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)します。 名前とポート**NotifyReceivePort**します。  
  
5. 変更の通知を受信するアダプターを構成するのには、次のバインド プロパティを設定することを確認、**従業員**テーブル。  
  
   |プロパティのバインド|値|  
   |----------------------|-----------|  
   |**InboundOperationType**|これを設定**通知**します。|  
   |**NotificationStatement**|これを設定します。<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **注:** この Select ステートメントで示すように、ステートメントで列名に指定すること具体的にする必要があります。 また、する必要があります常にテーブル名を指定、スキーマ名と共になど`dbo.Employee`します。|  
   |**NotifyOnListenerStart**|これを設定**True**します。|  
  
    異なるバインディング プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
### <a name="to-create-a-request-response-send-port-for-two-operations"></a>要求-応答送信の 2 つの操作用のポートを作成するには  
  
1. "を展開するアダプターの送信メッセージを SQL Server"セクションの説明に従い[wcf-custom アダプタと SQL アダプタを使用してポートを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)します。 名前とポート**SQLOutboundPort**します。  
  
2. 実行するため、2 つの操作を使用して、同じ送信ポート、動的アクション マッピングを使用して、操作のアクションを指定する必要があります。 ポートを構成するときに、**アクション**ボックスで、次のように、アクションのマッピングを指定します。  
  
   ```  
   <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
     <Operation Name="UpdateEmp" Action="TypedProcedure/dbo/UPDATE_EMPLOYEE" />  
     <Operation Name="InsertPO" Action="TableOp/Insert/dbo/Purchase_Order" />  
   </BtsActionMapping>  
   ```  
  
    オーケストレーションで要求-応答の送信ポートの 2 つの操作を作成することに注意してください: **UpdateEmp**と**InsertPO**します。 そのため、物理ポートの構成では、動的アクション マッピングで同じ操作名を指定します。 上記の例のアクションで**UpdateEmp**操作が`TypedProcedure/dbo/UPDATE_EMPLOYEE`します。 同様に、アクションを**InsertPO**操作が`TableOp/Insert/dbo/Purchase_Order`します。  
  
3. 応答メッセージにマップするオーケストレーションで作成したマッパーを使用する送信ポートを構成することも必要があります**UPDATE_EMPLOYEE**でストアド プロシージャ、挿入操作の要求メッセージを**Purchase_。順序**テーブル。 そのためには次を行います。  
  
   1. SQLOutboundPort を右クリックして[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、およびクリック**プロパティ**します。  
  
   2. **SQLOutboundPort – 送信ポートのプロパティ** ダイアログ ボックスで、左側のウィンドウからクリックして**送信マップ**します。  
  
   3. 右側のウィンドウからの**送信マップ**ボックスに、下のセルをクリックして、**マップ**列で、ドロップダウン リストから選択します。**変換 _ 1**。 これで、BizTalk オーケストレーションで作成したマップの名前は、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  
  
       **[OK]** をクリックします。  
  
       ![送信マップの構成](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-010-map-ports.gif "sql_adap_tut_010_map_ports")  
  
### <a name="to-create-an-smtp-send-port"></a>SMTP 送信ポートを作成するには  
  
1. 説明に従い、"の SMTP 送信ポートを構成する方法、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール"セクションで[ http://go.microsoft.com/fwlink/?LinkId=141549](http://go.microsoft.com/fwlink/?LinkId=141549)します。 名前とポート**EmailResponse**します。  
  
2. ポートの構成の一環として、指定の購買部門の電子メール アドレス、**に**プロパティ。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 作成したこの手順では、SQL Server からの通知の受信ポートを SQL Server で、操作を実行するための Wcf-custom 送信ポートおよび購買部門に電子メールとしての SQL Server からの応答を送信するための SMTP ポート Wcf-custom が表示されます。  
  
## <a name="next-steps"></a>次の手順  
 説明に従って、BizTalk アプリケーションの起動を構成し、[手順 3: 構成し、アプリケーションを起動](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)します。  
  
## <a name="see-also"></a>参照  
 [手順 1: オーケストレーションを展開します。](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md)   
 [手順 3: 構成し、アプリケーションを起動します](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)   
 [レッスン 5: ソリューションを展開する](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)