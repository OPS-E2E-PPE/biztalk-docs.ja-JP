---
title: BizTalk プロジェクトを作成する際の考慮事項 |Microsoft ドキュメント
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
ms.openlocfilehash: f0302d2329f848352f55d15f0c6e21bbdf72b0ca
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005955"
---
# <a name="considerations-when-creating-biztalk-projects"></a><span data-ttu-id="87bc6-102">BizTalk プロジェクトを作成する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="87bc6-102">Considerations When Creating BizTalk Projects</span></span>
<span data-ttu-id="87bc6-103">ここでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して BizTalk プロジェクトを作成する際に考慮すべき情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="87bc6-103">This section provides information that you should take into consideration when creating BizTalk projects using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="avoid-compilation-errors-caused-by-projects-that-are-too-large"></a><span data-ttu-id="87bc6-104">サイズの大きなプロジェクトが原因となるコンパイル エラーの回避</span><span class="sxs-lookup"><span data-stu-id="87bc6-104">Avoid compilation errors caused by projects that are too large</span></span>  
 <span data-ttu-id="87bc6-105">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コンパイラは、75 MB を超えるアセンブリのプロジェクトを正しくコンパイルできません。</span><span class="sxs-lookup"><span data-stu-id="87bc6-105">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler will not successfully compile a project if it would result in an assembly larger than 75 megabytes.</span></span> <span data-ttu-id="87bc6-106">致命的なエラー CS0013 が生成されるため、コンパイラがサイズ制限に達すると"メタデータをファイルに書き込み予期しないエラーが発生\<filename\>"され、停止します。</span><span class="sxs-lookup"><span data-stu-id="87bc6-106">When the compiler reaches a size constraint it will emit fatal error CS0013 "Unexpected error writing metadata to file \<filename\>" and halt.</span></span>  
  
 <span data-ttu-id="87bc6-107">この問題を回避するには、どうしても必要な場合を除き、プロジェクトが 10 MB を超えないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="87bc6-107">To avoid this problem, we recommend that projects not exceed 10 megabytes unless absolutely necessary.</span></span> <span data-ttu-id="87bc6-108">なぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="87bc6-108">Why?</span></span>  
  
-   <span data-ttu-id="87bc6-109">小さいプロジェクトは、展開手順が少ないので、展開が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="87bc6-109">Smaller projects are potentially simpler to deploy because there are fewer deployment steps.</span></span> <span data-ttu-id="87bc6-110">また、小さいプロジェクトを使用すると、相互の関連性が高い手順 (取引先の割引や見積依頼書の処理など) が多くなります。</span><span class="sxs-lookup"><span data-stu-id="87bc6-110">And with smaller projects the steps are more likely to be closely related -- managing trading partner discounts or handling RFPs.</span></span>  
  
-   <span data-ttu-id="87bc6-111">小さいプロジェクトでは、バグ、展開の問題、および他の問題を見分けることが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="87bc6-111">It is easier to isolate bugs, deployment issues, and other problems when using smaller projects.</span></span> <span data-ttu-id="87bc6-112">スキーマの数が 140 あり、使用するカスタム マップやカスタム スクリプトの数が多いプロジェクトのバグを発見することは、スキーマの数が 10 で、使用するカスタム マップやカスタム スクリプトの数が少ないプロジェクトのバグを発見するよりも困難です。</span><span class="sxs-lookup"><span data-stu-id="87bc6-112">Finding a bug in a project with 140 schemas and many custom maps and scripts will be more difficult than finding one in a project with only 10 schemas and a few custom maps and scripts.</span></span>  
  
-   <span data-ttu-id="87bc6-113">大きなプロジェクトを小さなプロジェクトに分割すると、複雑さを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="87bc6-113">Separating a large project into smaller projects can reduce complexity.</span></span> <span data-ttu-id="87bc6-114">小さいプロジェクトの方が管理が簡単です。</span><span class="sxs-lookup"><span data-stu-id="87bc6-114">The smaller projects are more manageable.</span></span>  
  
-   <span data-ttu-id="87bc6-115">小さいプロジェクトは、高速にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="87bc6-115">Smaller projects compile faster.</span></span>  
  
-   <span data-ttu-id="87bc6-116">関連性のない多くのスキーマを持つ大きなプロジェクトを、関連性の高いスキーマを持つ小さなプロジェクトに分割すると、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="87bc6-116">Splitting a large project with many unrelated schemas into smaller projects with strongly related schemas may result in better performance.</span></span> <span data-ttu-id="87bc6-117">これは、ため、一度に読み込まれるアセンブリの一部のみです。</span><span class="sxs-lookup"><span data-stu-id="87bc6-117">This is because only some of the assemblies will be loaded at a time.</span></span>  
  
## <a name="avoid-using-the-project-name-as-the-map-type-name"></a><span data-ttu-id="87bc6-118">マップの型名としてプロジェクト名を使用することの回避</span><span class="sxs-lookup"><span data-stu-id="87bc6-118">Avoid using the Project Name as the Map Type Name</span></span>  
 <span data-ttu-id="87bc6-119">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で新しいマップを BizTalk プロジェクトに追加する際に、マップの型名としてプロジェクト名を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="87bc6-119">When adding a new map to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] do not use the project name as the type name.</span></span> <span data-ttu-id="87bc6-120">コンパイラはのような 1 つまたは複数のエラーを生成する場合、"型名\<名前\>' 型に存在しません"です。</span><span class="sxs-lookup"><span data-stu-id="87bc6-120">If you do, the compiler will generate one or more errors similar to "The type name \<name\>' does not exist in the type".</span></span>  
  
 <span data-ttu-id="87bc6-121">BizTalk プロジェクトからマップの型名を変更するには、[ソリューション エクスプローラー] ペインのマップをクリックし、[プロパティ] ペインの "型名" プロパティを確認してください。</span><span class="sxs-lookup"><span data-stu-id="87bc6-121">To change the type name for a map from within a BizTalk project, click the map in the Solution Explorer pane, then verify the type name property in the Properties pane.</span></span> <span data-ttu-id="87bc6-122">マップの型名が同じ場合、型名を修正して、型名に依存する構成を変更してください。</span><span class="sxs-lookup"><span data-stu-id="87bc6-122">If it is the same, you need to modify it making sure to change any configurations that rely on it.</span></span>  
  
## <a name="visual-studio-team-system-support"></a><span data-ttu-id="87bc6-123">Visual Studio Team System のサポート</span><span class="sxs-lookup"><span data-stu-id="87bc6-123">Visual Studio Team System Support</span></span>  
 <span data-ttu-id="87bc6-124">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の BizTalk プロジェクトでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System のすべての機能が直接サポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="87bc6-124">BizTalk projects in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] do not directly support all features of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System.</span></span> <span data-ttu-id="87bc6-125">ソース管理機能[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System は、BizTalk Server のサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87bc6-125">The source control features of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System are supported for BizTalk Server.</span></span> <span data-ttu-id="87bc6-126">また、Visual SourceSafe も、BizTalk プロジェクト アイテムの追跡とバージョン管理で完全にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="87bc6-126">Visual SourceSafe is also fully supported for the tracking and versioning of BizTalk project artifacts.</span></span>