---
title: "手順 2: 新しいプロジェクトの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, projects
- projects, creating
- message enrichment tutorial, projects
ms.assetid: 6e994845-53b8-4de8-a64f-32d36f7b5412
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4b296b01179b3ce52aef41dc246dbed2588c3e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-2-create-a-new-project"></a><span data-ttu-id="6027c-102">手順 2: 新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6027c-102">Step 2: Create a New Project</span></span>
<span data-ttu-id="6027c-103">使用して新しいソリューションをビルドするこの手順で、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="6027c-103">In this step, you build a new solution by using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] environment.</span></span> <span data-ttu-id="6027c-104">最初に、(データ型、セグメント、およびテーブルの値) の一般的なスキーマの 3 つ HL7 V2.2 スキーマを使用して、送信 HL7 メッセージに使用するスキーマなどを含む新しいプロジェクト (BTAHL7V22Common) を作成します。</span><span class="sxs-lookup"><span data-stu-id="6027c-104">First, you create a new project (BTAHL7V22Common) that contains the three common schemas (for data types, segments, and table values) that the HL7 V2.2 schemas use, including the schema that you will use for the outgoing HL7 message.</span></span> <span data-ttu-id="6027c-105">次に、別新しいプロジェクトをビルドする (BTAHL7V2XCommon) HL7 メッセージ (MSH_25_GLO_DEF) 内のヘッダーに使用される共通の標準的なスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6027c-105">Second, you build another new project (BTAHL7V2XCommon) that contains the common standard schema used for headers in HL7 messages (MSH_25_GLO_DEF).</span></span>  
  
### <a name="to-create-a-new-project"></a><span data-ttu-id="6027c-106">新しいプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="6027c-106">To create a new project</span></span>  
  
1.  <span data-ttu-id="6027c-107">開始**Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="6027c-107">Start **Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="6027c-108">**[ファイル]** メニューの **[新規作成]**をポイントし、 **[プロジェクト]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6027c-108">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="6027c-109">新しいプロジェクト ダイアログ ボックスで、展開、 **BizTalk プロジェクト**フォルダーをクリックして、 **BTAHL7Projects**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="6027c-109">In the New Project dialog box, expand the **BizTalk Projects** folder, and then click the **BTAHL7Projects** folder.</span></span>  
  
4.  <span data-ttu-id="6027c-110">**テンプレート** ウィンドウで、をクリックして**BTAHL7V22Common プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="6027c-110">In the **Templates** pane, click **BTAHL7V22Common Project**.</span></span>  
  
5.  <span data-ttu-id="6027c-111">**名前**フィールドに「 **BTAHL7V22Common**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="6027c-111">In the **Name** field, type **BTAHL7V22Common** as the project name.</span></span>  
  
6.  <span data-ttu-id="6027c-112">**場所**フィールドに「 *\<ドライブ\>***: \Tutorial**クリックして、パスとして**OK**を開くには新しいプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6027c-112">In the **Location** field, type *\<drive\>***:\Tutorial** as the path, and then click **OK** to open the new project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6027c-113">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、3 つの一般的なスキーマを新しいプロジェクトをソリューション エクスプ ローラーに追加します。</span><span class="sxs-lookup"><span data-stu-id="6027c-113">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) adds a new project to Solution Explorer with the three common schemas:</span></span>  
  
    -   <span data-ttu-id="6027c-114">datatypes_22.xsd</span><span class="sxs-lookup"><span data-stu-id="6027c-114">datatypes_22.xsd</span></span>  
  
    -   <span data-ttu-id="6027c-115">segments_22.xsd</span><span class="sxs-lookup"><span data-stu-id="6027c-115">segments_22.xsd</span></span>  
  
    -   <span data-ttu-id="6027c-116">tablevalues_22.xsd</span><span class="sxs-lookup"><span data-stu-id="6027c-116">tablevalues_22.xsd</span></span>  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="6027c-117">ファイル、プロジェクト フォルダーを作成して、 \<*ドライブ*\>: \Tutorial\BTAHL7V22Common フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="6027c-117"> creates the project folder and files in the \<*drive*\>:\Tutorial\BTAHL7V22Common folder.</span></span>  
  
7.  <span data-ttu-id="6027c-118">**[ファイル]** メニューの **[新規作成]**をポイントし、 **[プロジェクト]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6027c-118">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
8.  <span data-ttu-id="6027c-119">新しいプロジェクト ダイアログ ボックスで、展開、 **BizTalk プロジェクト**フォルダーをクリックして、 **BTAHL7Projects**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="6027c-119">In the New Project dialog box, expand the **BizTalk Projects** folder, and then click the **BTAHL7Projects** folder.</span></span>  
  
9. <span data-ttu-id="6027c-120">**テンプレート** ウィンドウで、をクリックして**BTAHL7V2XCommon プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="6027c-120">In the **Templates** pane, click **BTAHL7V2XCommon Project**.</span></span>  
  
10. <span data-ttu-id="6027c-121">**名前**フィールドに「 **BTAHL7V2XCommon**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="6027c-121">In the **Name** field, type **BTAHL7V2XCommon** as the project name.</span></span>  
  
11. <span data-ttu-id="6027c-122">**場所**フィールドに「 *\<ドライブ\>***: \Tutorial**パスとして。</span><span class="sxs-lookup"><span data-stu-id="6027c-122">In the **Location** field, type *\<drive\>***:\Tutorial** as the path.</span></span>  
  
12. <span data-ttu-id="6027c-123">**ソリューション**フィールドを選択**ソリューションに追加**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6027c-123">In the **Solution** field, select **Add to Solution**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6027c-124">次のスキーマで、ソリューション エクスプ ローラーに新しいプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="6027c-124"> adds a new project to Solution Explorer with the following schemas:</span></span>  
  
    -   <span data-ttu-id="6027c-125">ACK_24_GLO_DEF.xsd</span><span class="sxs-lookup"><span data-stu-id="6027c-125">ACK_24_GLO_DEF.xsd</span></span>  
  
    -   <span data-ttu-id="6027c-126">ACK_25_GLO_DEF.xsd</span><span class="sxs-lookup"><span data-stu-id="6027c-126">ACK_25_GLO_DEF.xsd</span></span>  
  
    -   <span data-ttu-id="6027c-127">MSH_25_GLO_DEF.xsd</span><span class="sxs-lookup"><span data-stu-id="6027c-127">MSH_25_GLO_DEF.xsd</span></span>  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="6027c-128">ファイル、プロジェクト フォルダーを作成して、 **\<ドライブ\>: \Tutorial\BTAHL7V22Common\BTAHL72XCommon**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="6027c-128"> creates the project folder and files in the **\<drive\>:\Tutorial\BTAHL7V22Common\BTAHL72XCommon** folder.</span></span>  
  
 <span data-ttu-id="6027c-129">進みます[手順 3: アセンブリに厳密な名前を割り当てます](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)です。</span><span class="sxs-lookup"><span data-stu-id="6027c-129">Proceed to [Step 3: Assign a Strong Name to the Assembly](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6027c-130">参照</span><span class="sxs-lookup"><span data-stu-id="6027c-130">See Also</span></span>  
 [<span data-ttu-id="6027c-131">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="6027c-131">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)