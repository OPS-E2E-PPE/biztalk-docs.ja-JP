---
title: 'レッスン 5: カスタム受信パイプラインに SWIFT の逆アセンブラーを追加する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, adding disassembler
- custom pipelines
- disassembler, custom pipelines
- disassembler, adding to pipelines
ms.assetid: 96e26d97-bfab-448f-b7b6-3bc2ec3ccebf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0616c4adddc6e2d096624d02b968a21012ccd93b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005555"
---
# <a name="lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline"></a><span data-ttu-id="530a2-102">レッスン 5: カスタム受信パイプラインに SWIFT の逆アセンブラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="530a2-102">Lesson 5: Adding the SWIFT Disassembler to a Custom Receive Pipeline</span></span>
<span data-ttu-id="530a2-103">このレッスンでは、パイプラインにカスタムの SWIFT 逆アセンブラー (DASM) を追加します。</span><span class="sxs-lookup"><span data-stu-id="530a2-103">In this lesson, you add the custom SWIFT disassembler (DASM) to your pipeline.</span></span> <span data-ttu-id="530a2-104">逆アセンブラー パイプライン コンポーネントは、バッチ内のメッセージを個々 のドキュメントに分割するパイプライン コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="530a2-104">A DASM pipeline component is a pipeline component that divides messages in a batch into individual documents.</span></span>  
  
 <span data-ttu-id="530a2-105">逆アセンブラー パイプライン コンポーネントで提供される[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server は。</span><span class="sxs-lookup"><span data-stu-id="530a2-105">The DASM pipeline components provided in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server are:</span></span>  
  
-   <span data-ttu-id="530a2-106">フラット ファイル逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="530a2-106">Flat file disassembler</span></span>  
  
-   <span data-ttu-id="530a2-107">BizTalk Framework 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="530a2-107">BizTalk Framework disassembler</span></span>  
  
-   <span data-ttu-id="530a2-108">XML 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="530a2-108">XML disassembler</span></span>  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="530a2-109">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]追加 SWIFT 逆アセンブラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="530a2-109"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] adds an additional SWIFT disassembler.</span></span>  
  
### <a name="to-add-the-swift-custom-disassembler-to-your-pipeline"></a><span data-ttu-id="530a2-110">SWIFT カスタム逆アセンブラーをパイプラインに追加するには</span><span class="sxs-lookup"><span data-stu-id="530a2-110">To add the SWIFT custom disassembler to your pipeline</span></span>  
  
1.  <span data-ttu-id="530a2-111">[表示] メニューからクリックして**ツールボックス**です。</span><span class="sxs-lookup"><span data-stu-id="530a2-111">From the View menu, click **Toolbox**.</span></span>  
  
2.  <span data-ttu-id="530a2-112">**BizTalk パイプライン コンポーネントのツールボックス**、 をクリックして**SWIFT 逆アセンブラー**ドラッグして、**ここにドロップ**下のボックス、**逆アセンブル**で図形をステージ**BizTalk パイプライン デザイナ**です。</span><span class="sxs-lookup"><span data-stu-id="530a2-112">From the **BizTalk Pipeline Components Toolbox**, click **SWIFT Disassembler** and drag it to the **Drop Here** box below the **Disassemble** stage shape in **BizTalk Pipeline Designer**.</span></span> <span data-ttu-id="530a2-113">ままにして、 **SWIFT 逆アセンブラー**で選択された図形、 **BizTalk パイプライン デザイナ**です。</span><span class="sxs-lookup"><span data-stu-id="530a2-113">Leave the **SWIFT Disassembler** shape selected in the **BizTalk Pipeline Designer**.</span></span>  
  
3.  <span data-ttu-id="530a2-114">**プロパティ**ペインで、 **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**の**SWIFT ヘッダー スキーマ**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="530a2-114">In the **Properties** pane, select **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** for the **SWIFT Header Schema** property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="530a2-115">混同しないでください**SWIFT ヘッダー スキーマ**とメッセージ ヘッダーのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="530a2-115">Do not confuse **SWIFT Header Schema** and Message Header Schema.</span></span> <span data-ttu-id="530a2-116">設定する必要があります**SWIFT ヘッダー スキーマ**手順 3 でします。</span><span class="sxs-lookup"><span data-stu-id="530a2-116">You must set **SWIFT Header Schema** in step 3.</span></span>  
  
4.  <span data-ttu-id="530a2-117">**プロパティ** ウィンドウで、いることを確認、 **BRE 検証**プロパティに設定されている**True**です。</span><span class="sxs-lookup"><span data-stu-id="530a2-117">In the **Properties** pane, ensure that the **BRE Validation** property is set to **True**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="530a2-118">このチュートリアルで後ほど説明については、ビジネス ルール エンジン (BRE) の次に示します。</span><span class="sxs-lookup"><span data-stu-id="530a2-118">An explanation of the Business Rule Engine (BRE) follows later in this tutorial.</span></span>  
  
5.  <span data-ttu-id="530a2-119">**プロパティ** ウィンドウで、いることを確認、 **XML 検証**プロパティに設定されている**True**です。</span><span class="sxs-lookup"><span data-stu-id="530a2-119">In the **Properties** pane, ensure that the **XML Validation** property is set to **True**.</span></span>  
  
6.  <span data-ttu-id="530a2-120">**プロパティ** ウィンドウで、いることを確認、**受信バッチ解除処理**プロパティに設定されている**False**です。</span><span class="sxs-lookup"><span data-stu-id="530a2-120">In the **Properties** pane, ensure that the **Inbound Debatching** property is set to **False**.</span></span>  
  
7.  <span data-ttu-id="530a2-121">**ファイル**メニューの **すべて保存**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="530a2-121">On the **File** menu, select **Save All** to save your changes.</span></span>  
  
 <span data-ttu-id="530a2-122">進みます[レッスン 6: カスタムを作成する送信パイプライン](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)です。</span><span class="sxs-lookup"><span data-stu-id="530a2-122">Proceed to [Lesson 6: Creating a Custom Send Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md).</span></span>