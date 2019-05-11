---
title: 手順 6:オーケストレーションの開始 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- loopback tutorial, starting orchestratrations
ms.assetid: f16a4a77-04fe-4e73-8517-556668174eb9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a79ac73ef2b275cd5b3740f6dccd32918f43b493
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280641"
---
# <a name="step-6-start-orchestrations"></a><span data-ttu-id="678e7-102">手順 6:オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="678e7-102">Step 6: Start Orchestrations</span></span>
<span data-ttu-id="678e7-103">この手順で Microsoft を使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Microsoft のオーケストレーションを開始する[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="678e7-103">In this step, you use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to start the orchestrations for Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span>  
  
### <a name="to-start-the-btarn-orchestrations-using-visual-studio"></a><span data-ttu-id="678e7-104">Visual Studio を使用して BTARN オーケストレーションを開始するには</span><span class="sxs-lookup"><span data-stu-id="678e7-104">To start the BTARN orchestrations using Visual Studio</span></span>  
  
1.  <span data-ttu-id="678e7-105">**BTARN**管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**と順に展開**BizTalk アプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="678e7-105">In the **BTARN** Management Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="678e7-106">クリックして**送信ポート**、し、開始**PrivateInitiator_To_LOB**と**PrivateResponder_To_LOB**送信ポート。</span><span class="sxs-lookup"><span data-stu-id="678e7-106">Click **Send Ports**, and then start **PrivateInitiator_To_LOB** and **PrivateResponder_To_LOB** send ports.</span></span>  
  
3.  <span data-ttu-id="678e7-107">クリックして**受信場所**、しを有効にして**LOB_To_PrivateInitiator**、 **LOB_To_PrivateResponder**、 **Async_Http_Receive**、**Sync_Http_Receive**受信場所。</span><span class="sxs-lookup"><span data-stu-id="678e7-107">Click **Receive Locations**, and then enable **LOB_To_PrivateInitiator**, **LOB_To_PrivateResponder**, **Async_Http_Receive**, and **Sync_Http_Receive** receive locations.</span></span>  
  
4.  <span data-ttu-id="678e7-108">クリックして**オーケストレーション**、すべてを開始および**BTARN オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="678e7-108">Click **Orchestrations**, and start all **BTARN orchestrations**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="678e7-109">参照</span><span class="sxs-lookup"><span data-stu-id="678e7-109">See Also</span></span>  
 <span data-ttu-id="678e7-110">[手順 7:サンプル LOB メッセージを作成します。](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md) </span><span class="sxs-lookup"><span data-stu-id="678e7-110">[Step 7: Create a Sample LOB Message](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md) </span></span>  
 [<span data-ttu-id="678e7-111">プログラミングによるオーケストレーション、送信ポート、受信場所の停止および開始</span><span class="sxs-lookup"><span data-stu-id="678e7-111">Stopping and Starting Orchestrations, Send Ports, and Receive Locations Programmatically</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)