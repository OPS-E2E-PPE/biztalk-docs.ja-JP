---
title: ビジネス ルール フレームワークのアーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, caching
- Business Rules Framework, Rule Engine Update service
- rule store [Business Rules Framework]
- Policy class [Business Rules Engine]
- Business Rules Framework, architecture
- Business Rules Framework, RuleEngine class
- Business Rules Framework, Policy class
- Business Rules Framework, authoring tools
- RuleEngine class [Business Rules Engine]
- caching, Business Rules Framework
- Business Rules Framework, fact retrievers
- architecture, Business Rules Framework
- Business Rules Framework, rule store
ms.assetid: f5570cca-7664-4180-af9c-64ef90a0022b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4b23723d01a29606637689966cc07246cdfbc1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233874"
---
# <a name="business-rules-framework-architecture"></a><span data-ttu-id="5a2f7-102">ビジネス ルール フレームワークのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="5a2f7-102">Business Rules Framework Architecture</span></span>
<span data-ttu-id="5a2f7-103">次の図に、ビジネス ルール フレームワークのコンポーネント アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-103">The following figure shows the component architecture of the Business Rules Framework.</span></span>  
  
 <span data-ttu-id="5a2f7-104">![ビジネス ルール フレームワーク コンポーネント アーキテクチャ](../core/media/ebiz-rulesarch-new.gif "ebiz_rulesarch_new")</span><span class="sxs-lookup"><span data-stu-id="5a2f7-104">![Business Rules Framework component architecture](../core/media/ebiz-rulesarch-new.gif "ebiz_rulesarch_new")</span></span>  
<span data-ttu-id="5a2f7-105">Microsoft ビジネス ルール フレームワークのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="5a2f7-105">Microsoft Business Rules Framework Architecture</span></span>  
  
 <span data-ttu-id="5a2f7-106">ここでは、このフレームワークの一部のコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-106">Some of the components of the framework are described in the following paragraphs.</span></span>  
  
## <a name="policy-class"></a><span data-ttu-id="5a2f7-107">Policy クラス</span><span class="sxs-lookup"><span data-stu-id="5a2f7-107">Policy Class</span></span>  
 <span data-ttu-id="5a2f7-108">A**ポリシー**オブジェクトは、ビジネス ポリシーの 1 つのインスタンスと、ルール ベースのアプリケーションによって使用されるインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-108">A **Policy** object is a single instance of a business policy, and provides the interface that is used by rule-based applications.</span></span> <span data-ttu-id="5a2f7-109">このオブジェクトで提供される抽象化により、ルール ストアの場所をアプリケーション開発者が配慮する必要がなくなり、ルール ストアからのルール セットの抽出、基になるルール エンジンのインスタンスのインスタンス化、長期間のファクトのエンジンへのアサートが可能になります。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-109">It provides an abstraction that frees the application developer from concern about the location of the rule store, extracting rule sets from the rule store, instantiating instances of the underlying rule engine, and ensuring that long-term facts are asserted into the engine.</span></span> <span data-ttu-id="5a2f7-110">ルール ベースのアプリケーションを多くのシナリオでの同時実行のインスタンスを使用して、**ポリシー**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-110">In many scenarios, a rule-based application uses concurrent instances of the **Policy** object.</span></span> <span data-ttu-id="5a2f7-111">これらの同時インスタンスでは、同一ポリシーを表すことも、同一ポリシーの複数バージョンを表すことも、異種ポリシーの複数バージョンを表すこともあります。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-111">These concurrent instances can represent the same policy, different versions of the same policy, or different versions of different policies.</span></span>  
  
## <a name="ruleengine-class"></a><span data-ttu-id="5a2f7-112">RuleEngine クラス</span><span class="sxs-lookup"><span data-stu-id="5a2f7-112">RuleEngine Class</span></span>  
 <span data-ttu-id="5a2f7-113">**RuleEngine**オブジェクトはビジネス ポリシーの実行エンジンとして機能します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-113">The **RuleEngine** object serves as the execution engine for business policies.</span></span> <span data-ttu-id="5a2f7-114">このオブジェクトは、3 つのプラグイン コンポーネント (変換者、推論エンジン、および追跡インターセプター) を実装に使用します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-114">It uses three plug-in components (translator, inference engine, and tracking interceptor) for implementation.</span></span> <span data-ttu-id="5a2f7-115">A **RuleEngine**オブジェクトは、 **RuleSet**入力として、ビジネス ポリシーを表すオブジェクト、トランスレーター、推論エンジン、およびルールを実装するセット用に構成された追跡情報インターセプターを使用して、ルールによって定義されたビジネス ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-115">A **RuleEngine** object takes a **RuleSet** object representing a business policy as input and uses the translator, inference engine, and tracking interceptor configured for the rule set to implement the business policy defined by the rule set.</span></span>  
  
## <a name="fact-retriever"></a><span data-ttu-id="5a2f7-116">ファクト取得コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5a2f7-116">Fact Retriever</span></span>  
 <span data-ttu-id="5a2f7-117">ファクト取得コンポーネントは、ユーザーによって定義される省略可能なプラグイン コンポーネントであり、ビジネス ポリシーによって使用される長期間のファクトを収集します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-117">A fact retriever is an optional, user-defined, plug-in component that is responsible for gathering long-term facts for use by business policies.</span></span> <span data-ttu-id="5a2f7-118">詳細については、次を参照してください。[ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)です。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-118">For more information, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span>  
  
 <span data-ttu-id="5a2f7-119">実行する前に、**ポリシー**オブジェクト インスタンスを提供、 **RuleEngine**ファクト取得コンポーネント、一連のルール エンジン内のファクトを更新する機会を提供するインスタンスの作業メモリです。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-119">Before execution, a **Policy** object instance provides its **RuleEngine** instance to the fact retriever, giving it the opportunity to update the set of facts in the rule engine's working memory.</span></span> <span data-ttu-id="5a2f7-120">詳細については、次を参照してください。[短期的なファクトとします。長期間のファクト](../core/short-term-facts-vs-long-term-facts.md)です。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-120">For more information, see [Short-Term Facts vs. Long-Term Facts](../core/short-term-facts-vs-long-term-facts.md).</span></span>  
  
## <a name="rule-engine-update-service"></a><span data-ttu-id="5a2f7-121">ルール エンジン更新サービス</span><span class="sxs-lookup"><span data-stu-id="5a2f7-121">Rule Engine Update Service</span></span>  
 <span data-ttu-id="5a2f7-122">ルール エンジン更新サービスは、分散環境でビジネス ポリシーの動的な更新を可能にします。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-122">The Rule Engine Update service provides dynamic business policy updates in a distributed environment.</span></span> <span data-ttu-id="5a2f7-123">自動的に起動する Microsoft Windows NT サービスのアプリケーションでは、ビジネス ポリシーが変更された場合に発生するポリシー展開イベントと展開解除イベントをサブスクライブする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-123">An autostart Microsoft Windows NT service application is responsible for subscribing to policy deployment and undeployment events that occur when business policies are changed.</span></span>  
  
 <span data-ttu-id="5a2f7-124">一般的な企業シナリオでは、ビジネス ポリシーの展開は、更新、テスト、およびバージョン管理の後で行われます。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-124">In a typical enterprise scenario, business policies are deployed after being updated, tested, and versioned.</span></span> <span data-ttu-id="5a2f7-125">展開とは、更新されたポリシーをセキュリティで保護された永続的なルール ストアに追加して、必要に応じてストアに対してロジックを実行し、更新されたポリシーに関する情報をすべての関係者に公開することを指します (公開されるのはポリシー自体ではなく、ポリシーに関する情報です)。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-125">Deployment consists of adding the updated policy to a secure, persistent rule store and optionally executing logic on the store to publish information about the updated policy to all interested parties (note that information about the policy is published and not the policy itself).</span></span>  
  
 <span data-ttu-id="5a2f7-126">ルール ベース アプリケーションのホスト サーバーで実行されるルール エンジン更新サービスは、ポリシー更新通知を受信し、これらの情報を後で使用できるようにキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-126">The Rule Engine Update service, running on a server hosting rule-based applications, receives the policy update notification and caches the information for subsequent use.</span></span> <span data-ttu-id="5a2f7-127">ポリシーの更新に公開/サブスクライブ モデルを使用すると、サービスのダウンタイムまたは中断を生じることなく、ビジネス ポリシーをほぼリアルタイムで変更できます。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-127">The use of a pub/sub model for policy updates enables you to change business policies in near real time without service downtime or interruption.</span></span>  
  
## <a name="policyvocabulary-authoring-tools"></a><span data-ttu-id="5a2f7-128">ポリシー/ボキャブラリ作成ツール</span><span class="sxs-lookup"><span data-stu-id="5a2f7-128">Policy/Vocabulary Authoring Tools</span></span>  
 <span data-ttu-id="5a2f7-129">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のビジネス ルール作成ツールには、ポリシーやボキャブラリを作成するためのエンド ユーザー向け機能と開発者向け機能が両方備わっています。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-129">The Business Rule Composer in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides policy and vocabulary authoring capabilities to both end users and developers.</span></span>  
  
## <a name="rule-store"></a><span data-ttu-id="5a2f7-130">ルール ストア</span><span class="sxs-lookup"><span data-stu-id="5a2f7-130">Rule Store</span></span>  
 <span data-ttu-id="5a2f7-131">A*ルール ストア*は、ビジネス ポリシーとボキャブラリのリポジトリ。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-131">A *rule store* is a repository for business policies and vocabularies.</span></span> <span data-ttu-id="5a2f7-132">このリポジトリは、簡単なファイルである場合も、安全性、拡張性、持続性、および信頼性の高い Microsoft SQL Server などのデータベースである場合もあります </span><span class="sxs-lookup"><span data-stu-id="5a2f7-132">The repository can be a simple file or a secure, scalable, persistent, and reliable database such as Microsoft SQL Server.</span></span> <span data-ttu-id="5a2f7-133">(SQL Server として使用される既定のルール ストア framework 用)。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-133">(SQL Server is used as the default rule store for the framework).</span></span>  
  
## <a name="caching"></a><span data-ttu-id="5a2f7-134">キャッシュ</span><span class="sxs-lookup"><span data-stu-id="5a2f7-134">Caching</span></span>  
 <span data-ttu-id="5a2f7-135">ビジネス ルール エンジン フレームワークのキャッシュ メカニズムを提供する**RuleEngine**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-135">The Business Rules Engine Framework provides a caching mechanism for **RuleEngine** instances.</span></span> <span data-ttu-id="5a2f7-136">各**RuleEngine**インスタンスには、特定のポリシーのバージョンのメモリ内表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-136">Each **RuleEngine** instance contains an in-memory representation of a specific policy version.</span></span>  
  
 <span data-ttu-id="5a2f7-137">次の手順では、新しいプロセス**ポリシー**インスタンスがインスタンス化 (を実行したり API に対する呼び出しを**ルールの呼び出し**図形)。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-137">The following steps describe the process when a new **Policy** instance is instantiated (either with a call on the API or execution of the **Call Rules** shape):</span></span>  
  
1.  <span data-ttu-id="5a2f7-138">**ポリシー**オブジェクトの要求、 **RuleEngine**ルール エンジン キャッシュからのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-138">The **Policy** object requests a **RuleEngine** instance from the rule engine cache.</span></span>  
  
2.  <span data-ttu-id="5a2f7-139">場合、 **RuleEngine**ポリシーのバージョンが、キャッシュに存在するをインスタンス化、 **RuleEngine**にインスタンスが返されます、**ポリシー**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-139">If a **RuleEngine** instance for the policy version exists in the cache, the **RuleEngine** instance is returned to the **Policy** object.</span></span> <span data-ttu-id="5a2f7-140">場合、 **RuleEngine**インスタンスではない場合、キャッシュは、新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-140">If a **RuleEngine** instance is not available, the cache creates a new instance.</span></span> <span data-ttu-id="5a2f7-141">ときに、 **RuleEngine**インスタンスがインスタンス化は、さらに、ポリシーのバージョンのいずれかが構成されている場合は、新しいファクト取得コンポーネントのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-141">When a **RuleEngine** instance is instantiated, it does, in turn, create a new fact retriever instance if one is configured for the policy version.</span></span>  
  
 <span data-ttu-id="5a2f7-142">ときに、 **Execute**メソッドが、**ポリシー**オブジェクトを次の手順が発生します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-142">When the **Execute** method is called on the **Policy** object, the following steps occur:</span></span>  
  
1.  <span data-ttu-id="5a2f7-143">ポリシー オブジェクトの呼び出し、 **UpdateFacts**ファクト取得コンポーネントが存在する場合は、ファクト取得コンポーネントのインスタンス上のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-143">The Policy object calls the **UpdateFacts**method on the fact retriever instance if a fact retriever exists.</span></span> <span data-ttu-id="5a2f7-144">メソッドのファクト取得コンポーネントの実装の作業メモリに長期間のファクトをアサートする可能性があります、 **RuleEngine**です。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-144">The fact retriever's implementation of the method may assert long term facts into the working memory of the **RuleEngine**.</span></span>  
  
2.  <span data-ttu-id="5a2f7-145">**ポリシー**オブジェクトに含まれている短期間のファクトをアサートする、**配列**渡された、 **Execute**呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-145">The **Policy** object asserts the short term facts contained in the **Array** that was passed in the **Execute** call.</span></span>  
  
3.  <span data-ttu-id="5a2f7-146">**ポリシー**オブジェクト呼び出し**Execute**上、 **RuleEngine**です。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-146">The **Policy** object calls **Execute** on the **RuleEngine**.</span></span>  
  
4.  <span data-ttu-id="5a2f7-147">**RuleEngine**実行が完了して、制御を戻します、**ポリシー**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-147">The **RuleEngine** completes execution and returns control to the **Policy**object.</span></span>  
  
5.  <span data-ttu-id="5a2f7-148">**ポリシー**オブジェクトはから短期間のファクトを取り消します、 **RuleEngine**です。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-148">The**Policy**object retracts the short term facts from the **RuleEngine**.</span></span> <span data-ttu-id="5a2f7-149">ファクト取得コンポーネントによってアサートされた長期間のファクトは、ルール エンジンの作業メモリに残ります。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-149">The long term facts asserted by the fact retriever will remain in the working memory of the rule engine.</span></span>  
  
 <span data-ttu-id="5a2f7-150">後に、 **Dispose**でメソッドが呼び出さ、**ポリシー**オブジェクト、 **RuleEngine**ルール エンジン キャッシュへのインスタンスを解放します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-150">After the **Dispose** method is called on the **Policy** object, the **RuleEngine** instance is released back to the rule engine cache.</span></span>  
  
 <span data-ttu-id="5a2f7-151">ルール エンジンのキャッシュは、読み込みで必要な場合、特定のポリシー バージョンに関して複数のルール エンジン インスタンスを保持し、各ルール エンジン インスタンスはそれぞれ独自のファクト取得コンポーネント インスタンスを保持します。</span><span class="sxs-lookup"><span data-stu-id="5a2f7-151">The rule engine cache will have multiple rule engine instances for a given policy version if the load requires it, and each rule engine instance has its own fact retriever instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a2f7-152">参照</span><span class="sxs-lookup"><span data-stu-id="5a2f7-152">See Also</span></span>  
 [<span data-ttu-id="5a2f7-153">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="5a2f7-153">Business Rules Engine</span></span>](../core/business-rules-engine.md)