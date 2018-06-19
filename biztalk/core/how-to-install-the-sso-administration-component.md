---
title: SSO 管理コンポーネントのインストール |Microsoft ドキュメント
description: SSO の管理を取得するカスタム インストールを実行して、ssomanage または SSO 管理を使用して、BizTalk Server でサーバー名を入力するには
ms.custom: ''
ms.date: 09/27/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 096839e2-7129-498d-92ee-5afeea8dbe0d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab2bb01defe700408a551a144eae67d0405565f4
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2017
ms.locfileid: "22317987"
---
# <a name="how-to-install-the-sso-administration-component"></a><span data-ttu-id="ea8f1-103">SSO 管理コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="ea8f1-103">How to Install the SSO Administration Component</span></span>

## <a name="overview"></a><span data-ttu-id="ea8f1-104">概要</span><span class="sxs-lookup"><span data-stu-id="ea8f1-104">Overview</span></span>
<span data-ttu-id="ea8f1-105">スタンドアロン機能として、エンタープライズ シングル サインオンの管理コンポーネントをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-105">You can install the Enterprise Single Sign-On Administration component as a stand-alone feature.</span></span> <span data-ttu-id="ea8f1-106">このコンポーネントは、SSO システムをリモートで管理する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-106">This is useful if you need to administer the SSO system remotely.</span></span> <span data-ttu-id="ea8f1-107">ハードウェアおよびソフトウェアの要件は、一般的なエンタープライズ SSO ランタイム サービスのインストールと同じです。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-107">The hardware and software requirements are the same as for a typical Enterprise SSO Runtime Services installation.</span></span>  
  
 <span data-ttu-id="ea8f1-108">管理コンポーネントをインストールした後は、管理用に使用する SSO サーバーを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-108">After installing the administration component, you enter the SSO Server to be used for management.</span></span> <span data-ttu-id="ea8f1-109">コマンド ライン ツール (ssomanage.exe) または SSO 管理 MMC スナップインで、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-109">You can do this with either the command line tool (ssomanage.exe), or the SSO Administration MMC Snap-In.</span></span> <span data-ttu-id="ea8f1-110">どちらの手順は、このトピックに記載されています。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-110">Both procedures are listed in this topic.</span></span>  
  
 <span data-ttu-id="ea8f1-111">SSO 管理ユーティリティ (ssomanage.exe) をインストールしても、コマンド ライン ユーティリティにアクセスするショートカットは [スタート] メニューに作成されません。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-111">Installing the SSO administrative utility (ssomanage.exe) does not create shortcuts on the Start menu to access the command line utilities.</span></span> <span data-ttu-id="ea8f1-112">をインストールした後、SSO 管理ユーティリティを実行するには、コマンド プロンプトを開き、とにある SSO ディレクトリに移動する必要があります`Program Files\Common Files\Enterprise Single Sign-On`です。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-112">To run the SSO administrative utilities after installation, you must open a command prompt, and navigate to the SSO directory at `Program Files\Common Files\Enterprise Single Sign-On`.</span></span>  
  
 <span data-ttu-id="ea8f1-113">エンタープライズ SSO の管理機能には、MMC スナップインも含まれています。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-113">The Enterprise SSO Administration feature also includes an MMC Snap-in.</span></span> <span data-ttu-id="ea8f1-114">MMC 3.0 は、関数にスナップインのコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-114">MMC 3.0 must be installed on your computer for the Snap-in to function.</span></span>  
  
 <span data-ttu-id="ea8f1-115">開くには、エンタープライズ SSO MMC スナップインから、**開始**メニューの **すべてのプログラム** **Microsoft エンタープライズ シングル サインオン**、し**SSO管理**です。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-115">To open the Enterprise SSO MMC Snap-in from the **Start** menu, select **All Programs**, select **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
## <a name="install-the-enterprise-single-sign-on-administrative-component"></a><span data-ttu-id="ea8f1-116">エンタープライズ シングル サインオン管理コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-116">Install the Enterprise Single Sign-On administrative component</span></span>  
  
-   <span data-ttu-id="ea8f1-117">カスタム インストールを行う[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、エンタープライズ シングル サインオン管理機能のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-117">Do a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and select only the Enterprise Single Sign-On Administration feature.</span></span> <span data-ttu-id="ea8f1-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、下に記載されてこの**追加のソフトウェア**です。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-118">For [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], this is listed under **Additional Software**.</span></span>  
  
## <a name="enter-the-server-using-the-mmc-snap-in"></a><span data-ttu-id="ea8f1-119">MMC スナップインを使用してサーバー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-119">Enter the server using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="ea8f1-120">現在管理コンポーネントがインストールされていないコンピューターに管理コンポーネントをインストールした後、SSO 管理スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-120">After installing the administrative component on a computer where it is not currently installed, open the SSO Administration Snap-In.</span></span>  
  
     <span data-ttu-id="ea8f1-121">**開始**メニューの **すべてのプログラム** **Microsoft エンタープライズ シングル サインオン**、し、 **SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-121">In the **Start** menu, select **All Programs**, select **Microsoft Enterprise Single Sign-On**, and then select **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="ea8f1-122">MMC スナップインで、**コンソール ルート**を右クリックして**エンタープライズ シングル サインオン**、 をクリック**選択**です。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-122">In the MMC Snap-In under the **Console Root**, right-click **Enterprise Single Sign-On**, and click **Select**.</span></span>  
  
     <span data-ttu-id="ea8f1-123">**SSO サーバーの選択** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-123">The **Select SSO Server** dialog box will appear.</span></span>  
  
3.  <span data-ttu-id="ea8f1-124">指定する SSO サーバーの名前を入力または参照します。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-124">Enter or browse to the SSO server name you want to specify.</span></span> <span data-ttu-id="ea8f1-125">コンピューター上のすべてのユーザーの SSO サーバーを指定するには、選択**すべてのユーザーの SSO サーバーの設定**です。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-125">To specify the SSO server for all users on the computer, select **Set SSO Server for all users**.</span></span>  
  
4.  <span data-ttu-id="ea8f1-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-126">Click **OK**.</span></span>  
  
## <a name="enter-the-server-using-the-command-line-tool"></a><span data-ttu-id="ea8f1-127">コマンド ライン ツールを使用してサーバー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-127">Enter the server using the command line tool</span></span>  
  
1.  <span data-ttu-id="ea8f1-128">をクリックして**開始**、 をクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-128">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="ea8f1-129">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-129">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="ea8f1-130">既定のインストール ディレクトリは`\Program Files\Common Files\Enterprise Single Sign-On`します。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-130">The default installation directory is `\Program Files\Common Files\Enterprise Single Sign-On`.</span></span>  
  
3.  <span data-ttu-id="ea8f1-131">次のオプションのいずれかを選択して、SSO サーバーを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-131">Enter the SSO Server by selecting one of the following options:</span></span>  
  
    1.  <span data-ttu-id="ea8f1-132">型**ssomanage – server**管理操作を実行するときに接続する SSO サーバーを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-132">Type **ssomanage –server** to enter the SSO Server you want to connect to when performing administration operations.</span></span>  
  
         <span data-ttu-id="ea8f1-133">\- または -</span><span class="sxs-lookup"><span data-stu-id="ea8f1-133">\- OR -</span></span>  
  
    2.  <span data-ttu-id="ea8f1-134">型**ssomanage-serverall**管理操作を実行するときにこのコンピューターのすべてのユーザーが接続する SSO サーバーを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea8f1-134">Type **ssomanage -serverall** to enter the SSO Server all users of this computer will connect to when performing administration operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8f1-135">参照</span><span class="sxs-lookup"><span data-stu-id="ea8f1-135">See Also</span></span>  
 <span data-ttu-id="ea8f1-136">[SSO クライアント ユーティリティをインストールする方法](../core/how-to-install-the-sso-client-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ea8f1-136">[How to Install the SSO Client Utility](../core/how-to-install-the-sso-client-utility.md) </span></span>  
 <span data-ttu-id="ea8f1-137">[SSO を構成します。](../core/configuring-sso.md) </span><span class="sxs-lookup"><span data-stu-id="ea8f1-137">[Configuring SSO](../core/configuring-sso.md) </span></span>  
 [<span data-ttu-id="ea8f1-138">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="ea8f1-138">Installing SSO</span></span>](../core/installing-sso.md)
