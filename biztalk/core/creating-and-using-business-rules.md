---
title: ビジネス ルールの作成と |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Editor
- Business Rules Editor
ms.assetid: a15fd09b-ff4e-4c26-8cb6-5ffd258a2182
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9d01e5eaf96c6490c68424fd09e297e0e60ef9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979395"
---
# <a name="creating-and-using-business-rules"></a><span data-ttu-id="d203d-102">ビジネス ルールの作成および使用</span><span class="sxs-lookup"><span data-stu-id="d203d-102">Creating and Using Business Rules</span></span>
<span data-ttu-id="d203d-103">ビジネス ルール (またはビジネス ポリシー) は、組織の構造、活動、および戦略を定義し、制御するものです。</span><span class="sxs-lookup"><span data-stu-id="d203d-103">Business rules (or business policies) define and control the structure, operation, and strategy of an organization.</span></span> <span data-ttu-id="d203d-104">ビジネス ルールは手順書や契約書などで正式に規定されている場合もあれば、従業員の知識や専門知識として存在する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d203d-104">Business rules may be formally defined in procedure manuals, contracts, or agreements, or may exist as knowledge or expertise embodied in employees.</span></span> <span data-ttu-id="d203d-105">ビジネス ルールは動的で時間と共に変化し、すべての種類のアプリケーションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="d203d-105">Business rules are dynamic and subject to change over time, and can be found in all types of applications.</span></span> <span data-ttu-id="d203d-106">金融保険、e ビジネス、輸送、電気通信、Web ベースのサービス、パーソナル化などは、ビジネス ルールによって統制される数多くのビジネス分野のごく一部に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="d203d-106">Finance and insurance, e-business, transportation, telecommunications, Web-based services, and personalization are just a few of the many business domains that are governed by business rules.</span></span> <span data-ttu-id="d203d-107">これらのビジネス分野が共通して抱えているニーズは、ビジネス上の戦略、ポリシー、および規定を情報技術 (IT) 担当者に伝えてソフトウェア アプリケーションに組み込むことです。</span><span class="sxs-lookup"><span data-stu-id="d203d-107">Each of these business domains shares the need to convey business strategies, policies, and regulations to information technology (IT) personnel for inclusion into software applications.</span></span>  
  
 <span data-ttu-id="d203d-108">C、C++、Microsoft Visual Basic などの従来の手続き型言語およびオブジェクト指向言語は、プログラマ指向です。</span><span class="sxs-lookup"><span data-stu-id="d203d-108">Traditional procedural and object-oriented programming languages, such as C, C++, and Microsoft Visual Basic, are oriented towards programmers.</span></span> <span data-ttu-id="d203d-109">Java や C# などの高度なオブジェクト指向言語も、主にプログラマのための言語です。</span><span class="sxs-lookup"><span data-stu-id="d203d-109">Even advanced object-oriented languages, such as Java and C#, are still primarily programmers' languages.</span></span> <span data-ttu-id="d203d-110">設計、開発、コンパイル、テストで構成される従来のソフトウェア開発サイクルには、かなりの時間と調整が必要であり、自動化されたビジネス ポリシーの保守にプログラマ以外が参加するのは不可能です。</span><span class="sxs-lookup"><span data-stu-id="d203d-110">The traditional software development cycle of design, develop, compile, and test requires substantial time and coordination, and does not enable nonprogrammers to participate in the maintenance of automated business policies.</span></span> <span data-ttu-id="d203d-111">ビジネス ルール フレームワークは、この問題に対処するために、時間のかかる従来のアプリケーション プログラミング サイクルを排除した高速なアプリケーション作成を可能にする開発環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="d203d-111">The Business Rules Framework addresses this problem by providing a development environment that allows rapid application creation without the lengthy cycle of traditional application programming.</span></span> <span data-ttu-id="d203d-112">たとえば、このフレームワークを使用して構築されたビジネス ポリシーを更新する場合は、関連するオーケストレーションを再コンパイルおよび再展開する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="d203d-112">For example, business policies constructed by using this framework can be updated without recompiling and redeploying the associated orchestrations.</span></span>  
  
 <span data-ttu-id="d203d-113">ビジネス ルール フレームワークは Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と緊密に統合されているため、開発者は次の機能を利用してビジネス ルールを構築し、管理できます。</span><span class="sxs-lookup"><span data-stu-id="d203d-113">The Business Rules Framework is tightly integrated with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and developers can use the following features to build and manage business rules:</span></span>  
  
- <span data-ttu-id="d203d-114">ビジネス ルールを評価する推論メカニズムを実装したパフォーマンスに優れたルール エンジン。</span><span class="sxs-lookup"><span data-stu-id="d203d-114">A high-performance rule engine that implements an inference mechanism to evaluate the business rules.</span></span>  
  
- <span data-ttu-id="d203d-115">ルールベースのアプリケーションを開発するための機能豊富な一連のアプリケーション プログラミング インターフェイス (API)。</span><span class="sxs-lookup"><span data-stu-id="d203d-115">A rich set of application programming interfaces (APIs) for developing rule-based applications.</span></span>  
  
- <span data-ttu-id="d203d-116">グラフィカル ユーザー インターフェイスであるビジネス ルール作成ツール。開発者、ビジネス アナリスト、および管理者はこのツールをさまざまに使用して、ルールやポリシーを効率的に開発し、適用できます。</span><span class="sxs-lookup"><span data-stu-id="d203d-116">A graphical user interface, the Business Rule Composer, which developers, business analysts, and administrators can use in various ways to efficiently develop and apply rules and policies.</span></span>  
  
- <span data-ttu-id="d203d-117">BizTalk オーケストレーションとのシームレスな統合。これにより、ビジネス ポリシーやビジネス ルールのセットを BizTalk オーケストレーションから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d203d-117">A seamless integration with BizTalk orchestrations, which enables you to invoke a business policy or a set of business rules from a BizTalk orchestration.</span></span>  
  
- <span data-ttu-id="d203d-118">ルール エンジン展開ウィザード。ビジネス ルールまたはそれらのルールが使用するボキャブラリのインポートとエクスポート、およびそれらのルールの展開と展開解除を迅速に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d203d-118">The Rule Engine Deployment Wizard, which enables you to rapidly import or export business rules or the vocabularies used by the rules, as well as to deploy or undeploy these rules.</span></span>  
  
  <span data-ttu-id="d203d-119">次の図に示すように、ビジネス ルール フレームワークを使って作成したビジネス ルール (ポリシー) は、オーケストレーションに基づくビジネス プロセスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d203d-119">The business rules (policy) you create by using the Business Rules Framework can be used in an orchestrated business process, as shown in the following figure.</span></span>  
  
  <span data-ttu-id="d203d-120">![プロセスでビジネス ポリシーを示す図。] (../core/media/ebiz-dev-busprcsi.gif "ebiz_dev_busprcsi")</span><span class="sxs-lookup"><span data-stu-id="d203d-120">![Diagram showing buisness policy in process.](../core/media/ebiz-dev-busprcsi.gif "ebiz_dev_busprcsi")</span></span>  
  <span data-ttu-id="d203d-121">ビジネス ポリシー</span><span class="sxs-lookup"><span data-stu-id="d203d-121">Business Policy</span></span>  
  
  <span data-ttu-id="d203d-122">このセクションでは、ビジネス ルール フレームワークの活用方法、および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 付属のツールを使用してビジネス ルールを開発する方法に関する概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="d203d-122">This section provides conceptual information about how you can leverage the Business Rules Framework and use the tools that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides to develop business rules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d203d-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d203d-123">In This Section</span></span>  
  
-   [<span data-ttu-id="d203d-124">ビジネス ルールの作成</span><span class="sxs-lookup"><span data-stu-id="d203d-124">Creating Business Rules</span></span>](../core/creating-business-rules-using-the-business-rule-composer.md)  
  
-   [<span data-ttu-id="d203d-125">ビジネス ルール フレームワークのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="d203d-125">Business Rules Framework Security</span></span>](../core/business-rules-framework-security.md)  
  
-   [<span data-ttu-id="d203d-126">ビジネス ルール フレームワークによるプログラミング</span><span class="sxs-lookup"><span data-stu-id="d203d-126">Programming with Business Rules Framework</span></span>](../core/programming-with-business-rules-framework.md)  
  
-   [<span data-ttu-id="d203d-127">ルール エンジンの構成およびチューニング パラメーター</span><span class="sxs-lookup"><span data-stu-id="d203d-127">Rule Engine Configuration and Tuning Parameters</span></span>](../core/rule-engine-configuration-and-tuning-parameters.md)