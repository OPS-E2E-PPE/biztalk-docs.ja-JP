---
title: "単体テスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c40e5b82-dbb2-4767-8286-88e2de4129f3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5f792adf73fb1e3791f0dfe6c8c5f60a3bb81e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="unit-testing"></a><span data-ttu-id="eaf85-102">単体テスト</span><span class="sxs-lookup"><span data-stu-id="eaf85-102">Unit Testing</span></span>
<span data-ttu-id="eaf85-103">BizTalk Server には、単体テストを有効にできる機能が導入されています、**展開**BizTalk プロジェクトのプロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="eaf85-103">BizTalk Server introduces a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="eaf85-104">次のスクリーン ショットは、このプロジェクトのプロジェクトを右クリックすると、プロジェクト デザイナーからアクセス設定を示しています。**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="eaf85-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click **Properties**.</span></span>  
  
 <span data-ttu-id="eaf85-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span><span class="sxs-lookup"><span data-stu-id="eaf85-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span></span>  
  
 <span data-ttu-id="eaf85-106">**単体テスト プロジェクトのプロパティを公開するプロジェクト デザイナーの 展開 タブのスクリーン ショット**</span><span class="sxs-lookup"><span data-stu-id="eaf85-106">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property**</span></span>  
  
 <span data-ttu-id="eaf85-107">この機能により、スキーマ、マップ、パイプラインの単体テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="eaf85-107">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="eaf85-108">BizTalk Server のドキュメントのトピックでは、単体テスト機能を使用するアプローチの例をいくつかを説明します。</span><span class="sxs-lookup"><span data-stu-id="eaf85-108">The topics in the BizTalk Server documentation provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="eaf85-109">この機能を有効にしてプロジェクトを再構築すると、次の基本クラスから、単体テストをサポートするためのアイテム クラスが派生します。</span><span class="sxs-lookup"><span data-stu-id="eaf85-109">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="eaf85-110">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="eaf85-110">Artifact type</span></span>|<span data-ttu-id="eaf85-111">基本クラス</span><span class="sxs-lookup"><span data-stu-id="eaf85-111">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="eaf85-112">スキーマ</span><span class="sxs-lookup"><span data-stu-id="eaf85-112">Schema</span></span>|<span data-ttu-id="eaf85-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="eaf85-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="eaf85-114">マップ</span><span class="sxs-lookup"><span data-stu-id="eaf85-114">Map</span></span>|<span data-ttu-id="eaf85-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="eaf85-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="eaf85-116">パイプライン</span><span class="sxs-lookup"><span data-stu-id="eaf85-116">Pipeline</span></span>|<span data-ttu-id="eaf85-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="eaf85-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
 <span data-ttu-id="eaf85-118">単体テストで BizTalk Server で導入された機能の詳細については、BizTalk Server ヘルプの次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf85-118">For more information about the unit testing feature introduced with BizTalk Server, see the following topics in the BizTalk Server Help:</span></span>  
  
-   <span data-ttu-id="eaf85-119">[単体テストのスキーマおよびマップの機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)。</span><span class="sxs-lookup"><span data-stu-id="eaf85-119">[Using the Unit Testing Feature with Schemas and Maps](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).</span></span>  
  
-   <span data-ttu-id="eaf85-120">[単体テストでのパイプライン機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)</span><span class="sxs-lookup"><span data-stu-id="eaf85-120">[Using the Unit Testing Feature with Pipelines](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf85-121">参照</span><span class="sxs-lookup"><span data-stu-id="eaf85-121">See Also</span></span>  
 [<span data-ttu-id="eaf85-122">自動テストの実装</span><span class="sxs-lookup"><span data-stu-id="eaf85-122">Implementing Automated Testing</span></span>](../technical-guides/implementing-automated-testing.md)