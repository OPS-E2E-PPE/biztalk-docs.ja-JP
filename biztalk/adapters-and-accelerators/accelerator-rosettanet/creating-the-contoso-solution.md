---
title: "Contoso ソリューションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: private process tutorial, creating solutions
ms.assetid: 02f5326a-68bd-418a-af81-684a73056e2c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcc840a33bf9f0a4708b7c9b44902fc02b5f2ea7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="creating-the-contoso-solution"></a><span data-ttu-id="e1a55-102">Contoso ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="e1a55-102">Creating the Contoso Solution</span></span>
<span data-ttu-id="e1a55-103">ここでは、Contoso 組織側で従う必要のある手順の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1a55-103">This section details the steps that you have to follow for the Contoso organization.</span></span> <span data-ttu-id="e1a55-104">使用して 2 つの組織の連絡先情報および取引先契約を追加するには、まず、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e1a55-104">The first step is to add the contact information and partner agreements for the two organizations using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="e1a55-105">次に、基幹業務 (LOB) スキーマを作成し、これらのスキーマとそれぞれの RosettaNet ベースの PIP (Partner Interface Process) スキーマとの間のマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1a55-105">You then create line-of-business (LOB) schemas, and construct a mapping between those schemas and their respective RosettaNet-based Partner Interface Process (PIP) schemas.</span></span> <span data-ttu-id="e1a55-106">次に、ERP システムとの通信には SQL アダプターを、Fabrikam への情報の送信には HTTP アダプターを使用するポート情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="e1a55-106">Next, you configure port information using the SQL adapter for communicating with the ERP system, and the HTTP adapter for sending information to Fabrikam.</span></span> <span data-ttu-id="e1a55-107">最後の手順では、BizTalk Server でビジネス ルール エンジン (BRE) を使用するプライベート プロセス オーケストレーションをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="e1a55-107">The last step is to customize the private process orchestration to use the Business Rule Engine (BRE) in BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1a55-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e1a55-108">In This Section</span></span>  
  
-   [<span data-ttu-id="e1a55-109">Contoso の組織および取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="e1a55-109">Creating Organizations and Trading Partner Agreement for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-organizations-and-trading-partner-agreement-for-contoso.md)  
  
-   [<span data-ttu-id="e1a55-110">Contoso LOB スキーマとマップの作成</span><span class="sxs-lookup"><span data-stu-id="e1a55-110">Creating the Contoso LOB Schemas and Maps</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-lob-schemas-and-maps.md)  
  
-   [<span data-ttu-id="e1a55-111">Contoso の BizTalk ポートの作成と構成</span><span class="sxs-lookup"><span data-stu-id="e1a55-111">Creating and Configuring BizTalk Ports for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)  
  
-   [<span data-ttu-id="e1a55-112">Contoso のプライベート プロセスの作成と変更</span><span class="sxs-lookup"><span data-stu-id="e1a55-112">Creating and Modifying the Private Process for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-modifying-the-private-process-for-contoso.md)