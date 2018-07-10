---
title: 信頼性の維持 |Microsoft Docs
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
ms.openlocfilehash: faf58e24442d2a17bace7b0d56393d1c793b9cd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985675"
---
# <a name="maintaining-reliability"></a>信頼性の維持
このセクションで信頼性に関する問題を解決する方法について説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。 実行される定期的なメンテナンスのチェックでこれらの問題を検出する可能性がある、[ルーチン メンテナンスのチェックリスト](../technical-guides/routine-maintenance-checklists.md)このドキュメントの「します。  

 このセクションのトピックだけでなくは、このドキュメントでその他のトピックは、信頼性の問題を説明します。 これらのトピックが記載されて[関連セクション](../technical-guides/maintaining-reliability.md#BKMK_Related)以下。  

## <a name="testing-group-failover"></a>グループのフェールオーバーのテスト  
 毎月実行される信頼性チェックの一部として、このセクションの手順を実行します。 これらの手順には、グループのフェールオーバー ポリシーをテストし、グループ リソースがフェールオーバーできるかどうかをテストが含まれます。  

> [!NOTE]  
>  コンピューターがドメインに参加している場合、Domain Admins グループのメンバーは、この手順を実行できる必要があります。  

> [!NOTE]  
>  このセクションでは、手順を実行する必要がありますがログオンして、ローカル コンピューターの Administrators グループのメンバーとして、またはをされている必要が適切な権限が委任します。  

 Windows Server 2008 を実行するコンピューターでグループのフェールオーバーをテストするには、次の手順を実行します。  

#### <a name="to-test-a-group-failover-policy"></a>グループのフェールオーバー ポリシーをテストするには  

1.  インストールされていることを確認、**フェールオーバー クラスタ リング**機能に少なくとも 2 つのコンピューター上には、2 つのノードの Windows フェールオーバー クラスターを作成するための Windows Server 2008 を実行します。 この機能をインストールする方法については、次を参照してください。[フェールオーバー クラスタ リング機能をインストール](http://go.microsoft.com/fwlink/?LinkId=157259)(http://go.microsoft.com/fwlink/?LinkId=157259)します。  

2.  フェールオーバー クラスター管理 を開く**開始**をクリック**管理ツール**、 をクリックし、**フェールオーバー クラスター管理**します。  

3.  コンソール ツリーで、クラスター ノードを展開し、展開、**サービスとアプリケーション**ノード、フェールオーバー、クリックしてアプリケーションのクラスター化されたインスタンスを右クリックして**プロパティ**。  

4.  **フェールオーバー**タブで、設定 **、指定した期間内の最大エラー** 0 をクリックする **[ok]** します。  

5.  コンソール ツリーで、展開、**サービスとアプリケーション**ノード。  

6.  詳細ペインで、リソースを右クリックし、**プロパティ**します。  

7.  **ポリシー**タブで、設定**指定期間内の再起動の試行**0 をクリックする **[ok]** します。  

8.  リソースを右クリックし、をクリックして**その他のアクション**、 をクリックし、**このリソースの障害をシミュレート**します。 グループが、前の手順で指定したポリシーに基づいて反応かどうかを確認します。  

9. クリックして、フェールオーバー、アプリケーションのクラスター化されたインスタンスを右クリックして**プロパティ**します。  

10. **フェールオーバー**タブで、設定**指定期間内の最大エラー数**1、およびクリックに **[ok]** します。  

11. リソースを右クリックして**このリソースをオンライン**します。  

#### <a name="to-test-whether-group-resources-can-fail-over"></a>グループ リソースがフェールオーバーできるかどうかをテストするには  

1.  インストールされていることを確認、**フェールオーバー クラスタ リング**Windows Server 2008 を実行しているコンピューター上で機能します。 この機能をインストールする方法については、次を参照してください。[フェールオーバー クラスタ リング機能をインストール](http://go.microsoft.com/fwlink/?LinkId=157259)(http://go.microsoft.com/fwlink/?LinkId=157259)します。  

2.  フェールオーバー クラスター管理 を開く**開始**をクリック**管理ツール**、 をクリックし、**フェールオーバー クラスター管理**します。  

3.  コンソール ツリーで、クラスター ノードを展開し、展開、**サービスとアプリケーション**ノード、クラスター化されたインスタンスをフェールオーバーするアプリケーションの順にクリックします。  

4.  **アクション** メニューのをクリックして**このサービスまたはアプリケーションを別のノードに移動**、アプリケーションのフェールオーバー先のノードをクリックします。  

5.  **アクションを確認してください** ダイアログ ボックスで、選択したノードにアプリケーションの移行を選択します。  

6.  に対して、アプリケーションへの移動先ノードが表示されていることを確認、**現在の所有者**アプリケーションの詳細ウィンドウにします。  

##  <a name="BKMK_BTSGrp"></a> BizTalk グループの一部である複数のサーバーのことを確認します。  
 システムの信頼性を確保するには、は、BizTalk グループの一部が少なくとも 2 つの物理 BizTalk サーバーにあります。  BizTalk グループにサーバーを追加する必要がある場合は、次に留意してください。  

- サーバーは、1 つの BizTalk グループに関連付けられた場合のみできます。 サーバーが別のグループに既に属している場合、まず現在のグループからサーバーを削除し、その後でサーバーを新しいグループに追加する必要があります。 BizTalk グループからサーバーを削除する方法の詳細についてを参照してください「する方法をサーバーから、グループの削除」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=155577](http://go.microsoft.com/fwlink/?LinkId=155577)します。  

- BizTalk Server 環境内の異なるサーバーに関連付けられた BizTalk グループどうしは、メッセージの交換以外の連携を行いません。  

- BizTalk Server ランタイムは、BizTalk グループに追加するコンピューターにインストールする必要があります。  

> [!NOTE]  
>  このトピックの手順を実行するには、必要があるログオンが SSO 管理者グループのメンバーとは、Windows の Administrators グループのメンバーとして。  

#### <a name="to-determine-whether-at-least-two-physical-biztalk-servers-are-part-of-the-biztalk-group"></a>2 つの物理的な BizTalk server、BizTalk グループの一部である以上かどうかを判断するには  

1. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリックし、**BizTalk Server 管理**します。  

2. 展開、[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]ノード、展開、 **BizTalk グループ**ノードの順に展開し、**プラットフォームの設定**ノード。  

3. をクリックして、**サーバー**ノード。 複数のサーバーが表示されていることを確認、**サーバー**ウィンドウ。  

   > [!NOTE]  
   >  サーバーに関する情報を表示するには、サーバーを右クリックして**ビュー**、 をクリックし、**グループ ハブ ページ**します。  

#### <a name="to-add-a-server-to-a-biztalk-group"></a>サーバーを BizTalk グループに追加するには  

1. を BizTalk グループに追加するコンピューターに次のようにクリックします。**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリックし、 **BizTalk Server 構成**します。  

2. **Microsoft BizTalk Server 2010 構成**、**カスタム構成**します。  

3. **データベース サーバー名**サーバーが参加している BizTalk グループの SQL server の名前を入力します。  

4. **サービス資格情報**、適切なユーザー名とサービスを使用し、パスワードを入力**構成**します。  

5. 画面の左側にあるナビゲーション ツリーで、クリックして**エンタープライズ SSO**します。  

6. **エンタープライズ シングル サインオン**] ページで [**既存の SSO システムに参加**します。  

   > [!NOTE]  
   >  サーバー名とデータベース名が、サーバーの参加先 BizTalk グループのマスター SSO データベース サーバーを指していることを確認します。  

7. 画面の左側にあるナビゲーション ツリーで、クリックして**グループ**します。  

8. **グループ**] ページで [**既存の BizTalk グループに参加**します。  

   > [!NOTE]  
   >  サーバー名とデータベース名が、サーバーの参加先 BizTalk グループのデータベースをポイントすることを確認します。  

9. メニュー バーでクリックして**構成の適用**このコンピューターでエンタープライズ シングル サインオンとグループの両方を構成します。  

##  <a name="BKMK_Related"></a> 関連項目  

- ハードウェア RAID で障害が発生したディスクのチェック方法の詳細については、「ディスク プロパティの表示」で、Windows Server 2003 製品ヘルプにあるを参照してください。 [ http://go.microsoft.com/fwlink/?linkid=104161](http://go.microsoft.com/fwlink/?linkid=104161)します。  

- 手動で中断されたメッセージのチェック方法の詳細についてを参照してください「Investigating オーケストレーション、ポート、およびメッセージのエラー」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkID=154512](http://go.microsoft.com/fwlink/?LinkID=154512)します。  

- 各ホストは、少なくとも 2 つの物理 BizTalk サーバーで実行されているインスタンスについては、次を参照してください。 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)します。  

- 各ホストは、少なくとも 2 つの物理 BizTalk サーバーで実行されているインスタンスについては、次を参照してください。[受信ホストをスケール](../technical-guides/scaling-out-receiving-hosts.md)します。  

- クラスター化されたすべてのサービスのフェールオーバーを確認する方法についてはテストされて、参照してください[マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)します。  

- BizTalk データベースが SQL サービスでクラスター化することを確認する方法については、次を参照してください。 [、BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)します。  

- (個別のホストが必要)、不安定なコードが使用されているかどうかを決定する方法の詳細については、次を参照してください。 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)します。  

- すべての新しい BizTalk アプリケーションの機能テストを実行する方法の詳細については、次を参照してください[アプリケーションのテスト。](../technical-guides/testing-an-application.md)
