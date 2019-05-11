---
title: 取引先の BizTalk Server を使用してパートナーの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f31a5e49-ef19-41a3-9cf3-cf85d0685a59
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e78055229a522afcc0af02e5ea4ff0ea66b6189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313343"
---
# <a name="trading-partner-management-using-biztalk-server"></a><span data-ttu-id="82da3-102">BizTalk Server を使用した取引先管理</span><span class="sxs-lookup"><span data-stu-id="82da3-102">Trading Partner Management Using BizTalk Server</span></span>
## <a name="introduction-to-tpm"></a><span data-ttu-id="82da3-103">TPM の概要</span><span class="sxs-lookup"><span data-stu-id="82da3-103">Introduction to TPM</span></span>
<span data-ttu-id="82da3-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 取引先管理 (TPM) は、パートナーとそのビジネスに関する情報の管理方法と保存方法の基本的な概念を再構築するものです。</span><span class="sxs-lookup"><span data-stu-id="82da3-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Trading Partner Management (TPM) rebuilds the fundamental concepts around how to manage and store information about partners and their business.</span></span> <span data-ttu-id="82da3-105">拡張 TPM ソリューションには、フィールドのビジネス エンティティとリレーションシップが反映されます。これにより組織は、取引先とのビジネス パートナーシップをより高度に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="82da3-105">The enhanced TPM solution reflects the business entities and relationships in the field, thereby enabling organizations to better manage your business partnerships with trading partners.</span></span> <span data-ttu-id="82da3-106">TPM ソリューションによる取引パートナーシップ BizTalk 環境でのモデルの詳細については、次を参照してください。 [、取引先管理ソリューションのビルド ブロック](../core/building-blocks-of-a-trading-partner-management-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="82da3-106">For more information on how the TPM solution models trading partnerships in a BizTalk environment, see [Building Blocks of a Trading Partner Management Solution](../core/building-blocks-of-a-trading-partner-management-solution.md).</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="82da3-107">電子データ交換 (EDI) データ交換および AS2 データ トランスポートのネイティブ サポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="82da3-107">includes native support for Electronic Data Interchange (EDI) data exchange and AS2 data transport.</span></span> <span data-ttu-id="82da3-108">このサポートにより、企業は、EDI トランザクションの自動交換によって実現される生産性の向上を図りながら EDI ベースのビジネス プロセス管理ソリューションを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="82da3-108">This support enables businesses to extend their EDI-based business process management solutions, taking advantage of the productivity improvements that the automated exchange of EDI transactions provides.</span></span> <span data-ttu-id="82da3-109">BizTalk Server は、EDI および EDIINT/AS2 を使用して、重要なサプライ チェーン ビジネス プロセスに対し、パートナー接続におけるセキュリティ保護と信頼性を高める手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="82da3-109">BizTalk Server provides these businesses with the means to more securely and reliably connect partners to critical supply-chain business processes using EDI and EDIINT/AS2.</span></span>  
  
 <span data-ttu-id="82da3-110">EDI および AS2 のサポートと組み合わせると、TPM ソリューションで取引を管理するための堅牢でスケーラブルなソリューションの提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="82da3-110">The TPM solution coupled with the EDI and AS2 support provide a robust and scalable solution for managing trading partners in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="82da3-111">このセクションのトピックおよび以下に示すその他のトピックで、TPM の高レベルな概要と、TPM を使用した取引先管理方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="82da3-111">The topics in this section, and other topics listed below, provide a high-level overview of TPM and how to use TPM to manage trading partners.</span></span> <span data-ttu-id="82da3-112">これらのトピックには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] による EDI および AS2 プロセスの実行方法も説明されています。</span><span class="sxs-lookup"><span data-stu-id="82da3-112">The topics also provide description of how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performs EDI and AS2 processing.</span></span>  
  
## <a name="in-this-section-and-more-good-info"></a><span data-ttu-id="82da3-113">このセクションで詳細な情報</span><span class="sxs-lookup"><span data-stu-id="82da3-113">In this section and more good info</span></span>

<span data-ttu-id="82da3-114">**については、最初に、およびチュートリアル**</span><span class="sxs-lookup"><span data-stu-id="82da3-114">**Learn, get started, and tutorials**</span></span>  

-   [<span data-ttu-id="82da3-115">取引先管理ソリューションの構成要素</span><span class="sxs-lookup"><span data-stu-id="82da3-115">Building Blocks of a Trading Partner Management Solution</span></span>](../core/building-blocks-of-a-trading-partner-management-solution.md)  
  
-   [<span data-ttu-id="82da3-116">BizTalk Server の EDI 機能</span><span class="sxs-lookup"><span data-stu-id="82da3-116">BizTalk Server EDI Functionality</span></span>](../core/biztalk-server-edi-functionality.md)  
  
-   [<span data-ttu-id="82da3-117">BizTalk Server の AS2 機能</span><span class="sxs-lookup"><span data-stu-id="82da3-117">BizTalk Server AS2 Functionality</span></span>](../core/biztalk-server-as2-functionality.md)  

- [<span data-ttu-id="82da3-118">EDI および AS2 ソリューションのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="82da3-118">EDI and AS2 solution architecture</span></span>](../core/edi-and-as2-solution-architecture.md)

-   [<span data-ttu-id="82da3-119">環境を最適化するための構成後の手順</span><span class="sxs-lookup"><span data-stu-id="82da3-119">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md) 

- [<span data-ttu-id="82da3-120">EDI、AS2、および EDIFACT のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="82da3-120">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)


<span data-ttu-id="82da3-121">**EDI および AS2 ソリューションの作成の詳細**</span><span class="sxs-lookup"><span data-stu-id="82da3-121">**Deep-dive in creating EDI and AS2 solutions**</span></span>
- [<span data-ttu-id="82da3-122">EDI および AS2 のアイテムの作成</span><span class="sxs-lookup"><span data-stu-id="82da3-122">Create EDI and AS2 artifacts</span></span>](../core/managing-edi-and-as2-solutions.md)

- [<span data-ttu-id="82da3-123">BizTalk Server EDI ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="82da3-123">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)

- [<span data-ttu-id="82da3-124">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="82da3-124">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)

-   [<span data-ttu-id="82da3-125">EDI および AS2 の SDK のサンプル)</span><span class="sxs-lookup"><span data-stu-id="82da3-125">EDI and AS2 SDK samples)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)  


 <span data-ttu-id="82da3-126">**バインド ファイルの使用**</span><span class="sxs-lookup"><span data-stu-id="82da3-126">**Using binding files**</span></span>  

- [<span data-ttu-id="82da3-127">バインド ファイルをインポートまたはエクスポート - 新しい BizTalk Server 2016 の使用します。</span><span class="sxs-lookup"><span data-stu-id="82da3-127">Use binding files to import or export - NEW in BizTalk Server 2016</span></span>](../core/use-binding-files-to-import-or-export.md)  

-   [<span data-ttu-id="82da3-128">EDI AS2 ソリューションのバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="82da3-128">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)  
  
-   [<span data-ttu-id="82da3-129">Edi-as2 ソリューションのバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="82da3-129">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)  
  
-   [<span data-ttu-id="82da3-130">バインド ファイルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="82da3-130">Customizing Binding Files</span></span>](../core/customizing-binding-files.md)  


<span data-ttu-id="82da3-131">**監視し、トラブルシューティング**</span><span class="sxs-lookup"><span data-stu-id="82da3-131">**Monitor and troubleshoot**</span></span>

- [<span data-ttu-id="82da3-132">EDI および AS2 ソリューションの監視</span><span class="sxs-lookup"><span data-stu-id="82da3-132">Monitoring EDI and AS2 Solutions</span></span>](../core/monitoring-edi-and-as2-solutions.md)

- [<span data-ttu-id="82da3-133">EDI および AS2 ソリューションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="82da3-133">Troubleshooting EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)
  
- <span data-ttu-id="82da3-134">UI の詳細の表示 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="82da3-134">View UI details [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span> 
  
- [<span data-ttu-id="82da3-135">EDI および AS2 イベントとエラー</span><span class="sxs-lookup"><span data-stu-id="82da3-135">EDI and AS2 Events and Errors</span></span>](../core/edi-and-as2-events-and-errors.md)
 


  
