---
title: '手順 16: オーケストレーションの開始 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- message enrichment tutorial, orchestrations
ms.assetid: a9032b0b-1497-4f6a-8474-a94c14976be0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d2d1429d6b5d8df7facf55900683356200279b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992771"
---
# <a name="step-16-start-the-orchestration"></a><span data-ttu-id="06482-102">手順 16: オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="06482-102">Step 16: Start the Orchestration</span></span>
<span data-ttu-id="06482-103">この手順では、オーケストレーションを実行する物理環境と、オーケストレーションで設計したビジネス プロセスを関連付けるために、サービスを参加させます。</span><span class="sxs-lookup"><span data-stu-id="06482-103">In this step, you enlist the service in order to associate the business process that you designed in the orchestration with the physical environment in which the orchestration will run.</span></span> <span data-ttu-id="06482-104">さらに、アプリケーションをテストできるように、オーケストレーションの処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="06482-104">Additionally, you start the processing of the orchestration so that you can test your application.</span></span>  
  
### <a name="to-start-the-orchestration"></a><span data-ttu-id="06482-105">オーケストレーションを開始するには</span><span class="sxs-lookup"><span data-stu-id="06482-105">To start the orchestration</span></span>  
  
1. <span data-ttu-id="06482-106">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、コンソールのツリー ウィンドウで [**オーケストレーション**、右クリックして**BTAHL7_Project.Doorbell_Orchestration**、] をクリックし、**参加**.</span><span class="sxs-lookup"><span data-stu-id="06482-106">In the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, in the console tree pane, under **Orchestrations**, right-click **BTAHL7_Project.Doorbell_Orchestration**, and then click **Enlist**.</span></span>  
  
2. <span data-ttu-id="06482-107">右クリック**BTAHL7_Project.Doorbell_Orchestration**、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="06482-107">Right-click **BTAHL7_Project.Doorbell_Orchestration**, and then click **Start**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="06482-108">開始したことを確認、 **MLLPSendPort**送信ポートを有効になっている、 **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**受信場所。</span><span class="sxs-lookup"><span data-stu-id="06482-108">Ensure that you have started the **MLLPSendPort** send port and enabled the **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** receive location.</span></span>  
  
   <span data-ttu-id="06482-109">続行する[手順 17: WSClient アプリケーションの作成](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="06482-109">Proceed to [Step 17: Create the WSClient Application](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06482-110">参照</span><span class="sxs-lookup"><span data-stu-id="06482-110">See Also</span></span>  
 [<span data-ttu-id="06482-111">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="06482-111">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)