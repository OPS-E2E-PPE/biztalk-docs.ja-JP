---
title: "エンタープライズ シングル サインオンを回復する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 845e6ff7-88a8-4ab4-b307-f9275d44600e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa0c0b5435e235a07046f311a971a0036dc8346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-enterprise-single-sign-on"></a><span data-ttu-id="b8808-102">エンタープライズ シングル サインオンを復旧する方法</span><span class="sxs-lookup"><span data-stu-id="b8808-102">How to Recover Enterprise Single Sign-On</span></span>
<span data-ttu-id="b8808-103">BizTalk Server を復旧する前に、まずはエンタープライズ シングル サインオン (SSO) を復旧する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8808-103">Before you can recover BizTalk Server, you must first recover Enterprise Single Sign-On (SSO).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b8808-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="b8808-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="b8808-105">この作業を実行するには、シングル サインオン管理者グループのメンバーおよび管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8808-105">You must be logged on as a member of the Single Sign-On Administrators group and a member of the Administrators group to perform this task.</span></span>  
  
-   <span data-ttu-id="b8808-106">SSO の構成中に使用したパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="b8808-106">You must have the password used during SSO configuration.</span></span>  
  
-   <span data-ttu-id="b8808-107">リモート サーバー上のすべてのデータベースが破損していない必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8808-107">All databases are intact on the remote server.</span></span>  
  
-   <span data-ttu-id="b8808-108">バックアップ マスター シークレット ファイルが破損しておらず、安全な場所に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8808-108">The backup master secret file is intact and stored in a safe place.</span></span>  
  
### <a name="to-recover-enterprise-single-sign-on"></a><span data-ttu-id="b8808-109">エンタープライズ シングル サインオンを復旧するには</span><span class="sxs-lookup"><span data-stu-id="b8808-109">To recover Enterprise Single Sign-On</span></span>  
  
1.  <span data-ttu-id="b8808-110">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 構成**です。</span><span class="sxs-lookup"><span data-stu-id="b8808-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="b8808-111">Microsoft BizTalk Server 構成で、コンソール ツリーで、をクリックして**エンタープライズ SSO**です。</span><span class="sxs-lookup"><span data-stu-id="b8808-111">In Microsoft BizTalk Server Configuration, in the console tree, click **Enterprise SSO**.</span></span>  
  
3.  <span data-ttu-id="b8808-112">詳細ウィンドウで、次のように選択します。**を有効にするエンタープライズ シングル サインオンこのコンピューターに**、クリックして**既存の SSO システムに参加**です。</span><span class="sxs-lookup"><span data-stu-id="b8808-112">In the details pane, select **Enable Enterprise Single Sign-On on this computer**, and then click **Join an existing SSO system**.</span></span>  
  
4.  <span data-ttu-id="b8808-113">**データ ストア**、SSO データベースと SSO データベースの名前をホストする SQL server の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b8808-113">In **Data stores**, enter the name of the SQL server hosting the SSO database and the name of the SSO database.</span></span>  
  
5.  <span data-ttu-id="b8808-114">**Windows サービス**、最初にインストールして BizTalk Server を構成するときに使用する SSO サービス アカウントのユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8808-114">In **Windows service**, enter the user name and password for the SSO service account that you used when you originally installed and configured BizTalk Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b8808-115">別のアカウントを使用することもできますが、使用するアカウントはシングル サインオン管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8808-115">You can use a different account, but it must be a member of the Single Sign-On Administrators group.</span></span>  
  
6.  <span data-ttu-id="b8808-116">[**構成の適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8808-116">Click **Apply Configuration**.</span></span>  
  
     <span data-ttu-id="b8808-117">マスター シークレットが取得されなかったことを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8808-117">A warning that no master secrets were retrieved is displayed.</span></span> <span data-ttu-id="b8808-118">イベント ビューアーを使用すると、エンタープライズ シングル サインオン サービスがコンピューターで開始され実行されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b8808-118">You can use Event Viewer to verify that the Enterprise Single Sign-On service is now started and running on the computer.</span></span>  
  
7.  <span data-ttu-id="b8808-119">をクリックして**ファイル**、クリックして**終了**です。</span><span class="sxs-lookup"><span data-stu-id="b8808-119">Click **File**, and then click **Exit**.</span></span>  
  
8.  <span data-ttu-id="b8808-120">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="b8808-120">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="b8808-121">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b8808-121">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="b8808-122">**cd プログラム files \common files \enterprise でのシングル サインオン**</span><span class="sxs-lookup"><span data-stu-id="b8808-122">**cd Program Files\Common Files\Enterprise Single Sign-On**</span></span>  
  
10. <span data-ttu-id="b8808-123">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b8808-123">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="b8808-124">**ssoconfig restoresecret と入力***\<backupfile >* </span><span class="sxs-lookup"><span data-stu-id="b8808-124">**ssoconfig -restoreSecret**  *\<backupfile>*</span></span>  
  
     <span data-ttu-id="b8808-125">ここで *\<backupfile >*バックアップしたマスター シークレット ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8808-125">where *\<backupfile>* is the name of the master secret file that you backed up.</span></span>  
  
     <span data-ttu-id="b8808-126">ときに**ssoconfig**バックアップ ファイルのパスワードの入力を求め SSO の構成中に指定されたパスワードを入力してください。</span><span class="sxs-lookup"><span data-stu-id="b8808-126">When **ssoconfig** prompts you for the backup file password, enter the password that was specified during SSO configuration.</span></span> <span data-ttu-id="b8808-127">パスワードが正しい場合、 **ssoconfig**次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8808-127">If the password is correct, **ssoconfig** displays the following message:</span></span>  
  
     <span data-ttu-id="b8808-128">**操作は正常に完了しました**</span><span class="sxs-lookup"><span data-stu-id="b8808-128">**The operation completed successfully**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8808-129">参照</span><span class="sxs-lookup"><span data-stu-id="b8808-129">See Also</span></span>  
 <span data-ttu-id="b8808-130">[BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="b8808-130">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="b8808-131">エンタープライズを構成する BizTalk Server 構成を使用して SSO</span><span class="sxs-lookup"><span data-stu-id="b8808-131">Configuring Enterprise SSO Using the BizTalk Server Configuration</span></span>](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)