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
ms.openlocfilehash: faa6dd215aee23f49442e614649fa33f7321d42e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unit-testing"></a><span data-ttu-id="1569a-102">単体テスト</span><span class="sxs-lookup"><span data-stu-id="1569a-102">Unit Testing</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="1569a-103">単体テストで有効にする機能が導入されています、**展開**BizTalk プロジェクトのプロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="1569a-103"> introduces a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="1569a-104">次のスクリーン ショットは、このプロジェクトのプロジェクトを右クリックすると、プロジェクト デザイナーからアクセス設定を示しています。**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="1569a-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click **Properties**.</span></span>  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 <span data-ttu-id="1569a-105">**単体テスト プロジェクトのプロパティを公開するプロジェクト デザイナーの 展開 タブのスクリーン ショット**</span><span class="sxs-lookup"><span data-stu-id="1569a-105">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property**</span></span>  
  
 <span data-ttu-id="1569a-106">この機能により、スキーマ、マップ、パイプラインの単体テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1569a-106">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="1569a-107">各トピックで、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ドキュメントは、単体テスト機能を使用する、いくつかのアプローチの例を提供します。</span><span class="sxs-lookup"><span data-stu-id="1569a-107">The topics in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] documentation provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="1569a-108">この機能を有効にしてプロジェクトを再構築すると、次の基本クラスから、単体テストをサポートするためのアイテム クラスが派生します。</span><span class="sxs-lookup"><span data-stu-id="1569a-108">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="1569a-109">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="1569a-109">Artifact type</span></span>|<span data-ttu-id="1569a-110">基本クラス</span><span class="sxs-lookup"><span data-stu-id="1569a-110">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="1569a-111">スキーマ</span><span class="sxs-lookup"><span data-stu-id="1569a-111">Schema</span></span>|<span data-ttu-id="1569a-112">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="1569a-112">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="1569a-113">マップ</span><span class="sxs-lookup"><span data-stu-id="1569a-113">Map</span></span>|<span data-ttu-id="1569a-114">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="1569a-114">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="1569a-115">パイプライン</span><span class="sxs-lookup"><span data-stu-id="1569a-115">Pipeline</span></span>|<span data-ttu-id="1569a-116">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="1569a-116">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
 <span data-ttu-id="1569a-117">詳細については、単体テスト機能で導入された[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]、次のトピックを参照してください、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="1569a-117">For more information about the unit testing feature introduced with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], see the following topics in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help:</span></span>  
  
-   <span data-ttu-id="1569a-118">[単体テストのスキーマおよびマップの機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)。</span><span class="sxs-lookup"><span data-stu-id="1569a-118">[Using the Unit Testing Feature with Schemas and Maps](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).</span></span>  
  
-   <span data-ttu-id="1569a-119">[単体テストでのパイプライン機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)</span><span class="sxs-lookup"><span data-stu-id="1569a-119">[Using the Unit Testing Feature with Pipelines](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1569a-120">参照</span><span class="sxs-lookup"><span data-stu-id="1569a-120">See Also</span></span>  
 [<span data-ttu-id="1569a-121">テストの自動化を実装します。</span><span class="sxs-lookup"><span data-stu-id="1569a-121">Implementing Automated Testing</span></span>](../technical-guides/implementing-automated-testing.md)