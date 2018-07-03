---
title: 取引先の構成要素はパートナー管理ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0dabb562-7065-44b8-a26f-658d70b126eb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e72d0fc6ff852b18d6cfe18e8c1a6fe9eb9839
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993091"
---
# <a name="building-blocks-of-a-trading-partner-management-solution"></a><span data-ttu-id="379f6-102">取引先管理ソリューションの構成要素</span><span class="sxs-lookup"><span data-stu-id="379f6-102">Building Blocks of a Trading Partner Management Solution</span></span>
## <a name="overview"></a><span data-ttu-id="379f6-103">概要</span><span class="sxs-lookup"><span data-stu-id="379f6-103">Overview</span></span>
<span data-ttu-id="379f6-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の中核的な価値提案の 1 つは、ユーザーに、取引先との B2B (business-to-business) 通信を行う能力を与えることです。</span><span class="sxs-lookup"><span data-stu-id="379f6-104">One of the core value propositions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to empower customers to enable business-to-business (B2B) communication with their business partners.</span></span> <span data-ttu-id="379f6-105">このようなビジネス ニーズを満たすために、企業は以下に関する情報のモデル化、保存、および管理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="379f6-105">To fulfill such business needs, enterprises need to model, store, and manage information about:</span></span>  
  
- <span data-ttu-id="379f6-106">パートナーおよびパートナーのビジネス</span><span class="sxs-lookup"><span data-stu-id="379f6-106">Partners and their businesses</span></span>  
  
- <span data-ttu-id="379f6-107">パートナーとの通信ルール - 使用するメッセージ エンコード プロトコル (EDI 標準)、使用するトランスポート プロトコル (AS2) などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="379f6-107">Rules of engagement with the partners – These include details such as which message encoding protocol to use (EDI standards), which transport protocol to use (AS2), etc.</span></span>  
  
  <span data-ttu-id="379f6-108">中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI および AS2 でサポートするためには引き続き管理し、パートナーとパートナーのビジネスに関する情報を格納する方法について、基本的な概念に追加します。</span><span class="sxs-lookup"><span data-stu-id="379f6-108">While [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] continues to provide support for EDI and AS2, it adds to the fundamental concepts around how to manage and store information about partners and their business.</span></span> <span data-ttu-id="379f6-109">EDI 標準、AS2 メッセージ処理、および概念が一緒に、B2B 通信または取引先管理 (TPM) ソリューションのビルド ブロックを形成します。</span><span class="sxs-lookup"><span data-stu-id="379f6-109">EDI standards, AS2 messaging, and the concepts put together form the building blocks of a B2B communication or a Trading Partner Management (TPM) solution.</span></span> <span data-ttu-id="379f6-110">ここでは、これらの概念の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="379f6-110">This section provides detailed explanation about these concepts.</span></span> 
 
  <span data-ttu-id="379f6-111">方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI および AS2 のサポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="379f6-111">For information about how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] supports EDI and AS2, see:</span></span>
 
  - [<span data-ttu-id="379f6-112">BizTalk Server の EDI 機能</span><span class="sxs-lookup"><span data-stu-id="379f6-112">BizTalk Server EDI functionality</span></span>](../core/biztalk-server-edi-functionality.md)
  - [<span data-ttu-id="379f6-113">BizTalk Server AS2 機能</span><span class="sxs-lookup"><span data-stu-id="379f6-113">BizTalk Server AS2 functionality</span></span>](../core/biztalk-server-as2-functionality.md)
  
## <a name="in-this-section"></a><span data-ttu-id="379f6-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="379f6-114">In This Section</span></span>  
  
-   [<span data-ttu-id="379f6-115">取引先とビジネス プロファイル</span><span class="sxs-lookup"><span data-stu-id="379f6-115">Trading partners and business profiles</span></span>](../core/trading-partners-and-business-profiles.md)
  
-   [<span data-ttu-id="379f6-116">プロトコルの設定</span><span class="sxs-lookup"><span data-stu-id="379f6-116">Protocol settings</span></span>](../core/protocol-settings.md)  
  
-   [<span data-ttu-id="379f6-117">取引先アグリーメント</span><span class="sxs-lookup"><span data-stu-id="379f6-117">Trading partner agreement</span></span>](../core/trading-partner-agreement.md)  
  
-   [<span data-ttu-id="379f6-118">まとめ: 取引先を定義するパートナーの管理ソリューション</span><span class="sxs-lookup"><span data-stu-id="379f6-118">Putting it all together: Defining a trading partner management solution</span></span>](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="379f6-119">参照</span><span class="sxs-lookup"><span data-stu-id="379f6-119">See Also</span></span>  
 [<span data-ttu-id="379f6-120">BizTalk Server を使用して取引先のパートナー管理</span><span class="sxs-lookup"><span data-stu-id="379f6-120">Trading Partner Management Using BizTalk Server</span></span>](../core/trading-partner-management-using-biztalk-server.md)