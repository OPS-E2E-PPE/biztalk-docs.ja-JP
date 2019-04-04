---
title: SSO を有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], creating
- SSO, enabling
- maps [SSO], creating
- managing [SSO], enabling
- SSO, maps
- SSO, applications
- creating, applications [SSO]
- managing [SSO], creating affiliate applications
ms.assetid: dda89d15-6b70-4c40-b658-2f6cbdd545c8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bb2c6e5349a74fb212bdf7011fb294cb1810e67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966259"
---
# <a name="how-to-enable-sso"></a><span data-ttu-id="6936d-102">SSO を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="6936d-102">How to Enable SSO</span></span>
<span data-ttu-id="6936d-103">MMC スナップインまたはコマンド ラインを使用して、エンタープライズ シングル サインオン (SSO) システムを全面的に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6936d-103">You can enable the entire Enterprise Single Sign-On (SSO) system by using either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="6936d-104">有効化コマンドを実行した後、各シングル サインオン サーバーで最新のグローバル情報を取得するために SSO データベースをポーリングするので、すべてのサーバーが有効になるまでに、若干の遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="6936d-104">After you run the enabling command, there is a short delay before all Single Sign-On Servers are enabled, as each polls the SSO database for the latest global information.</span></span>  
  
 <span data-ttu-id="6936d-105">SSO システムの関連アプリケーションおよびマッピングを構成する場合、関連アプリケーションを作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="6936d-105">If you want to configure affiliate applications and mappings in the SSO system, you must also create an affiliate application.</span></span> <span data-ttu-id="6936d-106">SSO 関連管理者が関連アプリケーションを作成した後で、アプリケーション管理者が変更を加えたり、アプリケーション ユーザー (エンド ユーザー) が自分のマッピングを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="6936d-106">After an SSO affiliate administrator creates an affiliate application, an application administrator can make changes to it, and application users (end-users) can create their own mappings.</span></span> <span data-ttu-id="6936d-107">詳細については、[関連アプリケーションを管理する](../core/managing-affiliate-applications.md)と[ユーザー マッピングを管理する](../core/managing-user-mappings.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6936d-107">For more information, see [Managing Affiliate Applications](../core/managing-affiliate-applications.md) and [Managing User Mappings](../core/managing-user-mappings.md).</span></span>  
  
### <a name="to-enable-the-sso-system-using-the-mmc-snap-in"></a><span data-ttu-id="6936d-108">MMC スナップインを使用して SSO システムを有効にするには</span><span class="sxs-lookup"><span data-stu-id="6936d-108">To enable the SSO system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="6936d-109">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリックします**SSO 管理**します。</span><span class="sxs-lookup"><span data-stu-id="6936d-109">Click **Start**, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="6936d-110">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="6936d-110">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="6936d-111">右クリック**システム**、 をクリックし、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="6936d-111">Right-click **System**, and then click **Enable**.</span></span>  
  
### <a name="to-enable-the-sso-system-using-the-command-line"></a><span data-ttu-id="6936d-112">コマンド ラインを使用して SSO システムを有効にするには</span><span class="sxs-lookup"><span data-stu-id="6936d-112">To enable the SSO system using the command line</span></span>  
  
1.  <span data-ttu-id="6936d-113">クリックして**開始**、 をクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="6936d-113">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="6936d-114">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="6936d-114">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="6936d-115">既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="6936d-115">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="6936d-116">型**ssomanage – enablesso**します。</span><span class="sxs-lookup"><span data-stu-id="6936d-116">Type **ssomanage –enablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6936d-117">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6936d-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-sso-to-create-affiliate-applications-and-mappings"></a><span data-ttu-id="6936d-118">SSO で関連アプリケーションおよびマッピングを作成できるようにするには</span><span class="sxs-lookup"><span data-stu-id="6936d-118">To enable SSO to create affiliate applications and mappings</span></span>  
  
1. <span data-ttu-id="6936d-119">SSO 管理者または SSO 関連管理者として、SSO サーバーか、SSO の SSO 管理サブサービスを実装しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6936d-119">Log on as an SSO administrator or SSO affiliate administrator to the SSO Server, or on a computer that has the SSO administration sub services of SSO.</span></span>  
  
2. <span data-ttu-id="6936d-120">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="6936d-120">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
3. <span data-ttu-id="6936d-121">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="6936d-121">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="6936d-122">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="6936d-122">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4. <span data-ttu-id="6936d-123">型**ssomanage-enablesso**エンタープライズ シングル サインオン サービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6936d-123">Type **ssomanage -enablesso** to enable the Enterprise Single Sign-On service.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6936d-124">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6936d-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5. <span data-ttu-id="6936d-125">SSO 関連管理者としてログオンします。</span><span class="sxs-lookup"><span data-stu-id="6936d-125">Log on as an SSO affiliate administrator.</span></span>  
  
6. <span data-ttu-id="6936d-126">型**ssomanage-createapps *\<アプリケーション ファイル\>*** 関連アプリケーションを作成する場所\<アプリケーション ファイル\>は XML ファイルです関連アプリケーションの定義を含むです。</span><span class="sxs-lookup"><span data-stu-id="6936d-126">Type **ssomanage -createapps *\<application file\>*** to create an affiliate application, where \<application file\> is the XML file that contains definitions for the affiliate applications.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6936d-127">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6936d-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6936d-128">参照</span><span class="sxs-lookup"><span data-stu-id="6936d-128">See Also</span></span>  
 <span data-ttu-id="6936d-129">[SSO サーバーを設定する方法](../core/how-to-set-the-sso-server.md) </span><span class="sxs-lookup"><span data-stu-id="6936d-129">[How to Set the SSO Server](../core/how-to-set-the-sso-server.md) </span></span>  
 <span data-ttu-id="6936d-130">[SSO を無効にする方法](../core/how-to-disable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="6936d-130">[How to Disable SSO](../core/how-to-disable-sso.md) </span></span>  
 <span data-ttu-id="6936d-131">[SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="6936d-131">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="6936d-132">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="6936d-132">Using SSO</span></span>](../core/using-sso.md)