---
title: 小規模中規模の企業からのセキュリティのケース スタディ |Microsoft ドキュメント
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
ms.openlocfilehash: 9af0f013960e882ffe6b5c081ae1452df4aaecf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269290"
---
# <a name="security-case-studies-for-small-to-medium-sized-companies"></a><span data-ttu-id="bf291-102">小規模中規模の企業からのセキュリティのケース スタディ</span><span class="sxs-lookup"><span data-stu-id="bf291-102">Security Case Studies for Small to Medium-Sized Companies</span></span>
<span data-ttu-id="bf291-103">自社のデータやリソースが、特定のユーザーまたはアプリケーションからしかアクセスされることのないように真剣に取り組む企業にとって、セキュリティは重大な関心事です。</span><span class="sxs-lookup"><span data-stu-id="bf291-103">Security is a concern of any company that is serious about making sure that only a select group of people or applications can access its data and resources.</span></span> <span data-ttu-id="bf291-104">セキュリティに対するアプローチや実装の方法は、個々の企業によってさまざまです。</span><span class="sxs-lookup"><span data-stu-id="bf291-104">Companies approach and implement security in a variety of ways.</span></span>  
  
 <span data-ttu-id="bf291-105">このセクションでは、セキュリティで保護された環境で Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を展開するためのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="bf291-105">This section provides guidelines for deploying Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a secure environment.</span></span> <span data-ttu-id="bf291-106">BizTalk Server の導入に対する潜在的な脅威の評価に役立つ情報と、中小企業向けのアーキテクチャの例も示します。</span><span class="sxs-lookup"><span data-stu-id="bf291-106">It provides information to help you assess the potential threats to your BizTalk Server implementation, a sample architecture for small and medium-size companies.</span></span>  
  
 <span data-ttu-id="bf291-107">セキュリティを考慮せずにビジネスを運営することが困難な時代です。</span><span class="sxs-lookup"><span data-stu-id="bf291-107">It is difficult to run a business today without thinking about security.</span></span> <span data-ttu-id="bf291-108">オンライン取り引きを行う場合は、顧客のクレジット カード情報を保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf291-108">If you carry out online transactions, you want to protect the credit card information of your customers.</span></span> <span data-ttu-id="bf291-109">Fortune 誌の 500 社に選ばれる規模の企業では、自社のネットワークに悪意のあるユーザーを寄せ付けないようにすることが望まれます。</span><span class="sxs-lookup"><span data-stu-id="bf291-109">If you work for a Fortune 500 company, you want to keep malicious users away from your networks.</span></span> <span data-ttu-id="bf291-110">コンピュータのユーザーなら、仕事に支障をきたすようなウイルスやワームによるデータの破損を避けるための対策を講じなければなりません。</span><span class="sxs-lookup"><span data-stu-id="bf291-110">If you are a desktop user, you want to keep viruses and worms from damaging your data and limiting your ability to do your work.</span></span> <span data-ttu-id="bf291-111">ほとんど毎日のように、新しいソフトウェアの脆弱性や、急速に広まって根絶するのが難しく、いっそう悪質になった新しいワームやウイルス、あるいは悪意のあるユーザーによって書き換えられた企業の Web サイトに関する話題が報じられています。</span><span class="sxs-lookup"><span data-stu-id="bf291-111">Almost every day you hear or read about new software vulnerabilities; about new worms and viruses that are faster spreading, harder to eradicate, and more damaging than the previous ones; and about the Web sites of companies being defaced by malicious users.</span></span> <span data-ttu-id="bf291-112">ビジネスが大規模か小規模か、顧客の数が多いか少ないか、コンピュータが 1 台であるか数百台であるかにかかわらず、仕事に必要なデータやコンピュータを悪意のあるユーザーやプログラム (ウイルス、ワーム) から守る必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf291-112">Whatever your business is—large or small, a few customers or millions of customers, one computer or hundreds of computers—you need to keep malicious users and programs (viruses, worms) from compromising your data, computers, and ability to do your job.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf291-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bf291-113">In This Section</span></span>  
  
-   [<span data-ttu-id="bf291-114">セキュリティに関するケース スタディ: 会社 A</span><span class="sxs-lookup"><span data-stu-id="bf291-114">Security Case Studies: Company A</span></span>](../core/security-case-studies-company-a.md)  
  
-   [<span data-ttu-id="bf291-115">会社 B のセキュリティに関するケース スタディ:</span><span class="sxs-lookup"><span data-stu-id="bf291-115">Security Case Studies: Company B</span></span>](../core/security-case-studies-company-b.md)  
  
-   [<span data-ttu-id="bf291-116">脅威モデル分析</span><span class="sxs-lookup"><span data-stu-id="bf291-116">Threat Model Analysis</span></span>](../core/threat-model-analysis.md)  
  
-   [<span data-ttu-id="bf291-117">小規模および中規模企業向けのサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="bf291-117">Sample Architectures for Small & Medium-Sized Companies</span></span>](../core/sample-architectures-for-small-medium-sized-companies.md)  
  
-   [<span data-ttu-id="bf291-118">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="bf291-118">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)