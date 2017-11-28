---
title: "アダプターと BizTalk server アクセラレータ |Microsoft ドキュメント"
description: "すべてのアダプターと組み込みアダプター、BAP、HL7、Swift、RosettaNet、FileAct および InterAct を含む biztalk アクセラレータの概要"
caps.latest.revision: "3"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df7f26a1-e47b-4323-b9f0-58842c55a6f8
ms.author: mandia
ms.openlocfilehash: 9f3f73fd4b53161e5d3e0aa81ee660a56d8ff850
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapters-and-accelerators-in-biztalk-server"></a><span data-ttu-id="91ed7-103">アダプターと BizTalk server アクセラレータ</span><span class="sxs-lookup"><span data-stu-id="91ed7-103">Adapters and Accelerators in BizTalk Server</span></span>
 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="91ed7-104">別のアダプターとのデータを受信し、さまざまなサービスにデータを送信し、システムの LOB アプリケーションを作成するためのアクセラレータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="91ed7-104"> includes different adapters and accelerators for you to create applications that receive data, and send data to different services and LOB systems.</span></span> 
 
<span data-ttu-id="91ed7-105">このセクションでは、別のアダプターやアクセラレータで利用可能なについて説明します。[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="91ed7-105">This section describes the different adapters and accelerators available with  [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

## <a name="out-of-the-box-adapters"></a><span data-ttu-id="91ed7-106">既定のアダプター</span><span class="sxs-lookup"><span data-stu-id="91ed7-106">Out-of-the-box adapters</span></span>
<span data-ttu-id="91ed7-107">BizTalk Server をインストールするときに、使用する準備ができている組み込みのアダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="91ed7-107">When you install BizTalk Server, you also install the built-in adapters that are ready to be used.</span></span> <span data-ttu-id="91ed7-108">これらのアダプターの一部には、ファイル、FTP、MQ Series、Service Bus、Logic Apps、POP3、SharePoint、および詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="91ed7-108">Some of these adapters include File, FTP, MQ Series, Service Bus, Logic Apps, POP3, SharePoint, and more.</span></span>

<span data-ttu-id="91ed7-109">**[アダプターを使用して](../core/using-adapters.md)、それらのすべてを一覧表示し、また各アダプターを使用する方法を示します。**</span><span class="sxs-lookup"><span data-stu-id="91ed7-109">**[Using Adapters](../core/using-adapters.md) lists all of them, and also shows you how to use each adapter.**</span></span>
 
## <a name="biztalk-adapter-pack"></a><span data-ttu-id="91ed7-110">BizTalk アダプター パック</span><span class="sxs-lookup"><span data-stu-id="91ed7-110">BizTalk Adapter Pack</span></span>
<span data-ttu-id="91ed7-111">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]が付属して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、WCF ベース アダプターの接続を提供し、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Oracle、SAP、Siebel、および SQL Server にします。</span><span class="sxs-lookup"><span data-stu-id="91ed7-111">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] is included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and provides WCF-based adapters to connect your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to Oracle, SAP, Siebel, and SQL Server.</span></span> <span data-ttu-id="91ed7-112">使用して、独自の WCF ベース アダプターを作成することも、[!INCLUDE[afproductnameshort_md](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="91ed7-112">You can also create your own WCF-based adapters using the [!INCLUDE[afproductnameshort_md](../includes/afproductnameshort-md.md)].</span></span> 

<span data-ttu-id="91ed7-113">**参照してください[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)インストールをステップ実行チュートリアルおよびシナリオでは、これらのアダプターを構成する別のアダプターを使用してアプリケーションを作成し、取得WCFベースのサービスプロセスメッセージのことをお勧め**.</span><span class="sxs-lookup"><span data-stu-id="91ed7-113">**See [BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md) to install and configure these adapters, step through tutorials and scenarios, create applications using the different adapters, and get a good idea of how WCF-based services process messages**.</span></span> 

<span data-ttu-id="91ed7-114">一部のサンプルはいただけますも[http://go.microsoft.com/fwlink/p/?LinkID=196854](http://go.microsoft.com/fwlink/p/?LinkID=196854)です。</span><span class="sxs-lookup"><span data-stu-id="91ed7-114">Some samples are also available at [http://go.microsoft.com/fwlink/p/?LinkID=196854](http://go.microsoft.com/fwlink/p/?LinkID=196854).</span></span> 

## <a name="fileact-and-interact"></a><span data-ttu-id="91ed7-115">FileAct と対話します。</span><span class="sxs-lookup"><span data-stu-id="91ed7-115">FileAct and InterAct</span></span>
<span data-ttu-id="91ed7-116">[!INCLUDE[swift_adapter_md](../includes/swift-adapter-md.md)]に含まれて[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]、間の接続を提供し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]と社会 Worldwide 銀行間財務通信 (SWIFT) セキュリティで保護された IP ネットワーク (SIPN) にします。</span><span class="sxs-lookup"><span data-stu-id="91ed7-116">The [!INCLUDE[swift_adapter_md](../includes/swift-adapter-md.md)] are included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and provide connectivity between your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] and the Society for Worldwide Interbank Financial Telecommunication (SWIFT) Secure IP Network (SIPN).</span></span> 

<span data-ttu-id="91ed7-117">FileAct アダプターでは、ファイル、およびそれらのファイルに関連する情報の交換をセキュリティと堅牢性を提供します。</span><span class="sxs-lookup"><span data-stu-id="91ed7-117">The FileAct adapter provides secure and reliable exchange of files, and information pertaining to those files.</span></span> 

<span data-ttu-id="91ed7-118">InterAct アダプターでは、安全性と信頼性の高いメッセージ交換の各構造化された財務を提供します。</span><span class="sxs-lookup"><span data-stu-id="91ed7-118">The InterAct adapter provides secure and reliable exchange of individual structured financial messages.</span></span> 

<span data-ttu-id="91ed7-119">**参照してください[FileAct および InterAct](../adapters-and-accelerators/fileact-interact/microsoft-biztalk-server-fileact-and-interact-adapters-documentation.md)をインストールして、これらのアダプターを構成する、いくつかのチュートリアルとシナリオの手順しのアーキテクチャを理解**です。</span><span class="sxs-lookup"><span data-stu-id="91ed7-119">**See [FileAct and InterAct](../adapters-and-accelerators/fileact-interact/microsoft-biztalk-server-fileact-and-interact-adapters-documentation.md) to install and configure these adapters, step through some tutorials and scenarios, and get a good understanding of the architecture**.</span></span> 

## <a name="hl7"></a><span data-ttu-id="91ed7-120">HL7</span><span class="sxs-lookup"><span data-stu-id="91ed7-120">HL7</span></span>

<span data-ttu-id="91ed7-121">[!INCLUDE[btaBTAHL7NoNumber_md](../includes/btabtahl7nonumber-md.md)]が付属して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]との間の接続を提供し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]と正常性レベル 7 (HL7) 標準に基づく医療コンピューター アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="91ed7-121">The [!INCLUDE[btaBTAHL7NoNumber_md](../includes/btabtahl7nonumber-md.md)] is included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and provides connectivity between your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] and health care computer applications based on the Health Level Seven (HL7) standard.</span></span>

<span data-ttu-id="91ed7-122">**参照してください[HL7](../adapters-and-accelerators/accelerator-hl7/microsoft-biztalk-accelerator-for-hl7-documentation.md)インストールして、アダプターでは、いくつかのチュートリアルおよびシナリオでは、ステップを構成するには、アダプターの動作について説明し、スキーマ、受信確認をバッチ処理、検証、および複数をなど、さまざまな機能を使用**.</span><span class="sxs-lookup"><span data-stu-id="91ed7-122">**See [HL7](../adapters-and-accelerators/accelerator-hl7/microsoft-biztalk-accelerator-for-hl7-documentation.md) to install and configure the adapter, step through several tutorials and scenarios, learn how the adapter works, and use the different features, including schemas, acknowledgments, batching, validation, and more**.</span></span>

## <a name="rosettanet"></a><span data-ttu-id="91ed7-123">RosettaNet</span><span class="sxs-lookup"><span data-stu-id="91ed7-123">RosettaNet</span></span>
<span data-ttu-id="91ed7-124">BizTalk Accelerator for RosettaNet (BTARN) は BizTalk Server に付属し、開発と RosettaNet の標準ベースの統合ソリューションの展開を合理化します。</span><span class="sxs-lookup"><span data-stu-id="91ed7-124">The BizTalk Accelerator for RosettaNet (BTARN) is included with BizTalk Server, and streamlines the development and deployment of RosettaNet standards-based integration solutions.</span></span> <span data-ttu-id="91ed7-125">BTARN の RNIF RosettaNet Implementation Framework (); をサポートしていますこれは、ビジネス パートナーが共同作業して RosettaNet Partner Interface Process (Pip) を実行できるオープン ネットワーク アプリケーション フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="91ed7-125">BTARN supports the RosettaNet Implementation Framework (RNIF); which is an open network application framework that enables business partners to collaboratively run RosettaNet Partner Interface Processes (PIPs).</span></span> 

<span data-ttu-id="91ed7-126">**参照してください[RosettaNet](../adapters-and-accelerators/accelerator-rosettanet/microsoft-biztalk-accelerator-for-rosettanet-documentation.md)をこのアクセラレータと、BizTalk Server ソリューションでの使用の詳細を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="91ed7-126">**See [RosettaNet](../adapters-and-accelerators/accelerator-rosettanet/microsoft-biztalk-accelerator-for-rosettanet-documentation.md) to learn more about this accelerator, and using it with your BizTalk Server solutions.**</span></span> 

## <a name="swift"></a><span data-ttu-id="91ed7-127">SWIFT</span><span class="sxs-lookup"><span data-stu-id="91ed7-127">SWIFT</span></span>
<span data-ttu-id="91ed7-128">[!INCLUDE[btaA4SWIFTNoVersion_md](../includes/btaa4swiftnoversion-md.md)]が付属して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]との間の接続を提供し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]とメッセージ形式社会のワールドワイド銀行間財務通信 (SWIFT)。</span><span class="sxs-lookup"><span data-stu-id="91ed7-128">The [!INCLUDE[btaA4SWIFTNoVersion_md](../includes/btaa4swiftnoversion-md.md)] is included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and provides connectivity between your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] and the Society for Worldwide Interbank Financial Telecommunication (SWIFT) message formats.</span></span>

<span data-ttu-id="91ed7-129">アダプターを使用して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]顧客、パートナー、およびシステム インテグレーターは、開発、配置、およびコア金融サービス アプリケーションのインフラストラクチャやビジネス プロセスの統合ソリューションのサポートを合理化できます。</span><span class="sxs-lookup"><span data-stu-id="91ed7-129">Using the adapter with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], customers, partners, and system integrators can streamline the development, deployment, and support of integration solutions for core financial services application infrastructure and business processes.</span></span>

<span data-ttu-id="91ed7-130">**参照してください[SWIFT](../adapters-and-accelerators/accelerator-swift/microsoft-biztalk-accelerator-for-swift-documentation.md)をインストールして、アダプターを構成して、いくつかのチュートリアルでは、手順、および使用メッセージ修復 FIN 応答と FRR 成果物の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="91ed7-130">**See [SWIFT](../adapters-and-accelerators/accelerator-swift/microsoft-biztalk-accelerator-for-swift-documentation.md) to install and configure the adapter, step through some tutorials, and use the message repair, FIN response and FRR artifacts, and more**.</span></span>

## <a name="get-some-help"></a><span data-ttu-id="91ed7-131">いくつかのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="91ed7-131">Get some help</span></span> 
<span data-ttu-id="91ed7-132">いくつかのヘルプを取得し、内の他のヘルプ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]フォーラム[http://go.microsoft.com/fwlink/p/?LinkId=87695](http://go.microsoft.com/fwlink/p/?LinkId=87695)です。</span><span class="sxs-lookup"><span data-stu-id="91ed7-132">Get some help, and help others in the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] forums [http://go.microsoft.com/fwlink/p/?LinkId=87695](http://go.microsoft.com/fwlink/p/?LinkId=87695).</span></span>