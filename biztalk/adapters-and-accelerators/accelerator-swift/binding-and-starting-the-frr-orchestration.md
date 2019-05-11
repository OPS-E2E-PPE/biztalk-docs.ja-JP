---
title: バインドと FRR オーケストレーションの開始 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, binding orchestrations
- FRR, starting orchestrations
- bindings, orchestrations
- orchestrations, bindings
ms.assetid: b74a0116-e98b-4fec-b386-710ce421a1e2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1189b7db68cc0894725a98887fc82d30dde5a33
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378978"
---
# <a name="binding-and-starting-the-frr-orchestration"></a><span data-ttu-id="6a7ce-102">バインドおよび FRR オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-102">Binding and Starting the FRR Orchestration</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="6a7ce-103">FRR オーケストレーションが展開されたアセンブリ (Microsoft として含まれています。Solutions.FinancialServices.SWIFT.FrrOrchestration)。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-103">includes the FRR orchestration as a deployed assembly (Microsoft .Solutions.FinancialServices.SWIFT.FrrOrchestration).</span></span> <span data-ttu-id="6a7ce-104">このオーケストレーションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-104">You need to start this orchestration.</span></span>  
  
 <span data-ttu-id="6a7ce-105">**まとめ**</span><span class="sxs-lookup"><span data-stu-id="6a7ce-105">**Summary**</span></span>  
  
 <span data-ttu-id="6a7ce-106">FRR オーケストレーションを開始するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-106">To start the FRR orchestration, do the following:</span></span>  
  
-   <span data-ttu-id="6a7ce-107">BizTalkServerApplication ホストを設定して FrrOrchestration.FrrMain オーケストレーションをバインドします。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-107">Bind the FrrOrchestration.FrrMain orchestration by setting the host to BizTalkServerApplication.</span></span>  
  
-   <span data-ttu-id="6a7ce-108">FrrOrchestration.FrrMain オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-108">Start the FrrOrchestration.FrrMain orchestration.</span></span>  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a><span data-ttu-id="6a7ce-109">バインドして FRR オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="6a7ce-109">To bind and start the FRR orchestration</span></span>  
  
1.  <span data-ttu-id="6a7ce-110">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、し**BizTalkアプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-110">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and then **BizTalk Application 1**.</span></span> <span data-ttu-id="6a7ce-111">クリックして**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-111">Click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="6a7ce-112">オーケストレーション ペインで右クリックし、 **FrrOrchestration.FrrMain**オーケストレーション、およびクリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-112">In the Orchestrations pane, right-click the **FrrOrchestration.FrrMain** orchestration, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6a7ce-113">[オーケストレーションのプロパティ] ダイアログ ボックスで、**バインド**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-113">In the Orchestration Properties dialog box, click **Bindings** in the left pane.</span></span> <span data-ttu-id="6a7ce-114">**ホスト**、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-114">For **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="6a7ce-115">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-115">Click **Apply**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="6a7ce-116">オーケストレーション ペインで右クリックし、 **FrrMain**オーケストレーション、およびクリック**開始**します。</span><span class="sxs-lookup"><span data-stu-id="6a7ce-116">In the Orchestrations pane, right-click the **FrrMain** orchestration, and then click **Start**.</span></span>