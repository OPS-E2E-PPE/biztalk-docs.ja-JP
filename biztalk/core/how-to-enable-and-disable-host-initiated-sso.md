---
title: 側開始 SSO を有効にし、ホストを無効にする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: c1e5783893bbc9091d0a5f1fb3f116b17413bc5d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968984"
---
# <a name="how-to-enable-and-disable-host-initiated-sso"></a><span data-ttu-id="2da85-102">側開始 SSO を有効にし、ホストを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="2da85-102">How to Enable and Disable Host Initiated SSO</span></span>
<span data-ttu-id="2da85-103">既定では、ホスト側開始シングル サインオンはシングル サインオン システムで有効になっていないため、SSO 管理者が有効化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2da85-103">By default, host initiated Single Sign-On is not enabled in the Single Sign-On system, and must be enabled by the SSO Administrator.</span></span>  
  
### <a name="to-enable-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="2da85-104">MMC スナップインを使用してホスト側開始 SSO を有効にするには</span><span class="sxs-lookup"><span data-stu-id="2da85-104">To enable host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="2da85-105">**開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="2da85-105">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="2da85-106">ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="2da85-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="2da85-107">右クリック**システム**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2da85-107">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2da85-108">クリックして、**オプション**タブです。</span><span class="sxs-lookup"><span data-stu-id="2da85-108">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="2da85-109">選択、**有効にするホスト側開始 SSO**ボックスし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2da85-109">Select the **Enable host initiated SSO** box, and click **OK**.</span></span>  
  
### <a name="to-enable-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="2da85-110">コマンド ラインを使用してホスト側開始 SSO を有効にするには</span><span class="sxs-lookup"><span data-stu-id="2da85-110">To enable host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="2da85-111">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2da85-111">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2da85-112">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2da85-112">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2da85-113">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="2da85-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2da85-114">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="2da85-114">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2da85-115">型**ssomanage-hisso を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="2da85-115">Type **ssomanage -enable hisso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2da85-116">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2da85-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
 <span data-ttu-id="2da85-117">SSO を無効にすると SSO システム全体に適用されるので、ホスト側開始 SSO に関連するすべての操作が無効になります。</span><span class="sxs-lookup"><span data-stu-id="2da85-117">Disabling SSO applies to the entire SSO system, and all operations related to host initiated SSO are turned off.</span></span>  
  
#### <a name="to-disable-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="2da85-118">MMC スナップインを使用してホスト側開始 SSO を無効にするには</span><span class="sxs-lookup"><span data-stu-id="2da85-118">To disable host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="2da85-119">**開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="2da85-119">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="2da85-120">ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="2da85-120">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="2da85-121">右クリック**システム**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2da85-121">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2da85-122">クリックして、**オプション**タブです。</span><span class="sxs-lookup"><span data-stu-id="2da85-122">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="2da85-123">クリア、**有効にするホスト側開始 SSO**ボックスし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2da85-123">Clear the **Enable host initiated SSO** box, and click **OK**.</span></span>  
  
#### <a name="to-disable-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="2da85-124">コマンド ラインを使用してホスト側開始 SSO を無効にするには</span><span class="sxs-lookup"><span data-stu-id="2da85-124">To disable host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="2da85-125">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2da85-125">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2da85-126">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2da85-126">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2da85-127">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="2da85-127">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2da85-128">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="2da85-128">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2da85-129">型**ssomanage-hisso を無効にする**に応じて。</span><span class="sxs-lookup"><span data-stu-id="2da85-129">Type **ssomanage -disable hisso** as appropriate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2da85-130">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2da85-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da85-131">参照</span><span class="sxs-lookup"><span data-stu-id="2da85-131">See Also</span></span>  
 [<span data-ttu-id="2da85-132">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="2da85-132">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)