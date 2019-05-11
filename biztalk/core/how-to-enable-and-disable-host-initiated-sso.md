---
title: 側開始 SSO を有効にし、ホストを無効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host initiated SSO, disabling
- disabling, host initiated SSO
- enabling, host initiated SSO
- host initiated SSO, enabling
ms.assetid: a11d314a-6ff9-4d0a-89c3-c412541c2cec
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 312d5c295981bf7af5ec4ed45140fa6c915a7ae6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337966"
---
# <a name="how-to-enable-and-disable-host-initiated-sso"></a><span data-ttu-id="4d6b3-102">側開始 SSO を有効にし、ホストを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="4d6b3-102">How to Enable and Disable Host Initiated SSO</span></span>
<span data-ttu-id="4d6b3-103">既定ではホスト側開始シングル サインオン、シングル サインオン システムを有効にしないと、SSO 管理者によって有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-103">By default, host initiated Single Sign-On is not enabled in the Single Sign-On system, and must be enabled by the SSO Administrator.</span></span>  
  
### <a name="to-enable-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="4d6b3-104">側開始 SSO を MMC スナップインを使用してホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-104">To enable host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="4d6b3-105">**開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-105">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="4d6b3-106">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="4d6b3-107">右クリックして**システム**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-107">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="4d6b3-108">をクリックして、**オプション**タブ。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-108">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="4d6b3-109">選択、**有効にするホスト側開始 SSO**ボックスし、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-109">Select the **Enable host initiated SSO** box, and click **OK**.</span></span>  
  
### <a name="to-enable-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="4d6b3-110">側開始 SSO をコマンドラインを使用してホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-110">To enable host initiated SSO using the command line</span></span>  
  
1. <span data-ttu-id="4d6b3-111">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-111">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="4d6b3-112">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-112">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="4d6b3-113">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="4d6b3-114">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-114">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4. <span data-ttu-id="4d6b3-115">型**ssomanage-hisso を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-115">Type **ssomanage -enable hisso**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4d6b3-116">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
   <span data-ttu-id="4d6b3-117">SSO を無効にすると、SSO システム全体に適用され、ホスト側開始 SSO に関連するすべての操作がオフになります。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-117">Disabling SSO applies to the entire SSO system, and all operations related to host initiated SSO are turned off.</span></span>  
  
#### <a name="to-disable-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="4d6b3-118">側開始 SSO を MMC スナップインを使用してホストを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-118">To disable host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="4d6b3-119">**開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-119">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="4d6b3-120">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-120">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="4d6b3-121">右クリックして**システム**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-121">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="4d6b3-122">をクリックして、**オプション**タブ。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-122">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="4d6b3-123">クリア、**有効にするホスト側開始 SSO**ボックスし、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-123">Clear the **Enable host initiated SSO** box, and click **OK**.</span></span>  
  
#### <a name="to-disable-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="4d6b3-124">側開始 SSO をコマンドラインを使用してホストを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-124">To disable host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="4d6b3-125">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-125">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="4d6b3-126">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-126">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="4d6b3-127">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-127">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="4d6b3-128">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-128">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="4d6b3-129">型**ssomanage-hisso を無効にする**に応じて。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-129">Type **ssomanage -disable hisso** as appropriate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d6b3-130">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d6b3-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6b3-131">参照</span><span class="sxs-lookup"><span data-stu-id="4d6b3-131">See Also</span></span>  
 [<span data-ttu-id="4d6b3-132">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="4d6b3-132">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)