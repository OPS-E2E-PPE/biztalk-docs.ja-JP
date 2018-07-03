---
title: エンタープライズ シングル サインオンを復旧する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 845e6ff7-88a8-4ab4-b307-f9275d44600e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d56953fcab29b53f23ba3097296a74aeb67a17c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973123"
---
# <a name="how-to-recover-enterprise-single-sign-on"></a><span data-ttu-id="7692e-102">エンタープライズ シングル サインオンを復旧する方法</span><span class="sxs-lookup"><span data-stu-id="7692e-102">How to Recover Enterprise Single Sign-On</span></span>
<span data-ttu-id="7692e-103">BizTalk Server を復旧する前に、まずはエンタープライズ シングル サインオン (SSO) を復旧する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7692e-103">Before you can recover BizTalk Server, you must first recover Enterprise Single Sign-On (SSO).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7692e-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="7692e-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="7692e-105">この作業を実行するには、シングル サインオン管理者グループのメンバーおよび管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7692e-105">You must be logged on as a member of the Single Sign-On Administrators group and a member of the Administrators group to perform this task.</span></span>  
  
-   <span data-ttu-id="7692e-106">SSO の構成中に使用したパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="7692e-106">You must have the password used during SSO configuration.</span></span>  
  
-   <span data-ttu-id="7692e-107">リモート サーバー上のすべてのデータベースが破損していない必要があります。</span><span class="sxs-lookup"><span data-stu-id="7692e-107">All databases are intact on the remote server.</span></span>  
  
-   <span data-ttu-id="7692e-108">バックアップ マスター シークレット ファイルが破損しておらず、安全な場所に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7692e-108">The backup master secret file is intact and stored in a safe place.</span></span>  
  
### <a name="to-recover-enterprise-single-sign-on"></a><span data-ttu-id="7692e-109">エンタープライズ シングル サインオンを復旧するには</span><span class="sxs-lookup"><span data-stu-id="7692e-109">To recover Enterprise Single Sign-On</span></span>  
  
1. <span data-ttu-id="7692e-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 構成**します。</span><span class="sxs-lookup"><span data-stu-id="7692e-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2. <span data-ttu-id="7692e-111">Microsoft BizTalk Server 構成では、コンソール ツリーで、クリックして**エンタープライズ SSO**します。</span><span class="sxs-lookup"><span data-stu-id="7692e-111">In Microsoft BizTalk Server Configuration, in the console tree, click **Enterprise SSO**.</span></span>  
  
3. <span data-ttu-id="7692e-112">詳細] ウィンドウで、[**を有効にするエンタープライズ シングル サインオン コンピューターこの**、順にクリックします**既存の SSO システムに参加**します。</span><span class="sxs-lookup"><span data-stu-id="7692e-112">In the details pane, select **Enable Enterprise Single Sign-On on this computer**, and then click **Join an existing SSO system**.</span></span>  
  
4. <span data-ttu-id="7692e-113">**データ ストア**、SSO データベースと SSO データベースの名前をホストする SQL server の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7692e-113">In **Data stores**, enter the name of the SQL server hosting the SSO database and the name of the SSO database.</span></span>  
  
5. <span data-ttu-id="7692e-114">**Windows サービス**、最初にインストールして BizTalk Server を構成するときに使用した SSO サービス アカウントのユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7692e-114">In **Windows service**, enter the user name and password for the SSO service account that you used when you originally installed and configured BizTalk Server.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="7692e-115">別のアカウントを使用することもできますが、使用するアカウントはシングル サインオン管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7692e-115">You can use a different account, but it must be a member of the Single Sign-On Administrators group.</span></span>  
  
6. <span data-ttu-id="7692e-116">**[構成の適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7692e-116">Click **Apply Configuration**.</span></span>  
  
    <span data-ttu-id="7692e-117">マスター シークレットが取得されなかったことを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7692e-117">A warning that no master secrets were retrieved is displayed.</span></span> <span data-ttu-id="7692e-118">イベント ビューアーを使用すると、エンタープライズ シングル サインオン サービスがコンピューターで開始され実行されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7692e-118">You can use Event Viewer to verify that the Enterprise Single Sign-On service is now started and running on the computer.</span></span>  
  
7. <span data-ttu-id="7692e-119">クリックして**ファイル**、 をクリックし、**終了**します。</span><span class="sxs-lookup"><span data-stu-id="7692e-119">Click **File**, and then click **Exit**.</span></span>  
  
8. <span data-ttu-id="7692e-120">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="7692e-120">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="7692e-121">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7692e-121">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="7692e-122">**cd Program files \common files \enterprise でシングル サインオン**</span><span class="sxs-lookup"><span data-stu-id="7692e-122">**cd Program Files\Common Files\Enterprise Single Sign-On**</span></span>  
  
10. <span data-ttu-id="7692e-123">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7692e-123">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="7692e-124">**ssoconfig-restoresecret***\<backupfile  \>*</span><span class="sxs-lookup"><span data-stu-id="7692e-124">**ssoconfig -restoreSecret**  *\<backupfile\>*</span></span>  
  
     <span data-ttu-id="7692e-125">場所*\<backupfile\>* バックアップしたマスター シークレット ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7692e-125">where *\<backupfile\>* is the name of the master secret file that you backed up.</span></span>  
  
     <span data-ttu-id="7692e-126">ときに**ssoconfig** SSO を構成中に指定されたパスワードを入力するバックアップ ファイルのパスワードをユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="7692e-126">When **ssoconfig** prompts you for the backup file password, enter the password that was specified during SSO configuration.</span></span> <span data-ttu-id="7692e-127">パスワードが正しい場合、 **ssoconfig**次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7692e-127">If the password is correct, **ssoconfig** displays the following message:</span></span>  
  
     <span data-ttu-id="7692e-128">**操作は正常に完了しました**</span><span class="sxs-lookup"><span data-stu-id="7692e-128">**The operation completed successfully**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7692e-129">参照</span><span class="sxs-lookup"><span data-stu-id="7692e-129">See Also</span></span>  
 <span data-ttu-id="7692e-130">[BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="7692e-130">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="7692e-131">Enterprise を構成する BizTalk Server 構成を使用して SSO</span><span class="sxs-lookup"><span data-stu-id="7692e-131">Configuring Enterprise SSO Using the BizTalk Server Configuration</span></span>](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)