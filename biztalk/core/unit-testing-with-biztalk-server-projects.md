---
title: "BizTalk Server プロジェクトを使用した単体テスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2594f29-fc34-4dda-9316-2afd4e0056d7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15f73b9c343e62e0a0a83bf76f8c762b9ce9ede9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unit-testing-with-biztalk-server-projects"></a><span data-ttu-id="f3296-102">BizTalk Server プロジェクトを使用した単体テスト</span><span class="sxs-lookup"><span data-stu-id="f3296-102">Unit Testing with BizTalk Server Projects</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="f3296-103">単体テストで有効にする機能を導入、**展開**BizTalk プロジェクトのプロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="f3296-103"> introduced a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="f3296-104">次のスクリーン ショットは、このプロジェクトのプロジェクトを右クリックすると、プロジェクト デザイナーからアクセス設定を示しています。、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="f3296-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click the **Properties**.</span></span>  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 <span data-ttu-id="f3296-105">**単体テスト プロジェクトのプロパティを公開するプロジェクト デザイナーの 展開 タブのスクリーン ショット。**</span><span class="sxs-lookup"><span data-stu-id="f3296-105">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property.**</span></span>  
  
 <span data-ttu-id="f3296-106">この機能により、スキーマ、マップ、パイプラインの単体テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f3296-106">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="f3296-107">このセクションのトピックでは、単体テスト機能を使用するアプローチの例をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="f3296-107">The topics in this section provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="f3296-108">この機能を有効にしてプロジェクトを再構築すると、次の基本クラスから、単体テストをサポートするためのアイテム クラスが派生します。</span><span class="sxs-lookup"><span data-stu-id="f3296-108">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="f3296-109">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="f3296-109">Artifact type</span></span>|<span data-ttu-id="f3296-110">基本クラス</span><span class="sxs-lookup"><span data-stu-id="f3296-110">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="f3296-111">スキーマ</span><span class="sxs-lookup"><span data-stu-id="f3296-111">Schema</span></span>|<span data-ttu-id="f3296-112">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="f3296-112">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="f3296-113">マップ</span><span class="sxs-lookup"><span data-stu-id="f3296-113">Map</span></span>|<span data-ttu-id="f3296-114">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="f3296-114">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="f3296-115">パイプライン</span><span class="sxs-lookup"><span data-stu-id="f3296-115">Pipeline</span></span>|<span data-ttu-id="f3296-116">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="f3296-116">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="f3296-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f3296-117">In This Section</span></span>  
  
-   [<span data-ttu-id="f3296-118">単体テストのスキーマおよびマップを持つ機能の使用</span><span class="sxs-lookup"><span data-stu-id="f3296-118">Using the Unit Testing Feature with Schemas and Maps</span></span>](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)  
  
-   [<span data-ttu-id="f3296-119">単体テストのパイプラインを持つ機能の使用</span><span class="sxs-lookup"><span data-stu-id="f3296-119">Using the Unit Testing Feature with Pipelines</span></span>](../core/using-the-unit-testing-feature-with-pipelines.md)  
  
## <a name="related-sections"></a><span data-ttu-id="f3296-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3296-120">Related Sections</span></span>  
 [<span data-ttu-id="f3296-121">単体テスト (Visual Studio) の操作</span><span class="sxs-lookup"><span data-stu-id="f3296-121">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)