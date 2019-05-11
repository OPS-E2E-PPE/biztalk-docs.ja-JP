---
title: BizTalk Server における HIPAA のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ad8c64-6375-4364-80ce-440db943c222
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06d59b485553f2a994dc3dcc47ce14f58a469735
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344355"
---
# <a name="hipaa-support-in-biztalk-server"></a><span data-ttu-id="4785a-102">BizTalk Server における HIPAA のサポート</span><span class="sxs-lookup"><span data-stu-id="4785a-102">HIPAA Support in BizTalk Server</span></span>
<span data-ttu-id="4785a-103">このトピックでは、HIPAA の概要を提供します。 どのように[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]HIPAA をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4785a-103">This topic provides a brief overview of HIPAA and how [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] supports HIPAA.</span></span>  
  
## <a name="introduction-to-hipaa"></a><span data-ttu-id="4785a-104">HIPAA の概要</span><span class="sxs-lookup"><span data-stu-id="4785a-104">Introduction to HIPAA</span></span>  
 <span data-ttu-id="4785a-105">Health Insurance Portability と Accountability Act of 1996 (HIPAA) など、要求、送金、適格性、要求の状態の要求および応答のトランザクションを電子的に行うときに、必須の標準を使用する管理対象のエンティティが必要ですし、その他。</span><span class="sxs-lookup"><span data-stu-id="4785a-105">The Health Insurance Portability and Accountability Act of 1996 (HIPAA) requires covered entities to use mandated standards when they electronically conduct transactions such as claims, remittance, eligibility, claims status requests and responses, and others.</span></span> <span data-ttu-id="4785a-106">HIPAA の適用対象事業は、正常性の計画、クリアリング ハウス、およびほとんどの医療プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="4785a-106">Covered entities under HIPAA are health plans, clearing houses, and most health care providers.</span></span>  
  
## <a name="hipaa-support-in-biztalk-server"></a><span data-ttu-id="4785a-107">BizTalk Server における HIPAA のサポート</span><span class="sxs-lookup"><span data-stu-id="4785a-107">HIPAA support in BizTalk Server</span></span>  
 <span data-ttu-id="4785a-108">マイクロソフトは医療を支援して、準ずる組織が医療が配信され、機関の効率を向上します。</span><span class="sxs-lookup"><span data-stu-id="4785a-108">Microsoft is committed to helping health care and allied organizations improve the way health care is delivered and financed.</span></span> <span data-ttu-id="4785a-109">Microsoft は、時間と HIPAA の規制を遵守する必要がありますの組織で費やすコストを削減する予定です。</span><span class="sxs-lookup"><span data-stu-id="4785a-109">Microsoft intends to reduce the amount of time and money that organizations must spend complying with HIPAA regulations.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4785a-110">により組織が対応する自動化されたビジネス プロセスを作成するという課題は、接続し、多様な医療システム間で相互運用。</span><span class="sxs-lookup"><span data-stu-id="4785a-110">helps organizations meet the challenges of creating automated business processes that connect and interoperate across diverse healthcare systems.</span></span> <span data-ttu-id="4785a-111">HIPAA 影響を受けた組織を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の開発、実装、および連邦法とも準拠しているトランザクションに準拠したソリューションの統合に役立つ機能です。</span><span class="sxs-lookup"><span data-stu-id="4785a-111">Organizations affected by HIPAA can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]’s capabilities to help in developing, implementing, and integrating transaction-compliant solutions which also comply with federal law.</span></span>  
  
[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4785a-112">HIPAA のサポートを提供するネイティブ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4785a-112">includes native functionality providing support for HIPAA.</span></span> <span data-ttu-id="4785a-113">この機能は、アダプターやアクセラレータなどの製品へのアドインではなく、</span><span class="sxs-lookup"><span data-stu-id="4785a-113">It is not an add-in to the product, such as an adapter or an accelerator.</span></span> <span data-ttu-id="4785a-114">これは、製品に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="4785a-114">It is built into the product.</span></span> [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4785a-115">EDI を含むコンポーネントとするために必要な機能に準拠すると共に、HIPAA 規制を適切に管理および評価されたビジネス プロセスとしての HIPAA を導入します。</span><span class="sxs-lookup"><span data-stu-id="4785a-115">includes the EDI components and capabilities that are required to both comply with the HIPAA mandates and to also embrace HIPAA as a well-managed and measured business process.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4785a-116">HIPAA version 5010 と 4010 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4785a-116">supports HIPAA version 5010 and 4010.</span></span>  
  
## <a name="hipaa-documentation-in-biztalk-server"></a><span data-ttu-id="4785a-117">BizTalk Server の HIPAA ドキュメント</span><span class="sxs-lookup"><span data-stu-id="4785a-117">HIPAA documentation in BizTalk Server</span></span>  
 <span data-ttu-id="4785a-118">主要な EDI 標準は、(ANSI によって標準化され、主に北米で使用)、X12 と EDIFACT (国連によって標準化されていると、主に米国外で使用)。</span><span class="sxs-lookup"><span data-stu-id="4785a-118">The primary EDI standards are X12 (standardized by ANSI and primarily used in North America) and EDIFACT (standardized by the United Nations and primarily used outside the U.S.).</span></span> <span data-ttu-id="4785a-119">HIPAA は X12 から派生した標準です。</span><span class="sxs-lookup"><span data-stu-id="4785a-119">HIPAA is a standard derived from X12.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4785a-120">ネイティブの X12 の一部として HIPAA サポートを提供します。 EDI 機能。</span><span class="sxs-lookup"><span data-stu-id="4785a-120">provides HIPAA support as part of the native X12 EDI functionality.</span></span> <span data-ttu-id="4785a-121">そのため、サポート、X12 への参照を表示場所、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメントについては、このサポートにも当てはまります HIPAA 処理、特に明示しない限り、します。</span><span class="sxs-lookup"><span data-stu-id="4785a-121">Therefore, where you see references to X12 support in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation, this support also applies to HIPAA processing, unless explicitly stated otherwise.</span></span>  
  
 <span data-ttu-id="4785a-122">次のセクションは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HIPAA に関する具体的な情報があります。</span><span class="sxs-lookup"><span data-stu-id="4785a-122">The following sections in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] have specific information about HIPAA.</span></span>  
  
 <span data-ttu-id="4785a-123">**作業の開始**</span><span class="sxs-lookup"><span data-stu-id="4785a-123">**Getting Started**</span></span>  
  
- [<span data-ttu-id="4785a-124">HIPAA トランザクション セット</span><span class="sxs-lookup"><span data-stu-id="4785a-124">HIPAA Transaction Sets</span></span>](../core/hipaa-transaction-sets.md)  
  
  <span data-ttu-id="4785a-125">**計画および設計**</span><span class="sxs-lookup"><span data-stu-id="4785a-125">**Planning and Architecture**</span></span>  
  
- [<span data-ttu-id="4785a-126">HIPAA ドキュメント スキーマ バージョン 5010</span><span class="sxs-lookup"><span data-stu-id="4785a-126">HIPAA Document Schema Version 5010</span></span>](../core/hipaa-document-schema-version-5010.md)  
  
- [<span data-ttu-id="4785a-127">HIPAA スキーマのトリガー フィールドの注釈</span><span class="sxs-lookup"><span data-stu-id="4785a-127">HIPAA Schema Trigger Field Annotations</span></span>](../core/hipaa-schema-trigger-field-annotations.md)  
  
- [<span data-ttu-id="4785a-128">HIPAA サブドキュメントの分割</span><span class="sxs-lookup"><span data-stu-id="4785a-128">Splitting HIPAA Subdocuments</span></span>](../core/splitting-hipaa-subdocuments.md)  
  
  <span data-ttu-id="4785a-129">**開発**</span><span class="sxs-lookup"><span data-stu-id="4785a-129">**Development**</span></span>  
  
- [<span data-ttu-id="4785a-130">EDI スキーマの変更</span><span class="sxs-lookup"><span data-stu-id="4785a-130">Modifying EDI Schemas</span></span>](../core/modifying-edi-schemas.md) 

- [<span data-ttu-id="4785a-131">エンベロープ スキーマでの列挙のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4785a-131">Customizing Enumerations in the Envelope Schema</span></span>](../core/customizing-enumerations-in-the-envelope-schema.md)

- [<span data-ttu-id="4785a-132">クロスフィールド検証の構成</span><span class="sxs-lookup"><span data-stu-id="4785a-132">Configuring Cross-Field Validation</span></span>](../core/configuring-cross-field-validation.md)

  
 <span data-ttu-id="4785a-133">**トラブルシューティング**</span><span class="sxs-lookup"><span data-stu-id="4785a-133">**Troubleshooting**</span></span>  
  
-   [<span data-ttu-id="4785a-134">EDI 受信処理に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="4785a-134">Known Issues with EDI Receive Processing</span></span>](../core/known-issues-with-edi-receive-processing.md)  
  
-   [<span data-ttu-id="4785a-135">EDI ソリューションで使用される XML ツールに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="4785a-135">Known Issues with XML Tools Used with EDI Solutions</span></span>](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)  
  
## <a name="more-information-about-hipaa"></a><span data-ttu-id="4785a-136">HIPAA の詳細について</span><span class="sxs-lookup"><span data-stu-id="4785a-136">More information about HIPAA</span></span>  
  
-   <span data-ttu-id="4785a-137">移動するための電子データ交換 Accredited Standards Committee American National Standards Institute については、 [ASC X12 ホーム](http://www.x12.org/)します。</span><span class="sxs-lookup"><span data-stu-id="4785a-137">For information about the American National Standards Institute, Accredited Standards Committee for Electronic Data Interchange, go to [ASC X12 home](http://www.x12.org/).</span></span>  
  
-   <span data-ttu-id="4785a-138">X12 の保険小委員会についてとその実装については、HIPAA で採用されているガイドを参照してください[Washington Publishing Company の HIPAA EDI ガイド](http://www.wpc-edi.com/)します。</span><span class="sxs-lookup"><span data-stu-id="4785a-138">For information about X12's Insurance Subcommittee and their implementation guides adopted under HIPAA, go to [Washington Publishing Company's HIPAA EDI guides](http://www.wpc-edi.com/).</span></span>
  
-   <span data-ttu-id="4785a-139">電子データ交換のワークグループについてを参照してください[Workgroup for Electronic Data Interchange ホーム ページ](http://www.wedi.org/)します。</span><span class="sxs-lookup"><span data-stu-id="4785a-139">For information about the Workgroup for Electronic Data Interchange, go to [Workgroup for Electronic Data Interchange home page](http://www.wedi.org/).</span></span>