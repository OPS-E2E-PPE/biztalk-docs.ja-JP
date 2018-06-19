---
title: 'まとめ: 取引先管理ソリューションを定義する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4219312a-c4b5-45f3-b77b-d5cc4f1a1ca4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea32fba8e9e57d7a0549a680b06e08d5bf8e087f
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22269226"
---
# <a name="putting-it-all-together-defining-a-trading-partner-management-solution"></a><span data-ttu-id="25b51-102">まとめ: 取引先管理ソリューションを定義する</span><span class="sxs-lookup"><span data-stu-id="25b51-102">Putting it all Together: Defining a Trading Partner Management Solution</span></span>
<span data-ttu-id="25b51-103">TPM ソリューションの構築で使用するさまざまなコンポーネントについて理解できたので、次に標準的な TPM ソリューションの流れと、さまざまな構成要素の連携について説明します。</span><span class="sxs-lookup"><span data-stu-id="25b51-103">Now that we have understood about the different types of components in building a TPM solution, let us understand the flow of a typical TPM solution and how the different building blocks work together.</span></span> <span data-ttu-id="25b51-104">ここでは、TPM ソリューションのモデリングのベスト プラクティスも示します。</span><span class="sxs-lookup"><span data-stu-id="25b51-104">This section also lists some best practices for modeling a TPM solution.</span></span>  
  
 <span data-ttu-id="25b51-105">TPM ソリューションの作成の標準的な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="25b51-105">A typical flow for creating a TPM solution would include the following:</span></span>  
  
1.  <span data-ttu-id="25b51-106">商取引に関係するすべての組織を表すパートナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="25b51-106">Create partners representing all the organizations involved in a business trade.</span></span> <span data-ttu-id="25b51-107">たとえば、商取引に 2 つの組織が関係する場合は、それぞれについて取引先を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25b51-107">For example, if there are two business organizations involved in a business trade, you must create a trading partner for each of them.</span></span> <span data-ttu-id="25b51-108">取引先を作成する方法の手順については、次を参照してください[全般的なパーティ プロパティを構成する](../core/configuring-general-party-properties.md)または[一般的なパーティ プロパティの構成 (AS2)。](../core/configuring-general-party-properties-as2.md)</span><span class="sxs-lookup"><span data-stu-id="25b51-108">For instructions on how to create trading partners, see [Configuring General Party Properties](../core/configuring-general-party-properties.md) or [Configuring General Party Properties (AS2)](../core/configuring-general-party-properties-as2.md)</span></span>  
  
2.  <span data-ttu-id="25b51-109">組織内の部署ごとに、それを表すプロファイルをパートナー内に作成します。</span><span class="sxs-lookup"><span data-stu-id="25b51-109">For each business division within an organization, create a profile within the partner representing the business division.</span></span> <span data-ttu-id="25b51-110">たとえば、組織に "購買" と "資材" という部署がある場合は、各部署を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のビジネス プロファイルとして表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="25b51-110">For example, if an organization has “Purchase” and “Supplies” business divisions, each of these divisions must be represented as a business profile in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="25b51-111">また、自分の組織を表すパートナーのビジネス プロファイルだけではなく、取引先のパートナーも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25b51-111">Also, you must create the business profiles not just for the partner representing your organization but also the partner with which you trade.</span></span> <span data-ttu-id="25b51-112">ビジネス プロファイルを作成する方法については、次を参照してください。[ビジネス プロファイル プロパティを設定する](../core/configuring-business-profile-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="25b51-112">For instructions on how to create business profiles, see [Configuring Business Profile Properties](../core/configuring-business-profile-properties.md).</span></span>  
  
3.  <span data-ttu-id="25b51-113">ビジネス プロファイルごとに、メッセージ エンコードの設定とメッセージ プロトコルの設定を含む B2B プロトコル設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="25b51-113">For each business profile, define the B2B protocol settings that include the message encoding setting and the message protocol settings.</span></span> <span data-ttu-id="25b51-114">これらの設定では、B2B メッセージのエンコード方法および 2 つのビジネス プロファイル間での伝送方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="25b51-114">These settings define how the B2B messages are encoded and transported between two business profiles.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25b51-115">この段階では、プロトコル設定の指定は省略できます。</span><span class="sxs-lookup"><span data-stu-id="25b51-115">Specifying protocol settings is optional at this stage.</span></span> <span data-ttu-id="25b51-116">取引先アグリーメントの一部として、プロトコルの設定を直接追加できます。</span><span class="sxs-lookup"><span data-stu-id="25b51-116">You can directly add the protocol settings as part of the trading partner agreement.</span></span>  
  
4.  <span data-ttu-id="25b51-117">2 つのビジネス プロファイルがメッセージ交換の間に使用することを合意したエンコードとメッセージ プロトコルを定義する取引先アグリーメント (TPA) を、ビジネス プロファイルの間に作成します。</span><span class="sxs-lookup"><span data-stu-id="25b51-117">Create Trading Partner Agreements (TPA) between the business profiles that define the encoding and/or messaging protocols the two business profiles agree to use while exchanging messages.</span></span> <span data-ttu-id="25b51-118">アグリーメントを作成する方法については、次を参照してください[X12 に固有のアグリーメント プロパティの構成](../core/configuring-x12-specific-agreement-properties.md)、 [EDIFACT に固有のアグリーメントのプロパティを構成する](../core/configuring-edifact-specific-agreement-properties.md)、または[AS2 を構成します。アグリーメントのプロパティ](../core/configuring-as2-agreement-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="25b51-118">For instructions on how to create agreements, see [Configuring X12-Specific Agreement Properties](../core/configuring-x12-specific-agreement-properties.md), [Configuring EDIFACT-Specific Agreement Properties](../core/configuring-edifact-specific-agreement-properties.md), or [Configuring AS2 Agreement Properties](../core/configuring-as2-agreement-properties.md).</span></span>  
  
 <span data-ttu-id="25b51-119">以上の作業を実行することで、取引先と B2B メッセージを交換するための TPM ソリューションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="25b51-119">By performing the above set of tasks you would have created TPM solution to exchange B2B messages with your trading partner.</span></span>  
  
## <a name="where-do-i-start"></a><span data-ttu-id="25b51-120">開始方法</span><span class="sxs-lookup"><span data-stu-id="25b51-120">Where do I Start?</span></span>  
 <span data-ttu-id="25b51-121">以下に従って開始することができます。</span><span class="sxs-lookup"><span data-stu-id="25b51-121">You can start by going through the following sections:</span></span>  
  
-   <span data-ttu-id="25b51-122">X12 固有のチュートリアル「[チュートリアル 2: EDI インターフェイス開発チュートリアル](../core/tutorial-2-edi-interface-developer-tutorial.md)です。</span><span class="sxs-lookup"><span data-stu-id="25b51-122">X12-specific tutorial at [Tutorial 2: EDI Interface Developer Tutorial](../core/tutorial-2-edi-interface-developer-tutorial.md).</span></span>  
  
-   <span data-ttu-id="25b51-123">AS2 固有のチュートリアル「[チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)です。</span><span class="sxs-lookup"><span data-stu-id="25b51-123">AS2-specific tutorial at [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  
  
-   <span data-ttu-id="25b51-124">X12-および EDIFACT に固有のチュートリアル [を開発し、BizTalk Server EDI ソリューションを構成する](../core/developing-and-configuring-biztalk-server-edi-solutions.md)です。</span><span class="sxs-lookup"><span data-stu-id="25b51-124">X12- and EDIFACT-specific walkthroughs under [Developing and Configuring BizTalk Server EDI Solutions](../core/developing-and-configuring-biztalk-server-edi-solutions.md).</span></span>  
  
-   <span data-ttu-id="25b51-125">AS2 固有のチュートリアル[を開発し、BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)です。</span><span class="sxs-lookup"><span data-stu-id="25b51-125">AS2-specific walkthroughs under [Developing and Configuring BizTalk Server AS2 Solutions](../core/developing-and-configuring-biztalk-server-as2-solutions.md).</span></span>  
  
-   <span data-ttu-id="25b51-126">パーティ、プロファイル、および X12 と EDIFACT での手順に従ってメッセージのアグリーメントを作成する[EDI プロパティを設定する](../core/configuring-edi-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="25b51-126">Create parties, profiles, and agreements for X12 and EDIFACT messaging by following instructions at [Configuring EDI Properties](../core/configuring-edi-properties.md).</span></span>  
  
-   <span data-ttu-id="25b51-127">パーティ、プロファイル、およびメッセージングでの手順に従って、AS2 のアグリーメントを作成する[AS2 プロパティを設定する](../core/configuring-as2-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="25b51-127">Create parties, profiles, and agreements for AS2 messaging by following instructions at [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b51-128">参照</span><span class="sxs-lookup"><span data-stu-id="25b51-128">See Also</span></span>  
 [<span data-ttu-id="25b51-129">取引先管理ソリューションの構成要素</span><span class="sxs-lookup"><span data-stu-id="25b51-129">Building Blocks of a Trading Partner Management Solution</span></span>](../core/building-blocks-of-a-trading-partner-management-solution.md)