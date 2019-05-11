---
title: アプリケーションへの成果物の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9b5e92e-2e55-41d7-9959-f62753bbeb04
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ac647201a834d90d745564076b040954c1c3667
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401418"
---
# <a name="adding-artifacts-to-an-application"></a><span data-ttu-id="c98d2-102">成果物をアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c98d2-102">Adding Artifacts to an Application</span></span>
<span data-ttu-id="c98d2-103">追加できますと送信などの成果物を構成し、受信ポート、受信場所、オーケストレーション、管理を使用してコンソールします。</span><span class="sxs-lookup"><span data-stu-id="c98d2-103">You can add and configure artifacts, such as send and receive ports, receive locations, and orchestrations, by using the Administration console.</span></span> <span data-ttu-id="c98d2-104">バインド ファイルを生成します。 また、異なる環境にアプリケーションをインポートするごとに異なるバインドを適用する場合、アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c98d2-104">You can also generate binding files and add them to the application if you want to apply different bindings for the different environments that you will import the application into.</span></span>  
  
 <span data-ttu-id="c98d2-105">さらに追加することができます (通常は BizTalk Server 以外の) スクリプト、証明書、およびアプリケーションのリソース ノードの下に、Readme ファイルなどの成果物。</span><span class="sxs-lookup"><span data-stu-id="c98d2-105">You can add additional (typically non-BizTalk Server) artifacts, such as scripts, certificates, and Readme files, to the application under the Resources node.</span></span> <span data-ttu-id="c98d2-106">これを行うには、管理コンソールまたは BTSTask を使用します。</span><span class="sxs-lookup"><span data-stu-id="c98d2-106">To do so, use the Administration console or BTSTask.</span></span>  
  
 <span data-ttu-id="c98d2-107">成果物の詳細については、次を参照してください[成果物を追加または作成する方法](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)、[管理成果物](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)と[バインド ファイルとアプリケーションの展開。](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).</span><span class="sxs-lookup"><span data-stu-id="c98d2-107">For more information about artifacts, see [How to Create or Add an Artifact](http://go.microsoft.com/fwlink/?LinkID=154724) (http://go.microsoft.com/fwlink/?LinkID=154724), [Managing Artifacts](http://go.microsoft.com/fwlink/?LinkID=154725) (http://go.microsoft.com/fwlink/?LinkID=154725) and [Binding Files and Application Deployment](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).</span></span>  
  
## <a name="factoring-artifacts-into-multiple-biztalk-applications"></a><span data-ttu-id="c98d2-108">成果物を複数の BizTalk アプリケーションにファクタリング</span><span class="sxs-lookup"><span data-stu-id="c98d2-108">Factoring Artifacts into Multiple BizTalk Applications</span></span>  
 <span data-ttu-id="c98d2-109">開発プロセス中に、利便性のためにアセンブリを単一のアプリケーションに展開することがあります。</span><span class="sxs-lookup"><span data-stu-id="c98d2-109">During the development process, you may have deployed your assemblies into a single application for convenience.</span></span> <span data-ttu-id="c98d2-110">さまざまな理由により、実稼働環境に展開する前にアセンブリを複数のアプリケーションにファクタリングする必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c98d2-110">For various reasons, you may want to factor the artifacts into multiple applications before they are deployed into production.</span></span>  
  
 <span data-ttu-id="c98d2-111">を展開する前に、アセンブリのファクタリングの徹底的な分析を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c98d2-111">Before deploying, you should perform an in-depth analysis of the factoring of an assembly.</span></span> <span data-ttu-id="c98d2-112">かどうかを実行するありませんファクタリング、完全なファクタリング、または最適なファクタリングを決定します。</span><span class="sxs-lookup"><span data-stu-id="c98d2-112">Determine whether you should perform No factoring, Full factoring, or Optimal factoring.</span></span>  
  
 <span data-ttu-id="c98d2-113">**なしのファクタリング**</span><span class="sxs-lookup"><span data-stu-id="c98d2-113">**No Factoring**</span></span>  
  
 <span data-ttu-id="c98d2-114">すべての BizTalk アイテムは、1 つのアセンブリには。</span><span class="sxs-lookup"><span data-stu-id="c98d2-114">All BizTalk artifacts are in one assembly.</span></span> <span data-ttu-id="c98d2-115">これは、最も理解し、デプロイしますが、最小限の柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="c98d2-115">This is the easiest to understand and deploy, but provides the least amount of flexibility.</span></span>  
  
 <span data-ttu-id="c98d2-116">**完全なファクタリング**</span><span class="sxs-lookup"><span data-stu-id="c98d2-116">**Full Factoring**</span></span>  
  
 <span data-ttu-id="c98d2-117">各 BizTalk アイテムが、独自のアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="c98d2-117">Each BizTalk artifact is in its own assembly.</span></span> <span data-ttu-id="c98d2-118">これにより、最高の柔軟性を提供しますが、最も複雑なデプロイを理解するには。</span><span class="sxs-lookup"><span data-stu-id="c98d2-118">This provides the most flexibility, but is the most complex to deploy and understand.</span></span>  
  
 <span data-ttu-id="c98d2-119">**最適なファクタリング**</span><span class="sxs-lookup"><span data-stu-id="c98d2-119">**Optimal Factoring**</span></span>  
  
 <span data-ttu-id="c98d2-120">No ファクタリングと、BizTalk アプリケーションの詳細な分析に基づく完全なファクタリングが最適なファクタリングします。</span><span class="sxs-lookup"><span data-stu-id="c98d2-120">Optimal factoring falls between No Factoring and Full Factoring based on in-depth analysis of your BizTalk applications.</span></span> <span data-ttu-id="c98d2-121">バージョン管理、に加えては、BizTalk ホストの設計を簡単に実装するこのできます。</span><span class="sxs-lookup"><span data-stu-id="c98d2-121">In addition to versioning, this allows you to more easily implement your BizTalk host design.</span></span> <span data-ttu-id="c98d2-122">これは、BizTalk アイテム間の関係を探すことによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="c98d2-122">This is achieved by looking for relationships among BizTalk artifacts.</span></span> <span data-ttu-id="c98d2-123">可能であれば、常に同じアセンブリ内でまとめてバージョン管理される成果物を配置します。</span><span class="sxs-lookup"><span data-stu-id="c98d2-123">If possible, put artifacts that are always versioned together in the same assembly.</span></span> <span data-ttu-id="c98d2-124">成果物の独立したバージョン管理が必要な場合は、異なるアセンブリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c98d2-124">If independent versioning of the artifacts is required, then they must be put in different assemblies.</span></span> <span data-ttu-id="c98d2-125">これは実現するレベルを取り除いたものです。</span><span class="sxs-lookup"><span data-stu-id="c98d2-125">This is the level of factoring that you want to achieve.</span></span>