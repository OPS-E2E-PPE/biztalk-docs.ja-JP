---
title: '手順 1: 追加のヘッダーと受信確認スキーマ |Microsoft ドキュメント'
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
ms.openlocfilehash: f79778801b1ca70d4e8356a24886c792fe447e33
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005339"
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a><span data-ttu-id="30e8a-102">手順 1: ヘッダーと受信確認スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="30e8a-102">Step 1: Add Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="30e8a-103">この手順では、BTAHL72XCommon プロジェクト テンプレートに基づく新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="30e8a-103">In this step, you create a new project based on the BTAHL72XCommon Project template.</span></span> <span data-ttu-id="30e8a-104">このテンプレートには、メッセージ ヘッダー (MSH_25_GLO_DEF.xsd) と受信確認 (ACK_24_GLO_DEF.xsd) の 3 つの一般的なスキーマが含まれています (ACK_25_GLO_DEF.xsd) とします。</span><span class="sxs-lookup"><span data-stu-id="30e8a-104">This template contains the three common schemas for message headers (MSH_25_GLO_DEF.xsd) and acknowledgments (ACK_24_GLO_DEF.xsd) and (ACK_25_GLO_DEF.xsd).</span></span> <span data-ttu-id="30e8a-105">そのためのプロジェクトでこれらのスキーマを含める必要がありますを BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ビルドや、メッセージ ヘッダーと受信確認を正しく検証します。</span><span class="sxs-lookup"><span data-stu-id="30e8a-105">You must include these schemas in a project so that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) builds and/or validates the message headers and acknowledgments correctly.</span></span> <span data-ttu-id="30e8a-106">このプロセスは、すべてのスキーマ バージョンの間で共通[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-106">This process is common across all schema versions of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span></span>  
  
 <span data-ttu-id="30e8a-107">アセンブリに割り当てること、およびアセンブリを展開しても強力なキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="30e8a-107">You also create a strong key, assign it to the assembly, and then deploy the assembly.</span></span> <span data-ttu-id="30e8a-108">強力なキーは、アセンブリのセキュリティと id を提供し、展開に必要なです。</span><span class="sxs-lookup"><span data-stu-id="30e8a-108">The strong key provides security and identity to the assembly, and is necessary for deployment.</span></span> <span data-ttu-id="30e8a-109">アセンブリを展開するときに、構成データベース (BizTalk 管理データベースとも呼ばれます) と、グローバル アセンブリ キャッシュ (GAC) に格納されます。</span><span class="sxs-lookup"><span data-stu-id="30e8a-109">When you deploy the assembly, it is stored in the Configuration database (also known as the BizTalk Management database) and the global assembly cache (GAC).</span></span>  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a><span data-ttu-id="30e8a-110">プロジェクトを作成し、ヘッダーと受信確認のスキーマを追加するには</span><span class="sxs-lookup"><span data-stu-id="30e8a-110">To create the project and add header and acknowledgment schemas</span></span>  
  
1.  <span data-ttu-id="30e8a-111">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-111">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="30e8a-112">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、順にクリック**BTAHL7Projects**です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-112">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="30e8a-113">**テンプレート**一覧で、クリックして**BTAHL7V2XCommon プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-113">In the **Templates** list, click **BTAHL7V2XCommon Project**.</span></span>  
  
4.  <span data-ttu-id="30e8a-114">**名前**ボックスに、入力**BTAHL7V2XCommon**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="30e8a-114">In the **Name** box, type **BTAHL7V2XCommon** as the project name.</span></span>  
  
5.  <span data-ttu-id="30e8a-115">**場所**ボックスを参照 **\<** *ドライブ***:\>\Batching チュートリアル**です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-115">In the **Location** box, browse to **\<***drive***:\>\Batching Tutorial**.</span></span>  
  
6.  <span data-ttu-id="30e8a-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30e8a-116">Click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30e8a-117">ソリューション エクスプ ローラーで、3 つのスキーマ (MSH_25_GLO_DEF.xsd、ACK_24_GLO_DEF.xsd、および ACK_25_GLO_DEF.xsd) は、プロジェクトに含まれます。</span><span class="sxs-lookup"><span data-stu-id="30e8a-117">In Solution Explorer, three schemas (MSH_25_GLO_DEF.xsd, ACK_24_GLO_DEF.xsd, and ACK_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="30e8a-118">アセンブリに厳密なキーを割り当てるし、展開するには</span><span class="sxs-lookup"><span data-stu-id="30e8a-118">To assign a strong key to the assembly and deploy</span></span>  
  
1.  <span data-ttu-id="30e8a-119">開いている**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-119">Open **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="30e8a-120">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、参照、  **\<** *ドライブ***\>: \Batching チュートリアル**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="30e8a-120">On the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, browse to the **\<***drive***\>:\Batching Tutorial** folder.</span></span>  
  
3.  <span data-ttu-id="30e8a-121">コマンド プロンプトで次のように入力します。 **sn – k key.snk**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="30e8a-121">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="30e8a-122">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="30e8a-122">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="30e8a-123">使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="30e8a-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4.  <span data-ttu-id="30e8a-124">ソリューション エクスプ ローラーで右クリック**BTAHL7V2Xcommon プロジェクト**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-124">In Solution Explorer, right-click **BTAHL7V2Xcommon Project**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="30e8a-125">**BTAHL7V2XCommon プロジェクトのプロパティ ページ**ダイアログ ボックスで、をクリックして**署名**です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-125">In the **BTAHL7V2XCommon Project Property Page** dialog box, click **Signing**.</span></span>  
  
6.  <span data-ttu-id="30e8a-126">確認**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="30e8a-126">Check **Sign the assembly** check box.</span></span>  
  
7.  <span data-ttu-id="30e8a-127">**厳密な名前を選択して**キー ファイルのドロップダウン リストを**\<を参照しています...\>**.</span><span class="sxs-lookup"><span data-stu-id="30e8a-127">In **Choose a Strong name** key file drop down list select **\<Browse…\>**.</span></span>  
  
8.  <span data-ttu-id="30e8a-128">参照\<*ドライブ*\>: \Batching チュートリアルでは、選択**key.snk**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-128">Browse to \<*drive*\>:\Batching Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="30e8a-129">BTAHL7V2XCommon プロジェクト プロパティ ページ ウィンドウで、をクリックして**OK**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="30e8a-129">In the BTAHL7V2XCommon Project Property Pages window, click **OK** to save your changes.</span></span>  
  
10. <span data-ttu-id="30e8a-130">ソリューション エクスプ ローラーで右クリック**BTAHL7V2Xcommon プロジェクト**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-130">In Solution Explorer, right-click **BTAHL7V2Xcommon Project**, and then click **Deploy**.</span></span> <span data-ttu-id="30e8a-131">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="30e8a-131">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="30e8a-132">使用して、正しい配置メッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]展開のトラブルシューティングにします。</span><span class="sxs-lookup"><span data-stu-id="30e8a-132">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
 <span data-ttu-id="30e8a-133">進みます[手順 2: v2.3.1 の一般的なスキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)です。</span><span class="sxs-lookup"><span data-stu-id="30e8a-133">Proceed to [Step 2: Add Common Schemas for v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md).</span></span>