---
title: '手順 6: オーケストレーションの開始 |Microsoft ドキュメント'
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
ms.openlocfilehash: 7ef08b7c0db08d527df4943aa25650d81231e703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209514"
---
# <a name="step-6-start-orchestrations"></a><span data-ttu-id="c056f-102">手順 6: オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c056f-102">Step 6: Start Orchestrations</span></span>
<span data-ttu-id="c056f-103">このステップで使用して[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]のオーケストレーションを開始する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c056f-103">In this step, you use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to start the orchestrations for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span>  
  
### <a name="to-start-the-btarn-orchestrations-using-visual-studio"></a><span data-ttu-id="c056f-104">Visual Studio を使用して BTARN オーケストレーションを開始するには</span><span class="sxs-lookup"><span data-stu-id="c056f-104">To start the BTARN orchestrations using Visual Studio</span></span>  
  
1.  <span data-ttu-id="c056f-105">**BTARN**管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、および展開し、 **BizTalk アプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="c056f-105">In the **BTARN** Management Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="c056f-106">をクリックして**送信ポート**、し、開始**PrivateInitiator_To_LOB**と**PrivateResponder_To_LOB**送信ポート。</span><span class="sxs-lookup"><span data-stu-id="c056f-106">Click **Send Ports**, and then start **PrivateInitiator_To_LOB** and **PrivateResponder_To_LOB** send ports.</span></span>  
  
3.  <span data-ttu-id="c056f-107">をクリックして**受信場所**、し有効にして**LOB_To_PrivateInitiator**、 **LOB_To_PrivateResponder**、 **Async_Http_Receive**、および**Sync_Http_Receive**受信場所。</span><span class="sxs-lookup"><span data-stu-id="c056f-107">Click **Receive Locations**, and then enable **LOB_To_PrivateInitiator**, **LOB_To_PrivateResponder**, **Async_Http_Receive**, and **Sync_Http_Receive** receive locations.</span></span>  
  
4.  <span data-ttu-id="c056f-108">をクリックして**オーケストレーション**、すべてを開始および**BTARN オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="c056f-108">Click **Orchestrations**, and start all **BTARN orchestrations**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c056f-109">参照</span><span class="sxs-lookup"><span data-stu-id="c056f-109">See Also</span></span>  
 <span data-ttu-id="c056f-110">[手順 7: サンプル LOB メッセージを作成します。](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md) </span><span class="sxs-lookup"><span data-stu-id="c056f-110">[Step 7: Create a Sample LOB Message](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md) </span></span>  
 [<span data-ttu-id="c056f-111">停止および開始オーケストレーション、送信ポート、および受信場所をプログラムで</span><span class="sxs-lookup"><span data-stu-id="c056f-111">Stopping and Starting Orchestrations, Send Ports, and Receive Locations Programmatically</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)