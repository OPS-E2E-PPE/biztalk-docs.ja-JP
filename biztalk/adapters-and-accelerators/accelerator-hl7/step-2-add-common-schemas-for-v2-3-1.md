---
title: '手順 2: v2.3.1 の一般的なスキーマを追加する |Microsoft ドキュメント'
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
ms.openlocfilehash: ba84c9f45c477aefe7615eca906c40014b06bd04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206514"
---
# <a name="step-2-add-common-schemas-for-v231"></a><span data-ttu-id="1f8d0-102">手順 2: v2.3.1 の一般的なスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-102">Step 2: Add Common Schemas for v2.3.1</span></span>
<span data-ttu-id="1f8d0-103">この手順では、BTAHL7231Common プロジェクト テンプレートに基づく新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-103">In this step, you create a new project based on the BTAHL7231Common Project template.</span></span> <span data-ttu-id="1f8d0-104">このテンプレートに含まれます (データ型、セグメント、およびテーブルの値) の 3 つの一般的なスキーマを[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) v2.3.1 メッセージ インスタンスの検証に使用します。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-104">This template contains the three common schemas (for data types, segments, and table values) that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses to validate v2.3.1 message instances.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1f8d0-105">これらの共通スキーマを使用して、個々 のメッセージの受信のバッチで使用するスキーマを含め、HL7 v2.3.1 スキーマと共に (ADT ^ A03)。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-105"> uses these common schemas in conjunction with the HL7 v2.3.1 schemas, including the schema that you will use for the individual messages in the incoming batch (ADT^A03).</span></span>  
  
 <span data-ttu-id="1f8d0-106">ステップの最後に、アセンブリに厳密なキーを割り当てるし、展開します。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-106">At the end of the step, you assign a strong key to the assembly and deploy.</span></span> <span data-ttu-id="1f8d0-107">2 番目の強力なキー; を作成する必要はありません。作成した厳密なキーを使用する[手順 1: ヘッダーの追加および確認スキーマ](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-107">You do not have to create a second strong key; you can use the strong key that you created in [Step 1: Add Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md).</span></span>  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a><span data-ttu-id="1f8d0-108">V2.3.1 一般的なスキーマを追加してアセンブリを展開するには</span><span class="sxs-lookup"><span data-stu-id="1f8d0-108">To add v2.3.1 common schemas and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="1f8d0-109">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-109">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="1f8d0-110">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**です。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-110">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="1f8d0-111">**テンプレート**セクションで、 **BTAHL7V231Common プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-111">In the **Templates** section, select **BTAHL7V231Common Project**.</span></span>  
  
4.  <span data-ttu-id="1f8d0-112">**名前**ボックスに、入力**BTAHL7V231Common プロジェクト**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-112">In the **Name** box, enter **BTAHL7V231Common Project** as the project name.</span></span>  
  
5.  <span data-ttu-id="1f8d0-113">**ソリューション**ボックスで、**ソリューションに追加**です。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-113">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6.  <span data-ttu-id="1f8d0-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-114">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f8d0-115">ソリューション エクスプ ローラーで、3 つのスキーマ (datatypes_231.xsd、segments_231.xsd、および tablevalues_231.xsd) は、プロジェクトに含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-115">In Solution Explorer, three schemas (datatypes_231.xsd, segments_231.xsd, and tablevalues_231.xsd) are included in the project.</span></span>  
  
7.  <span data-ttu-id="1f8d0-116">ソリューション エクスプ ローラーで右クリック**BTAHL7V231Common プロジェクト**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-116">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Properties**.</span></span>  
  
8.  <span data-ttu-id="1f8d0-117">BTAHL7V231Common プロパティ ページ ダイアログ ボックスで、をクリックして**署名**です。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-117">On the BTAHL7V231Common Property Pages dialog box, click **Signing**.</span></span>  
  
9. <span data-ttu-id="1f8d0-118">確認**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-118">Check **Sign the assembly** check box.</span></span>  
  
10. <span data-ttu-id="1f8d0-119">厳密な名前キー ファイルの選択 でドロップダウン リストを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-119">In Choose a strong name key file drop down list select.</span></span>  
  
11. <span data-ttu-id="1f8d0-120">参照 **: \Batching チュートリアル** **key.snk**、順にクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-120">Browse to **:\Batching Tutorial**, select **key.snk**, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="1f8d0-121">右クリック**BTAHL7V231Common**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-121">Right-click **BTAHL7V231Common**, and then click **Deploy**.</span></span> <span data-ttu-id="1f8d0-122">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-122">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f8d0-123">使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="1f8d0-124">進みます[手順 3: トリガー イベント (メッセージ) スキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)です。</span><span class="sxs-lookup"><span data-stu-id="1f8d0-124">Proceed to [Step 3: Add a Trigger Event (Message) Schema](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span></span>