---
title: "ビジネス ルール エンジン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Engine
- Business Rules Engine
- Business Rules Engine, rules
- Business Rules Engine, about Business Rules Engine
ms.assetid: 87b38507-9f6d-4863-88a6-9c20f15a4e55
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d99cff10324f1cf1ba97d99431524474ed5f039b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="business-rules-engine"></a><span data-ttu-id="3fdbc-102">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="3fdbc-102">Business Rules Engine</span></span>
<span data-ttu-id="3fdbc-103">ビジネス ルール フレームワークは、Microsoft .NET 準拠のクラス ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-103">The Business Rules Framework is a Microsoft .NET-compliant class library.</span></span> <span data-ttu-id="3fdbc-104">このフレームワークは、非常に判読しやすく意味論的にも充実した宣言型のルールを、任意のビジネス オブジェクト (.NET コンポーネント)、XML ドキュメント、またはデータベース テーブルにリンクできる効率的な推論エンジンを提供します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-104">It provides an efficient inference engine that can link highly readable, declarative, semantically rich rules to any business objects (.NET components), XML documents, or database tables.</span></span> <span data-ttu-id="3fdbc-105">アプリケーション開発者は、ビジネス ロジックの小さな構成要素 (小さなルール セット) を基にしてルールを作成することによって、ビジネス ルールを構築できます。ルールは、.NET オブジェクト、データベース テーブル、および XML ドキュメントに含まれている情報 (ファクト) に対して適用されます。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-105">Application developers can build business rules by constructing rules from small building blocks of business logic (small rule sets) that operate on information (facts) contained in .NET objects, database tables, and XML documents.</span></span> <span data-ttu-id="3fdbc-106">このデザイン パターンによって、コードの再利用、デザインの簡潔化、およびビジネス ロジックのモジュール化が促進されます。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-106">This design pattern promotes code reuse, design simplicity, and modularity of business logic.</span></span> <span data-ttu-id="3fdbc-107">また、ルール エンジンを利用することで、ビジネス アプリケーションのアーキテクチャやデザインに制約が生じることはありません。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-107">In addition, the rule engine does not impose on the architecture or design of business applications.</span></span> <span data-ttu-id="3fdbc-108">実際、ルール エンジンを直接呼び出してルール テクノロジをビジネス アプリケーションに追加することも、ビジネス オブジェクトを変更せずにこれらを呼び出す外部ロジックを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-108">In fact, you can add rule technology to a business application by directly invoking the rule engine, or you can have external logic that invokes your business objects without modifying them.</span></span> <span data-ttu-id="3fdbc-109">つまり、このテクノロジによって、開発者は最小限の作業でアプリケーションを作成および保守できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-109">In short, the technology enables developers to create and maintain applications with minimal effort.</span></span>  
  
 <span data-ttu-id="3fdbc-110">ルールベースのアプリケーション開発を計画するときは、そのルールをビジネス プロセスにどう適合させるかを決めておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-110">In planning development of a rule-based application, you first need to determine how rules will fit into your business processes.</span></span> <span data-ttu-id="3fdbc-111">アプリケーション側では、ポリシーのインスタンスを作成し、操作の対象となるデータ、つまりファクトをポリシーに渡します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-111">Your application will create an instance of a policy and supply it with data, or facts, on which to operate.</span></span> <span data-ttu-id="3fdbc-112">ポリシー オブジェクトは、ルール エンジンをカプセル化して、実行ポイントを 1 か所にまとめます。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-112">The policy object encapsulates the rule engine and provides a single point of entry through which to run it.</span></span>  
  
 <span data-ttu-id="3fdbc-113">ルール デザインの開発とテストも計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-113">You also will need to plan for the development and testing of your rules design.</span></span> <span data-ttu-id="3fdbc-114">ポリシーを展開および更新する方法を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-114">You must consider how you are going to deploy and update your policies.</span></span> <span data-ttu-id="3fdbc-115">ルール エンジン実行の進捗状況を追跡し、現在の状態を監視する必要も生じるのが普通です。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-115">You will likely want to track the progress of your rule engine's execution and monitor its current state.</span></span>  
  
 <span data-ttu-id="3fdbc-116">ルールの開発を計画する際は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-116">Account for the following steps as you plan your rules development:</span></span>  
  
1.  <span data-ttu-id="3fdbc-117">アプリケーションにルールを組み込む方法を検討します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-117">Plan how to incorporate your rules into your application.</span></span>  
  
2.  <span data-ttu-id="3fdbc-118">アプリケーション内で、ルールによって表すビジネス ロジックを特定します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-118">Identify the business logic that you want to represent with rules in your application.</span></span> <span data-ttu-id="3fdbc-119">"ビジネス ロジック" という語が示す意味はさまざまです。たとえば、"500 ドルを超える注文書にはマネージャーの承認が必要である" もビジネス ロジックです。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-119">The term "business logic" can refer to many things; an example of business logic is "Purchase orders for more than five hundred dollars must be approved by a manager."</span></span>  
  
3.  <span data-ttu-id="3fdbc-120">ルール要素のデータ ソースを特定します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-120">Identify data sources for your rule elements.</span></span> <span data-ttu-id="3fdbc-121">オプションで、ボキャブラリ (基になるバインドを表すドメイン固有の命名規則) を定義し、公開できます。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-121">You can optionally define and publish vocabularies (domain-specific nomenclature that represents underlying bindings).</span></span>  
  
4.  <span data-ttu-id="3fdbc-122">ルールをボキャブラリ定義から定義するか、データ バインドから直接定義し、それによってビジネス ロジックを表すポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-122">Define rules from vocabulary definitions or directly from data bindings, and from them compose a policy that represents your business logic.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3fdbc-123">ボキャブラリは、ルールに適用する前に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-123">Vocabularies must be published before they can be applied in rules.</span></span>  
  
5.  <span data-ttu-id="3fdbc-124">サンプルのファクトを使用してポリシーをテストし、デバッグします。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-124">Test and debug the policy with sample facts.</span></span> <span data-ttu-id="3fdbc-125">ビジネス ルール作成ツールでポリシーのテスト機能を使用するか、使用することができます**ポリシー**または**PolicyTester**アプリケーション、コマンドライン プログラム、またはオーケストレーションから実行するクラス。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-125">You can either use the Test Policy functionality in the Business Rule Composer or use **Policy** or **PolicyTester** classes to execute from an application, command-line program, or orchestration.</span></span>  
  
6.  <span data-ttu-id="3fdbc-126">ポリシーのバージョンをルール ストアに公開します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-126">Publish the policy version to the rule store.</span></span>  
  
7.  <span data-ttu-id="3fdbc-127">ポリシーのバージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-127">Deploy the policy version.</span></span>  
  
8.  <span data-ttu-id="3fdbc-128">ホスト アプリケーションに短期間のファクト リストをインスタンス化し、構築します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-128">Instantiate and build the short-term fact list in the hosting application.</span></span> <span data-ttu-id="3fdbc-129">使用して、**ルールの呼び出し**ビジネス ポリシーを実行またはプログラムによって、ホスト アプリケーションでポリシーのバージョンのインスタンスを作成するためのオーケストレーションの図形です。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-129">Use the **Call Rules** shape in an orchestration to execute your business policy or programmatically instantiate a policy version in your hosting application.</span></span>  
  
9. <span data-ttu-id="3fdbc-130">必要に応じてルールの実行を監視および追跡します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-130">Monitor and track rule execution as needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3fdbc-131">既定の追跡情報インターセプターはオーケストレーションと連携して機能します。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-131">The default tracking interceptor works with orchestrations.</span></span> <span data-ttu-id="3fdbc-132">ホスト アプリケーションがオーケストレーションではない場合は、独自の追跡情報インターセプターを作成して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fdbc-132">If your hosting application is not an orchestration, you must write your own tracking interceptor to do this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3fdbc-133">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3fdbc-133">In This Section</span></span>  
  
-   [<span data-ttu-id="3fdbc-134">ルール</span><span class="sxs-lookup"><span data-stu-id="3fdbc-134">Rules</span></span>](../core/rules.md)  
  
-   [<span data-ttu-id="3fdbc-135">ポリシー</span><span class="sxs-lookup"><span data-stu-id="3fdbc-135">Policies</span></span>](../core/policies.md)  
  
-   [<span data-ttu-id="3fdbc-136">ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="3fdbc-136">Vocabularies</span></span>](../core/vocabularies.md)  
  
-   [<span data-ttu-id="3fdbc-137">ビジネス ルール フレームワークのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="3fdbc-137">Business Rules Framework Architecture</span></span>](../core/business-rules-framework-architecture.md)  
  
-   [<span data-ttu-id="3fdbc-138">ファクト</span><span class="sxs-lookup"><span data-stu-id="3fdbc-138">Facts</span></span>](../core/facts.md)  
  
-   [<span data-ttu-id="3fdbc-139">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="3fdbc-139">Rule Engine</span></span>](../core/rule-engine.md)