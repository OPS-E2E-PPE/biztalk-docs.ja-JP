---
title: BizUnit テスト_ケースの段階 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed0e725f-2c52-43f7-ae30-343413a703c2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b67f9211c6525ca64afcd40d2155169af138026
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305507"
---
# <a name="stages-of-a-bizunit-test-case"></a><span data-ttu-id="3ccc2-102">BizUnit テスト_ケースのステージ</span><span class="sxs-lookup"><span data-stu-id="3ccc2-102">Stages of a BizUnit Test Case</span></span>
<span data-ttu-id="3ccc2-103">BizUnit テスト_ケースは、3 つのステージで構成されます。**TestSetup**、 **TestExecution**、および**TestCleanup**します。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-103">Each BizUnit test case consists of three stages: **TestSetup**, **TestExecution**, and **TestCleanup**.</span></span> <span data-ttu-id="3ccc2-104">各ステージには、作業の 1 つの個別単位を実行する責任を持っている 1 つまたは複数のテスト ステップが含まれています。たとえば、 **FileCreateStep**特定のファイル名で指定した場所でファイルの作成を担当します。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-104">Each stage contains one or more test steps that are responsible for performing a single discrete unit of work; for example, the **FileCreateStep** is responsible for creating a file in a location you specify with a given filename.</span></span>  <span data-ttu-id="3ccc2-105">BizUnit は、70 以上のテスト ステップが含まれていて、拡張機能により、フレームワークに簡単に追加する新しいテスト ステップも提供します。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-105">BizUnit includes over 70 test steps and also provides extension capabilities which allow new test steps to be easily added to the framework.</span></span> <span data-ttu-id="3ccc2-106">フレームワークに新しい手順を追加する機能は、幅広いシナリオで使用するための BizUnit を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-106">The ability to add new steps to the framework allows BizUnit to be used across a broad range of scenarios.</span></span> <span data-ttu-id="3ccc2-107">このトピックでは、さらに詳しく BizUnit テストの段階について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-107">This topic describes the BizUnit test stages in further detail.</span></span>  
  
## <a name="setup-stage"></a><span data-ttu-id="3ccc2-108">セットアップの段階</span><span class="sxs-lookup"><span data-stu-id="3ccc2-108">Setup Stage</span></span>  
 <span data-ttu-id="3ccc2-109">このセットアップ ステージでは、テスト用プラットフォームを準備します。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-109">This setup stage prepares the platform for the testing.</span></span> <span data-ttu-id="3ccc2-110">たとえば、特定のテストを実行するには、ファイルは、テストの実際の実行の準備として、ファイル ドロップにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-110">For example, before a particular test can be run, a file may need to be copied to a file drop in preparation for the actual execution of the test.</span></span> <span data-ttu-id="3ccc2-111">クリーンアップするには、このステージは、任意のファイルの場所や、テストで使用されるデータベースのテーブルも使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-111">You could also use this stage to cleanup any file locations or database tables that will be used in the test.</span></span> <span data-ttu-id="3ccc2-112">BizUnit 内のすべてのステージでは、追加できるテスト ステップの数に制限がない、複雑なシナリオを処理するために必要な柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-112">As with every stage in BizUnit, there is no limit to the number of test steps that can be added, which provides the flexibility required to handle complex scenarios.</span></span>  
  
## <a name="execution-stage"></a><span data-ttu-id="3ccc2-113">実行のステージ</span><span class="sxs-lookup"><span data-stu-id="3ccc2-113">Execution Stage</span></span>  
 <span data-ttu-id="3ccc2-114">実行段階では、テストが実際に実行します。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-114">The execution stage is where the test is actually run.</span></span> <span data-ttu-id="3ccc2-115">これは、検証するときは、システムの機能は実際にテストします。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-115">This is where the function of the system you are validating is actually tested.</span></span>  
  
## <a name="cleanup-stage"></a><span data-ttu-id="3ccc2-116">クリーンアップのステージ</span><span class="sxs-lookup"><span data-stu-id="3ccc2-116">Cleanup Stage</span></span>  
 <span data-ttu-id="3ccc2-117">クリーンアップ ステージは、テスト手順については、一貫性のあるテストを実行する前に、の状態をプラットフォームが返すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-117">The cleanup stage is the container for test steps that returns the platform to the consistent state that it was in before you ran the test.</span></span> <span data-ttu-id="3ccc2-118">この段階は、実行段階でエラーが発生した場合でも常に実行します。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-118">This stage is always executed, even if an error occurs in the execution stage.</span></span> <span data-ttu-id="3ccc2-119">プラットフォームを基盤に返される理由は、1 つのテスト_ケースが各テスト・ケースを自律的にテスト スイートの一部として実行されるように、別に干渉しないようにです。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-119">The reason the platform should be returned to its starting point is to prevent one test case from interfering with another so that each test case is run autonomously as part of the test suite.</span></span> <span data-ttu-id="3ccc2-120">BizUnit で効率的なテストの基本原則の 1 つは、この段階で、システムの完全なクリーンアップのことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-120">Ensuring a complete cleanup of the system at this stage is one of the guiding principles for effective testing with BizUnit.</span></span>  
  
 <span data-ttu-id="3ccc2-121">次の図は、3 つの段階でのテスト ステップを含む、サンプルのテスト ケースの形式を示しています。 セットアップ、実行、およびクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-121">The following diagram illustrates the format of a sample test case, which contains test steps in the three stages: setup, execution, and cleanup.</span></span> <span data-ttu-id="3ccc2-122">BizUnit とテスト_ケースを定義するときに、この構造体を常に従うことが重要です。</span><span class="sxs-lookup"><span data-stu-id="3ccc2-122">It is important to always follow this structure when defining test cases with BizUnit.</span></span>  
  
 <span data-ttu-id="3ccc2-123">![BizUnit テストのステージ](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")</span><span class="sxs-lookup"><span data-stu-id="3ccc2-123">![Stages of a BizUnit Test](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")</span></span>  
<span data-ttu-id="3ccc2-124">BizUnit テストのステージ</span><span class="sxs-lookup"><span data-stu-id="3ccc2-124">Stages of a BizUnit test</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ccc2-125">参照</span><span class="sxs-lookup"><span data-stu-id="3ccc2-125">See Also</span></span>  
 [<span data-ttu-id="3ccc2-126">自動テストを容易にするための BizUnit の使用</span><span class="sxs-lookup"><span data-stu-id="3ccc2-126">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)