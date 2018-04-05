---
title: 使い始める BizTalk Accelerator for RosettaNet |Microsoft ドキュメント
description: について説明し、BizTalk Server では、RosettaNet accelerator (BTARN) で作業を開始するために使用可能なチュートリアルを参照してください。
caps.latest.revision: 7
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btarn.configuration.introduction
ms.assetid: 28a8942c-b461-4b2f-bc1f-1fc22cd08882
ms.author: mandia
ms.openlocfilehash: 156153010a4ee9caa5cb02535d516e05e49a21fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-biztalk-accelerator-for-rosettanet"></a><span data-ttu-id="88009-103">使い始める BizTalk Accelerator for RosettaNet</span><span class="sxs-lookup"><span data-stu-id="88009-103">Get started with BizTalk Accelerator for RosettaNet</span></span>
<span data-ttu-id="88009-104">Microsoft BizTalk Accelerator for RosettaNet (BTARN) は、開発と RosettaNet の標準ベースの統合ソリューションの配置を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="88009-104">The Microsoft BizTalk Accelerator for RosettaNet (BTARN) streamlines the development and deployment of RosettaNet standards-based integration solutions.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="88009-105">RosettaNet Implementation Framework (RNIF) バージョン 1.1 および 2.0.01 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="88009-105"> supports the RosettaNet Implementation Framework (RNIF) versions 1.1 and 2.0.01.</span></span> <span data-ttu-id="88009-106">RNIF はオープン ネットワーク アプリケーション フレームワークであり、ビジネス パートナーが共同作業して RosettaNet PIP (Partner Interface Process) を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="88009-106">RNIF is an open network application framework that enables business partners to collaboratively run RosettaNet Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="88009-107">参照してください[GS1 米国](http://go.microsoft.com/fwlink/?LinkID=33859)RosettaNet 規格の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="88009-107">See [GS1 US](http://go.microsoft.com/fwlink/?LinkID=33859) for more information about RosettaNet standard.</span></span>
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="88009-108"> では、CIDX (Chemical Data Exchange) Chem eStandards の交換もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="88009-108"> also supports the exchange of Chemical Data Exchange (CIDX) Chem eStandards.</span></span>  
  
<span data-ttu-id="88009-109">このセクションで説明できますの使用方法に関する BizTalk Server と RosettaNet accelerator、社内でエンタープライズ アプリケーション統合 (EAI)、およびビジネス パートナー間で企業間調達を自動化するロールに固有の情報ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="88009-109">This section provides role-specific information about how you can use BizTalk Server and the RosettaNet accelerator in your company for enterprise application integration (EAI), and among business partners to automate business-to-business procurement solutions.</span></span>  

## <a name="loopback-tutorial"></a><span data-ttu-id="88009-110">ループバック チュートリアル</span><span class="sxs-lookup"><span data-stu-id="88009-110">Loopback tutorial</span></span>

<span data-ttu-id="88009-111">RosettaNet accelerator を使用して、1 台のコンピューター上のホーム組織とパートナーの組織間でプロセスの実装をシミュレートする方法を説明する詳しい手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="88009-111">Includes detailed steps that describe how to use the RosettaNet accelerator to simulate a process implementation between the home and partner organization on a single computer.</span></span>

<span data-ttu-id="88009-112">このチュートリアルでは、ホーム組織、取引先組織、取引アグリーメントを作成し、ループバック ユーティリティを使用してミラー アグリーメントを作成し、次にサンプル プロセスを実行してループバック シナリオを検証します。</span><span class="sxs-lookup"><span data-stu-id="88009-112">In this tutorial, you create a home organization, a partner organization, a trade agreement, use the Loopback utility to create a mirror agreement, and then run a sample process to verify the loop-back scenario.</span></span>

<span data-ttu-id="88009-113">移動して[ループバック チュートリアル](loopback-tutorial.md)です。</span><span class="sxs-lookup"><span data-stu-id="88009-113">Go to [Loopback tutorial](loopback-tutorial.md).</span></span> 

## <a name="double-action-tutorial"></a><span data-ttu-id="88009-114">ダブル アクション チュートリアル</span><span class="sxs-lookup"><span data-stu-id="88009-114">Double action tutorial</span></span>

<span data-ttu-id="88009-115">RosettaNet accelerator を使用してエンド ツー エンド ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="88009-115">An end-to-end solution using the RosettaNet accelerator.</span></span> <span data-ttu-id="88009-116">詳しくは、次の 2 つの架空の企業間取引先シナリオを作成することで、RosettaNet 準拠のソリューションを実装する手順: Contoso、供給業者組織と Fabrikam、購入者組織。</span><span class="sxs-lookup"><span data-stu-id="88009-116">The tutorial details the steps to implement a RosettaNet-compliant solution by creating a trading partner scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>

<span data-ttu-id="88009-117">BTARN 管理コンソールの使用、基幹業務 (LOB) アプリケーションを作成するカスタム オーケストレーションの作成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="88009-117">It includes working with the BTARN Management Console, creating line-of-business (LOB) applications, and creating custom orchestrations.</span></span>

<span data-ttu-id="88009-118">移動して[ダブル アクション チュートリアル](double-action-tutorial.md)です。</span><span class="sxs-lookup"><span data-stu-id="88009-118">Go to [Double action tutorial](double-action-tutorial.md).</span></span> 


## <a name="private-process-tutorial"></a><span data-ttu-id="88009-119">プライベート プロセス チュートリアル</span><span class="sxs-lookup"><span data-stu-id="88009-119">Private process tutorial</span></span>
<span data-ttu-id="88009-120">RosettaNet accelerator を使用してエンド ツー エンド ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="88009-120">An end-to-end solution using the RosettaNet accelerator.</span></span> <span data-ttu-id="88009-121">詳しくは、次の 2 つの架空の会社間の取引シナリオを作成することで、RosettaNet 準拠のソリューションを実装する手順: Contoso、供給業者組織と Fabrikam、購入者組織。</span><span class="sxs-lookup"><span data-stu-id="88009-121">The tutorial details the steps to implement a RosettaNet-compliant solution by creating a trading scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>

<span data-ttu-id="88009-122">ここでは、ERP の統合、ビジネス ポリシーの実施、プライベート プロセスのカスタマイズ、およびセキュリティで保護された通信の使用など、RosettaNet ベースのソリューションの作成についてさまざまな角度から概説しています。</span><span class="sxs-lookup"><span data-stu-id="88009-122">It outlines various aspects of creating a RosettaNet-based solution, including ERP integration, business policy enforcement, private process customization, and promoting secure communication.</span></span>

<span data-ttu-id="88009-123">移動して[プライベート プロセス チュートリアル](private-process-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="88009-123">Go to [Private process tutorial](private-process-tutorial.md)</span></span>


## <a name="tutorial-links"></a><span data-ttu-id="88009-124">チュートリアルのリンク</span><span class="sxs-lookup"><span data-stu-id="88009-124">Tutorial Links</span></span>
[<span data-ttu-id="88009-125">ループバック チュートリアル</span><span class="sxs-lookup"><span data-stu-id="88009-125">Loopback tutorial</span></span>](loopback-tutorial.md)  
[<span data-ttu-id="88009-126">ダブル アクション チュートリアル</span><span class="sxs-lookup"><span data-stu-id="88009-126">Double action tutorial</span></span>](double-action-tutorial.md)  
[<span data-ttu-id="88009-127">プライベート プロセス チュートリアル</span><span class="sxs-lookup"><span data-stu-id="88009-127">Private process tutorial</span></span>](private-process-tutorial.md)

## <a name="see-also"></a><span data-ttu-id="88009-128">参照</span><span class="sxs-lookup"><span data-stu-id="88009-128">See also</span></span>
[<span data-ttu-id="88009-129">障碍を持つユーザー補助機能</span><span class="sxs-lookup"><span data-stu-id="88009-129">Accessibility for People with Disabilities</span></span>](accessibility-for-people-with-disabilities3.md)