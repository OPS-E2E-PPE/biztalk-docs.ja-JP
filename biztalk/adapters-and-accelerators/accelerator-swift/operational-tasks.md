---
title: "オペレーション タスク |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing
- BizTalk Accelerator for SWIFT, administering
- BizTalk Accelerator for SWIFT, managing
- administering
ms.assetid: 555335a0-5a85-4498-b34f-97bb508ea5b1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bc5b778f3bca84422ca961da4a358d2aa0f7f39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operational-tasks"></a><span data-ttu-id="060ea-102">オペレーション タスク</span><span class="sxs-lookup"><span data-stu-id="060ea-102">Operational tasks</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="060ea-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 1 つまたは複数のサーバーと一連の財務ビジネス プロセスを自動化して、SWIFT FIN 標準を使用してメッセージ交換を容易にすることでエンタープライズ アプリケーション統合 (EAI) のツールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="060ea-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] encompasses one or more servers and a series of tools for enterprise application integration (EAI), automating financial business processes, and facilitating message exchange using the SWIFT FIN standard.</span></span>  
  
 <span data-ttu-id="060ea-104">管理操作に含める[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="060ea-104">Operations include the administration and management of [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] applications.</span></span> <span data-ttu-id="060ea-105">A4SWIFT は、これらの操作を実行するのに次のツールとコンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="060ea-105">A4SWIFT uses the following tools and consoles to perform these operations:</span></span>  
  
-   <span data-ttu-id="060ea-106">**BizTalk Server 管理コンソールです。**</span><span class="sxs-lookup"><span data-stu-id="060ea-106">**BizTalk Server Administration Console.**</span></span> <span data-ttu-id="060ea-107">このツールを使用すると、BizTalk グループ、すべての BizTalk データベースを含むビジネス プロセスのパフォーマンスを追跡するために管理できます。</span><span class="sxs-lookup"><span data-stu-id="060ea-107">Use this tool to manage the BizTalk group, including all BizTalk databases, to track the performance of business processes.</span></span>  
  
-   <span data-ttu-id="060ea-108">**ビジネス アクティビティの監視 (BAM) フレームワークです。**</span><span class="sxs-lookup"><span data-stu-id="060ea-108">**Business Activity Monitoring (BAM) Framework.**</span></span> <span data-ttu-id="060ea-109">データ項目とビジネス トランザクション中に収集されたビジネス マイルス トーンを追跡するには、このツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="060ea-109">Use this tool to track data items and business milestones collected during business transactions.</span></span>  
  
 <span data-ttu-id="060ea-110">SWIFT の逆アセンブラーの強化 (装飾) A4SWIFT と共に処理されるメッセージの昇格させたプロパティです。</span><span class="sxs-lookup"><span data-stu-id="060ea-110">The SWIFT disassembler enhances (decorates) messages that it processes with A4SWIFT promoted properties.</span></span> <span data-ttu-id="060ea-111">そのため、BAM および HAT のクエリ式では、オプションでフィルター処理用のこれらのプロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="060ea-111">As such, HAT and BAM query expressions optionally include these properties for filtering.</span></span> <span data-ttu-id="060ea-112">A4SWIFT の昇格させたプロパティの一覧は、次を参照してください。 [A4SWIFT_ * 昇格されたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="060ea-112">For a list of A4SWIFT promoted properties, see [A4SWIFT_* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
 <span data-ttu-id="060ea-113">について[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]操作、セクションを参照して、操作で[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="060ea-113">For information about [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] operations, see the Operations section in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="060ea-114">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="060ea-114">This section contains:</span></span>  
  
-   [<span data-ttu-id="060ea-115">メッセージの修復し、新しいメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="060ea-115">Repairing Messages and Submitting New Messages</span></span>](../../adapters-and-accelerators/accelerator-swift/repairing-messages-and-submitting-new-messages.md)  
  
-   [<span data-ttu-id="060ea-116">管理操作</span><span class="sxs-lookup"><span data-stu-id="060ea-116">Administrative Operations</span></span>](../../adapters-and-accelerators/accelerator-swift/administrative-operations.md)