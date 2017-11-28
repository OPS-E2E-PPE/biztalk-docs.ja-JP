---
title: "成果物をアプリケーションに追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9b5e92e-2e55-41d7-9959-f62753bbeb04
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c08fa95dddad06efb2c51d93df56b757ae4caca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-artifacts-to-an-application"></a><span data-ttu-id="4e87b-102">成果物をアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4e87b-102">Adding Artifacts to an Application</span></span>
<span data-ttu-id="4e87b-103">追加し送信などのアイテムを構成して受信ポート、受信場所、オーケストレーションを管理を使用してコンソールします。</span><span class="sxs-lookup"><span data-stu-id="4e87b-103">You can add and configure artifacts, such as send and receive ports, receive locations, and orchestrations, by using the Administration console.</span></span> <span data-ttu-id="4e87b-104">バインド ファイルを生成し、アプリケーションをインポートする、さまざまな環境ごとに異なるバインドを適用する場合、アプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="4e87b-104">You can also generate binding files and add them to the application if you want to apply different bindings for the different environments that you will import the application into.</span></span>  
  
 <span data-ttu-id="4e87b-105">追加することができます (通常 BizTalk Server 以外の) スクリプト、証明書、およびリソース ノードの下のアプリケーションに、Readme ファイルなどのアイテムです。</span><span class="sxs-lookup"><span data-stu-id="4e87b-105">You can add additional (typically non-BizTalk Server) artifacts, such as scripts, certificates, and Readme files, to the application under the Resources node.</span></span> <span data-ttu-id="4e87b-106">これを行うには、管理コンソールまたは BTSTask を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e87b-106">To do so, use the Administration console or BTSTask.</span></span>  
  
 <span data-ttu-id="4e87b-107">成果物の詳細については、次を参照してください[成果物を追加または作成する方法](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?。LinkID = 154724)、[成果物の管理](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID = 154725) および[バインド ファイルとアプリケーションの配置](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID = 154726)。</span><span class="sxs-lookup"><span data-stu-id="4e87b-107">For more information about artifacts, see [How to Create or Add an Artifact](http://go.microsoft.com/fwlink/?LinkID=154724) (http://go.microsoft.com/fwlink/?LinkID=154724), [Managing Artifacts](http://go.microsoft.com/fwlink/?LinkID=154725) (http://go.microsoft.com/fwlink/?LinkID=154725) and [Binding Files and Application Deployment](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).</span></span>  
  
## <a name="factoring-artifacts-into-multiple-biztalk-applications"></a><span data-ttu-id="4e87b-108">成果物の複数の BizTalk アプリケーションにファクタリング</span><span class="sxs-lookup"><span data-stu-id="4e87b-108">Factoring Artifacts into Multiple BizTalk Applications</span></span>  
 <span data-ttu-id="4e87b-109">開発プロセス中に、利便性のためにアセンブリを単一のアプリケーションに展開することがあります。</span><span class="sxs-lookup"><span data-stu-id="4e87b-109">During the development process, you may have deployed your assemblies into a single application for convenience.</span></span> <span data-ttu-id="4e87b-110">さまざまな理由により、実稼働環境に展開する前にアセンブリを複数のアプリケーションにファクタリングする必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4e87b-110">For various reasons, you may want to factor the artifacts into multiple applications before they are deployed into production.</span></span>  
  
 <span data-ttu-id="4e87b-111">を展開する前に、アセンブリのファクタリングの詳細な分析を実行してください。</span><span class="sxs-lookup"><span data-stu-id="4e87b-111">Before deploying, you should perform an in-depth analysis of the factoring of an assembly.</span></span> <span data-ttu-id="4e87b-112">かどうか行う必要がありますいないファクタリング、完全ファクタリング、または最適なファクタリングを決定します。</span><span class="sxs-lookup"><span data-stu-id="4e87b-112">Determine whether you should perform No factoring, Full factoring, or Optimal factoring.</span></span>  
  
 <span data-ttu-id="4e87b-113">**ありませんファクタリング**</span><span class="sxs-lookup"><span data-stu-id="4e87b-113">**No Factoring**</span></span>  
  
 <span data-ttu-id="4e87b-114">すべての BizTalk アイテムは、1 つのアセンブリでです。</span><span class="sxs-lookup"><span data-stu-id="4e87b-114">All BizTalk artifacts are in one assembly.</span></span> <span data-ttu-id="4e87b-115">これは、最も理解および展開するが最低限の柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e87b-115">This is the easiest to understand and deploy, but provides the least amount of flexibility.</span></span>  
  
 <span data-ttu-id="4e87b-116">**完全ファクタリング**</span><span class="sxs-lookup"><span data-stu-id="4e87b-116">**Full Factoring**</span></span>  
  
 <span data-ttu-id="4e87b-117">各 BizTalk 成果物は、独自のアセンブリでです。</span><span class="sxs-lookup"><span data-stu-id="4e87b-117">Each BizTalk artifact is in its own assembly.</span></span> <span data-ttu-id="4e87b-118">これは、最大限の柔軟性を提供が複雑では、最もを展開し、理解します。</span><span class="sxs-lookup"><span data-stu-id="4e87b-118">This provides the most flexibility, but is the most complex to deploy and understand.</span></span>  
  
 <span data-ttu-id="4e87b-119">**最適なファクタリング**</span><span class="sxs-lookup"><span data-stu-id="4e87b-119">**Optimal Factoring**</span></span>  
  
 <span data-ttu-id="4e87b-120">最適なファクタリングいいえファクタリングと、BizTalk アプリケーションの詳細な分析に基づく完全ファクタリングの間に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4e87b-120">Optimal factoring falls between No Factoring and Full Factoring based on in-depth analysis of your BizTalk applications.</span></span> <span data-ttu-id="4e87b-121">バージョン管理、に加えてこれにより、BizTalk ホストの設計を簡単に実装します。</span><span class="sxs-lookup"><span data-stu-id="4e87b-121">In addition to versioning, this allows you to more easily implement your BizTalk host design.</span></span> <span data-ttu-id="4e87b-122">これは、BizTalk アイテム間の関係を探すことにより実現されます。</span><span class="sxs-lookup"><span data-stu-id="4e87b-122">This is achieved by looking for relationships among BizTalk artifacts.</span></span> <span data-ttu-id="4e87b-123">可能であれば、同じアセンブリ内で一緒にバージョン管理は、常にアイテムを配置します。</span><span class="sxs-lookup"><span data-stu-id="4e87b-123">If possible, put artifacts that are always versioned together in the same assembly.</span></span> <span data-ttu-id="4e87b-124">成果物の独立したバージョンが必要な場合は、異なるアセンブリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e87b-124">If independent versioning of the artifacts is required, then they must be put in different assemblies.</span></span> <span data-ttu-id="4e87b-125">これは、達成したいをファクタリングのレベルです。</span><span class="sxs-lookup"><span data-stu-id="4e87b-125">This is the level of factoring that you want to achieve.</span></span>