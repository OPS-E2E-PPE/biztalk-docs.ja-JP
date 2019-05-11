---
title: BizTalk Adapter Pack 2016 のインストール |Microsoft Docs
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
ms.openlocfilehash: 24c3e0ba9087dd82eaf3fbd362179b109a6b9fc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364017"
---
# <a name="install-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="58379-102">BizTalk Adapter Pack 2016 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="58379-102">Install the BizTalk Adapter Pack 2016</span></span>
## <a name="overview"></a><span data-ttu-id="58379-103">概要</span><span class="sxs-lookup"><span data-stu-id="58379-103">Overview</span></span>

<span data-ttu-id="58379-104">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] (BAP) が含まれている[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="58379-104">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] (BAP) is included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="58379-105">ダウンロードするときにその[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]にあるアダプターをダウンロードすることも、[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="58379-105">So when you download [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], you are also downloading the adapters in the [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)].</span></span> 

<span data-ttu-id="58379-106">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]を使用して、[!INCLUDE[firstref_btsWinCommFoundation_md](../includes/firstref-btswincommfoundation-md.md)]別のエンタープライズ基幹業務 (LOB) システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="58379-106">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] uses the [!INCLUDE[firstref_btsWinCommFoundation_md](../includes/firstref-btswincommfoundation-md.md)] to communicate with different enterprise line-of-business (LOB) systems.</span></span> <span data-ttu-id="58379-107">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]は要件、独自のセットアップ エクスペリエンスおよびインストール手順は、独自の独自セットがあります。</span><span class="sxs-lookup"><span data-stu-id="58379-107">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] has its own set of requirements, its own setup experience, and its own installation steps.</span></span> 

<span data-ttu-id="58379-108">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]は省略可能でしたい場合にのみ必要[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]エンタープライズ LOB システムは次のいずれかにメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="58379-108">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] is optional, and is only needed if you want [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to send or receive messages to any of the following enterprise LOB systems:</span></span> 

* <span data-ttu-id="58379-109">Oracle データベース</span><span class="sxs-lookup"><span data-stu-id="58379-109">Oracle Database</span></span>
* <span data-ttu-id="58379-110">Oracle E-business Suite (EBS)</span><span class="sxs-lookup"><span data-stu-id="58379-110">Oracle E-Business Suite (EBS)</span></span>
* <span data-ttu-id="58379-111">SAP</span><span class="sxs-lookup"><span data-stu-id="58379-111">SAP</span></span>
* <span data-ttu-id="58379-112">SQL Server</span><span class="sxs-lookup"><span data-stu-id="58379-112">SQL Server</span></span>
* <span data-ttu-id="58379-113">Siebel</span><span class="sxs-lookup"><span data-stu-id="58379-113">Siebel</span></span>

<span data-ttu-id="58379-114">すべてのバージョンの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]それ自体が含まれています[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]バージョン。</span><span class="sxs-lookup"><span data-stu-id="58379-114">Every version of [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] includes its own [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] version.</span></span> <span data-ttu-id="58379-115">含まれているバージョンのみ、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="58379-115">Only the version included with your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version is supported.</span></span> <span data-ttu-id="58379-116">旧バージョンと互換性のあるではありません。</span><span class="sxs-lookup"><span data-stu-id="58379-116">They are not backward-compatible.</span></span>

<span data-ttu-id="58379-117">このドキュメントは、Microsoft BizTalk Adapter Pack (BAP) が付属をインストールするには、ソフトウェアの要件と手順では、一覧表示されます。[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="58379-117">This document lists the software requirements, and the steps to install the Microsoft BizTalk Adapter Pack (BAP) included with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].</span></span> 

## <a name="get-started-here"></a><span data-ttu-id="58379-118">ここから開始します</span><span class="sxs-lookup"><span data-stu-id="58379-118">Get started here</span></span>
[<span data-ttu-id="58379-119">ソフトウェアの必要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="58379-119">Software prerequisites</span></span>](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="58379-120">インストール手順</span><span class="sxs-lookup"><span data-stu-id="58379-120">Install steps</span></span>](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="58379-121">インストール後の手順</span><span class="sxs-lookup"><span data-stu-id="58379-121">Post installation steps</span></span>](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="58379-122">更新またはアンインストール</span><span class="sxs-lookup"><span data-stu-id="58379-122">Update or uninstall</span></span>](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)