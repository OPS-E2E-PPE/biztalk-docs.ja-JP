---
title: 手順 1:ヘッダーと確認スキーマの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 808132bf-02e7-4ff4-b914-9fae5d27e5fd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87e470abd9e8e8d71f657d789089caefa40dc1e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289042"
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a><span data-ttu-id="2f7b3-102">手順 1:ヘッダーと確認スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-102">Step 1: Add Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="2f7b3-103">この手順では、BTAHL72XCommon プロジェクト テンプレートに基づいて新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-103">In this step, you create a new project based on the BTAHL72XCommon Project template.</span></span> <span data-ttu-id="2f7b3-104">このテンプレートには、メッセージ ヘッダー (MSH_25_GLO_DEF.xsd) および受信確認 (ACK_24_GLO_DEF.xsd) の 3 つの一般的なスキーマが含まれています (ACK_25_GLO_DEF.xsd) とします。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-104">This template contains the three common schemas for message headers (MSH_25_GLO_DEF.xsd) and acknowledgments (ACK_24_GLO_DEF.xsd) and (ACK_25_GLO_DEF.xsd).</span></span> <span data-ttu-id="2f7b3-105">そのためのプロジェクトでこれらのスキーマを含める必要がありますを BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ビルドまたはメッセージ ヘッダーと受信確認を正しく検証します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-105">You must include these schemas in a project so that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) builds and/or validates the message headers and acknowledgments correctly.</span></span> <span data-ttu-id="2f7b3-106">このプロセスは、すべてのスキーマ バージョンの間で共通[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-106">This process is common across all schema versions of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span></span>  
  
 <span data-ttu-id="2f7b3-107">アセンブリに割り当てること、およびアセンブリを展開しても強力なキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-107">You also create a strong key, assign it to the assembly, and then deploy the assembly.</span></span> <span data-ttu-id="2f7b3-108">強力なキーでは、アセンブリのセキュリティと id を提供します、展開に必要です。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-108">The strong key provides security and identity to the assembly, and is necessary for deployment.</span></span> <span data-ttu-id="2f7b3-109">アセンブリを展開するときに、構成データベース (BizTalk 管理データベースとも呼ばれます) と、グローバル アセンブリ キャッシュ (GAC) に格納されます。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-109">When you deploy the assembly, it is stored in the Configuration database (also known as the BizTalk Management database) and the global assembly cache (GAC).</span></span>  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a><span data-ttu-id="2f7b3-110">プロジェクトを作成し、ヘッダーと受信確認のスキーマを追加するには</span><span class="sxs-lookup"><span data-stu-id="2f7b3-110">To create the project and add header and acknowledgment schemas</span></span>  
  
1. <span data-ttu-id="2f7b3-111">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-111">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="2f7b3-112">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、 をクリックし、 **BTAHL7Projects**します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-112">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="2f7b3-113">**テンプレート**一覧で、 **BTAHL7V2XCommon プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-113">In the **Templates** list, click **BTAHL7V2XCommon Project**.</span></span>  
  
4. <span data-ttu-id="2f7b3-114">**名前**ボックスに「 **BTAHL7V2XCommon**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-114">In the **Name** box, type **BTAHL7V2XCommon** as the project name.</span></span>  
  
5. <span data-ttu-id="2f7b3-115">**場所**ボックスを参照する **\<** <em>ドライブ</em> **:\>\Batching チュートリアル**します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-115">In the **Location** box, browse to **\<**<em>drive</em>**:\>\Batching Tutorial**.</span></span>  
  
6. <span data-ttu-id="2f7b3-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-116">Click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f7b3-117">ソリューション エクスプ ローラーでプロジェクトの 3 つのスキーマ (MSH_25_GLO_DEF.xsd、ACK_24_GLO_DEF.xsd、および ACK_25_GLO_DEF.xsd) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-117">In Solution Explorer, three schemas (MSH_25_GLO_DEF.xsd, ACK_24_GLO_DEF.xsd, and ACK_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="2f7b3-118">アセンブリに厳密なキーを割り当てるし、デプロイするには</span><span class="sxs-lookup"><span data-stu-id="2f7b3-118">To assign a strong key to the assembly and deploy</span></span>  
  
1. <span data-ttu-id="2f7b3-119">開いている**Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-119">Open **Visual Studio Command Prompt**.</span></span>  
  
2. <span data-ttu-id="2f7b3-120">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、参照、 **\<** <em>ドライブ</em> **\>: \Batching チュートリアル**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-120">On the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, browse to the **\<**<em>drive</em>**\>:\Batching Tutorial** folder.</span></span>  
  
3. <span data-ttu-id="2f7b3-121">コマンド プロンプトで「 **sn – k key.snk**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-121">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="2f7b3-122">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-122">Ensure that a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2f7b3-123">適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4. <span data-ttu-id="2f7b3-124">ソリューション エクスプ ローラーで右クリックして**BTAHL7V2Xcommon プロジェクト**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-124">In Solution Explorer, right-click **BTAHL7V2Xcommon Project**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="2f7b3-125">**BTAHL7V2XCommon プロジェクトのプロパティ ページ**ダイアログ ボックスで、をクリックして**署名**します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-125">In the **BTAHL7V2XCommon Project Property Page** dialog box, click **Signing**.</span></span>  
  
6. <span data-ttu-id="2f7b3-126">確認**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-126">Check **Sign the assembly** check box.</span></span>  
  
7. <span data-ttu-id="2f7b3-127">**厳密な名前を選択**キー ファイルのドロップダウン リストを **\<を参照しています\>** .</span><span class="sxs-lookup"><span data-stu-id="2f7b3-127">In **Choose a Strong name** key file drop down list select **\<Browse…\>**.</span></span>  
  
8. <span data-ttu-id="2f7b3-128">参照\<*ドライブ*\>: \Batching チュートリアルでは、選択**key.snk**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-128">Browse to \<*drive*\>:\Batching Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="2f7b3-129">BTAHL7V2XCommon プロジェクト プロパティ ページ ウィンドウで、次のようにクリックします。 **OK** 、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-129">In the BTAHL7V2XCommon Project Property Pages window, click **OK** to save your changes.</span></span>  
  
10. <span data-ttu-id="2f7b3-130">ソリューション エクスプ ローラーで右クリックして**BTAHL7V2Xcommon プロジェクト**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-130">In Solution Explorer, right-click **BTAHL7V2Xcommon Project**, and then click **Deploy**.</span></span> <span data-ttu-id="2f7b3-131">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-131">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f7b3-132">デプロイの適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]デプロイのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-132">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
    <span data-ttu-id="2f7b3-133">続行する[手順 2。V2.3.1 の一般的なスキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)します。</span><span class="sxs-lookup"><span data-stu-id="2f7b3-133">Proceed to [Step 2: Add Common Schemas for v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md).</span></span>