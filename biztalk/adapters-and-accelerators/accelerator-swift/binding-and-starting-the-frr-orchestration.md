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
ms.openlocfilehash: b01386cedbd25148e5ea0ce2ac44fb56e9fe3d03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987443"
---
# <a name="binding-and-starting-the-frr-orchestration"></a><span data-ttu-id="4e112-102">バインドおよび FRR オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="4e112-102">Binding and Starting the FRR Orchestration</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="4e112-103"> FRR オーケストレーションが展開されたアセンブリ (Microsoft として含まれています。Solutions.FinancialServices.SWIFT.FrrOrchestration)。</span><span class="sxs-lookup"><span data-stu-id="4e112-103"> includes the FRR orchestration as a deployed assembly (Microsoft .Solutions.FinancialServices.SWIFT.FrrOrchestration).</span></span> <span data-ttu-id="4e112-104">このオーケストレーションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e112-104">You need to start this orchestration.</span></span>  
  
 <span data-ttu-id="4e112-105">**概要**</span><span class="sxs-lookup"><span data-stu-id="4e112-105">**Summary**</span></span>  
  
 <span data-ttu-id="4e112-106">FRR オーケストレーションを開始するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4e112-106">To start the FRR orchestration, do the following:</span></span>  
  
-   <span data-ttu-id="4e112-107">BizTalkServerApplication ホストを設定して FrrOrchestration.FrrMain オーケストレーションをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4e112-107">Bind the FrrOrchestration.FrrMain orchestration by setting the host to BizTalkServerApplication.</span></span>  
  
-   <span data-ttu-id="4e112-108">FrrOrchestration.FrrMain オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="4e112-108">Start the FrrOrchestration.FrrMain orchestration.</span></span>  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a><span data-ttu-id="4e112-109">バインドして FRR オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="4e112-109">To bind and start the FRR orchestration</span></span>  
  
1.  <span data-ttu-id="4e112-110">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、し**BizTalkアプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="4e112-110">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and then **BizTalk Application 1**.</span></span> <span data-ttu-id="4e112-111">クリックして**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="4e112-111">Click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="4e112-112">オーケストレーション ペインで右クリックし、 **FrrOrchestration.FrrMain**オーケストレーション、およびクリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4e112-112">In the Orchestrations pane, right-click the **FrrOrchestration.FrrMain** orchestration, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="4e112-113">[オーケストレーションのプロパティ] ダイアログ ボックスで、**バインド**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="4e112-113">In the Orchestration Properties dialog box, click **Bindings** in the left pane.</span></span> <span data-ttu-id="4e112-114">**ホスト**、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="4e112-114">For **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="4e112-115">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4e112-115">Click **Apply**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="4e112-116">オーケストレーション ペインで右クリックし、 **FrrMain**オーケストレーション、およびクリック**開始**します。</span><span class="sxs-lookup"><span data-stu-id="4e112-116">In the Orchestrations pane, right-click the **FrrMain** orchestration, and then click **Start**.</span></span>