---
title: A4SWIFT エンベロープ スキーマの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, envelope schemas
- A4SWIFT, deploying envelope schemas
- envelope schemas
- schemas, envelope schemas
ms.assetid: 6440608c-d30d-4d82-827a-8a4b2738db85
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae07b6b957f608e89c3ae65802d6627440201a65
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004147"
---
# <a name="deploying-a4swift-envelope-schemas"></a><span data-ttu-id="c31d5-102">A4SWIFT エンベロープ スキーマの展開</span><span class="sxs-lookup"><span data-stu-id="c31d5-102">Deploying A4SWIFT Envelope Schemas</span></span>
<span data-ttu-id="c31d5-103">Message Repair and New Submission を設定するたびに、プロジェクトのスキーマでエンベロープ スキーマを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c31d5-103">You must include envelope schemas in schema projects whenever you set up Message Repair and New Submission.</span></span> <span data-ttu-id="c31d5-104">エンベロープ スキーマで、EnvelopeMT103.xsd などが MRSR サイトへの書き込みに必要です。</span><span class="sxs-lookup"><span data-stu-id="c31d5-104">An envelope schema, such as EnvelopeMT103.xsd, is required to write to MRSR site.</span></span>  
  
 <span data-ttu-id="c31d5-105">**概要**</span><span class="sxs-lookup"><span data-stu-id="c31d5-105">**Summary**</span></span>  
  
 <span data-ttu-id="c31d5-106">ようエンベロープ スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-106">Add envelope schemas to your project, as follows:</span></span>  
  
- <span data-ttu-id="c31d5-107">Visual Studio で、メッセージ スキーマを含むプロジェクトに、各メッセージ スキーマをエンベロープ スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-107">In Visual Studio, to the project that contains your message schemas, add an envelope schema for each message schema.</span></span>  
  
- <span data-ttu-id="c31d5-108">1 つまたは複数のエンベロープ スキーマを含む任意のプロジェクトに RuntimeSchemas.dll への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-108">Add a reference to RuntimeSchemas.dll to any project that contains one or more envelope schemas.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="c31d5-109">RuntimeSchemas.dll への参照を追加することが必要な[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Message Repair and New Submission をプロジェクトにエンベロープ スキーマを追加した場合にのみのプロジェクトします。</span><span class="sxs-lookup"><span data-stu-id="c31d5-109">Adding a reference to RuntimeSchemas.dll is required for an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] project only when you have added an envelope schema for Message Repair and New Submission to the project.</span></span>  
  
- <span data-ttu-id="c31d5-110">未解析メッセージのエンベロープ スキーマ (EnvelopeUnparsedMessage.xsd) をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-110">Add the Unparsed Message envelope schema (EnvelopeUnparsedMessage.xsd) to the project.</span></span>  
  
### <a name="to-add-a-swift-envelope-schema"></a><span data-ttu-id="c31d5-111">SWIFT エンベロープ スキーマに追加するには</span><span class="sxs-lookup"><span data-stu-id="c31d5-111">To add a SWIFT envelope schema</span></span>  
  
1.  <span data-ttu-id="c31d5-112">ソリューション エクスプ ローラーの Visual Studio でスキーマ プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c31d5-112">In Solution Explorer of Visual Studio, open your schemas project.</span></span>  
  
2.  <span data-ttu-id="c31d5-113">右クリック**参照**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-113">Right-click **References**, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="c31d5-114">[参照の追加] ダイアログ ボックスで、**参照**タグ。</span><span class="sxs-lookup"><span data-stu-id="c31d5-114">In the Add Reference dialog box, click the **Browse** tag.</span></span>  
  
4.  <span data-ttu-id="c31d5-115">コンポーネントの選択 ダイアログ ボックスで、開く、**検索**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="c31d5-115">In the Select Component dialog box, open the **Look in** drop-down list.</span></span> <span data-ttu-id="c31d5-116">移動 ***\<ドライブ\>*:\Program \microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\Assemblies**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-116">Move to ***\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\Assemblies**.</span></span> <span data-ttu-id="c31d5-117">選択**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**クリックして、アセンブリの一覧から**追加**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-117">Select **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** from the list of assemblies, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="c31d5-118">**参照の追加**ダイアログ ボックスで、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-118">In the **Add Reference** dialog box, click **OK**.</span></span>  
  
6.  <span data-ttu-id="c31d5-119">プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-119">Right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
7.  <span data-ttu-id="c31d5-120">追加で既存の項目 ダイアログ ボックスで、**検索**ドロップダウン ボックスに移動**\<ドライブ\>: \Program Files\ Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Categoryn\MTxxx**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-120">In the Add Existing Item dialog box, in the **Look in** drop-down box, move to **\<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Categoryn\MTxxx**.</span></span> <span data-ttu-id="c31d5-121">たとえば、エンベロープ スキーマを選択**EnvelopeMT103.xsd**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-121">Select the envelope schema, for example, **EnvelopeMT103.xsd**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="c31d5-122">追加で既存の項目 ダイアログ ボックスで、**検索**ドロップダウン ボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-122">In the Add Existing Item dialog box, in the **Look in** drop-down box, move to.</span></span> <span data-ttu-id="c31d5-123">エンベロープ スキーマ、たとえば、EnvelopeMT103.xsd を選択し、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c31d5-123">Select the envelope schema, for example, EnvelopeMT103.xsd, and then click Add.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c31d5-124">A4SWIFT は、ソリューション エクスプ ローラーで示すように、プロジェクトのエンベロープ スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-124">A4SWIFT adds the envelope schema for your project, as shown in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="c31d5-125">ソリューション エクスプ ローラーでプロジェクトを右クリックして**追加**、 をクリックし、**既存項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-125">In Solution Explorer, right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
9. <span data-ttu-id="c31d5-126">[既存項目の追加] ダイアログ ボックスで、Message Repair and New Submission 機能を使用する場合、**検索**ドロップダウン ボックスに移動 **\<*ドライブ*\>: \Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Unparsed メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-126">If using the Message Repair and New Submission feature, in the Add Existing Item dialog box, in the **Look in** drop-down box, move to **\<*drive*\>:\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Unparsed Message**.</span></span> <span data-ttu-id="c31d5-127">選択**EnvelopeUnparsedMessage.xsd**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-127">Select **EnvelopeUnparsedMessage.xsd**, and then click **Add**.</span></span>  
  
10. <span data-ttu-id="c31d5-128">ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-128">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
11. <span data-ttu-id="c31d5-129">ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="c31d5-129">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>