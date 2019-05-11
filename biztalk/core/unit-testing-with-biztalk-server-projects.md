---
title: BizTalk Server プロジェクトでの単体テスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2594f29-fc34-4dda-9316-2afd4e0056d7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19cb904341baf5d6a48af2ea55006522793b3d59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292633"
---
# <a name="unit-testing-with-biztalk-server-projects"></a><span data-ttu-id="1168e-102">BizTalk Server プロジェクトでの単体テスト</span><span class="sxs-lookup"><span data-stu-id="1168e-102">Unit Testing with BizTalk Server Projects</span></span>
<span data-ttu-id="1168e-103">BizTalk Server には、単体テストを有効にできる機能が導入された、**展開**BizTalk プロジェクトのプロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="1168e-103">BizTalk Server introduced a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="1168e-104">次のスクリーン ショットは、このプロジェクトのプロジェクトを右クリックすると、プロジェクト デザイナーからアクセス設定を示しています、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="1168e-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click the **Properties**.</span></span>  
  
 <span data-ttu-id="1168e-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span><span class="sxs-lookup"><span data-stu-id="1168e-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span></span>  
  
 <span data-ttu-id="1168e-106">**プロジェクトの単体テストを有効にするプロパティを公開するプロジェクト デザイナーの [展開] タブのスクリーン ショット。**</span><span class="sxs-lookup"><span data-stu-id="1168e-106">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property.**</span></span>  
  
 <span data-ttu-id="1168e-107">この機能は、スキーマ、マップ、用の単体テストを作成することができ、パイプラインします。</span><span class="sxs-lookup"><span data-stu-id="1168e-107">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="1168e-108">このセクションのトピックでは、単体テスト機能を使用するアプローチの例をいくつかを説明します。</span><span class="sxs-lookup"><span data-stu-id="1168e-108">The topics in this section provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="1168e-109">この機能が有効になっているし、プロジェクトを再構築、成果物の単体テストをサポートするために次の基本クラスからクラスが派生されます。</span><span class="sxs-lookup"><span data-stu-id="1168e-109">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="1168e-110">成果物の種類</span><span class="sxs-lookup"><span data-stu-id="1168e-110">Artifact type</span></span>|<span data-ttu-id="1168e-111">基本クラス</span><span class="sxs-lookup"><span data-stu-id="1168e-111">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="1168e-112">スキーマ</span><span class="sxs-lookup"><span data-stu-id="1168e-112">Schema</span></span>|<span data-ttu-id="1168e-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="1168e-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="1168e-114">マップ</span><span class="sxs-lookup"><span data-stu-id="1168e-114">Map</span></span>|<span data-ttu-id="1168e-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="1168e-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="1168e-116">パイプライン</span><span class="sxs-lookup"><span data-stu-id="1168e-116">Pipeline</span></span>|<span data-ttu-id="1168e-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="1168e-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="1168e-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1168e-118">In This Section</span></span>  
  
-   [<span data-ttu-id="1168e-119">単体テストのスキーマとマップを含む機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="1168e-119">Using the Unit Testing Feature with Schemas and Maps</span></span>](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)  
  
-   [<span data-ttu-id="1168e-120">単体テストのパイプラインを持つ機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="1168e-120">Using the Unit Testing Feature with Pipelines</span></span>](../core/using-the-unit-testing-feature-with-pipelines.md)  
  
## <a name="related-sections"></a><span data-ttu-id="1168e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="1168e-121">Related Sections</span></span>  
 [<span data-ttu-id="1168e-122">単体テスト (Visual Studio) の操作</span><span class="sxs-lookup"><span data-stu-id="1168e-122">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)