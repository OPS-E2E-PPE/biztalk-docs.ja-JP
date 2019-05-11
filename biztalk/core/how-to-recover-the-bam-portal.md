---
title: BAM ポータルを復旧する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a5df99-6d03-4f1f-8540-1700d3a0b9db
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7f0d9a813b2a8cee115ba782131c2492ea14fff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335593"
---
# <a name="how-to-recover-the-bam-portal"></a><span data-ttu-id="39c49-102">BAM ポータルを復旧する方法</span><span class="sxs-lookup"><span data-stu-id="39c49-102">How to Recover the BAM Portal</span></span>
<span data-ttu-id="39c49-103">ビジネス アクティビティ監視 (BAM) を使用している場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の復旧処理の一環として、BAM ポータルを復旧する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39c49-103">If you are using Business Activity Monitoring (BAM), you must recover the BAM portal as a part of recovering your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="39c49-104">BAM を使用していない場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="39c49-104">If you are not using BAM, this procedure is optional.</span></span>  
  
 <span data-ttu-id="39c49-105">BAM ポータル構成の復旧手順は、使用している IIS のバージョンによって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="39c49-105">The procedure for recovering the BAM portal configuration differs considerably depending on which version of IIS you are using.</span></span> <span data-ttu-id="39c49-106">IIS 7 の構成を復元する際に使用する**Appcmd.exe**、全体の既定の Web サイト、BAM ポータルだけでなく、構成を復元するとします。</span><span class="sxs-lookup"><span data-stu-id="39c49-106">When you restore the configuration for IIS 7, you use **Appcmd.exe**, and you restore the configuration for the entire default Web site, not just the BAM portal.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="39c49-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="39c49-107">Prerequisites</span></span>  
 <span data-ttu-id="39c49-108">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="39c49-108">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-the-bam-portal-configuration-iis-70"></a><span data-ttu-id="39c49-109">BAM ポータル構成 (IIS 7.0) を復旧するには</span><span class="sxs-lookup"><span data-stu-id="39c49-109">To recover the BAM portal configuration (IIS 7.0)</span></span>  
  
1.  <span data-ttu-id="39c49-110">実行 ダイアログ ボックスで、名前 ボックスで、以下を入力: `runas /user:` *computername*`\`*accountname* `cmd`、クリックして**OK**またはキーを押して**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="39c49-110">On the Run dialog, in the Open box, type the following: `runas /user:`*computername*`\`*accountname* `cmd`, and then click **OK** or press **Enter**.</span></span>  
  
     <span data-ttu-id="39c49-111">*Accountname*ローカル コンピューターの administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="39c49-111">*Accountname* must be a member of the administrators group on the local computer.</span></span>  
  
2.  <span data-ttu-id="39c49-112">パスワードを入力メッセージが表示されたら、 *accountname*、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="39c49-112">When prompted, type the password for *accountname*, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="39c49-113">型`cd %windir%\system32\inetsrv`、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="39c49-113">Type `cd %windir%\system32\inetsrv`, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="39c49-114">型`appcmd restore backup “`*バックアップ名*`”`、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="39c49-114">Type `appcmd restore backup “`*backupname*`”`, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="39c49-115">*バックアップ名*を使用して以前作成したバックアップの名前を指定**Appcmd.exe**です。</span><span class="sxs-lookup"><span data-stu-id="39c49-115">*Backupname* is the name of a backup you previously created using **Appcmd.exe**.</span></span> <span data-ttu-id="39c49-116">このバックアップが存在する必要があります、 **%windir%\system32\inetsrv\backup**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="39c49-116">This backup must exist in the **%windir%\system32\inetsrv\backup** directory.</span></span> <span data-ttu-id="39c49-117">バックアップを使用して別のコンピューターで作成されたパスワードを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="39c49-117">The backup cannot be used to restore passwords created on a different computer.</span></span> <span data-ttu-id="39c49-118">BAMAppPool が既定以外の id で実行するよう構成かどうか**NetworkService**アカウント、別途、次の手順で説明されているアカウントとパスワードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39c49-118">If the BAMAppPool is configured to run under an identity other than the default **NetworkService** account, you must configure the account and password separately, as described in the next step.</span></span>  
  
5.  <span data-ttu-id="39c49-119">使用して、**インターネット インフォメーション サービス (IIS) マネージャー\*\*\*\*アプリケーション プール**で、**接続**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="39c49-119">Using the **Internet Information Services (IIS) Manager**, select **Application Pools** in the **Connections** pane.</span></span>  
  
6.  <span data-ttu-id="39c49-120">**アプリケーション プール** ウィンドウを右クリックし、 **BAMAppPool**をクリックし、**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="39c49-120">In the **Application Pools** pane, right-click the **BAMAppPool**, then click **Advanced Settings**</span></span>  
  
7.  <span data-ttu-id="39c49-121">**高度な設定**s ダイアログ ボックスで、下にスクロール、**プロセス モデル**セクションです。</span><span class="sxs-lookup"><span data-stu-id="39c49-121">In the **Advanced Setting**s dialog, scroll down to the **Process Model** section.</span></span> <span data-ttu-id="39c49-122">クリックして、 **Identity**ボックス。</span><span class="sxs-lookup"><span data-stu-id="39c49-122">Click the **Identity** box.</span></span> <span data-ttu-id="39c49-123">ボックスの右側に省略記号ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c49-123">This will cause an ellipses button to appear on the right side of the box.</span></span> <span data-ttu-id="39c49-124">クリックして、**楕円**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="39c49-124">Click the **ellipses** button.</span></span>  
  
8.  <span data-ttu-id="39c49-125">**アプリケーション プール Id**ダイアログ ボックスで、をクリックして、**カスタム アカウント** ボタン、をクリックして、**設定**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="39c49-125">In the **Application Pool Identity** dialog, click the **Custom account** button, then click the **Set** button.</span></span>  
  
9. <span data-ttu-id="39c49-126">**資格情報の設定** ダイアログ ボックスで、BAMAppPool で使用するパスワードとアカウントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="39c49-126">In the **Set Credentials** dialog box, enter the account name and password you want to use for the BAMAppPool.</span></span> <span data-ttu-id="39c49-127">として、アカウント名を入力する必要があります*コンピューター名*`\`*accountname*、または*ドメイン*`\`*accountname*.</span><span class="sxs-lookup"><span data-stu-id="39c49-127">The account name should be entered as *computer name*`\`*accountname*, or *domain*`\`*accountname*.</span></span> <span data-ttu-id="39c49-128">をクリックして**OK**を閉じる、**資格情報の設定**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="39c49-128">Click **OK** to close the **Set Credentials** dialog.</span></span>  
  
10. <span data-ttu-id="39c49-129">をクリックして**OK**を閉じる、**アプリケーション プール Id**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="39c49-129">Click **OK** to close the **Application Pool Identity** dialog.</span></span>  
  
11. <span data-ttu-id="39c49-130">をクリックして**OK**を閉じる、**詳細設定**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="39c49-130">Click **OK** to close the **Advanced Settings** dialog.</span></span>  
  
12. <span data-ttu-id="39c49-131">いることを確認、 **BAMAppPool**アプリケーション プールの一覧で選択されています。</span><span class="sxs-lookup"><span data-stu-id="39c49-131">Verify that the **BAMAppPool** is selected in the list of application pools.</span></span> <span data-ttu-id="39c49-132">**アクション**の右側のペイン、**インターネット インフォメーション サービス (IIS) マネージャー**画面で、**アプリケーション プールのタスク**をクリックして**の開始**.</span><span class="sxs-lookup"><span data-stu-id="39c49-132">In the **Actions** pane on the right of the **Internet Information Services (IIS) Manager** screen, under **Application Pool Tasks**, click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c49-133">参照</span><span class="sxs-lookup"><span data-stu-id="39c49-133">See Also</span></span>  
 <span data-ttu-id="39c49-134">[BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="39c49-134">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="39c49-135">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="39c49-135">BAM Portal</span></span>](../core/bam-portal.md)