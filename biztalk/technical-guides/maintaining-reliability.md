---
title: 信頼性を確保 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09cdce13-a75b-44d7-8388-7a868bb51c69
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb1f956c0f3b09ee51d3dd9d05f64dbd3eeeab3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299650"
---
# <a name="maintaining-reliability"></a>信頼性を維持します。
このセクションで信頼性の問題を解決する方法に関する情報を提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。 実行される定期的なメンテナンス チェックでこれらの問題を検出する可能性があります、[ルーチン メンテナンス チェックリスト](../technical-guides/routine-maintenance-checklists.md)このドキュメントの「します。  
  
 このセクションのトピック、に加えては、このドキュメントでは、その他のトピックは、信頼性の問題を解決します。 これらのトピックが記載されて[関連項目](../technical-guides/maintaining-reliability.md#BKMK_Related)以下です。  
  
## <a name="testing-group-failover"></a>グループのフェールオーバーをテストします。  
 毎月実行する必要がある、信頼性チェックの一部として、このセクションで、手順を実行します。 これらの手順には、グループのフェールオーバー ポリシーのテストと、グループのリソースがフェールオーバーできるかどうかをテストが含まれます。  
  
> [!NOTE]  
>  コンピューターがドメインに参加している場合、Domain Admins グループのメンバーはこの手順を実行できる必要があります。  
  
> [!NOTE]  
>  このセクションの手順を実行するログオンがある、ローカル コンピューターの Administrators グループのメンバーとしてまたはされている必要がありますが、適切な権限を委任します。  
  
 Windows Server 2008 を実行するコンピューターでグループのフェールオーバーをテストする次の手順を実行します。  
  
#### <a name="to-test-a-group-failover-policy"></a>グループのフェールオーバー ポリシーをテストするには  
  
1.  インストールされていることを確認、**フェールオーバー クラスタ リング**機能には、少なくとも 2 台のコンピューター上には、2 つのノード Windows フェールオーバー クラスターを作成するために Windows Server 2008 を実行します。 この機能をインストールする方法については、次を参照してください。[フェールオーバー クラスタ リング機能をインストール](http://go.microsoft.com/fwlink/?LinkId=157259)(http://go.microsoft.com/fwlink/?LinkId=157259)。  
  
2.  フェールオーバー クラスター管理 を開く**開始**をクリックすると、**管理ツール**、クリックして**フェイル オーバー クラスター管理**です。  
  
3.  コンソール ツリーで、クラスター ノードを展開し、**サービスとアプリケーション** ノードをクリックして、フェールオーバーできません。 アプリケーションのクラスター化されたインスタンスを右クリック**プロパティ**です。  
  
4.  **フェールオーバー**  タブで、設定**指定期間内の最大エラー数**0 でありをクリック**OK**です。  
  
5.  コンソール ツリーで、展開、**サービスとアプリケーション**ノード。  
  
6.  詳細ウィンドウで、リソースを右クリックし、をクリックして**プロパティ**です。  
  
7.  **ポリシー**  タブで、設定**指定した期間の再起動の試行回数**0 でありをクリック**OK**です。  
  
8.  リソースを右クリックし、をクリックして**他のアクション**、クリックして**このリソースの障害をシミュレート**です。 グループが、前の手順で指定したポリシーのベース反応するかどうかを確認します。  
  
9. クリックして、フェールオーバーできません。 アプリケーションのクラスター化されたインスタンスを右クリック**プロパティ**です。  
  
10. **フェールオーバー**  タブで、設定**指定期間内の最大エラー数**1、およびクリックを**ok**です。  
  
11. リソースを右クリックし **このリソースをオンライン**です。  
  
#### <a name="to-test-whether-group-resources-can-fail-over"></a>グループのリソースがフェールオーバーできるかどうかをテストするには  
  
1.  インストールされていることを確認、**フェールオーバー クラスタ リング**Windows Server 2008 を実行しているコンピューター上で機能します。 この機能をインストールする方法については、次を参照してください。[フェールオーバー クラスタ リング機能をインストール](http://go.microsoft.com/fwlink/?LinkId=157259)(http://go.microsoft.com/fwlink/?LinkId=157259)。  
  
2.  フェールオーバー クラスター管理 を開く**開始**をクリックすると、**管理ツール**、クリックして**フェイル オーバー クラスター管理**です。  
  
3.  コンソール ツリーで、クラスター ノードを展開し、**サービスとアプリケーション**ノード、クラスター化されたインスタンスをフェールオーバーするアプリケーションの順にクリックします。  
  
4.  **アクション** メニューのをクリックして**このサービスまたはアプリケーションを別のノードに移動**、アプリケーションのフェールオーバー先のノードをクリックします。  
  
5.  **アクションを確認してください** ダイアログ ボックスで、選択したノードにアプリケーションを移動します。  
  
6.  に対して、アプリケーションへの移動先となるノードが表示されていることを確認してください、**現在の所有者**アプリケーションの詳細ペインでします。  
  
##  <a name="BKMK_BTSGrp"></a>BizTalk グループの一部である複数のサーバーを確保します。  
 システムの信頼性を確保するには、少なくとも 2 つの物理 BizTalk サーバーは、BizTalk グループの一部をする必要があります。  BizTalk グループにサーバーを追加する必要がある場合は、次に留意してください。  
  
-   サーバーは、1 つの BizTalk グループに関連付けられたのみできます。 サーバーが別のグループに既に属している場合、まず現在のグループからサーバーを削除し、その後でサーバーを新しいグループに追加する必要があります。 詳細については、BizTalk グループからサーバーを削除するを参照してください「方法に、サーバーから、グループの削除」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkId=155577](http://go.microsoft.com/fwlink/?LinkId=155577)です。  
  
-   BizTalk Server 環境内の異なるサーバーに関連付けられた BizTalk グループどうしは、メッセージの交換以外の連携を行いません。  
  
-   BizTalk Server ランタイムは、BizTalk グループに追加するコンピューターにインストールする必要があります。  
  
> [!NOTE]  
>  このトピックの手順を実行するには、必要があるログオンが SSO 管理者グループのメンバーとは、Windows Administrators グループのメンバーとして。  
  
#### <a name="to-determine-whether-at-least-two-physical-biztalk-servers-are-part-of-the-biztalk-group"></a>2 つの物理 BizTalk サーバーにはを少なくともかどうかを決定するには、BizTalk グループの一部であります。  
  
1.  開いている、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール をクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** をクリックし、**BizTalk Server 管理**です。  
  
2.  展開、[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]ノード、展開、 **BizTalk グループ**ノードの順に展開し、**プラットフォームの設定**ノード。  
  
3.  クリックして、**サーバー**ノード。 複数のサーバーが表示されていることを確認、**サーバー**ウィンドウです。  
  
    > [!NOTE]  
    >  サーバーに関する情報を表示するには、サーバーを右クリックし、 をポイント**ビュー**、クリックして**グループ ハブ ページ**です。  
  
#### <a name="to-add-a-server-to-a-biztalk-group"></a>サーバーを BizTalk グループに追加するには  
  
1.  BizTalk グループに追加するコンピューター、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、クリックして**BizTalk Server 構成**です。  
  
2.  **Microsoft BizTalk Server 2010 構成****カスタム構成**です。  
  
3.  **データベース サーバー名**サーバーが参加する BizTalk グループの SQL server の名前を入力します。  
  
4.  **サービス資格情報**、適切なユーザー名とサービスを使用し、パスワードを入力**構成**です。  
  
5.  画面の左側にあるナビゲーション ツリーで、クリックして**エンタープライズ SSO**です。  
  
6.  **エンタープライズ シングル サインオン**] ページで [**既存の SSO システムに参加**です。  
  
    > [!NOTE]  
    >  サーバー名とデータベース名が、サーバーの参加先 BizTalk グループのマスター SSO データベース サーバーを指していることを確認します。  
  
7.  画面の左側にあるナビゲーション ツリーで、クリックして**グループ**です。  
  
8.  **グループ**] ページで [**既存の BizTalk グループに参加**です。  
  
    > [!NOTE]  
    >  サーバー名とデータベース名が、サーバーの参加先 BizTalk グループのデータベースを指していることを確認します。  
  
9. メニュー バーで、をクリックして**構成の適用**をこのコンピューターでエンタープライズ シングル サインオンとグループの両方を構成します。  
  
##  <a name="BKMK_Related"></a> 関連項目  
  
-   チェックの失敗したディスク ハードウェア RAID の詳細については、「ディスク プロパティの表示」Windows Server 2003 製品ヘルプ内でを参照してください。 [http://go.microsoft.com/fwlink/?linkid=104161](http://go.microsoft.com/fwlink/?linkid=104161)です。  
  
-   手動で中断されたメッセージの確認方法についてを参照してください「Investigating オーケストレーション、ポート、およびメッセージ エラー」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkID=154512](http://go.microsoft.com/fwlink/?LinkID=154512)です。  
  
-   各ホストが少なくとも 2 台の物理的な BizTalk サーバーで実行されているインスタンスであることを確認する方法については、次を参照してください。 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)です。  
  
-   各ホストが少なくとも 2 台の物理的な BizTalk サーバーで実行されているインスタンスであることを確認する方法については、次を参照してください。[受信ホストをスケール](../technical-guides/scaling-out-receiving-hosts.md)です。  
  
-   クラスター化されたすべてのサービスのフェールオーバーを確認する方法については、テスト済みを参照してください[マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)です。  
  
-   BizTalk データベースが SQL サービスでクラスター化されていることを確認する方法については、次を参照してください。 [BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)です。  
  
-   (個別のホストが必要)、不安定なコードが使用されているかどうかを決定する方法については、次を参照してください。 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)です。  
  
-   すべての新しい BizTalk アプリケーションの機能テストを実行する方法については、次を参照してください[アプリケーションのテスト。](../technical-guides/testing-an-application.md)