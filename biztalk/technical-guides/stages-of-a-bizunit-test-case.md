---
title: BizUnit テスト ケースの段階 |Microsoft ドキュメント
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
ms.openlocfilehash: 2ff435fd1c69118112b0121bf68b38ae3151885f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302378"
---
# <a name="stages-of-a-bizunit-test-case"></a><span data-ttu-id="ce24a-102">BizUnit テスト ケースの段階</span><span class="sxs-lookup"><span data-stu-id="ce24a-102">Stages of a BizUnit Test Case</span></span>
<span data-ttu-id="ce24a-103">各 BizUnit テスト ケースは、3 つのステージで構成されています: **TestSetup**、 **TestExecution**、および**TestCleanup**です。</span><span class="sxs-lookup"><span data-stu-id="ce24a-103">Each BizUnit test case consists of three stages: **TestSetup**, **TestExecution**, and **TestCleanup**.</span></span> <span data-ttu-id="ce24a-104">各ステージには、作業の 1 つの個別単位を実行するは、1 つまたは複数のテスト ステップが含まれています。たとえば、 **FileCreateStep**は指定されたファイル名で指定した場所にファイルの作成を担当します。</span><span class="sxs-lookup"><span data-stu-id="ce24a-104">Each stage contains one or more test steps that are responsible for performing a single discrete unit of work; for example, the **FileCreateStep** is responsible for creating a file in a location you specify with a given filename.</span></span>  <span data-ttu-id="ce24a-105">BizUnit は、70 以上のテスト ステップが含まれていて、新しいフレームワークに容易に追加するテストの手順を実行できるようにする拡張機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="ce24a-105">BizUnit includes over 70 test steps and also provides extension capabilities which allow new test steps to be easily added to the framework.</span></span> <span data-ttu-id="ce24a-106">新しいステップ フレームワークを追加する機能には、幅広いシナリオで使用するための BizUnit ができます。</span><span class="sxs-lookup"><span data-stu-id="ce24a-106">The ability to add new steps to the framework allows BizUnit to be used across a broad range of scenarios.</span></span> <span data-ttu-id="ce24a-107">このトピックでは、さらに詳しく BizUnit テストの段階について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce24a-107">This topic describes the BizUnit test stages in further detail.</span></span>  
  
## <a name="setup-stage"></a><span data-ttu-id="ce24a-108">セットアップ ステージ</span><span class="sxs-lookup"><span data-stu-id="ce24a-108">Setup Stage</span></span>  
 <span data-ttu-id="ce24a-109">このセットアップ ステージでは、テストのプラットフォームを準備します。</span><span class="sxs-lookup"><span data-stu-id="ce24a-109">This setup stage prepares the platform for the testing.</span></span> <span data-ttu-id="ce24a-110">たとえば、特定のテストを実行することができます、前に、ファイルは、テストの実際の実行の準備として、ファイル ドロップにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce24a-110">For example, before a particular test can be run, a file may need to be copied to a file drop in preparation for the actual execution of the test.</span></span> <span data-ttu-id="ce24a-111">任意のファイルの場所や、テストで使用されるデータベース テーブル クリーンアップするには、このステージを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce24a-111">You could also use this stage to cleanup any file locations or database tables that will be used in the test.</span></span> <span data-ttu-id="ce24a-112">BizUnit 内のすべてのステージに追加できるテスト ステップの数に制限がない、複雑なシナリオを処理するために必要な柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="ce24a-112">As with every stage in BizUnit, there is no limit to the number of test steps that can be added, which provides the flexibility required to handle complex scenarios.</span></span>  
  
## <a name="execution-stage"></a><span data-ttu-id="ce24a-113">実行のステージ</span><span class="sxs-lookup"><span data-stu-id="ce24a-113">Execution Stage</span></span>  
 <span data-ttu-id="ce24a-114">実行段階では、テストが実際に実行します。</span><span class="sxs-lookup"><span data-stu-id="ce24a-114">The execution stage is where the test is actually run.</span></span> <span data-ttu-id="ce24a-115">これは、実際にテストが検証しているシステムの機能です。</span><span class="sxs-lookup"><span data-stu-id="ce24a-115">This is where the function of the system you are validating is actually tested.</span></span>  
  
## <a name="cleanup-stage"></a><span data-ttu-id="ce24a-116">クリーンアップ ステージ</span><span class="sxs-lookup"><span data-stu-id="ce24a-116">Cleanup Stage</span></span>  
 <span data-ttu-id="ce24a-117">クリーンアップ ステージを返す、プラットフォーム、一貫した状態でテストを実行する前にテスト ステップのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="ce24a-117">The cleanup stage is the container for test steps that returns the platform to the consistent state that it was in before you ran the test.</span></span> <span data-ttu-id="ce24a-118">この段階が実行のステージでエラーが発生した場合でも常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="ce24a-118">This stage is always executed, even if an error occurs in the execution stage.</span></span> <span data-ttu-id="ce24a-119">プラットフォームを基盤に返される理由は、1 つのテスト_ケースの各テスト・ケースは、テスト スイートの一部として自律的に実行されるように、別に干渉することを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="ce24a-119">The reason the platform should be returned to its starting point is to prevent one test case from interfering with another so that each test case is run autonomously as part of the test suite.</span></span> <span data-ttu-id="ce24a-120">この段階で、システムの完全なクリーンアップを確保すると、BizUnit で効果的なテストの基本原則の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="ce24a-120">Ensuring a complete cleanup of the system at this stage is one of the guiding principles for effective testing with BizUnit.</span></span>  
  
 <span data-ttu-id="ce24a-121">次の図は、次の 3 つの段階的にテスト ステップを含むサンプル テスト ケースの形式: セットアップ、実行、およびクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="ce24a-121">The following diagram illustrates the format of a sample test case, which contains test steps in the three stages: setup, execution, and cleanup.</span></span> <span data-ttu-id="ce24a-122">BizUnit を持つテスト_ケースを定義するときに、この構造体を常に従うことが重要であります。</span><span class="sxs-lookup"><span data-stu-id="ce24a-122">It is important to always follow this structure when defining test cases with BizUnit.</span></span>  
  
 <span data-ttu-id="ce24a-123">![BizUnit テストのステージ](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")</span><span class="sxs-lookup"><span data-stu-id="ce24a-123">![Stages of a BizUnit Test](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")</span></span>  
<span data-ttu-id="ce24a-124">BizUnit テストのステージ</span><span class="sxs-lookup"><span data-stu-id="ce24a-124">Stages of a BizUnit test</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce24a-125">参照</span><span class="sxs-lookup"><span data-stu-id="ce24a-125">See Also</span></span>  
 [<span data-ttu-id="ce24a-126">BizUnit を使用して自動テストを容易にするには</span><span class="sxs-lookup"><span data-stu-id="ce24a-126">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)