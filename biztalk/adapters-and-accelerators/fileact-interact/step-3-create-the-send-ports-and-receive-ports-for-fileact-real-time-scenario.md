---
title: '手順 3: 送信ポートを作成し、FileAct リアルタイムのシナリオの受信ポート |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d7d39c7-a08b-4fbb-85fe-b30a8d62524b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa7b0465ca6909998379ea94ef173d30387da602
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223778"
---
# <a name="step-3-create-the-send-ports-and-receive-ports-for-the-fileact-real-time-scenario"></a><span data-ttu-id="146d8-102">手順 3: 送信ポートを作成し、FileAct リアルタイムのシナリオの受信ポート</span><span class="sxs-lookup"><span data-stu-id="146d8-102">Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="146d8-103">このセクションの手順を開始する前に行う必要があります[手順 2: FileAct リアルタイム シナリオ Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="146d8-103">Before you begin the steps in this section, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="146d8-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="146d8-104">In This Section</span></span>  
  
-   [<span data-ttu-id="146d8-105">手順 3: ファイルの受信場所、FileAct リアルタイムのシナリオの追加</span><span class="sxs-lookup"><span data-stu-id="146d8-105">Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="146d8-106">手順 3 b: FILEACT の受信場所が FileAct リアルタイム シナリオの追加</span><span class="sxs-lookup"><span data-stu-id="146d8-106">Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="146d8-107">手順 3 C: FileAct リアルタイム シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="146d8-107">Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)  
  
-   [<span data-ttu-id="146d8-108">ステップ 3 D: FileAct リアルタイム シナリオ FILEACT 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="146d8-108">Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="146d8-109">ステップ 3 e: FileAct リアルタイム シナリオ Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="146d8-109">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)  
  
-   [<span data-ttu-id="146d8-110">ステップ 3 f: ソフトウェア HandleFileEventRequest メッセージをキャプチャする FileAct リアルタイム シナリオの FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="146d8-110">Step 3F: Add a FILE Send Port for the FileAct Real-Time Scenario to Capture Sw-HandleFileEventRequest Messages</span></span>](../../adapters-and-accelerators/fileact-interact/step-3f-add-file-send-port-to-get-sw-handlefileeventrequest-messages--fileact.md)