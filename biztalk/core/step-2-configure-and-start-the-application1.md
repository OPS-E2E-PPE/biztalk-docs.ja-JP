---
title: "手順 2: を構成し、アプリケーション 1 を開始 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cb061ca-acf4-4de4-a634-b3bb98876989
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc9c3c027126d3a461bf99329b70fda57b9be647
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-and-start-the-application"></a>手順 2: を構成し、アプリケーションを起動
![手順 3 の 2](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:**でこの手順で構成し、EAISolution アプリケーションを起動します。  
  
 **目的:**バインドに関するほとんどの場合は、構成します。  バインディングは、オーケストレーション ポートなど、ロール リンクの論理エンドポイントとの送信などの物理的なエンドポイント間のマッピングを作成し、ポートまたはパーティを受信します。 これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。 バインドを作成するには BizTalk Server 管理コンソールを使用します。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[手順 1: プロジェクトを配置](../core/step-1-deploy-the-projects.md)です。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンする必要があります。  
  
## <a name="procedures"></a>手順  
 BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする BizTalk Server の機能です。 BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションで使用される "アイテム" の論理グループです。  詳細については、次を参照してください。 [BizTalk アプリケーションは何ですか?](../core/what-is-a-biztalk-application.md)です。  [手順 1: プロジェクトを配置](../core/step-1-deploy-the-projects.md)に、プロジェクトを展開する"EAISolution"アプリケーション名を設定します。  したがって、EAISolution アプリケーションには、オーケストレーション、2 つのスキーマおよびマップが含まれています。  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a>EAISolution アプリケーションを BizTalk Server 管理コンソールから開くには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。  
  
2.  左側にあるコンソール ツリーで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**更新**です。  
  
3.  展開**BizTalk グループ**、展開**アプリケーション**、クリックして**EAISolution**です。  
  
 [レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)オーケストレーションを作成しました。  オーケストレーションでは、論理ポートを定義しました。  次の手順では、物理ポートを定義して論理ポートにバインドします。  
  
#### <a name="to-create-the-receiverequest-port"></a>ReceiveRequest ポートを作成するには  
  
1.  BizTalk Server 管理コンソールから下にある、 **EAISolution**  ノードを右クリックして**受信ポート**、 をポイント**新規**、順にクリック**一方向受信ポート**です。  
  
2.  [全般] タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**EAISolutionReceiveRequestPort**です。|  
    |**失敗したメッセージのルーティングを有効にします。**|(選択解除)|  
  
3.  をクリックして**受信場所**、クリックして**新規**です。  
  
4.  [Receive Location1 - 受信場所のプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**EAISolutionReceiveRequestLocation**です。|  
    |**型**|選択**ファイル**です。|  
    |**受信ハンドラー**|[ **BizTalkServerApplication**] を選択します。|  
    |**受信パイプライン**|選択**XMLReceive**です。|  
  
5.  をクリックして**構成**です。  
  
6.  [FILE トランスポートのプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信フォルダー**|型**C:\BTSTutorials\WareHouse\Request**です。|  
  
7.  をクリックして**OK** 3 回です。  
  
#### <a name="to-create-the-senddecline-port"></a>SendDecline ポートを作成するには  
  
1.  BizTalk Server 管理コンソールから下にある、 **EAISolution**  ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリック**静的な一方向送信ポート**です。  
  
2.  [全般] タブには、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**EAISolutionSendDeclinePort**です。|  
    |**型**|選択**ファイル**です。|  
    |**送信ハンドラー**|選択**BizTAlkServerApplication**です。|  
    |**送信パイプライン**|選択**XML Transmit**です。|  
  
3.  をクリックして**構成**です。  
  
4.  [FILE トランスポートのプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信フォルダー**|型**C:\BTSTutorials\WareHouse\RequestDecline**です。|  
    |**ファイル名**|型**RequestDecline_%MessageID%.xml**です。|  
  
5.  **[OK]** を 2 回クリックします。  
  
#### <a name="to-create-the-sendtoerp-port"></a>SendToERP ポートを作成するには  
  
1.  BizTalk Server 管理コンソールから下にある、 **EAISolution**  ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリック**静的な一方向送信ポート**です。  
  
2.  [全般] タブには、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**EAISolutionSendToERPPort**です。|  
    |**型**|選択**ファイル**です。|  
    |**送信ハンドラー**|選択**BizTAlkServerApplication**です。|  
    |**送信パイプライン**|選択**XML Transmit**です。|  
  
3.  をクリックして**構成**です。  
  
4.  [FILE トランスポートのプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信フォルダー**|型**C:\BTSTutorials\ERP\Request**です。|  
    |**ファイル名**|型**Request_%MessageID%.xml**です。|  
  
5.  **[OK]** を 2 回クリックします。  
  
#### <a name="to-bind-the-ports"></a>ポートをバインドするには  
  
1.  BizTalk Server 管理コンソール を右クリックして**EAISolution**、クリックして**構成**です。  
  
2.  アプリケーションの構成、左側のウィンドウでクリックして**EAIProcess**です。  これは前に作成したオーケストレーションです。  
  
3.  右側のウィンドウから次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホスト**|[ **BizTalkServerApplication**] を選択します。|  
    |**受信ポート**の**ReceiveRequestPort**|選択**EAISolutionReceiveReqeustPort**です。|  
    |**送信ポート/送信ポート グループ**の**ReceiveRequestPort**|選択**EAISolutionSendDeclinePort**です。|  
    |**受信ポート**の**ReceiveRequestPort**|選択**EAISolutionSendToERPPort**です。|  
  
4.  をクリックして**OK**構成を保存します。  
  
#### <a name="to-start-the-application"></a>アプリケーションを開始するには、次の操作を行います。  
  
1.  BizTalk Server 管理コンソール を右クリックして**EAISolution**、クリックして**開始**です。  
  
2.  ダイアログ ボックスで、をクリックして**開始**です。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、EAIApplication アプリケーションを構成し、開始しました。  
  
## <a name="next-steps"></a>次の手順  
 EAI ソリューションでのメッセージをどのように処理するかをテストする[手順 3: ソリューションをテストする](../core/step-3-test-the-solution2.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 1: 配置プロジェクト](../core/step-1-deploy-the-projects.md)   
 [手順 3: ソリューションをテストします。](../core/step-3-test-the-solution2.md)