---
title: セキュリティに関するケース スタディ:会社 A |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 9417ecf9-e340-479f-b120-552c62f3b189
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 213dfa9cb7664b96a867beed944698f71da9bb4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251054"
---
# <a name="security-case-studies-company-a"></a><span data-ttu-id="96741-102">セキュリティに関するケース スタディ:会社 A</span><span class="sxs-lookup"><span data-stu-id="96741-102">Security Case Studies: Company A</span></span>
<span data-ttu-id="96741-103">会社 A は、マテリアルと、工業部門にサービスの主要なサプライヤーです。</span><span class="sxs-lookup"><span data-stu-id="96741-103">Company A is a major supplier of material and services to the industrial sector.</span></span> <span data-ttu-id="96741-104">そのビジネス モデルは、主要な顧客とサプライヤーの電子商取引に依存しています。</span><span class="sxs-lookup"><span data-stu-id="96741-104">Its business model relies on electronic transactions with key customers and suppliers.</span></span> <span data-ttu-id="96741-105">会社 A では、Microsoft BizTalk アプリケーションを使用して、トランザクションと内部および外部の環境間の通信を管理します。</span><span class="sxs-lookup"><span data-stu-id="96741-105">Company A uses Microsoft BizTalk Application to manage transactions and communications between internal and external environments.</span></span>  
  
## <a name="potential-threats-and-security-concerns"></a><span data-ttu-id="96741-106">潜在的な脅威とセキュリティに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="96741-106">Potential Threats and Security Concerns</span></span>  
 <span data-ttu-id="96741-107">会社 A は、認証された送信元からのメッセージのみを処理するかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96741-107">Company A wants to make sure that it processes only messages from authenticated sources.</span></span> <span data-ttu-id="96741-108">BizTalk Server で処理するドキュメントの一部などの機密情報を格納できます財務および人事データ。</span><span class="sxs-lookup"><span data-stu-id="96741-108">Some of the documents BizTalk Server processes can contain sensitive information such as financial and personnel data.</span></span> <span data-ttu-id="96741-109">会社 A は、カスタム暗号化 Api を使用して、各受信メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="96741-109">Company A verifies each incoming message by using custom cryptographic APIs.</span></span> <span data-ttu-id="96741-110">セキュリティのニーズを処理するために、物理アーキテクチャにも構築します。</span><span class="sxs-lookup"><span data-stu-id="96741-110">It has also built its physical architecture to handle its security needs.</span></span>  
  
 <span data-ttu-id="96741-111">会社 A は、メッセージ トラフィックの一部のファイル転送プロトコル (FTP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="96741-111">Company A uses file transfer protocol (FTP) for some of its message traffic.</span></span> <span data-ttu-id="96741-112">FTP はセキュリティで保護された本質的にありませんが、会社 A は、他の外部に接続するアプリケーションを保護するために多くのファイアウォールがあるため、関連するリスクを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="96741-112">Although FTP is inherently not secure, Company A accepts the associated risks because it has many firewalls to help secure other outward-facing applications.</span></span> <span data-ttu-id="96741-113">会社 A は、HTTPS 経由の受信データの一部を受信するため、サービス拒否 (DoS) 攻撃の外部ソースからについて懸念しています。</span><span class="sxs-lookup"><span data-stu-id="96741-113">Because Company A receives some of its incoming data through HTTPS, it is concerned about denial of service (DoS) attacks from external sources.</span></span> <span data-ttu-id="96741-114">DoS 攻撃が発生した場合、企業は、適切な人にすぐに警告するメカニズムを持っています。</span><span class="sxs-lookup"><span data-stu-id="96741-114">If a DoS attack does occur, the company has mechanisms to alert the appropriate people immediately.</span></span>  
  
## <a name="security-architecture"></a><span data-ttu-id="96741-115">セキュリティのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="96741-115">Security Architecture</span></span>  
 <span data-ttu-id="96741-116">次の図は、会社 A を使用するセキュリティ アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="96741-116">The following figure shows the security architecture that Company A uses.</span></span> <span data-ttu-id="96741-117">フロント エンドのアプリケーションとコンテンツ サーバー、そのバックエンド データベースとビジネス ロジック サーバー、および送信メッセージ インフラストラクチャを保護するためにファイアウォールを使用してその環境をセグメント化したことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="96741-117">Notice that it has segmented its environment with firewalls to help protect its front-end application and content servers, its back-end database and business logic servers, and its outgoing message infrastructure.</span></span>  
  
 <span data-ttu-id="96741-118">**図 1. 会社 A セキュリティ アーキテクチャ**</span><span class="sxs-lookup"><span data-stu-id="96741-118">**Figure 1 Company A security architecture**</span></span>  
  
 <span data-ttu-id="96741-119">![会社のセキュリティ アーキテクチャ](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")</span><span class="sxs-lookup"><span data-stu-id="96741-119">![Company A security architecture](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")</span></span>  
  
 <span data-ttu-id="96741-120">会社 A には、BizTalk Server との情報を送受信する 2 つの主な方法があります。</span><span class="sxs-lookup"><span data-stu-id="96741-120">Company A has two main methods to send and receive information to and from BizTalk Server.</span></span> <span data-ttu-id="96741-121">最初のメソッドは、FTP を使用します。</span><span class="sxs-lookup"><span data-stu-id="96741-121">The first method uses FTP.</span></span> <span data-ttu-id="96741-122">電子データをサポートして、会社 A は、業者やパートナーとの通信にサード パーティの変換サービス プロバイダーを使用して、(EDI) トランザクションを交換します。</span><span class="sxs-lookup"><span data-stu-id="96741-122">Company A supports electronic data interchange (EDI) transactions by using a third-party translation service provider to communicate with its suppliers and partners.</span></span> <span data-ttu-id="96741-123">このサード パーティの変換サービス プロバイダーは、BizTalk Server が EDI 形式で処理する必要があります着信および発信の注文を処理します。</span><span class="sxs-lookup"><span data-stu-id="96741-123">This third-party translation service provider handles incoming and outgoing orders that BizTalk Server must process in an EDI format.</span></span>  
  
 <span data-ttu-id="96741-124">会社 A を使用する 2 番目のメソッドは、HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="96741-124">The second method that Company A uses is HTTPS.</span></span> <span data-ttu-id="96741-125">会社 A は、その業界のハブとして機能し、購入と販売製品、自社が販売しているし、簡単に使用するサード パーティのサービス プロバイダーでも機能します。</span><span class="sxs-lookup"><span data-stu-id="96741-125">Company A also works with a third-party service provider that serves as a hub for its industry and makes the purchase and sale of products Company A sells and consumes easier.</span></span>  
  
## <a name="secure-digital-certificates"></a><span data-ttu-id="96741-126">デジタル証明書をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="96741-126">Secure Digital Certificates</span></span>  
 <span data-ttu-id="96741-127">会社 A は、独自のセキュリティで保護されたデジタル証明書を実装します。</span><span class="sxs-lookup"><span data-stu-id="96741-127">Company A implements its own secure digital certificates.</span></span> <span data-ttu-id="96741-128">いくつかの証明書のみを管理します。</span><span class="sxs-lookup"><span data-stu-id="96741-128">It manages only a few certificates.</span></span> <span data-ttu-id="96741-129">サード パーティのサービス プロバイダーを使用しているためには、デジタル証明書についてあまり懸念していません。</span><span class="sxs-lookup"><span data-stu-id="96741-129">Because it uses a third-party service provider, it is less concerned about digital certificates.</span></span> <span data-ttu-id="96741-130">会社 A は、サービス プロバイダーがさまざまな機関と対話するために、サービス プロバイダーにとってをデジタル証明書を気付きます。</span><span class="sxs-lookup"><span data-stu-id="96741-130">Company A realizes that digital certificates are a greater concern for the service provider, because the service provider interacts with many different institutions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96741-131">参照</span><span class="sxs-lookup"><span data-stu-id="96741-131">See Also</span></span>  
 <span data-ttu-id="96741-132">[中小規模の企業のセキュリティのケース スタディ](../core/security-case-studies-for-small-to-medium-sized-companies.md)  </span><span class="sxs-lookup"><span data-stu-id="96741-132">[Security Case Studies for Small & Medium-Sized Companies](../core/security-case-studies-for-small-to-medium-sized-companies.md)  </span></span>  
 [<span data-ttu-id="96741-133">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="96741-133">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)