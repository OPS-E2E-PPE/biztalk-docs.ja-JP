---
title: 単体テスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c40e5b82-dbb2-4767-8286-88e2de4129f3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d92743dbfde629212231e9fb8a1e73496f4ca6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400595"
---
# <a name="unit-testing"></a><span data-ttu-id="b1bb4-102">単体テスト</span><span class="sxs-lookup"><span data-stu-id="b1bb4-102">Unit Testing</span></span>
<span data-ttu-id="b1bb4-103">BizTalk Server に単体テストで有効にする機能が導入されています、**展開**BizTalk プロジェクトのプロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="b1bb4-103">BizTalk Server introduces a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="b1bb4-104">次のスクリーン ショットは、このプロジェクトのプロジェクトを右クリックすると、プロジェクト デザイナーからアクセス設定を示しています。**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="b1bb4-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click **Properties**.</span></span>  
  
 <span data-ttu-id="b1bb4-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span><span class="sxs-lookup"><span data-stu-id="b1bb4-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span></span>  
  
 <span data-ttu-id="b1bb4-106">**プロジェクトの単体テストを有効にするプロパティを公開するプロジェクト デザイナーの [展開] タブのスクリーン ショット**</span><span class="sxs-lookup"><span data-stu-id="b1bb4-106">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property**</span></span>  
  
 <span data-ttu-id="b1bb4-107">この機能は、スキーマ、マップ、用の単体テストを作成することができ、パイプラインします。</span><span class="sxs-lookup"><span data-stu-id="b1bb4-107">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="b1bb4-108">BizTalk Server のドキュメントでは、単体テスト機能を使用するアプローチの例をいくつか説明します。</span><span class="sxs-lookup"><span data-stu-id="b1bb4-108">The topics in the BizTalk Server documentation provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="b1bb4-109">この機能が有効になっているし、プロジェクトを再構築、成果物の単体テストをサポートするために次の基本クラスからクラスが派生されます。</span><span class="sxs-lookup"><span data-stu-id="b1bb4-109">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="b1bb4-110">成果物の種類</span><span class="sxs-lookup"><span data-stu-id="b1bb4-110">Artifact type</span></span>|<span data-ttu-id="b1bb4-111">基本クラス</span><span class="sxs-lookup"><span data-stu-id="b1bb4-111">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="b1bb4-112">スキーマ</span><span class="sxs-lookup"><span data-stu-id="b1bb4-112">Schema</span></span>|<span data-ttu-id="b1bb4-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="b1bb4-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="b1bb4-114">マップ</span><span class="sxs-lookup"><span data-stu-id="b1bb4-114">Map</span></span>|<span data-ttu-id="b1bb4-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="b1bb4-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="b1bb4-116">パイプライン</span><span class="sxs-lookup"><span data-stu-id="b1bb4-116">Pipeline</span></span>|<span data-ttu-id="b1bb4-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="b1bb4-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
 <span data-ttu-id="b1bb4-118">単体テストの BizTalk Server で導入された機能の詳細については、BizTalk Server ヘルプで、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1bb4-118">For more information about the unit testing feature introduced with BizTalk Server, see the following topics in the BizTalk Server Help:</span></span>  
  
-   <span data-ttu-id="b1bb4-119">[単体テストのスキーマとマップを含む機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)します。</span><span class="sxs-lookup"><span data-stu-id="b1bb4-119">[Using the Unit Testing Feature with Schemas and Maps](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).</span></span>  
  
-   <span data-ttu-id="b1bb4-120">[単体テストのパイプラインを持つ機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)</span><span class="sxs-lookup"><span data-stu-id="b1bb4-120">[Using the Unit Testing Feature with Pipelines](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1bb4-121">参照</span><span class="sxs-lookup"><span data-stu-id="b1bb4-121">See Also</span></span>  
 [<span data-ttu-id="b1bb4-122">自動テストの実装</span><span class="sxs-lookup"><span data-stu-id="b1bb4-122">Implementing Automated Testing</span></span>](../technical-guides/implementing-automated-testing.md)