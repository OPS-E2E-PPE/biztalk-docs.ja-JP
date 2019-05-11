---
title: BizTalk プロジェクトの作成時の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, size
- map type name
- projects, naming conventions
- projects, planning
ms.assetid: f6c3dc71-105f-46af-9e6e-9a4c3b982d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59b8749928891f963f3ca75032cc133c0ddf7848
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390368"
---
# <a name="considerations-when-creating-biztalk-projects"></a><span data-ttu-id="1c248-102">BizTalk プロジェクトの作成時の考慮事項</span><span class="sxs-lookup"><span data-stu-id="1c248-102">Considerations When Creating BizTalk Projects</span></span>
<span data-ttu-id="1c248-103">このセクションを使用して BizTalk を作成するときに考慮に入れる必要のある情報を提供します。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1c248-103">This section provides information that you should take into consideration when creating BizTalk projects using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="avoid-compilation-errors-caused-by-projects-that-are-too-large"></a><span data-ttu-id="1c248-104">大きすぎてプロジェクトによって発生したコンパイル エラーを回避します。</span><span class="sxs-lookup"><span data-stu-id="1c248-104">Avoid compilation errors caused by projects that are too large</span></span>  
 <span data-ttu-id="1c248-105">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コンパイラは正常にコンパイルできませんプロジェクト 75 メガバイトを超えるアセンブリになります。</span><span class="sxs-lookup"><span data-stu-id="1c248-105">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler will not successfully compile a project if it would result in an assembly larger than 75 megabytes.</span></span> <span data-ttu-id="1c248-106">致命的なエラー CS0013 が生成されるため、コンパイラがサイズの制約に達したときに"予期しないエラーがメタデータをファイルに書き込む\<ファイル名\>"し、停止します。</span><span class="sxs-lookup"><span data-stu-id="1c248-106">When the compiler reaches a size constraint it will emit fatal error CS0013 "Unexpected error writing metadata to file \<filename\>" and halt.</span></span>  
  
 <span data-ttu-id="1c248-107">この問題を回避するをお勧めのプロジェクトを超えないように 10 メガバイトしない限り、絶対に必要です。</span><span class="sxs-lookup"><span data-stu-id="1c248-107">To avoid this problem, we recommend that projects not exceed 10 megabytes unless absolutely necessary.</span></span> <span data-ttu-id="1c248-108">なぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1c248-108">Why?</span></span>  
  
-   <span data-ttu-id="1c248-109">小さいプロジェクトは、少数の展開手順があるため、デプロイする可能性のある簡単です。</span><span class="sxs-lookup"><span data-stu-id="1c248-109">Smaller projects are potentially simpler to deploy because there are fewer deployment steps.</span></span> <span data-ttu-id="1c248-110">小さいプロジェクトで、手順より密接に関連する可能性があります--パートナー割引を取引先や Rfp の処理を管理します。</span><span class="sxs-lookup"><span data-stu-id="1c248-110">And with smaller projects the steps are more likely to be closely related -- managing trading partner discounts or handling RFPs.</span></span>  
  
-   <span data-ttu-id="1c248-111">小さいプロジェクトを使用する場合は、バグ、展開の問題、およびその他の問題を分離しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="1c248-111">It is easier to isolate bugs, deployment issues, and other problems when using smaller projects.</span></span> <span data-ttu-id="1c248-112">140 のスキーマと多くのカスタム マップ、およびスクリプト プロジェクト内のバグの検索は、10 個のスキーマといくつかのカスタム マップ、およびスクリプト プロジェクトで 1 つの検索よりも困難になります。</span><span class="sxs-lookup"><span data-stu-id="1c248-112">Finding a bug in a project with 140 schemas and many custom maps and scripts will be more difficult than finding one in a project with only 10 schemas and a few custom maps and scripts.</span></span>  
  
-   <span data-ttu-id="1c248-113">大規模なプロジェクトを小さなプロジェクトに分割することと、複雑さを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="1c248-113">Separating a large project into smaller projects can reduce complexity.</span></span> <span data-ttu-id="1c248-114">小さいプロジェクトより管理しやすいです。</span><span class="sxs-lookup"><span data-stu-id="1c248-114">The smaller projects are more manageable.</span></span>  
  
-   <span data-ttu-id="1c248-115">小さいプロジェクトは高速にコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1c248-115">Smaller projects compile faster.</span></span>  
  
-   <span data-ttu-id="1c248-116">厳密に関連するスキーマを持つ小さなプロジェクトに関連付けられていない多数のスキーマを使用した大規模なプロジェクトを分割することと、パフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c248-116">Splitting a large project with many unrelated schemas into smaller projects with strongly related schemas may result in better performance.</span></span> <span data-ttu-id="1c248-117">これは、アセンブリの一部のみが一度に読み込まれるためにです。</span><span class="sxs-lookup"><span data-stu-id="1c248-117">This is because only some of the assemblies will be loaded at a time.</span></span>  
  
## <a name="avoid-using-the-project-name-as-the-map-type-name"></a><span data-ttu-id="1c248-118">マップの型名としてプロジェクト名を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1c248-118">Avoid using the Project Name as the Map Type Name</span></span>  
 <span data-ttu-id="1c248-119">BizTalk プロジェクトに新しいマップを追加するときに[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]型名としてプロジェクト名を使わないでください。</span><span class="sxs-lookup"><span data-stu-id="1c248-119">When adding a new map to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] do not use the project name as the type name.</span></span> <span data-ttu-id="1c248-120">ような 1 つまたは複数のエラーを生成する場合は、"型名\<名前\>' 型に存在しません"。</span><span class="sxs-lookup"><span data-stu-id="1c248-120">If you do, the compiler will generate one or more errors similar to "The type name \<name\>' does not exist in the type".</span></span>  
  
 <span data-ttu-id="1c248-121">BizTalk プロジェクトからマップの種類の名前を変更するには、ソリューション エクスプ ローラー ウィンドウでマップをクリックしてプロパティ ペインで、型名プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c248-121">To change the type name for a map from within a BizTalk project, click the map in the Solution Explorer pane, then verify the type name property in the Properties pane.</span></span> <span data-ttu-id="1c248-122">同じである場合は、変更に依存する構成を変更することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c248-122">If it is the same, you need to modify it making sure to change any configurations that rely on it.</span></span>  
  
## <a name="visual-studio-team-system-support"></a><span data-ttu-id="1c248-123">Visual Studio Team System のサポート</span><span class="sxs-lookup"><span data-stu-id="1c248-123">Visual Studio Team System Support</span></span>  
 <span data-ttu-id="1c248-124">BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]のすべての機能はサポートしない[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System です。</span><span class="sxs-lookup"><span data-stu-id="1c248-124">BizTalk projects in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] do not directly support all features of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System.</span></span> <span data-ttu-id="1c248-125">ソース管理機能の[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System が BizTalk Server のサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1c248-125">The source control features of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System are supported for BizTalk Server.</span></span> <span data-ttu-id="1c248-126">Visual SourceSafe は追跡と BizTalk プロジェクトの成果物のバージョン管理も完全サポートします。</span><span class="sxs-lookup"><span data-stu-id="1c248-126">Visual SourceSafe is also fully supported for the tracking and versioning of BizTalk project artifacts.</span></span>