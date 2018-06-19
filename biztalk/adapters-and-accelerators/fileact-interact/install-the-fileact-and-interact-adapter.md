---
title: FileAct をインストールし、アダプターの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf387d59-373b-4151-9dfd-30c511978862
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48a3beccd6179bcb4526ba41f4f41a7923f5f966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224170"
---
# <a name="install-the-fileact-and-interact-adapter"></a><span data-ttu-id="419c0-102">FileAct をインストールし、アダプターの対話</span><span class="sxs-lookup"><span data-stu-id="419c0-102">Install the FileAct and InterAct Adapter</span></span>
<span data-ttu-id="419c0-103">このセクションをインストールする手順を説明[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]– for SWIFT です。</span><span class="sxs-lookup"><span data-stu-id="419c0-103">This section provides instructions to install [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] – for SWIFT.</span></span> <span data-ttu-id="419c0-104">アダプターをインストールする前に、前提条件のソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="419c0-104">Before you install the adapters, you must install the prerequisite software.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="419c0-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="419c0-105">Prerequisites</span></span>  

* <span data-ttu-id="419c0-106">ローカルの administrators グループのメンバーであり、BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="419c0-106">Sign in with an account that is member of the local administrators group, and a member of the BizTalk Server Administrators group</span></span>
  
## <a name="step-1-install-biztalk-server-and-configure-bam"></a><span data-ttu-id="419c0-107">手順 1: BizTalk Server をインストールして BAM を構成します。</span><span class="sxs-lookup"><span data-stu-id="419c0-107">Step 1: Install BizTalk Server and configure BAM</span></span>

1. <span data-ttu-id="419c0-108">インストール[BizTalk Server 2016](../../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md)、または[BizTalk Server 2013 R2/2013](../../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)、およびビジネス アクティビティ監視 (BAM) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="419c0-108">Install [BizTalk Server 2016](../../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md), or [BizTalk Server 2013 R2 / 2013](../../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md), and install Business Activity Monitoring (BAM).</span></span>

2. <span data-ttu-id="419c0-109">構成[BizTalk Server](../../install-and-config-guides/configure-biztalk-server.md)、およびビジネス アクティビティ監視 (BAM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="419c0-109">Configure [BizTalk Server](../../install-and-config-guides/configure-biztalk-server.md), and configure Business Activity Monitoring (BAM).</span></span>
  
3. <span data-ttu-id="419c0-110">アクセスするための十分なセキュリティ特権があるかどうかを確認、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="419c0-110">Make sure you have enough security privileges to access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="419c0-111">[BizTalk Server のセキュリティ権限を最低限](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)優れたリソースです。</span><span class="sxs-lookup"><span data-stu-id="419c0-111">[Minimum Security Rights for BizTalk Server](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) is a great resource.</span></span>
  
## <a name="step-2-install-biztalk-accelerator-for-swift-a4swift"></a><span data-ttu-id="419c0-112">手順 2: 用 SWIFT (A4SWIFT) BizTalk アクセラレータをインストールします。</span><span class="sxs-lookup"><span data-stu-id="419c0-112">Step 2: Install BizTalk Accelerator for SWIFT (A4SWIFT)</span></span>  

<span data-ttu-id="419c0-113">インストールし、構成、 [BizTalk Accelerator 用 SWIFT](../../adapters-and-accelerators/accelerator-swift/install-configure-and-deploy-the-biztalk-accelerator-for-swift.md)です。</span><span class="sxs-lookup"><span data-stu-id="419c0-113">Install and configure the [BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/install-configure-and-deploy-the-biztalk-accelerator-for-swift.md).</span></span>

  
## <a name="step-3-install-swiftalliance-gateway-sag"></a><span data-ttu-id="419c0-114">手順 3: SWIFTAlliance ゲートウェイ (SAG) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="419c0-114">Step 3: Install SWIFTAlliance Gateway (SAG)</span></span>  
 <span data-ttu-id="419c0-115">FileAct および InterAct アダプターをインストールする前にメッセージ パートナーの SAG、終点、およびルーティング規則を作成し、接続をテストする SAG FileAct および InterAct アダプターをインストールするコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="419c0-115">Before you install the FileAct and InterAct adapters, create the SAG Message Partners, End Points, and Routing Rules, and test the SAG connectivity on the computer where you install the FileAct and InterAct adapters.</span></span>

<span data-ttu-id="419c0-116">参照してください[https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway](https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway) SWIFTAlliance ゲートウェイの詳細。</span><span class="sxs-lookup"><span data-stu-id="419c0-116">See [https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway](https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway) for specific details on the SWIFTAlliance Gateway.</span></span>  

## <a name="step-4-install-the-biztalk-fileact-and-interact-adapters"></a><span data-ttu-id="419c0-117">手順 4: BizTalk FileAct および InterAct アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="419c0-117">Step 4: Install the BizTalk FileAct and InterAct adapters</span></span>  
  
1. <span data-ttu-id="419c0-118">実行、 **Setup.exe**管理者は、インストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="419c0-118">Run the **Setup.exe** as administrator to start the installation.</span></span>  
  
2.  <span data-ttu-id="419c0-119">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="419c0-119">Select **Install**.</span></span>  
  
3.  <span data-ttu-id="419c0-120">ユーザー名と組織名を入力し、**次**です。</span><span class="sxs-lookup"><span data-stu-id="419c0-120">Enter your user name and organization name, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="419c0-121">**受け入れる**使用許諾契約書。</span><span class="sxs-lookup"><span data-stu-id="419c0-121">**Accept** the license agreement.</span></span>
  
5.  <span data-ttu-id="419c0-122">**インストール オプション** ページで、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="419c0-122">On the **Installation Options** page, do one of the following:</span></span>  
  
    -   <span data-ttu-id="419c0-123">選択、**完了**FileAct のすべてのコンポーネントをインストールおよび InterAct アダプター オプション。</span><span class="sxs-lookup"><span data-stu-id="419c0-123">Select the **Complete** option to install all components of the FileAct and InterAct adapters.</span></span>  
  
    -   <span data-ttu-id="419c0-124">選択、**カスタム**オプションをインストールするコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="419c0-124">Select the **Custom** option to choose which components to install.</span></span>  
  
     <span data-ttu-id="419c0-125">インストール場所を確認または選択**参照**を別のインストール場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="419c0-125">Verify the installation location, or select **Browse** to select a different installation location.</span></span> <span data-ttu-id="419c0-126">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="419c0-126">Select **Next**.</span></span>  
  
6.  <span data-ttu-id="419c0-127">**概要**] ページで、[**インストール**コンポーネントの一覧をインストールします。</span><span class="sxs-lookup"><span data-stu-id="419c0-127">On the **Summary** page, select **Install** to install the listed components.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="419c0-128">ときに**構成ウィザードの実行**がオン (既定)、 **Microsoft BizTalk FileAct およびアダプター構成の対話**を選択するときに、ウィザードが自動的に実行されます **[完了]**.</span><span class="sxs-lookup"><span data-stu-id="419c0-128">When **Run Configuration Wizard** is selected (the default), the **Microsoft BizTalk FileAct and InterAct Adapter Configuration** wizard runs automatically when you select **Finish**.</span></span>  
  
7. <span data-ttu-id="419c0-129">インストールが完了したら、選択**完了**です。</span><span class="sxs-lookup"><span data-stu-id="419c0-129">When the installation completes, select **Finish**.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="419c0-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="419c0-130">Next steps</span></span>

[<span data-ttu-id="419c0-131">FileAct および InterAct アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="419c0-131">Configure the FileAct and InterAct adapter</span></span>](../../adapters-and-accelerators/fileact-interact/configure-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="419c0-132">サンプルの対話と FileAct メッセージ</span><span class="sxs-lookup"><span data-stu-id="419c0-132">Sample InterAct and FileAct messages</span></span>](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md)  
[<span data-ttu-id="419c0-133">アンインストールまたは修復 FileAct および InterAct アダプター</span><span class="sxs-lookup"><span data-stu-id="419c0-133">Uninstall or repair the FileAct and InterAct adapter</span></span>](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="419c0-134">既知の問題のインストールします。</span><span class="sxs-lookup"><span data-stu-id="419c0-134">Read the installation known issues</span></span>](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
  
## <a name="see-also"></a><span data-ttu-id="419c0-135">参照</span><span class="sxs-lookup"><span data-stu-id="419c0-135">See Also</span></span>  
[<span data-ttu-id="419c0-136">FileAct および InterAct アダプターの概要</span><span class="sxs-lookup"><span data-stu-id="419c0-136">Getting started with the FileAct and InterAct adapters</span></span>](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)  
[<span data-ttu-id="419c0-137">FileAct および InterAct アダプターのアーキテクチャを理解します。</span><span class="sxs-lookup"><span data-stu-id="419c0-137">Understanding FileAct and InterAct adapter architecture</span></span>](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)