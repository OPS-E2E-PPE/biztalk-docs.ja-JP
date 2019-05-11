---
title: パスワード同期を管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], managing
- managing [SSO], disabling features
- managing [SSO], enabling features
- Password Synchronization [SSO], SSOMANAGE command line utility
- SSO database, SSOMANAGE command line utility
- managing, Password Synchronization [SSO]
- SSO database, database settings
- SSOMANAGE command line utility
ms.assetid: 033e63f2-e5b0-4400-99c3-145679d9b84e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df4030becd9dfe86abfaa5745cb72e42c0a4b0c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384651"
---
# <a name="how-to-manage-password-synchronization"></a><span data-ttu-id="2b34f-102">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="2b34f-102">How to Manage Password Synchronization</span></span>
<span data-ttu-id="2b34f-103">MMC スナップインまたは SSOMANAGE コマンド ライン ユーティリティを使用して有効または SSO の機能を無効にして、SSO データベースの現在の設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="2b34f-103">Use the MMC Snap-in or the SSOMANAGE command line utility to enable or disable SSO features, and to display current SSO database settings.</span></span>  
  
### <a name="to-manage-features-or-display-settings-using-the-mmc-snap-in"></a><span data-ttu-id="2b34f-104">機能の管理または MMC スナップインを使用して設定を表示するには</span><span class="sxs-lookup"><span data-stu-id="2b34f-104">To manage features or display settings using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="2b34f-105">適切な機能またはデータベースを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="2b34f-105">Right-click the appropriate feature or database.</span></span>  
  
2.  <span data-ttu-id="2b34f-106">適切なメニュー項目をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b34f-106">Click the appropriate menu item.</span></span>  
  
### <a name="to-enable-sso-features-using-the-command-line"></a><span data-ttu-id="2b34f-107">コマンドラインを使用して SSO 機能を有効にするには</span><span class="sxs-lookup"><span data-stu-id="2b34f-107">To enable SSO features using the command line</span></span>  
  
1.  <span data-ttu-id="2b34f-108">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b34f-108">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2b34f-109">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="2b34f-109">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2b34f-110">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="2b34f-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2b34f-111">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="2b34f-111">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2b34f-112">型**ssomanage-有効にする**Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2b34f-112">Type **ssomanage -enable** and press Enter.</span></span>  
  
### <a name="to-disable-sso-features-using-the-command-line"></a><span data-ttu-id="2b34f-113">コマンドラインを使用して SSO 機能を無効にするには</span><span class="sxs-lookup"><span data-stu-id="2b34f-113">To disable SSO features using the command line</span></span>  
  
1.  <span data-ttu-id="2b34f-114">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b34f-114">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2b34f-115">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="2b34f-115">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2b34f-116">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="2b34f-116">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2b34f-117">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="2b34f-117">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2b34f-118">型**ssomanage-を無効にする**Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2b34f-118">Type **ssomanage -disable** and press Enter.</span></span>  
  
### <a name="to-display-current-database-settings-using-the-command-line"></a><span data-ttu-id="2b34f-119">コマンドラインを使用して現在のデータベース設定を表示するには</span><span class="sxs-lookup"><span data-stu-id="2b34f-119">To display current database settings using the command line</span></span>  
  
1.  <span data-ttu-id="2b34f-120">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b34f-120">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2b34f-121">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="2b34f-121">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2b34f-122">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="2b34f-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2b34f-123">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="2b34f-123">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="2b34f-124">型**ssomanage-displaydb** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2b34f-124">Type **ssomanage -displaydb** and press Enter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b34f-125">参照</span><span class="sxs-lookup"><span data-stu-id="2b34f-125">See Also</span></span>  
 [<span data-ttu-id="2b34f-126">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="2b34f-126">Password Synchronization</span></span>](../core/password-synchronization2.md)