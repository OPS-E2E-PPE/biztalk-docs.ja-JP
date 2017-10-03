---
title: "パスワード同期を管理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2939fd0594c878e3a5f1416d0b1e871b78ba3858
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-password-synchronization"></a><span data-ttu-id="1f5fa-102">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="1f5fa-102">How to Manage Password Synchronization</span></span>
<span data-ttu-id="1f5fa-103">MMC スナップインまたは SSOMANAGE コマンド ライン ユーティリティを使用すると、SSO 機能を有効または無効にしたり、現在の SSO データベース設定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-103">Use the MMC Snap-in or the SSOMANAGE command line utility to enable or disable SSO features, and to display current SSO database settings.</span></span>  
  
### <a name="to-manage-features-or-display-settings-using-the-mmc-snap-in"></a><span data-ttu-id="1f5fa-104">MMC スナップインを使用して機能の管理や設定の表示を行うには</span><span class="sxs-lookup"><span data-stu-id="1f5fa-104">To manage features or display settings using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="1f5fa-105">対象の機能またはデータベースを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-105">Right-click the appropriate feature or database.</span></span>  
  
2.  <span data-ttu-id="1f5fa-106">適切なメニュー項目をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-106">Click the appropriate menu item.</span></span>  
  
### <a name="to-enable-sso-features-using-the-command-line"></a><span data-ttu-id="1f5fa-107">コマンド ラインを使用して SSO 機能を有効にするには</span><span class="sxs-lookup"><span data-stu-id="1f5fa-107">To enable SSO features using the command line</span></span>  
  
1.  <span data-ttu-id="1f5fa-108">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-108">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1f5fa-109">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-109">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f5fa-110">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1f5fa-111">既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-111">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1f5fa-112">型**ssomanage-有効にする**Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-112">Type **ssomanage -enable** and press Enter.</span></span>  
  
### <a name="to-disable-sso-features-using-the-command-line"></a><span data-ttu-id="1f5fa-113">コマンド ラインを使用して SSO 機能を無効にするには</span><span class="sxs-lookup"><span data-stu-id="1f5fa-113">To disable SSO features using the command line</span></span>  
  
1.  <span data-ttu-id="1f5fa-114">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-114">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1f5fa-115">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-115">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f5fa-116">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-116">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1f5fa-117">既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-117">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1f5fa-118">型**ssomanage-無効**Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-118">Type **ssomanage -disable** and press Enter.</span></span>  
  
### <a name="to-display-current-database-settings-using-the-command-line"></a><span data-ttu-id="1f5fa-119">コマンド ラインを使用して現在のデータベース設定を表示するには</span><span class="sxs-lookup"><span data-stu-id="1f5fa-119">To display current database settings using the command line</span></span>  
  
1.  <span data-ttu-id="1f5fa-120">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-120">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1f5fa-121">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-121">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1f5fa-122">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1f5fa-123">既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-123">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="1f5fa-124">型**ssomanage-displaydb** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1f5fa-124">Type **ssomanage -displaydb** and press Enter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f5fa-125">参照</span><span class="sxs-lookup"><span data-stu-id="1f5fa-125">See Also</span></span>  
 [<span data-ttu-id="1f5fa-126">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="1f5fa-126">Password Synchronization</span></span>](../core/password-synchronization2.md)