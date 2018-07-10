---
title: 脅威のモデルの分析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TMA, about TMA
- TMA
- TMA, procedure steps
ms.assetid: dfbf46aa-0a35-4925-8718-df8591efc279
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7fa52a2d256bace363c3453f19cabefca81cb73
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016849"
---
# <a name="threat-model-analysis"></a><span data-ttu-id="07c98-102">脅威モデル分析</span><span class="sxs-lookup"><span data-stu-id="07c98-102">Threat Model Analysis</span></span>
<span data-ttu-id="07c98-103">脅威モデル分析 (TMA) は、製品、アプリケーション、ネットワーク、環境にもたらされるセキュリティのリスクを判断し、どのように攻撃が発生するかを認識するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07c98-103">A threat model analysis (TMA) is an analysis that helps determine the security risks posed to a product, application, network, or environment, and how attacks can show up.</span></span> <span data-ttu-id="07c98-104">この分析は、緩和が必要な脅威とその緩和方法を決定することを目標とします。</span><span class="sxs-lookup"><span data-stu-id="07c98-104">The goal is to determine which threats require mitigation and how to mitigate them.</span></span>  
  
 <span data-ttu-id="07c98-105">このセクションでは、TMA プロセスに関する概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="07c98-105">This section provides high-level information about the TMA process.</span></span> <span data-ttu-id="07c98-106">詳細については、の第 4 章を参照してください。 *Writing Secure Code, Second edition*、Michael Howard と David leblanc 共著。</span><span class="sxs-lookup"><span data-stu-id="07c98-106">For more information, see Chapter 4 of *Writing Secure Code, Second edition*, by Michael Howard and David LeBlanc.</span></span>  
  
 <span data-ttu-id="07c98-107">TMA にはさまざまなメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="07c98-107">Some of the benefits of a TMA are:</span></span>  
  
- <span data-ttu-id="07c98-108">アプリケーションの理解を深めることができる。</span><span class="sxs-lookup"><span data-stu-id="07c98-108">Provides a better understanding of your application</span></span>  
  
- <span data-ttu-id="07c98-109">バグを見つけやすい。</span><span class="sxs-lookup"><span data-stu-id="07c98-109">Helps you find bugs</span></span>  
  
- <span data-ttu-id="07c98-110">新しいチーム メンバがアプリケーションを詳しく理解するのに役立つ。</span><span class="sxs-lookup"><span data-stu-id="07c98-110">Can help new team members understand the application in detail</span></span>  
  
- <span data-ttu-id="07c98-111">アプリケーションに基づいて作業する他のチームに関する重要な情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="07c98-111">Contains important information for other teams that build on your application</span></span>  
  
- <span data-ttu-id="07c98-112">テスタが役立てることができる。</span><span class="sxs-lookup"><span data-stu-id="07c98-112">Useful for testers</span></span>  
  
  <span data-ttu-id="07c98-113">TMA を実行する手順の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="07c98-113">The high-level steps to perform a TMA are:</span></span>  
  
- <span data-ttu-id="07c98-114">手順 1.</span><span class="sxs-lookup"><span data-stu-id="07c98-114">Step 1.</span></span> <span data-ttu-id="07c98-115">背景情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="07c98-115">Collect Background Information</span></span>  
  
- <span data-ttu-id="07c98-116">手順 2.</span><span class="sxs-lookup"><span data-stu-id="07c98-116">Step 2.</span></span> <span data-ttu-id="07c98-117">作成し、脅威モデル分析</span><span class="sxs-lookup"><span data-stu-id="07c98-117">Create and Analyze the Threat Model</span></span>  
  
- <span data-ttu-id="07c98-118">手順 3.</span><span class="sxs-lookup"><span data-stu-id="07c98-118">Step 3.</span></span> <span data-ttu-id="07c98-119">脅威を確認します。</span><span class="sxs-lookup"><span data-stu-id="07c98-119">Review Threats</span></span>  
  
- <span data-ttu-id="07c98-120">手順 4.</span><span class="sxs-lookup"><span data-stu-id="07c98-120">Step 4.</span></span> <span data-ttu-id="07c98-121">緩和方法とテクノロジを特定します。</span><span class="sxs-lookup"><span data-stu-id="07c98-121">Identify Mitigation Techniques and Technologies</span></span>  
  
- <span data-ttu-id="07c98-122">手順 5.</span><span class="sxs-lookup"><span data-stu-id="07c98-122">Step 5.</span></span> <span data-ttu-id="07c98-123">ドキュメントのセキュリティ モデルとデプロイに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="07c98-123">Document Security Model and Deployment Considerations</span></span>  
  
- <span data-ttu-id="07c98-124">手順 6.</span><span class="sxs-lookup"><span data-stu-id="07c98-124">Step 6.</span></span> <span data-ttu-id="07c98-125">実装とテストの軽減策</span><span class="sxs-lookup"><span data-stu-id="07c98-125">Implement and Test Mitigations</span></span>  
  
- <span data-ttu-id="07c98-126">手順 7.</span><span class="sxs-lookup"><span data-stu-id="07c98-126">Step 7.</span></span> <span data-ttu-id="07c98-127">脅威モデルのデザインとの同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="07c98-127">Keep the Threat Model in Sync with Design</span></span>  
  
## <a name="step-1-collect-background-information"></a><span data-ttu-id="07c98-128">手順 1.</span><span class="sxs-lookup"><span data-stu-id="07c98-128">Step 1.</span></span> <span data-ttu-id="07c98-129">背景情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="07c98-129">Collect Background Information</span></span>  
 <span data-ttu-id="07c98-130">TMA を成功させる準備として、背景情報を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c98-130">To prepare for a successful TMA, you have to collect some background information.</span></span> <span data-ttu-id="07c98-131">対象となる環境 (アプリケーション、プログラム、インフラストラクチャ全体) は次のように分析すると便利です。</span><span class="sxs-lookup"><span data-stu-id="07c98-131">It is useful to analyze your target environment (an application, program, or the whole infrastructure) as follows:</span></span>  
  
-   <span data-ttu-id="07c98-132">ユースケース シナリオを特定します。</span><span class="sxs-lookup"><span data-stu-id="07c98-132">Identify use-case scenarios.</span></span> <span data-ttu-id="07c98-133">対象となる環境の各ユースケース シナリオで、その環境が会社でどのように使用されるかという点と、その環境の制限を特定します。</span><span class="sxs-lookup"><span data-stu-id="07c98-133">For each use-case scenario for your target environment, identify how you expect your company to use the target environment, and any limitations or restrictions on the target environment.</span></span> <span data-ttu-id="07c98-134">この情報は、脅威モデルのスコープを定義するのに役立ち、資産 (データやコンピュータなど会社にとっての何らかの価値) に対する指針とエントリ ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="07c98-134">This information helps define the scope of the threat model discussion, and provides pointers to assets (anything of value to your company, such as data and computers) and entry points.</span></span>  
  
-   <span data-ttu-id="07c98-135">各シナリオのデータ フロー ダイアグラム (DFD) を作成します。</span><span class="sxs-lookup"><span data-stu-id="07c98-135">Create a data flow diagram (DFD) for each scenario.</span></span> <span data-ttu-id="07c98-136">脅威を十分に理解できる深さまで作成してください。</span><span class="sxs-lookup"><span data-stu-id="07c98-136">Make sure that you go deep enough to understand your threats.</span></span>  
  
-   <span data-ttu-id="07c98-137">対象となる環境の境界とスコープを判断します。</span><span class="sxs-lookup"><span data-stu-id="07c98-137">Determine the boundaries and scope of the target environment.</span></span>  
  
-   <span data-ttu-id="07c98-138">信頼されたコンポーネントと信頼されていないコンポーネントの境界を理解します。</span><span class="sxs-lookup"><span data-stu-id="07c98-138">Understand the boundaries between trusted and untrusted components.</span></span>  
  
-   <span data-ttu-id="07c98-139">各コンポーネントの構成および管理モデルを理解します。</span><span class="sxs-lookup"><span data-stu-id="07c98-139">Understand the configuration and administration model for each component.</span></span>  
  
-   <span data-ttu-id="07c98-140">外部依存関係の一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="07c98-140">Create a list of external dependencies.</span></span>  
  
-   <span data-ttu-id="07c98-141">各コンポーネントが依存する他のコンポーネントについて前提の一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="07c98-141">Create a list of assumptions about other components on which each component depends.</span></span> <span data-ttu-id="07c98-142">この一覧は、コンポーネント間の前提、アクション項目、他のチームとのフォローアップ項目などを検証するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07c98-142">This helps validate cross-component assumptions, action items, and follow-up items with other teams.</span></span>  
  
## <a name="step-2-create-and-analyze-the-threat-model"></a><span data-ttu-id="07c98-143">手順 2.</span><span class="sxs-lookup"><span data-stu-id="07c98-143">Step 2.</span></span> <span data-ttu-id="07c98-144">作成し、脅威モデル分析</span><span class="sxs-lookup"><span data-stu-id="07c98-144">Create and Analyze the Threat Model</span></span>  
 <span data-ttu-id="07c98-145">背景情報を収集したら、脅威モデルについてのミーティングを行います。</span><span class="sxs-lookup"><span data-stu-id="07c98-145">After you collect the background information, you should have a threat model meeting or meetings.</span></span> <span data-ttu-id="07c98-146">各開発分野 (プログラム マネージャ、開発者、テスタなど) から少なくとも 1 人のメンバが参加するようにします。</span><span class="sxs-lookup"><span data-stu-id="07c98-146">Make sure that at least one member of each development discipline (for example, program managers, developers, and testers) is at the meeting.</span></span> <span data-ttu-id="07c98-147">参加者に、ミーティングの目標は脅威を見つけることであって、脅威を解決することではないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="07c98-147">Make sure that you remind the attendees that the goal of the meeting is to find threats, not to fix them.</span></span> <span data-ttu-id="07c98-148">脅威モデルのミーティングでは次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="07c98-148">During the threat model meeting, do the following:</span></span>  
  
-   <span data-ttu-id="07c98-149">各ユースケースの DFD を調べます。</span><span class="sxs-lookup"><span data-stu-id="07c98-149">Examine the DFD for each use case.</span></span> <span data-ttu-id="07c98-150">各ユースケースについて、次の要素を特定します。</span><span class="sxs-lookup"><span data-stu-id="07c98-150">For each use case identify:</span></span>  
  
    -   <span data-ttu-id="07c98-151">エントリ ポイント</span><span class="sxs-lookup"><span data-stu-id="07c98-151">Entry points</span></span>  
  
    -   <span data-ttu-id="07c98-152">信頼の境界</span><span class="sxs-lookup"><span data-stu-id="07c98-152">Trust boundaries</span></span>  
  
    -   <span data-ttu-id="07c98-153">エントリ ポイントから最後の配置場所までのデータ フロー (往復)</span><span class="sxs-lookup"><span data-stu-id="07c98-153">Flow of data from entry point to final resting location (and back)</span></span>  
  
-   <span data-ttu-id="07c98-154">関連する資産を書き留めます。</span><span class="sxs-lookup"><span data-stu-id="07c98-154">Note the assets involved.</span></span>  
  
-   <span data-ttu-id="07c98-155">それぞれの DFD をについて説明し、DFD のすべてのエントリは、次のカテゴリでの脅威を探します: **S**poofing を識別、 **T**データ、ampering **R**、これが否認**は**漏洩、 **D**ービス拒否、および**E**levation 特権。</span><span class="sxs-lookup"><span data-stu-id="07c98-155">Discuss each DFD, and look for threats in the following categories for all entries in the DFD: **S**poofing identify, **T**ampering with data, **R**epudiation, **I**nformation disclosure, **D**enial of service, and **E**levation of privileges.</span></span>  
  
-   <span data-ttu-id="07c98-156">特定された脅威の一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="07c98-156">Create a list of the identified threats.</span></span> <span data-ttu-id="07c98-157">この一覧には、タイトル、簡単な説明 (脅威ツリーを含む)、資産、影響、リスク、緩和方法、緩和状態、バグ番号などを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="07c98-157">We recommend that this list include the following: title, brief description (including threat trees), asset (asset), impact(s), risk, mitigation techniques, mitigation status, and a bug number.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07c98-158">リスク、緩和方法、緩和状態などは、脅威を確認しながら追加することができます。</span><span class="sxs-lookup"><span data-stu-id="07c98-158">You can add risk, mitigation techniques, and mitigation status as you review the threats.</span></span> <span data-ttu-id="07c98-159">脅威モデルのミーティング中は、あまりこれらの項目に時間をかけないでください。</span><span class="sxs-lookup"><span data-stu-id="07c98-159">Do not spend too much time in these areas during the threat model meeting.</span></span>  
  
## <a name="step-3-review-threats"></a><span data-ttu-id="07c98-160">手順 3.</span><span class="sxs-lookup"><span data-stu-id="07c98-160">Step 3.</span></span> <span data-ttu-id="07c98-161">脅威を確認します。</span><span class="sxs-lookup"><span data-stu-id="07c98-161">Review Threats</span></span>  
 <span data-ttu-id="07c98-162">環境に対する脅威を特定したら、各脅威のリスクにランクを付け、各脅威への対応方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c98-162">After you have identified the threats to your environment, you must rank the risk of each threat and determine how you want to respond to each threat.</span></span> <span data-ttu-id="07c98-163">これは別にチーム ミーティングを開くか電子メールを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="07c98-163">You can do this with additional team meetings or through e-mail.</span></span> <span data-ttu-id="07c98-164">次の効果カテゴリを使用してリスク エクスポージャを計算することができます: **D**amage、潜在的な**R**可能性、 **E**xploitability、 **A**影響を受けるユーザー、および**D**iscoverability します。</span><span class="sxs-lookup"><span data-stu-id="07c98-164">You can use the following effect categories to calculate risk exposure: **D**amage potential, **R**eproducibility, **E**xploitability, **A**ffected users, and **D**iscoverability.</span></span>  
  
 <span data-ttu-id="07c98-165">対象となる環境への脅威をリスクごとに優先順位を付けて一覧を作成したら、各脅威への対応方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c98-165">After you have a list of the threats to your target environment prioritized by risk, you must determine how you will respond to each threat.</span></span> <span data-ttu-id="07c98-166">対応として、何もしない (ほとんどの場合お勧めできません)、問題の可能性についてユーザーに警告する、問題を除去する、問題を解決するという選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="07c98-166">Your response can be to do nothing (rarely a good choice), warn users about the potential problem, remove the problem, or fix the problem.</span></span>  
  
## <a name="step-4-identify-mitigation-techniques-and-technologies"></a><span data-ttu-id="07c98-167">手順 4.</span><span class="sxs-lookup"><span data-stu-id="07c98-167">Step 4.</span></span> <span data-ttu-id="07c98-168">緩和方法とテクノロジを特定します。</span><span class="sxs-lookup"><span data-stu-id="07c98-168">Identify Mitigation Techniques and Technologies</span></span>  
 <span data-ttu-id="07c98-169">解決する脅威を特定したら、各脅威に使用可能な緩和方法と各脅威の影響を軽減するのに最も適したテクノロジを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c98-169">After you identify which threats you will fix, you must determine the available mitigation techniques for each threat, and the most appropriate technology to reduce the effect of each threat.</span></span>  
  
 <span data-ttu-id="07c98-170">たとえば、対象となる環境の詳細によっては、認証技術を使用することによってデータ改ざんの脅威の影響を軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="07c98-170">For example, depending on the details of your target environment, you can reduce the effect of data-tamper threats by using authorization techniques.</span></span> <span data-ttu-id="07c98-171">その場合、使用に適した認証技術 (随意アクセス制御リスト (DACL)、アクセス許可、IP の制限など) を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c98-171">You then have to determine the appropriate authorization technology to use (for example, discretionary access control lists (DACLs), permissions, or IP restrictions).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="07c98-172">緩和方法と使用するテクノロジを評価する際は、会社にとっての採算や、緩和方法によって影響を受ける可能性がある会社のポリシーについても考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c98-172">When you evaluate mitigation techniques and technologies to use, you must consider what makes business sense for your company, and any policies your company has that might affect the mitigation technique to choose.</span></span>  
  
 <span data-ttu-id="07c98-173">TMA を完了した後、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="07c98-173">After you complete the TMA, do the following:</span></span>  
  
-   <span data-ttu-id="07c98-174">セキュリティ モデルと展開に関する考慮事項の文書化</span><span class="sxs-lookup"><span data-stu-id="07c98-174">Document the security model and deployment considerations</span></span>  
  
-   <span data-ttu-id="07c98-175">緩和の実装とテスト</span><span class="sxs-lookup"><span data-stu-id="07c98-175">Implement and test mitigations</span></span>  
  
-   <span data-ttu-id="07c98-176">脅威モデルとデザインとの同期の維持</span><span class="sxs-lookup"><span data-stu-id="07c98-176">Keep the threat model synchronized with design</span></span>  
  
## <a name="step-5-document-security-model-and-deployment-considerations"></a><span data-ttu-id="07c98-177">手順 5.</span><span class="sxs-lookup"><span data-stu-id="07c98-177">Step 5.</span></span> <span data-ttu-id="07c98-178">ドキュメントのセキュリティ モデルとデプロイに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="07c98-178">Document Security Model and Deployment Considerations</span></span>  
 <span data-ttu-id="07c98-179">TMA で見つかった事柄と、対象とする環境への脅威の影響を軽減するために決定した事柄を文書化しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="07c98-179">It is valuable to document what you discover during the TMA and how you decide to reduce the effect of the threats to your target environment.</span></span> <span data-ttu-id="07c98-180">このドキュメントは、品質保証 (QA)、テスト、サポート、運用担当者などに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07c98-180">This documentation can be useful to quality assurance (QA), test, support, and operations personnel.</span></span> <span data-ttu-id="07c98-181">対象となる環境とのやり取りやインターフェイスの機能を持つ他のアプリケーションに関する情報や、ファイアウォールやトポロジに関する推奨事項と要件も記載します。</span><span class="sxs-lookup"><span data-stu-id="07c98-181">Include information about other applications that interact or interface with your target environment, and the firewall and topology recommendations and requirements.</span></span>  
  
## <a name="step-6-implement-and-test-mitigations"></a><span data-ttu-id="07c98-182">手順 6.</span><span class="sxs-lookup"><span data-stu-id="07c98-182">Step 6.</span></span> <span data-ttu-id="07c98-183">実装とテストの軽減策</span><span class="sxs-lookup"><span data-stu-id="07c98-183">Implement and Test Mitigations</span></span>  
 <span data-ttu-id="07c98-184">TMA で特定された脅威を解決する準備ができたら、新しい脅威の侵入を最小限に抑えるための安全規約と展開基準に従えるように、開発用チェック リストと展開用チェック リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="07c98-184">When your team is ready to fix threats identified during the TMA, make sure you use development and deployment checklists to follow secure code and deployment standards that will help minimize the introduction of new threats.</span></span>  
  
 <span data-ttu-id="07c98-185">緩和策を実装したら、テストを行い、その脅威に対して望ましい保護レベルが実現されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="07c98-185">After you implement a mitigation, make sure you test it to make sure it provides the level of protection that you want for the threat.</span></span>  
  
## <a name="step-7-keep-the-threat-model-in-sync-with-design"></a><span data-ttu-id="07c98-186">手順 7.</span><span class="sxs-lookup"><span data-stu-id="07c98-186">Step 7.</span></span> <span data-ttu-id="07c98-187">脅威モデルのデザインとの同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="07c98-187">Keep the Threat Model in Sync with Design</span></span>  
 <span data-ttu-id="07c98-188">新しいアプリケーション、サーバー、その他の要素を環境に追加する場合は、脅威モデル分析の調査結果を見直し、新しい機能に対する TMA を行います。</span><span class="sxs-lookup"><span data-stu-id="07c98-188">As you add new applications, servers, and other elements to your environment, make sure that you revisit the findings of the threat model analysis and do TMAs for any new functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07c98-189">参照</span><span class="sxs-lookup"><span data-stu-id="07c98-189">See Also</span></span>  
<span data-ttu-id="07c98-190">[小規模中規模企業からのセキュリティのケース スタディ](../core/security-case-studies-for-small-to-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="07c98-190">[Security Case Studies for Small to Medium-Sized Companies](../core/security-case-studies-for-small-to-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="07c98-191">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="07c98-191">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)