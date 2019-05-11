---
title: ビジネス ルール エンジン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Engine
- Business Rules Engine
- Business Rules Engine, rules
- Business Rules Engine, about Business Rules Engine
ms.assetid: 87b38507-9f6d-4863-88a6-9c20f15a4e55
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aea07fd5b73fcc333a94c6d199db1e303fcc310d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357740"
---
# <a name="business-rules-engine"></a><span data-ttu-id="d8ede-102">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="d8ede-102">Business Rules Engine</span></span>
<span data-ttu-id="d8ede-103">ビジネス ルール フレームワークは、Microsoft です。NET 準拠のクラス ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="d8ede-103">The Business Rules Framework is a Microsoft .NET-compliant class library.</span></span> <span data-ttu-id="d8ede-104">任意のビジネス オブジェクト (.NET コンポーネント)、XML ドキュメント、またはデータベース テーブルに、意味的に豊富な高読み取り可能な宣言型ルールをリンクできる効率的な推論エンジンを提供します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-104">It provides an efficient inference engine that can link highly readable, declarative, semantically rich rules to any business objects (.NET components), XML documents, or database tables.</span></span> <span data-ttu-id="d8ede-105">アプリケーション開発者は、.NET オブジェクト、データベース テーブル、および XML ドキュメントに含まれる情報 (ファクト) に対して (小さなルール セット) のビジネス ロジックの小さなのビルディング ブロックからの規則を作成することにより、ビジネス ルールを構築できます。</span><span class="sxs-lookup"><span data-stu-id="d8ede-105">Application developers can build business rules by constructing rules from small building blocks of business logic (small rule sets) that operate on information (facts) contained in .NET objects, database tables, and XML documents.</span></span> <span data-ttu-id="d8ede-106">この設計パターンでは、コードの再利用、デザインの簡潔さ、およびビジネス ロジックのモジュール性を昇格します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-106">This design pattern promotes code reuse, design simplicity, and modularity of business logic.</span></span> <span data-ttu-id="d8ede-107">さらに、ルール エンジンでは、ビジネス アプリケーションの設計とアーキテクチャに強制しません。</span><span class="sxs-lookup"><span data-stu-id="d8ede-107">In addition, the rule engine does not impose on the architecture or design of business applications.</span></span> <span data-ttu-id="d8ede-108">実際には、ルール テクノロジをビジネス アプリケーションに追加するには、ルール エンジンを直接呼び出すことによってまたはそれらを変更することがなく、ビジネス オブジェクトを呼び出す外部ロジックがあることができます。</span><span class="sxs-lookup"><span data-stu-id="d8ede-108">In fact, you can add rule technology to a business application by directly invoking the rule engine, or you can have external logic that invokes your business objects without modifying them.</span></span> <span data-ttu-id="d8ede-109">簡単に言えば、テクノロジにより、開発者を作成し、最小限の労力でアプリケーションを維持します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-109">In short, the technology enables developers to create and maintain applications with minimal effort.</span></span>  
  
 <span data-ttu-id="d8ede-110">ルール ベースのアプリケーションの計画の開発では、最初に、ビジネス プロセスに規則を適合させる方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ede-110">In planning development of a rule-based application, you first need to determine how rules will fit into your business processes.</span></span> <span data-ttu-id="d8ede-111">アプリケーションは、ポリシーのインスタンスを作成し、データや操作を行うのファクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-111">Your application will create an instance of a policy and supply it with data, or facts, on which to operate.</span></span> <span data-ttu-id="d8ede-112">ポリシー オブジェクトは、ルール エンジンをカプセル化し、それを実行するエントリの 1 つのポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-112">The policy object encapsulates the rule engine and provides a single point of entry through which to run it.</span></span>  
  
 <span data-ttu-id="d8ede-113">また、ルールのデザインの開発およびテストを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ede-113">You also will need to plan for the development and testing of your rules design.</span></span> <span data-ttu-id="d8ede-114">デプロイし、ポリシーの更新を行う方法を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ede-114">You must consider how you are going to deploy and update your policies.</span></span> <span data-ttu-id="d8ede-115">ルール エンジンの実行の進行状況を追跡し、現在の状態を監視するが可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8ede-115">You will likely want to track the progress of your rule engine's execution and monitor its current state.</span></span>  
  
 <span data-ttu-id="d8ede-116">ルールの開発を計画するときは、次の手順のアカウントします。</span><span class="sxs-lookup"><span data-stu-id="d8ede-116">Account for the following steps as you plan your rules development:</span></span>  
  
1.  <span data-ttu-id="d8ede-117">ルールをアプリケーションに組み込む方法を計画します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-117">Plan how to incorporate your rules into your application.</span></span>  
  
2.  <span data-ttu-id="d8ede-118">アプリケーション内のルールを表現するビジネス ロジックを特定します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-118">Identify the business logic that you want to represent with rules in your application.</span></span> <span data-ttu-id="d8ede-119">「ビジネス ロジック」という用語は多くの要素を参照してください。ビジネス ロジックの例は、「500 ドル以上の発注書は、マネージャーによって承認する必要があります」です。</span><span class="sxs-lookup"><span data-stu-id="d8ede-119">The term "business logic" can refer to many things; an example of business logic is "Purchase orders for more than five hundred dollars must be approved by a manager."</span></span>  
  
3.  <span data-ttu-id="d8ede-120">ルール要素のデータ ソースを特定します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-120">Identify data sources for your rule elements.</span></span> <span data-ttu-id="d8ede-121">必要に応じて定義し、ボキャブラリ (基になるバインディングを表すドメイン固有用語) を発行できます。</span><span class="sxs-lookup"><span data-stu-id="d8ede-121">You can optionally define and publish vocabularies (domain-specific nomenclature that represents underlying bindings).</span></span>  
  
4.  <span data-ttu-id="d8ede-122">データ バインディング、直接またはボキャブラリの定義からルールを定義し、そこから、ビジネス ロジックを表すポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-122">Define rules from vocabulary definitions or directly from data bindings, and from them compose a policy that represents your business logic.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8ede-123">ルールに適用する前に、ボキャブラリを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ede-123">Vocabularies must be published before they can be applied in rules.</span></span>  
  
5.  <span data-ttu-id="d8ede-124">テストおよびデバッグのサンプルのファクトを持つポリシー。</span><span class="sxs-lookup"><span data-stu-id="d8ede-124">Test and debug the policy with sample facts.</span></span> <span data-ttu-id="d8ede-125">ビジネス ルール作成ツールでポリシーのテスト機能を使用するかを使用して、**ポリシー**または**PolicyTester**アプリケーション、コマンドライン プログラム、またはオーケストレーションから実行するクラス。</span><span class="sxs-lookup"><span data-stu-id="d8ede-125">You can either use the Test Policy functionality in the Business Rule Composer or use **Policy** or **PolicyTester** classes to execute from an application, command-line program, or orchestration.</span></span>  
  
6.  <span data-ttu-id="d8ede-126">ポリシーのバージョンをルール ストアに公開します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-126">Publish the policy version to the rule store.</span></span>  
  
7.  <span data-ttu-id="d8ede-127">ポリシーのバージョンをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="d8ede-127">Deploy the policy version.</span></span>  
  
8.  <span data-ttu-id="d8ede-128">インスタンスを作成し、ホスト アプリケーションでは、短期間のファクト リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-128">Instantiate and build the short-term fact list in the hosting application.</span></span> <span data-ttu-id="d8ede-129">使用して、**ルールの呼び出し**ビジネス ポリシーを実行またはプログラムによって、ホスト アプリケーションでポリシーのバージョンのインスタンスを作成するためのオーケストレーションの図形。</span><span class="sxs-lookup"><span data-stu-id="d8ede-129">Use the **Call Rules** shape in an orchestration to execute your business policy or programmatically instantiate a policy version in your hosting application.</span></span>  
  
9. <span data-ttu-id="d8ede-130">監視および追跡ルールの実行に応じて。</span><span class="sxs-lookup"><span data-stu-id="d8ede-130">Monitor and track rule execution as needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8ede-131">既定の追跡インターセプタは、オーケストレーションと連携します。</span><span class="sxs-lookup"><span data-stu-id="d8ede-131">The default tracking interceptor works with orchestrations.</span></span> <span data-ttu-id="d8ede-132">ホスト アプリケーションが、オーケストレーションではない場合を書き込む必要があります独自の追跡情報インターセプターこれを行う。</span><span class="sxs-lookup"><span data-stu-id="d8ede-132">If your hosting application is not an orchestration, you must write your own tracking interceptor to do this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8ede-133">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d8ede-133">In This Section</span></span>  
  
-   [<span data-ttu-id="d8ede-134">ルール</span><span class="sxs-lookup"><span data-stu-id="d8ede-134">Rules</span></span>](../core/rules.md)  
  
-   [<span data-ttu-id="d8ede-135">ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8ede-135">Policies</span></span>](../core/policies.md)  
  
-   [<span data-ttu-id="d8ede-136">ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="d8ede-136">Vocabularies</span></span>](../core/vocabularies.md)  
  
-   [<span data-ttu-id="d8ede-137">ビジネス ルール フレームワークのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d8ede-137">Business Rules Framework Architecture</span></span>](../core/business-rules-framework-architecture.md)  
  
-   [<span data-ttu-id="d8ede-138">ファクト</span><span class="sxs-lookup"><span data-stu-id="d8ede-138">Facts</span></span>](../core/facts.md)  
  
-   [<span data-ttu-id="d8ede-139">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="d8ede-139">Rule Engine</span></span>](../core/rule-engine.md)