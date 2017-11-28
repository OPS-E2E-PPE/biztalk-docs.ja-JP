---
title: "会社 A のセキュリティに関するケース スタディ: |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 9417ecf9-e340-479f-b120-552c62f3b189
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1f48edfc2ab2228d910a0729025fd7b4da117f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-case-studies-company-a"></a><span data-ttu-id="e4cae-102">セキュリティに関するケース スタディ: 会社 A</span><span class="sxs-lookup"><span data-stu-id="e4cae-102">Security Case Studies: Company A</span></span>
<span data-ttu-id="e4cae-103">会社 A は、原料供給業者の大手であり、工業部門にサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e4cae-103">Company A is a major supplier of material and services to the industrial sector.</span></span> <span data-ttu-id="e4cae-104">この会社のビジネス モデルは、主要な顧客および業者との電子商取引に依存しています。</span><span class="sxs-lookup"><span data-stu-id="e4cae-104">Its business model relies on electronic transactions with key customers and suppliers.</span></span> <span data-ttu-id="e4cae-105">会社 A では、Microsoft BizTalk アプリケーションを使用して、トランザクションと内部および外部の環境間の通信を管理します。</span><span class="sxs-lookup"><span data-stu-id="e4cae-105">Company A uses Microsoft BizTalk Application to manage transactions and communications between internal and external environments.</span></span>  
  
## <a name="potential-threats-and-security-concerns"></a><span data-ttu-id="e4cae-106">潜在的な脅威とセキュリティの問題</span><span class="sxs-lookup"><span data-stu-id="e4cae-106">Potential Threats and Security Concerns</span></span>  
 <span data-ttu-id="e4cae-107">会社 A は、認証された送信元からのメッセージのみを処理したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="e4cae-107">Company A wants to make sure that it processes only messages from authenticated sources.</span></span> <span data-ttu-id="e4cae-108">BizTalk Server で処理するドキュメントには、財務や人事に関するデータなどの機密情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4cae-108">Some of the documents BizTalk Server processes can contain sensitive information such as financial and personnel data.</span></span> <span data-ttu-id="e4cae-109">会社 A は、カスタム暗号化 API を使用して各着信メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="e4cae-109">Company A verifies each incoming message by using custom cryptographic APIs.</span></span> <span data-ttu-id="e4cae-110">また、自社の物理アーキテクチャを構築してセキュリティのニーズに対処しています。</span><span class="sxs-lookup"><span data-stu-id="e4cae-110">It has also built its physical architecture to handle its security needs.</span></span>  
  
 <span data-ttu-id="e4cae-111">会社 A は、一部のメッセージ トラフィックにファイル転送プロトコル (FTP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4cae-111">Company A uses file transfer protocol (FTP) for some of its message traffic.</span></span> <span data-ttu-id="e4cae-112">FTP は本質的にセキュリティで保護されていませんが、会社 A は、外部に接続された他のアプリケーションをセキュリティで保護できるように多くのファイアウォールを備えているため、関連するリスクを認めたうえで使用しています。</span><span class="sxs-lookup"><span data-stu-id="e4cae-112">Although FTP is inherently not secure, Company A accepts the associated risks because it has many firewalls to help secure other outward-facing applications.</span></span> <span data-ttu-id="e4cae-113">会社 A は着信データの一部を HTTPS 経由で受信するため、外部の送信元からのサービス拒否 (DoS) 攻撃について懸念しています。</span><span class="sxs-lookup"><span data-stu-id="e4cae-113">Because Company A receives some of its incoming data through HTTPS, it is concerned about denial of service (DoS) attacks from external sources.</span></span> <span data-ttu-id="e4cae-114">DoS 攻撃が発生した場合、会社には、すぐに担当者に警告するメカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="e4cae-114">If a DoS attack does occur, the company has mechanisms to alert the appropriate people immediately.</span></span>  
  
## <a name="security-architecture"></a><span data-ttu-id="e4cae-115">セキュリティのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e4cae-115">Security Architecture</span></span>  
 <span data-ttu-id="e4cae-116">次の図は、会社 A が使用するセキュリティ アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="e4cae-116">The following figure shows the security architecture that Company A uses.</span></span> <span data-ttu-id="e4cae-117">この会社はフロントエンドのアプリケーションとコンテンツ サーバー、バックエンドのデータベースとビジネス ロジック サーバー、および送信メッセージ インフラストラクチャを保護できるように、ファイアウォールを使用してその環境をセグメント化したことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e4cae-117">Notice that it has segmented its environment with firewalls to help protect its front-end application and content servers, its back-end database and business logic servers, and its outgoing message infrastructure.</span></span>  
  
 <span data-ttu-id="e4cae-118">**図 1. 会社 A のセキュリティ アーキテクチャ**</span><span class="sxs-lookup"><span data-stu-id="e4cae-118">**Figure 1 Company A security architecture**</span></span>  
  
 <span data-ttu-id="e4cae-119">![会社のセキュリティ アーキテクチャ](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")</span><span class="sxs-lookup"><span data-stu-id="e4cae-119">![Company A security architecture](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")</span></span>  
  
 <span data-ttu-id="e4cae-120">会社 A には、BizTalk Server との間で情報を送受信する主な方法が 2 とおりあります。</span><span class="sxs-lookup"><span data-stu-id="e4cae-120">Company A has two main methods to send and receive information to and from BizTalk Server.</span></span> <span data-ttu-id="e4cae-121">1 つ目の方法では、FTP を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4cae-121">The first method uses FTP.</span></span> <span data-ttu-id="e4cae-122">会社 A は、サード パーティの変換サービス プロバイダを使用して業者やパートナーと通信することにより、電子データ交換 (EDI) トランザクションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e4cae-122">Company A supports electronic data interchange (EDI) transactions by using a third-party translation service provider to communicate with its suppliers and partners.</span></span> <span data-ttu-id="e4cae-123">このサード パーティの変換サービス プロバイダは、BizTalk Server が EDI 形式で処理する必要のある注文の送受信を処理します。</span><span class="sxs-lookup"><span data-stu-id="e4cae-123">This third-party translation service provider handles incoming and outgoing orders that BizTalk Server must process in an EDI format.</span></span>  
  
 <span data-ttu-id="e4cae-124">2 つ目の方法では HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4cae-124">The second method that Company A uses is HTTPS.</span></span> <span data-ttu-id="e4cae-125">会社 A は、自社が販売および消費する製品の購入と販売を容易に行えるように、その業界で中心的な役割のサード パーティ製サービス プロバイダを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e4cae-125">Company A also works with a third-party service provider that serves as a hub for its industry and makes the purchase and sale of products Company A sells and consumes easier.</span></span>  
  
## <a name="secure-digital-certificates"></a><span data-ttu-id="e4cae-126">セキュリティで保護されたデジタル証明書</span><span class="sxs-lookup"><span data-stu-id="e4cae-126">Secure Digital Certificates</span></span>  
 <span data-ttu-id="e4cae-127">会社 A は、セキュリティで保護された独自のデジタル証明書を実装しています。</span><span class="sxs-lookup"><span data-stu-id="e4cae-127">Company A implements its own secure digital certificates.</span></span> <span data-ttu-id="e4cae-128">会社 A で管理する証明書はごくわずかです。</span><span class="sxs-lookup"><span data-stu-id="e4cae-128">It manages only a few certificates.</span></span> <span data-ttu-id="e4cae-129">会社 A ではサード パーティのサービス プロバイダを使用しているため、デジタル証明書についてあまり懸念していません。</span><span class="sxs-lookup"><span data-stu-id="e4cae-129">Because it uses a third-party service provider, it is less concerned about digital certificates.</span></span> <span data-ttu-id="e4cae-130">サービス プロバイダはさまざまな機関と連携するため、デジタル証明書がサービス プロバイダにとって非常に重要であることを会社 A は認識しています。</span><span class="sxs-lookup"><span data-stu-id="e4cae-130">Company A realizes that digital certificates are a greater concern for the service provider, because the service provider interacts with many different institutions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4cae-131">参照</span><span class="sxs-lookup"><span data-stu-id="e4cae-131">See Also</span></span>  
 <span data-ttu-id="e4cae-132">[中小規模の企業のセキュリティのケース スタディ](../core/security-case-studies-for-small-to-medium-sized-companies.md)  </span><span class="sxs-lookup"><span data-stu-id="e4cae-132">[Security Case Studies for Small & Medium-Sized Companies](../core/security-case-studies-for-small-to-medium-sized-companies.md)  </span></span>  
 [<span data-ttu-id="e4cae-133">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="e4cae-133">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)