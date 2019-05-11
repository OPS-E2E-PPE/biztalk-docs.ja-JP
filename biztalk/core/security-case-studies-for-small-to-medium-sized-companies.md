---
title: 小規模中規模企業からのセキュリティのケース スタディ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
- security, examples
- security, architecture
- architecture, medium distributions
ms.assetid: b33e3f2a-ddc4-47a8-92d7-511ae0cc880e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 738a36f096155ac89cf0c01258d69a3704048066
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251080"
---
# <a name="security-case-studies-for-small-to-medium-sized-companies"></a><span data-ttu-id="62532-102">小規模中規模企業からのセキュリティのケース スタディ</span><span class="sxs-lookup"><span data-stu-id="62532-102">Security Case Studies for Small to Medium-Sized Companies</span></span>
<span data-ttu-id="62532-103">セキュリティは、そのデータとリソース グループのユーザーまたはアプリケーションのみがアクセスできるようにしている企業にとって重要です。</span><span class="sxs-lookup"><span data-stu-id="62532-103">Security is a concern of any company that is serious about making sure that only a select group of people or applications can access its data and resources.</span></span> <span data-ttu-id="62532-104">企業では、アプローチし、さまざまな方法でセキュリティを実装します。</span><span class="sxs-lookup"><span data-stu-id="62532-104">Companies approach and implement security in a variety of ways.</span></span>  
  
 <span data-ttu-id="62532-105">このセクションでは、Microsoft を展開するためのガイドラインを提供します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セキュリティで保護された環境でします。</span><span class="sxs-lookup"><span data-stu-id="62532-105">This section provides guidelines for deploying Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a secure environment.</span></span> <span data-ttu-id="62532-106">小規模および中規模の企業のサンプル アーキテクチャ、BizTalk Server の実装に潜在的な脅威の評価に役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="62532-106">It provides information to help you assess the potential threats to your BizTalk Server implementation, a sample architecture for small and medium-size companies.</span></span>  
  
 <span data-ttu-id="62532-107">セキュリティを考慮せずに今日のビジネスに困難です。</span><span class="sxs-lookup"><span data-stu-id="62532-107">It is difficult to run a business today without thinking about security.</span></span> <span data-ttu-id="62532-108">オンラインのトランザクションを実行する場合、顧客のクレジット_カード情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="62532-108">If you carry out online transactions, you want to protect the credit card information of your customers.</span></span> <span data-ttu-id="62532-109">悪意のあるユーザー、ネットワークから離れた場所を保持する、Fortune 500 企業の作業している場合。</span><span class="sxs-lookup"><span data-stu-id="62532-109">If you work for a Fortune 500 company, you want to keep malicious users away from your networks.</span></span> <span data-ttu-id="62532-110">デスクトップのユーザーの場合に、データが破損し、作業を行う能力を制限するウイルスやワームを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62532-110">If you are a desktop user, you want to keep viruses and worms from damaging your data and limiting your ability to do your work.</span></span> <span data-ttu-id="62532-111">ほぼ毎日聞くかについては、新しいソフトウェアの脆弱性。新しいワームやウイルスが高速展開、急速に広まって根絶するは困難です。 前のものよりも大きな損害をもたらす企業の Web サイトに関する悪意のあるユーザーが改変されています。</span><span class="sxs-lookup"><span data-stu-id="62532-111">Almost every day you hear or read about new software vulnerabilities; about new worms and viruses that are faster spreading, harder to eradicate, and more damaging than the previous ones; and about the Web sites of companies being defaced by malicious users.</span></span> <span data-ttu-id="62532-112">ビジネスが何であれ —、大小いくつかの顧客や顧客、1 台のコンピューターまたはコンピューターの数百の何百万人も — データ、コンピューター、およびジョブを実行する能力を損なうことから悪意のあるユーザーとプログラム (ウイルス、ワーム) を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62532-112">Whatever your business is—large or small, a few customers or millions of customers, one computer or hundreds of computers—you need to keep malicious users and programs (viruses, worms) from compromising your data, computers, and ability to do your job.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62532-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="62532-113">In This Section</span></span>  
  
-   [<span data-ttu-id="62532-114">セキュリティに関するケース スタディ:会社 A</span><span class="sxs-lookup"><span data-stu-id="62532-114">Security Case Studies: Company A</span></span>](../core/security-case-studies-company-a.md)  
  
-   [<span data-ttu-id="62532-115">セキュリティに関するケース スタディ:会社 B</span><span class="sxs-lookup"><span data-stu-id="62532-115">Security Case Studies: Company B</span></span>](../core/security-case-studies-company-b.md)  
  
-   [<span data-ttu-id="62532-116">脅威モデル分析</span><span class="sxs-lookup"><span data-stu-id="62532-116">Threat Model Analysis</span></span>](../core/threat-model-analysis.md)  
  
-   [<span data-ttu-id="62532-117">中小企業向けのサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="62532-117">Sample Architectures for Small & Medium-Sized Companies</span></span>](../core/sample-architectures-for-small-medium-sized-companies.md)  
  
-   [<span data-ttu-id="62532-118">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="62532-118">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)