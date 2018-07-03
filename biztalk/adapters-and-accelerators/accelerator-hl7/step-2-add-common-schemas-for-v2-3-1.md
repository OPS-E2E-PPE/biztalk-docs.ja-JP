---
title: '手順 2: v2.3.1 の一般的なスキーマの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da98fe6c-4776-4cb8-8454-af3128dea4ab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b07419b50d02d1f810dffbd7417533e844a3ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994163"
---
# <a name="step-2-add-common-schemas-for-v231"></a><span data-ttu-id="19e5b-102">手順 2: v2.3.1 の一般的なスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-102">Step 2: Add Common Schemas for v2.3.1</span></span>
<span data-ttu-id="19e5b-103">この手順では、BTAHL7231Common プロジェクト テンプレートに基づいて新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-103">In this step, you create a new project based on the BTAHL7231Common Project template.</span></span> <span data-ttu-id="19e5b-104">このテンプレートが含まれています (データ型、セグメント、およびテーブルの値) の 3 つの一般的なスキーマには Microsoft BizTalk Accelerator には用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) v2.3.1 メッセージ インスタンスの検証に使用します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-104">This template contains the three common schemas (for data types, segments, and table values) that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses to validate v2.3.1 message instances.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="19e5b-105"> 受信バッチの個々 のメッセージに使用するスキーマを含む、HL7 v2.3.1 スキーマと共にこれらの一般的なスキーマを使用して (ADT ^ A03)。</span><span class="sxs-lookup"><span data-stu-id="19e5b-105"> uses these common schemas in conjunction with the HL7 v2.3.1 schemas, including the schema that you will use for the individual messages in the incoming batch (ADT^A03).</span></span>  
  
 <span data-ttu-id="19e5b-106">ステップの最後に、アセンブリに厳密なキーを割り当てるし、デプロイします。</span><span class="sxs-lookup"><span data-stu-id="19e5b-106">At the end of the step, you assign a strong key to the assembly and deploy.</span></span> <span data-ttu-id="19e5b-107">2 番目の強力なキーを作成する必要はありません。作成した厳密なキーを使用して[手順 1: ヘッダーの追加と確認スキーマ](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-107">You do not have to create a second strong key; you can use the strong key that you created in [Step 1: Add Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md).</span></span>  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a><span data-ttu-id="19e5b-108">V2.3.1 の一般的なスキーマを追加し、アセンブリを展開するには</span><span class="sxs-lookup"><span data-stu-id="19e5b-108">To add v2.3.1 common schemas and deploy the assembly</span></span>  
  
1. <span data-ttu-id="19e5b-109">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-109">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="19e5b-110">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-110">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="19e5b-111">**テンプレート**セクションで、 **BTAHL7V231Common プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-111">In the **Templates** section, select **BTAHL7V231Common Project**.</span></span>  
  
4. <span data-ttu-id="19e5b-112">**名前**ボックスに、入力**BTAHL7V231Common プロジェクト**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="19e5b-112">In the **Name** box, enter **BTAHL7V231Common Project** as the project name.</span></span>  
  
5. <span data-ttu-id="19e5b-113">**ソリューション**ボックスで、**ソリューションに追加**します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-113">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6. <span data-ttu-id="19e5b-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19e5b-114">Click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="19e5b-115">ソリューション エクスプ ローラーでプロジェクトの 3 つのスキーマ (datatypes_231.xsd、segments_231.xsd、および tablevalues_231.xsd) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="19e5b-115">In Solution Explorer, three schemas (datatypes_231.xsd, segments_231.xsd, and tablevalues_231.xsd) are included in the project.</span></span>  
  
7. <span data-ttu-id="19e5b-116">ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Common プロジェクト**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-116">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Properties**.</span></span>  
  
8. <span data-ttu-id="19e5b-117">BTAHL7V231Common プロパティ ページ ダイアログ ボックスで、をクリックして**署名**します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-117">On the BTAHL7V231Common Property Pages dialog box, click **Signing**.</span></span>  
  
9. <span data-ttu-id="19e5b-118">確認**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="19e5b-118">Check **Sign the assembly** check box.</span></span>  
  
10. <span data-ttu-id="19e5b-119">厳密な名前キー ファイルの選択 でドロップダウン リストを選択します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-119">In Choose a strong name key file drop down list select.</span></span>  
  
11. <span data-ttu-id="19e5b-120">参照 **: \Batching チュートリアル**を選択します**key.snk**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-120">Browse to **:\Batching Tutorial**, select **key.snk**, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="19e5b-121">右クリック**BTAHL7V231Common**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-121">Right-click **BTAHL7V231Common**, and then click **Deploy**.</span></span> <span data-ttu-id="19e5b-122">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-122">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="19e5b-123">適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="19e5b-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
    <span data-ttu-id="19e5b-124">続行する[手順 3: トリガー イベント (メッセージ) スキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)します。</span><span class="sxs-lookup"><span data-stu-id="19e5b-124">Proceed to [Step 3: Add a Trigger Event (Message) Schema](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span></span>