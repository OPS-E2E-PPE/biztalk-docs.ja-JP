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
ms.openlocfilehash: c29ec45b6ed7a8a7b5e3911794aa936a78c586ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357783"
---
# <a name="building-blocks-of-a-trading-partner-management-solution"></a><span data-ttu-id="b0d55-102">パートナーの取引先管理ソリューションのビルド ブロック</span><span class="sxs-lookup"><span data-stu-id="b0d55-102">Building Blocks of a Trading Partner Management Solution</span></span>
## <a name="overview"></a><span data-ttu-id="b0d55-103">概要</span><span class="sxs-lookup"><span data-stu-id="b0d55-103">Overview</span></span>
<span data-ttu-id="b0d55-104">1 つのコア価値提案の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]顧客、ビジネス パートナーと企業間取引 (B2B) 通信を有効にできるようにします。</span><span class="sxs-lookup"><span data-stu-id="b0d55-104">One of the core value propositions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to empower customers to enable business-to-business (B2B) communication with their business partners.</span></span> <span data-ttu-id="b0d55-105">このようなビジネスを満たすために必要な企業は、モデル化、保存、およびに関する情報を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0d55-105">To fulfill such business needs, enterprises need to model, store, and manage information about:</span></span>  
  
- <span data-ttu-id="b0d55-106">パートナーおよびパートナーのビジネス</span><span class="sxs-lookup"><span data-stu-id="b0d55-106">Partners and their businesses</span></span>  
  
- <span data-ttu-id="b0d55-107">パートナー – と活動ルールにはなどを (AS2) を使用するプロトコルなど (EDI 標準) を使用するエンコード プロトコル メッセージ、トランスポートの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b0d55-107">Rules of engagement with the partners – These include details such as which message encoding protocol to use (EDI standards), which transport protocol to use (AS2), etc.</span></span>  
  
  <span data-ttu-id="b0d55-108">中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI および AS2 でサポートするためには引き続き管理し、パートナーとパートナーのビジネスに関する情報を格納する方法について、基本的な概念に追加します。</span><span class="sxs-lookup"><span data-stu-id="b0d55-108">While [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] continues to provide support for EDI and AS2, it adds to the fundamental concepts around how to manage and store information about partners and their business.</span></span> <span data-ttu-id="b0d55-109">EDI 標準、AS2 メッセージ処理、および概念が一緒に、B2B 通信または取引先管理 (TPM) ソリューションのビルド ブロックを形成します。</span><span class="sxs-lookup"><span data-stu-id="b0d55-109">EDI standards, AS2 messaging, and the concepts put together form the building blocks of a B2B communication or a Trading Partner Management (TPM) solution.</span></span> <span data-ttu-id="b0d55-110">ここでは、これらの概念の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0d55-110">This section provides detailed explanation about these concepts.</span></span> 
 
  <span data-ttu-id="b0d55-111">方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI および AS2 のサポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0d55-111">For information about how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] supports EDI and AS2, see:</span></span>
 
  - [<span data-ttu-id="b0d55-112">BizTalk Server の EDI 機能</span><span class="sxs-lookup"><span data-stu-id="b0d55-112">BizTalk Server EDI functionality</span></span>](../core/biztalk-server-edi-functionality.md)
  - [<span data-ttu-id="b0d55-113">BizTalk Server AS2 機能</span><span class="sxs-lookup"><span data-stu-id="b0d55-113">BizTalk Server AS2 functionality</span></span>](../core/biztalk-server-as2-functionality.md)
  
## <a name="in-this-section"></a><span data-ttu-id="b0d55-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b0d55-114">In This Section</span></span>  
  
-   [<span data-ttu-id="b0d55-115">取引先とビジネス プロファイル</span><span class="sxs-lookup"><span data-stu-id="b0d55-115">Trading partners and business profiles</span></span>](../core/trading-partners-and-business-profiles.md)
  
-   [<span data-ttu-id="b0d55-116">プロトコルの設定</span><span class="sxs-lookup"><span data-stu-id="b0d55-116">Protocol settings</span></span>](../core/protocol-settings.md)  
  
-   [<span data-ttu-id="b0d55-117">取引先アグリーメント</span><span class="sxs-lookup"><span data-stu-id="b0d55-117">Trading partner agreement</span></span>](../core/trading-partner-agreement.md)  
  
-   [<span data-ttu-id="b0d55-118">まとめ。取引先パートナー管理ソリューションを定義します。</span><span class="sxs-lookup"><span data-stu-id="b0d55-118">Putting it all together: Defining a trading partner management solution</span></span>](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="b0d55-119">参照</span><span class="sxs-lookup"><span data-stu-id="b0d55-119">See Also</span></span>  
 [<span data-ttu-id="b0d55-120">BizTalk Server を使用して取引先のパートナー管理</span><span class="sxs-lookup"><span data-stu-id="b0d55-120">Trading Partner Management Using BizTalk Server</span></span>](../core/trading-partner-management-using-biztalk-server.md)