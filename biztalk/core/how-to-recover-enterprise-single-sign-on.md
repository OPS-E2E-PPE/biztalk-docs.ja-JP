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
ms.openlocfilehash: 0e42139a9e286024487417a005963eb677b880a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384436"
---
# <a name="how-to-recover-enterprise-single-sign-on"></a><span data-ttu-id="a6d7e-102">エンタープライズ シングル サインオンを復旧する方法</span><span class="sxs-lookup"><span data-stu-id="a6d7e-102">How to Recover Enterprise Single Sign-On</span></span>
<span data-ttu-id="a6d7e-103">BizTalk Server を回復する前にまずエンタープライズ シングル サインオン (SSO) を回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-103">Before you can recover BizTalk Server, you must first recover Enterprise Single Sign-On (SSO).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a6d7e-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="a6d7e-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="a6d7e-105">このタスクを実行するには、シングル サインオン管理者グループのメンバーと管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-105">You must be logged on as a member of the Single Sign-On Administrators group and a member of the Administrators group to perform this task.</span></span>  
  
-   <span data-ttu-id="a6d7e-106">SSO の構成時に使用するパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-106">You must have the password used during SSO configuration.</span></span>  
  
-   <span data-ttu-id="a6d7e-107">すべてのデータベースは、リモート サーバー上にそのままです。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-107">All databases are intact on the remote server.</span></span>  
  
-   <span data-ttu-id="a6d7e-108">バックアップ マスター シークレット ファイルは、安全な場所にそのままおよび格納されています。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-108">The backup master secret file is intact and stored in a safe place.</span></span>  
  
### <a name="to-recover-enterprise-single-sign-on"></a><span data-ttu-id="a6d7e-109">エンタープライズ シングル サインオンを回復するには</span><span class="sxs-lookup"><span data-stu-id="a6d7e-109">To recover Enterprise Single Sign-On</span></span>  
  
1. <span data-ttu-id="a6d7e-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 構成**します。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2. <span data-ttu-id="a6d7e-111">Microsoft BizTalk Server 構成では、コンソール ツリーで、クリックして**エンタープライズ SSO**します。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-111">In Microsoft BizTalk Server Configuration, in the console tree, click **Enterprise SSO**.</span></span>  
  
3. <span data-ttu-id="a6d7e-112">詳細] ウィンドウで、[**を有効にするエンタープライズ シングル サインオン コンピューターこの**、順にクリックします**既存の SSO システムに参加**します。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-112">In the details pane, select **Enable Enterprise Single Sign-On on this computer**, and then click **Join an existing SSO system**.</span></span>  
  
4. <span data-ttu-id="a6d7e-113">**データ ストア**、SSO データベースと SSO データベースの名前をホストする SQL server の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-113">In **Data stores**, enter the name of the SQL server hosting the SSO database and the name of the SSO database.</span></span>  
  
5. <span data-ttu-id="a6d7e-114">**Windows サービス**、最初にインストールして BizTalk Server を構成するときに使用した SSO サービス アカウントのユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-114">In **Windows service**, enter the user name and password for the SSO service account that you used when you originally installed and configured BizTalk Server.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a6d7e-115">別のアカウントを使用できますが、シングル サインオン管理者グループのメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-115">You can use a different account, but it must be a member of the Single Sign-On Administrators group.</span></span>  
  
6. <span data-ttu-id="a6d7e-116">**[構成の適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-116">Click **Apply Configuration**.</span></span>  
  
    <span data-ttu-id="a6d7e-117">マスター シークレットが取得されなかった、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-117">A warning that no master secrets were retrieved is displayed.</span></span> <span data-ttu-id="a6d7e-118">ことができますイベント ビューアーを使用ことを確認するのに、エンタープライズ シングル サインオン サービスを今すぐ開始と実行、コンピューター上です。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-118">You can use Event Viewer to verify that the Enterprise Single Sign-On service is now started and running on the computer.</span></span>  
  
7. <span data-ttu-id="a6d7e-119">クリックして**ファイル**、 をクリックし、**終了**します。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-119">Click **File**, and then click **Exit**.</span></span>  
  
8. <span data-ttu-id="a6d7e-120">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-120">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="a6d7e-121">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-121">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="a6d7e-122">**cd Program Files\Common Files\Enterprise Single Sign-On**</span><span class="sxs-lookup"><span data-stu-id="a6d7e-122">**cd Program Files\Common Files\Enterprise Single Sign-On**</span></span>  
  
10. <span data-ttu-id="a6d7e-123">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-123">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="a6d7e-124">**ssoconfig -restoreSecret**  *\<backupfile\>*</span><span class="sxs-lookup"><span data-stu-id="a6d7e-124">**ssoconfig -restoreSecret**  *\<backupfile\>*</span></span>  
  
     <span data-ttu-id="a6d7e-125">場所*\<backupfile\>* バックアップしたマスター シークレット ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-125">where *\<backupfile\>* is the name of the master secret file that you backed up.</span></span>  
  
     <span data-ttu-id="a6d7e-126">ときに**ssoconfig** SSO を構成中に指定されたパスワードを入力するバックアップ ファイルのパスワードをユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-126">When **ssoconfig** prompts you for the backup file password, enter the password that was specified during SSO configuration.</span></span> <span data-ttu-id="a6d7e-127">パスワードが正しい場合、 **ssoconfig**次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6d7e-127">If the password is correct, **ssoconfig** displays the following message:</span></span>  
  
     <span data-ttu-id="a6d7e-128">**操作は正常に完了しました**</span><span class="sxs-lookup"><span data-stu-id="a6d7e-128">**The operation completed successfully**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d7e-129">参照</span><span class="sxs-lookup"><span data-stu-id="a6d7e-129">See Also</span></span>  
 <span data-ttu-id="a6d7e-130">[BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="a6d7e-130">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="a6d7e-131">Enterprise を構成する BizTalk Server 構成を使用して SSO</span><span class="sxs-lookup"><span data-stu-id="a6d7e-131">Configuring Enterprise SSO Using the BizTalk Server Configuration</span></span>](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)