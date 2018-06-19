---
title: パイプライン プロジェクトを作成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b584e3ab-e824-4977-b4ed-4fc197a6cf7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eead267abbb990933e6fd3150d099d07b007526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209714"
---
# <a name="creating-a-pipeline-project"></a><span data-ttu-id="0c399-102">パイプライン プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c399-102">Creating a Pipeline Project</span></span>
<span data-ttu-id="0c399-103">パイプライン プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="0c399-103">To create a pipeline project:</span></span>  
  
1.  <span data-ttu-id="0c399-104">Visual Studio で新しい BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c399-104">In Visual Studio, create a new BizTalk project.</span></span>  
  
2.  <span data-ttu-id="0c399-105">受信パイプライン項目とは、送信パイプラインの項目をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="0c399-105">Add a receive pipeline item and a send pipeline item to the project.</span></span>  
  
3.  <span data-ttu-id="0c399-106">ReceivePipeline.btp ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c399-106">Open the ReceivePipeline.btp file.</span></span>  
  
4.  <span data-ttu-id="0c399-107">パイプライン デザイナーでは、ツールボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c399-107">In Pipeline Designer, open the Toolbox.</span></span>  
  
5.  <span data-ttu-id="0c399-108">右クリックし、**ツールボックス**画面、し、**アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="0c399-108">Right-click the **Toolbox** surface, and then select **Choose Items**.</span></span>  
  
6.  <span data-ttu-id="0c399-109">[ツールボックス アイテムの選択] ウィンドウ、**パイプライン コンポーネント**タブをクリックし、次のパイプライン コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c399-109">In the Choose Toolbox Items window, click the **Pipeline Components** tab, and then select the following pipeline components:</span></span>  
  
    -   <span data-ttu-id="0c399-110">SwiftMXDisassembler</span><span class="sxs-lookup"><span data-stu-id="0c399-110">SwiftMXDisassembler</span></span>  
  
    -   <span data-ttu-id="0c399-111">SwiftMXAssembler</span><span class="sxs-lookup"><span data-stu-id="0c399-111">SwiftMXAssembler</span></span>  
  
    -   <span data-ttu-id="0c399-112">Swift MXRR エンコーダー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0c399-112">Swift MXRR Encoder Component</span></span>  
  
    -   <span data-ttu-id="0c399-113">Swift MXRR デコーダー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0c399-113">Swift MXRR Decoder Component</span></span>  
  
    -   <span data-ttu-id="0c399-114">Swift MXRR 相関関係者の競合回避コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0c399-114">Swift MXRR Correlation Party Resolver Component</span></span>  
  
7.  <span data-ttu-id="0c399-115">ドラッグ、 **SwiftMXDisassembler**コンポーネントを受信パイプラインの逆アセンブラーのプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="0c399-115">Drag the **SwiftMXDisassembler** component into the Disassembler placeholder in the Receive Pipeline.</span></span>  
  
8.  <span data-ttu-id="0c399-116">SwiftMXDisassembler コンポーネントのプロパティを設定、 **BRE 検証**プロパティを TRUE または FALSE を受信メッセージのビジネス ルールの検証を有効にするかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0c399-116">In the SwiftMXDisassembler component properties, set the **BRE Validation** property to TRUE or FALSE depending on whether you want to enable Business Rules Validation on the incoming messages.</span></span> <span data-ttu-id="0c399-117">設定、 **TransportHeaderRequired**プロパティを TRUE または FALSE をトランスポート メッセージ ヘッダーでグループを指定するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0c399-117">Set the **TransportHeaderRequired** property to TRUE or FALSE depending on whether you want to provide transport header in messages.</span></span>  
  
9. <span data-ttu-id="0c399-118">デコーダーおよび受信パイプライン内のパーティの競合回避モジュールのプレース ホルダーに Swift MXRR デコーダーと Swift MXRR 相関パーティ競合回避モジュール コンポーネントをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="0c399-118">Drag the Swift MXRR Decoder and Swift MXRR Correlation Party Resolver component into the Decoder and the Party Resolver placeholder inside the Receive Pipeline.</span></span>  
  
10. <span data-ttu-id="0c399-119">選択、 **MXRR 相関パーティ リゾルバー**パイプラインでします。</span><span class="sxs-lookup"><span data-stu-id="0c399-119">Select the **MXRR Correlation Party Resolver** in the pipeline.</span></span> <span data-ttu-id="0c399-120">パイプライン コンポーネントのプロパティ ウィンドウで次のように設定します。、 **BAM の調整のログ記録を有効にする**プロパティを TRUE または FALSE を迅速な応答の調整を有効にするかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0c399-120">In the Pipeline Component Properties window, set the **Enable BAM Logging for Reconciliation** property to TRUE or FALSE, depending on whether you want to enable reconciliation for the SWIFT responses.</span></span>  
  
11. <span data-ttu-id="0c399-121">開く、 **SendPipeline.btp**ファイルをパイプライン デザイナーで開く、**ツールボックス**です。</span><span class="sxs-lookup"><span data-stu-id="0c399-121">Open the **SendPipeline.btp** file, In the Pipeline Designer, open the **Toolbox**.</span></span>  
  
12. <span data-ttu-id="0c399-122">ツールボックスで、ドラッグ、 **SwiftMXAssembler**コンポーネント、送信パイプラインの内部アセンブラー プレース ホルダーをします。</span><span class="sxs-lookup"><span data-stu-id="0c399-122">In Toolbox, drag the **SwiftMXAssembler** component into the Assembler placeholder inside the Send Pipeline.</span></span>  
  
13. <span data-ttu-id="0c399-123">ドラッグ、 **Swift MXRR エンコーダー**コンポーネント、送信パイプラインのエンコーダーのプレース ホルダーをします。</span><span class="sxs-lookup"><span data-stu-id="0c399-123">Drag the **Swift MXRR Encoder** component into the Encoder placeholders of the Send Pipeline.</span></span>  
  
14. <span data-ttu-id="0c399-124">選択、 **MXRR エンコーダー パーティ リゾルバー**パイプラインでし、パイプライン コンポーネントのプロパティ ウィンドウでは、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0c399-124">Select the **MXRR Encoder Party Resolver** in the pipeline, and then in the Pipeline Component Properties window, set the following properties.</span></span>  
  
15. <span data-ttu-id="0c399-125">有効にする**BAM の調整のログ記録**TRUE または FALSE の迅速な応答の調整を有効にするかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0c399-125">Enable **BAM Logging for Reconciliation** to TRUE or FALSE depending on whether you want to enable reconciliation for the SWIFT responses.</span></span>  
  
16. <span data-ttu-id="0c399-126">設定、**必要 LAU** TRUE または SWIFT Alliance アクセス (SAA) でメッセージの署名を有効にする必要があるかどうかに応じて FALSE にします。</span><span class="sxs-lookup"><span data-stu-id="0c399-126">Set the **LAU Required** to TRUE or FALSE depending on whether you have to enable the signing of the message at the SWIFT Alliance Access (SAA).</span></span>  
  
17. <span data-ttu-id="0c399-127">LAU のために必要なプロパティがあった場合は TRUE、LAU キーの最初の部分と LAU キー 2 番目の部分 (値する必要があるものと同じで、SAA を構成するときに提供されている。) を入力に設定されています</span><span class="sxs-lookup"><span data-stu-id="0c399-127">If the LAU Required property has been has been set to TRUE, then provide LAU Key First Part and LAU Key Second Part (the values have to be the same ones that were provided while configuring the SAA.)</span></span>  
  
18. <span data-ttu-id="0c399-128">プロジェクトをビルドし、展開します。</span><span class="sxs-lookup"><span data-stu-id="0c399-128">Build and then deploy the project.</span></span>