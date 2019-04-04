---
title: '手順 2: 構成し、開始、Application1 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cb061ca-acf4-4de4-a634-b3bb98876989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8edeb1cdb1f24774ec7c1e615377d81e4393c9dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024552"
---
# <a name="step-2-configure-and-start-the-application"></a>手順 2: 構成し、アプリケーションを起動します
![ステップ 2/3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **所要時間:** 10 分  
  
 **目標:** では、この手順では、構成し、EAISolution アプリケーションを起動します。  
  
 **目的:** 構成は、バインドに関するほとんどの場合は。  バインディングは、オーケストレーション ポートなど、ロール リンクの論理エンドポイントとの送信などの物理的なエンドポイント間のマッピングを作成し、受信ポートまたはパーティします。 これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。 バインドを作成するには BizTalk Server 管理コンソールを使用します。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
- この手順を開始する前に行う必要があります[手順 1: プロジェクトの配置](../core/step-1-deploy-the-projects.md)します。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンする必要があります。  
  
## <a name="procedures"></a>手順  
 BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする BizTalk Server の機能です。 BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションで使用される "アイテム" の論理グループです。  詳細については、[BizTalk アプリケーションとは何ですか?](../core/what-is-a-biztalk-application.md)を参照してください。  [手順 1: プロジェクトの配置](../core/step-1-deploy-the-projects.md)、"EAISolution"に、プロジェクトを展開するアプリケーション名を構成します。  したがって、EAISolution アプリケーションには、オーケストレーション、2 つのスキーマおよびマップが含まれています。  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a>EAISolution アプリケーションを BizTalk Server 管理コンソールから開くには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。  
  
2. 左側にあるコンソール ツリーで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**更新**します。  
  
3. 展開**BizTalk グループ**、展開**アプリケーション**、 をクリックし、 **EAISolution**します。  
  
   [レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)オーケストレーションを作成しました。  オーケストレーションでは、論理ポートを定義しました。  次の手順では、物理ポートを定義して論理ポートにバインドします。  
  
#### <a name="to-create-the-receiverequest-port"></a>ReceiveRequest ポートを作成するには  
  
1.  BizTalk Server 管理コンソールから下、 **EAISolution**ノードを右クリックして**受信ポート**、 をポイント**新規**、順にクリックします**一方向受信ポート**します。  
  
2.  [全般] タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**EAISolutionReceiveRequestPort**します。|  
    |**失敗したメッセージのルーティングを有効にします。**|(選択解除)|  
  
3.  クリックして**受信場所**、 をクリックし、**新規**します。  
  
4.  [Receive Location1 - 受信場所のプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**EAISolutionReceiveRequestLocation**します。|  
    |**型**|選択**ファイル**します。|  
    |**受信ハンドラー**|**[BizTalkServerApplication]** を選択します。|  
    |**受信パイプライン**|選択**XMLReceive**します。|  
  
5.  クリックして**構成**します。  
  
6.  [FILE トランスポートのプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信フォルダー**|型**C:\BTSTutorials\WareHouse\Request**します。|  
  
7.  クリックして**OK** 3 回です。  
  
#### <a name="to-create-the-senddecline-port"></a>SendDecline ポートを作成するには  
  
1.  BizTalk Server 管理コンソールから下、 **EAISolution**ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。  
  
2.  [全般] タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**EAISolutionSendDeclinePort**します。|  
    |**型**|選択**ファイル**します。|  
    |**送信ハンドラー**|選択**BizTAlkServerApplication**します。|  
    |**送信パイプライン**|選択**XML Transmit**します。|  
  
3.  クリックして**構成**します。  
  
4.  [FILE トランスポートのプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信フォルダー**|型**C:\BTSTutorials\WareHouse\RequestDecline**します。|  
    |**[ファイル名]**|型**RequestDecline_%MessageID%.xml**します。|  
  
5.  **[OK]** を 2 回クリックします。  
  
#### <a name="to-create-the-sendtoerp-port"></a>SendToERP ポートを作成するには  
  
1.  BizTalk Server 管理コンソールから下、 **EAISolution**ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。  
  
2.  [全般] タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**EAISolutionSendToERPPort**します。|  
    |**型**|選択**ファイル**します。|  
    |**送信ハンドラー**|選択**BizTAlkServerApplication**します。|  
    |**送信パイプライン**|選択**XML Transmit**します。|  
  
3.  クリックして**構成**します。  
  
4.  [FILE トランスポートのプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信フォルダー**|型**C:\BTSTutorials\ERP\Request**します。|  
    |**[ファイル名]**|型**Request_%MessageID%.xml**します。|  
  
5.  **[OK]** を 2 回クリックします。  
  
#### <a name="to-bind-the-ports"></a>ポートをバインドするには  
  
1.  BizTalk Server 管理コンソールの右クリック**EAISolution**、 をクリックし、**構成**します。  
  
2.  アプリケーションの構成から左側のウィンドウでクリックして**EAIProcess**します。  これは前に作成したオーケストレーションです。  
  
3.  右側のウィンドウから、次の手順を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホスト**|**[BizTalkServerApplication]** を選択します。|  
    |**受信ポート**の**ReceiveRequestPort**|選択**EAISolutionReceiveReqeustPort**します。|  
    |**送信ポート/送信ポート グループ**の**ReceiveRequestPort**|選択**EAISolutionSendDeclinePort**します。|  
    |**受信ポート**の**ReceiveRequestPort**|選択**EAISolutionSendToERPPort**します。|  
  
4.  をクリックして**OK**構成を保存します。  
  
#### <a name="to-start-the-application"></a>アプリケーションを開始するには、次の操作を行います。  
  
1.  BizTalk Server 管理コンソールの右クリック**EAISolution**、 をクリックし、**開始**します。  
  
2.  ダイアログ ボックスで、次のようにクリックします。**開始**します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 このステップでは、EAIApplication アプリケーションを構成し、開始しました。  
  
## <a name="next-steps"></a>次の手順  
 EAI ソリューションでメッセージを処理する方法をテストする[手順 3: ソリューションをテストする](../core/step-3-test-the-solution2.md)します。  
  
## <a name="see-also"></a>参照  
 [手順 1: 配置プロジェクト](../core/step-1-deploy-the-projects.md)   
 [手順 3: ソリューションのテスト](../core/step-3-test-the-solution2.md)