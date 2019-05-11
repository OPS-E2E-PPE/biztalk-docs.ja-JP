---
title: Contoso ソリューションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating solutions
ms.assetid: 02f5326a-68bd-418a-af81-684a73056e2c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 633c373090333e34952a7333899223087fce4dc8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284040"
---
# <a name="creating-the-contoso-solution"></a><span data-ttu-id="2c3e0-102">Contoso ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="2c3e0-102">Creating the Contoso Solution</span></span>
<span data-ttu-id="2c3e0-103">このセクションでは、Contoso 組織に従う必要のある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c3e0-103">This section details the steps that you have to follow for the Contoso organization.</span></span> <span data-ttu-id="2c3e0-104">Microsoft® を使用して 2 つの組織の連絡先情報および取引先契約を追加するには、まず[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="2c3e0-104">The first step is to add the contact information and partner agreements for the two organizations using the Microsoft® [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="2c3e0-105">基幹業務 (LOB) スキーマを作成し、それらのスキーマと、それぞれの RosettaNet ベース プロセス PIP (Partner Interface) スキーマの間のマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c3e0-105">You then create line-of-business (LOB) schemas, and construct a mapping between those schemas and their respective RosettaNet-based Partner Interface Process (PIP) schemas.</span></span> <span data-ttu-id="2c3e0-106">次に、情報を Fabrikam に送信するために、ERP システムと HTTP アダプターと通信するための SQL アダプタを使用するポート情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="2c3e0-106">Next, you configure port information using the SQL adapter for communicating with the ERP system, and the HTTP adapter for sending information to Fabrikam.</span></span> <span data-ttu-id="2c3e0-107">最後の手順では、BizTalk Server でビジネス ルール エンジン (BRE) を使用するプライベート プロセス オーケストレーションをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="2c3e0-107">The last step is to customize the private process orchestration to use the Business Rule Engine (BRE) in BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c3e0-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2c3e0-108">In This Section</span></span>  
  
-   [<span data-ttu-id="2c3e0-109">Contoso の組織および取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="2c3e0-109">Creating Organizations and Trading Partner Agreement for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-organizations-and-trading-partner-agreement-for-contoso.md)  
  
-   [<span data-ttu-id="2c3e0-110">Contoso LOB スキーマとマップの作成</span><span class="sxs-lookup"><span data-stu-id="2c3e0-110">Creating the Contoso LOB Schemas and Maps</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-lob-schemas-and-maps.md)  
  
-   [<span data-ttu-id="2c3e0-111">Contoso の BizTalk ポートの作成と構成</span><span class="sxs-lookup"><span data-stu-id="2c3e0-111">Creating and Configuring BizTalk Ports for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)  
  
-   [<span data-ttu-id="2c3e0-112">作成と Contoso のプライベート プロセスの変更</span><span class="sxs-lookup"><span data-stu-id="2c3e0-112">Creating and Modifying the Private Process for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-modifying-the-private-process-for-contoso.md)