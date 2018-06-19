---
title: オーケストレーションを構築する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, orchestrations
- building, solutions
- building, projects
- solutions, building
- projects, building
- orchestrations, building
ms.assetid: f12d5da0-fbae-4f0e-85bf-1ca2e9bf7d62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79e91ec6ecfa061aa4621effba9a1f868cad5d96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248146"
---
# <a name="how-to-build-orchestrations"></a><span data-ttu-id="62203-102">オーケストレーションのビルド方法</span><span class="sxs-lookup"><span data-stu-id="62203-102">How to Build Orchestrations</span></span>
<span data-ttu-id="62203-103">オーケストレーションをデザインしたら、BizTalk プロジェクトを、実行可能なオーケストレーションが格納されたアセンブリとしてビルドします。</span><span class="sxs-lookup"><span data-stu-id="62203-103">After you have completed an orchestration drawing, you build your BizTalk project into an assembly that encapsulates an executable orchestration.</span></span>  
  
 <span data-ttu-id="62203-104">ビルド プロセスでは、BizTalk オーケストレーション デザイナーが各図形を検査し、不備があった場合は、タスク一覧にエラーとして表示します。</span><span class="sxs-lookup"><span data-stu-id="62203-104">During the build process, BizTalk Orchestration Designer examines each shape to determine whether it is complete and correct, and reports an error in the task list if it is not.</span></span>  
  
 <span data-ttu-id="62203-105">Visual Studio には、次のようなビルド オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="62203-105">You have several options for building in Visual Studio:</span></span>  
  
-   <span data-ttu-id="62203-106">オーケストレーションの存在するソリューション全体をビルドする。</span><span class="sxs-lookup"><span data-stu-id="62203-106">You can build the entire solution in which your orchestration resides.</span></span>  
  
-   <span data-ttu-id="62203-107">ソリューション内の単一のプロジェクトをビルドする。</span><span class="sxs-lookup"><span data-stu-id="62203-107">You can build a single project within the solution.</span></span>  
  
-   <span data-ttu-id="62203-108">プロジェクトまたはソリューションのビルド時に特定のオーケストレーションをスキップする。</span><span class="sxs-lookup"><span data-stu-id="62203-108">You can skip the orchestration when building the project or solution.</span></span>  
  
 <span data-ttu-id="62203-109">他のコンポーネント (他のオーケストレーションも含む) をビルドするとき、特定のオーケストレーションだけはビルドの対象外にしたい場合があります。このような場合は、オーケストレーションの .odx ファイルのプロパティでビルドの対象外として指定することにより、そのオーケストレーションのビルドをスキップさせることができます。</span><span class="sxs-lookup"><span data-stu-id="62203-109">If you want to build other components, including other orchestrations, but do not want to build a particular orchestration, you can indicate in the file properties for the orchestration's .odx file that you do not want to build it, and it will be skipped.</span></span>  
  
### <a name="to-build-an-orchestration"></a><span data-ttu-id="62203-110">オーケストレーションをビルドするには</span><span class="sxs-lookup"><span data-stu-id="62203-110">To build an orchestration</span></span>  
  
-   <span data-ttu-id="62203-111">完成したオーケストレーションをテストしたり、実際に運用したりするためには、そのオーケストレーションが含まれる BizTalk プロジェクトをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="62203-111">After creating your orchestration, you need to build the BizTalk project that contains it before you can test or use the orchestration.</span></span> <span data-ttu-id="62203-112">ソリューション全体をビルドすることも、ソリューション内の単一のプロジェクトだけをビルドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="62203-112">You can build the entire solution, or a single project within the solution.</span></span>  
  
### <a name="to-build-a-solution"></a><span data-ttu-id="62203-113">ソリューションをビルドするには</span><span class="sxs-lookup"><span data-stu-id="62203-113">To build a solution</span></span>  
  
-   <span data-ttu-id="62203-114">ソリューション エクスプ ローラーでソリューションを右クリックし、**ソリューションのビルド**です。</span><span class="sxs-lookup"><span data-stu-id="62203-114">In Solution Explorer, right-click the solution and select **Build Solution**.</span></span>  
  
### <a name="to-build-a-project"></a><span data-ttu-id="62203-115">プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="62203-115">To build a project</span></span>  
  
-   <span data-ttu-id="62203-116">プロジェクトを右クリックし **ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="62203-116">Right-click a project and select **Build**.</span></span>  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a><span data-ttu-id="62203-117">特定のオーケストレーションをコンパイルから除外してプロジェクトまたはソリューションをビルドするには</span><span class="sxs-lookup"><span data-stu-id="62203-117">To build a project or solution without compiling a particular orchestration</span></span>  
  
-   <span data-ttu-id="62203-118">対応する .odx ファイルとプロパティ ウィンドウで、オーケストレーションをクリックし、をクリックして、**ビルド アクション**プロパティを選択**None**です。</span><span class="sxs-lookup"><span data-stu-id="62203-118">Click the .odx file corresponding to the orchestration, and in the Properties window, click the **Build Action** property and select **None**.</span></span>