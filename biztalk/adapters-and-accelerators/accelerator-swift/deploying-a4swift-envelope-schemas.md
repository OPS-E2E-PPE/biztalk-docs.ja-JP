---
title: "A4SWIFT エンベロープ スキーマを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, envelope schemas
- A4SWIFT, deploying envelope schemas
- envelope schemas
- schemas, envelope schemas
ms.assetid: 6440608c-d30d-4d82-827a-8a4b2738db85
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8811f1dd056ca5a4ea4582d593af30e2ffc879f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="deploying-a4swift-envelope-schemas"></a><span data-ttu-id="44f8b-102">A4SWIFT エンベロープ スキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="44f8b-102">Deploying A4SWIFT Envelope Schemas</span></span>
<span data-ttu-id="44f8b-103">Message Repair and New Submission を設定するときに、プロジェクトのスキーマでエンベロープ スキーマを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f8b-103">You must include envelope schemas in schema projects whenever you set up Message Repair and New Submission.</span></span> <span data-ttu-id="44f8b-104">エンベロープ スキーマで、EnvelopeMT103.xsd などが MRSR サイトへの書き込みに必要です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-104">An envelope schema, such as EnvelopeMT103.xsd, is required to write to MRSR site.</span></span>  
  
 <span data-ttu-id="44f8b-105">**概要**</span><span class="sxs-lookup"><span data-stu-id="44f8b-105">**Summary**</span></span>  
  
 <span data-ttu-id="44f8b-106">ようエンベロープ スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="44f8b-106">Add envelope schemas to your project, as follows:</span></span>  
  
-   <span data-ttu-id="44f8b-107">Visual Studio で、メッセージ スキーマを含むプロジェクトに、各メッセージ スキーマをエンベロープ スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="44f8b-107">In Visual Studio, to the project that contains your message schemas, add an envelope schema for each message schema.</span></span>  
  
-   <span data-ttu-id="44f8b-108">1 つまたは複数のエンベロープ スキーマを含むすべてのプロジェクトに RuntimeSchemas.dll への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="44f8b-108">Add a reference to RuntimeSchemas.dll to any project that contains one or more envelope schemas.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44f8b-109">RuntimeSchemas.dll への参照を追加することが必要な[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]プロジェクトの Message Repair and New Submission プロジェクトへのエンベロープ スキーマを追加した場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="44f8b-109">Adding a reference to RuntimeSchemas.dll is required for an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] project only when you have added an envelope schema for Message Repair and New Submission to the project.</span></span>  
  
-   <span data-ttu-id="44f8b-110">未解析のメッセージのエンベロープ スキーマ (EnvelopeUnparsedMessage.xsd) をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="44f8b-110">Add the Unparsed Message envelope schema (EnvelopeUnparsedMessage.xsd) to the project.</span></span>  
  
### <a name="to-add-a-swift-envelope-schema"></a><span data-ttu-id="44f8b-111">SWIFT エンベロープ スキーマに追加するには</span><span class="sxs-lookup"><span data-stu-id="44f8b-111">To add a SWIFT envelope schema</span></span>  
  
1.  <span data-ttu-id="44f8b-112">ソリューション エクスプ ローラーの Visual Studio で、スキーマ プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="44f8b-112">In Solution Explorer of Visual Studio, open your schemas project.</span></span>  
  
2.  <span data-ttu-id="44f8b-113">右クリック**参照**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-113">Right-click **References**, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="44f8b-114">[参照の追加] ダイアログ ボックス、**参照**タグ。</span><span class="sxs-lookup"><span data-stu-id="44f8b-114">In the Add Reference dialog box, click the **Browse** tag.</span></span>  
  
4.  <span data-ttu-id="44f8b-115">コンポーネントの選択 ダイアログ ボックスで、開く、**ファイルの場所**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="44f8b-115">In the Select Component dialog box, open the **Look in** drop-down list.</span></span> <span data-ttu-id="44f8b-116">移動 ***\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ Pack\Assemblies**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-116">Move to ***\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\Assemblies**.</span></span> <span data-ttu-id="44f8b-117">選択**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**クリックして、アセンブリの一覧から**追加**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-117">Select **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** from the list of assemblies, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="44f8b-118">**参照の追加**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-118">In the **Add Reference** dialog box, click **OK**.</span></span>  
  
6.  <span data-ttu-id="44f8b-119">プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-119">Right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
7.  <span data-ttu-id="44f8b-120">追加で既存の項目 ダイアログ ボックスで、**ファイルの場所**ドロップダウン ボックスに移動**\<ドライブ\>: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Categoryn\MTxxx**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-120">In the Add Existing Item dialog box, in the **Look in** drop-down box, move to **\<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Categoryn\MTxxx**.</span></span> <span data-ttu-id="44f8b-121">たとえば、エンベロープ スキーマを選択**EnvelopeMT103.xsd**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-121">Select the envelope schema, for example, **EnvelopeMT103.xsd**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="44f8b-122">追加で既存の項目 ダイアログ ボックスで、**ファイルの場所**ドロップダウン ボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="44f8b-122">In the Add Existing Item dialog box, in the **Look in** drop-down box, move to.</span></span> <span data-ttu-id="44f8b-123">エンベロープ スキーマ、たとえば、EnvelopeMT103.xsd を選択し、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44f8b-123">Select the envelope schema, for example, EnvelopeMT103.xsd, and then click Add.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44f8b-124">ソリューション エクスプ ローラーで示すように、A4SWIFT は、プロジェクトのエンベロープ スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="44f8b-124">A4SWIFT adds the envelope schema for your project, as shown in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="44f8b-125">ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**、クリックして**既存項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-125">In Solution Explorer, right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
9. <span data-ttu-id="44f8b-126">既存項目の追加 ダイアログ ボックスで、Message Repair and New Submission の機能を使用する場合、**ファイルの場所**ドロップダウン ボックスに移動  **\<*ドライブ*\>: \Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Unparsed メッセージ * *。</span><span class="sxs-lookup"><span data-stu-id="44f8b-126">If using the Message Repair and New Submission feature, in the Add Existing Item dialog box, in the **Look in** drop-down box, move to **\<*drive*\>:\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Unparsed Message**.</span></span> <span data-ttu-id="44f8b-127">選択**EnvelopeUnparsedMessage.xsd**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-127">Select **EnvelopeUnparsedMessage.xsd**, and then click **Add**.</span></span>  
  
10. <span data-ttu-id="44f8b-128">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-128">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
11. <span data-ttu-id="44f8b-129">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="44f8b-129">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>