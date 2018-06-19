---
title: BizTalk Adapter Pack 2016 のインストール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23c74470-6336-49be-95c3-32b5c279e0ab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fec17ce2da0183b9029839d3054261c5db3952a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224850"
---
# <a name="install-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="82df3-102">BizTalk Adapter Pack 2016 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="82df3-102">Install the BizTalk Adapter Pack 2016</span></span>
## <a name="overview"></a><span data-ttu-id="82df3-103">概要</span><span class="sxs-lookup"><span data-stu-id="82df3-103">Overview</span></span>

<span data-ttu-id="82df3-104">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] (BAP) が付属して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="82df3-104">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] (BAP) is included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="82df3-105">ダウンロードするときにその[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]にあるアダプターをダウンロードするも、[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="82df3-105">So when you download [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], you are also downloading the adapters in the [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)].</span></span> 

<span data-ttu-id="82df3-106">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]を使用して、[!INCLUDE[firstref_btsWinCommFoundation_md](../includes/firstref-btswincommfoundation-md.md)]別のエンタープライズ基幹業務 (LOB) システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="82df3-106">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] uses the [!INCLUDE[firstref_btsWinCommFoundation_md](../includes/firstref-btswincommfoundation-md.md)] to communicate with different enterprise line-of-business (LOB) systems.</span></span> <span data-ttu-id="82df3-107">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]要件、独自のセットアップ エクスペリエンス、および独自のインストール手順の独自セットがあります。</span><span class="sxs-lookup"><span data-stu-id="82df3-107">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] has its own set of requirements, its own setup experience, and its own installation steps.</span></span> 

<span data-ttu-id="82df3-108">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]は省略可能とする場合にのみ必要[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]を送信するか、次のエンタープライズ LOB システムへのメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="82df3-108">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] is optional, and is only needed if you want [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to send or receive messages to any of the following enterprise LOB systems:</span></span> 

* <span data-ttu-id="82df3-109">Oracle データベース</span><span class="sxs-lookup"><span data-stu-id="82df3-109">Oracle Database</span></span>
* <span data-ttu-id="82df3-110">Oracle E-business Suite (EBS)</span><span class="sxs-lookup"><span data-stu-id="82df3-110">Oracle E-Business Suite (EBS)</span></span>
* <span data-ttu-id="82df3-111">SAP</span><span class="sxs-lookup"><span data-stu-id="82df3-111">SAP</span></span>
* <span data-ttu-id="82df3-112">SQL Server</span><span class="sxs-lookup"><span data-stu-id="82df3-112">SQL Server</span></span>
* <span data-ttu-id="82df3-113">Siebel</span><span class="sxs-lookup"><span data-stu-id="82df3-113">Siebel</span></span>

<span data-ttu-id="82df3-114">すべてのバージョン[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]それ自体が含まれています[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]バージョン。</span><span class="sxs-lookup"><span data-stu-id="82df3-114">Every version of [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] includes its own [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] version.</span></span> <span data-ttu-id="82df3-115">付属するバージョンのみ、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョンはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="82df3-115">Only the version included with your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version is supported.</span></span> <span data-ttu-id="82df3-116">旧バージョンと互換性のあることはできません。</span><span class="sxs-lookup"><span data-stu-id="82df3-116">They are not backward-compatible.</span></span>

<span data-ttu-id="82df3-117">このドキュメントには、Microsoft BizTalk Adapter Pack (BAP) に含まれているをインストールするには、ソフトウェアの要件と手順[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="82df3-117">This document lists the software requirements, and the steps to install the Microsoft BizTalk Adapter Pack (BAP) included with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].</span></span> 

## <a name="get-started-here"></a><span data-ttu-id="82df3-118">ここから開始します。</span><span class="sxs-lookup"><span data-stu-id="82df3-118">Get started here</span></span>
[<span data-ttu-id="82df3-119">ソフトウェアの前提条件</span><span class="sxs-lookup"><span data-stu-id="82df3-119">Software prerequisites</span></span>](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="82df3-120">インストール手順</span><span class="sxs-lookup"><span data-stu-id="82df3-120">Install steps</span></span>](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="82df3-121">ポスト インストール手順</span><span class="sxs-lookup"><span data-stu-id="82df3-121">Post installation steps</span></span>](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="82df3-122">更新またはアンインストール</span><span class="sxs-lookup"><span data-stu-id="82df3-122">Update or uninstall</span></span>](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)