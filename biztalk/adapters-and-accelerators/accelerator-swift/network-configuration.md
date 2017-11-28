---
title: "ネットワーク構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deploying, network configuration
ms.assetid: fb6265b8-2e6d-4344-bb44-4f4fd995382d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83a9e8ffe6b278c91429835c3ae32c96d45ef22e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="network-configuration"></a><span data-ttu-id="cebc1-102">ネットワークの構成</span><span class="sxs-lookup"><span data-stu-id="cebc1-102">Network Configuration</span></span>
<span data-ttu-id="cebc1-103">このセクションでは、展開でネットワークを構成するための規範的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cebc1-103">This section provides prescriptive guidance for configuring the network in your deployment.</span></span> <span data-ttu-id="cebc1-104">詳細については、次を参照してください。[の展開の準備](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="cebc1-104">For more information, see [Preparing for Deployment](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span></span>  
  
 <span data-ttu-id="cebc1-105">スイッチの仮想ローカル エリア ネットワーク (Vlan) を定義して、適切なケーブルを接続します。</span><span class="sxs-lookup"><span data-stu-id="cebc1-105">You define virtual local area networks (VLANs) in the switch and then connect the appropriate cables.</span></span> <span data-ttu-id="cebc1-106">Vlan を定義すると、ネットワーク セグメントまたは層ごとに、スイッチのポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="cebc1-106">By defining the VLANs, you are designating ports on the switch for each network segment or tier.</span></span> <span data-ttu-id="cebc1-107">次の環境の各 VLAN を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebc1-107">You must create a VLAN for each of the following environments:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cebc1-108">層の送受信</span><span class="sxs-lookup"><span data-stu-id="cebc1-108"> receive and send tier</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cebc1-109">オーケストレーションとデータベース層</span><span class="sxs-lookup"><span data-stu-id="cebc1-109"> orchestration and database tier</span></span>  
  
-   <span data-ttu-id="cebc1-110">企業ネットワーク</span><span class="sxs-lookup"><span data-stu-id="cebc1-110">Corporate network</span></span>  
  
 <span data-ttu-id="cebc1-111">Vlan を定義した後は、スイッチ上の適切なポートに、サーバーからネットワーク ケーブルを接続できます。</span><span class="sxs-lookup"><span data-stu-id="cebc1-111">After you have defined the VLANs, you can connect the network cables from the servers to the appropriate ports on the switch.</span></span>  
  
 <span data-ttu-id="cebc1-112">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cebc1-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="cebc1-113">物理的なダイアグラム</span><span class="sxs-lookup"><span data-stu-id="cebc1-113">Physical Diagram</span></span>](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)  
  
-   [<span data-ttu-id="cebc1-114">ネットワーク負荷分散</span><span class="sxs-lookup"><span data-stu-id="cebc1-114">Network Load Balancing</span></span>](../../adapters-and-accelerators/accelerator-swift/network-load-balancing.md)