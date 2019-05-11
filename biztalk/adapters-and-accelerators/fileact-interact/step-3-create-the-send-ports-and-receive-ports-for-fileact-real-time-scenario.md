---
title: 手順 3:送信ポートを作成および FileAct リアルタイム シナリオ用の受信ポート |Microsoft Docs
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
ms.openlocfilehash: 70a0b8e561c9e26714b53730e7c4e7e4b1a9d323
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365749"
---
# <a name="step-3-create-the-send-ports-and-receive-ports-for-the-fileact-real-time-scenario"></a><span data-ttu-id="b1369-102">手順 3:送信ポートを作成および FileAct リアルタイム シナリオ用の受信ポート</span><span class="sxs-lookup"><span data-stu-id="b1369-102">Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="b1369-103">このセクションの手順を開始する前に行う必要があります[手順 2。FileAct リアルタイム シナリオ用に Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="b1369-103">Before you begin the steps in this section, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1369-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b1369-104">In This Section</span></span>  
  
-   [<span data-ttu-id="b1369-105">手順 3 a:ファイル受信 FileAct リアルタイム シナリオ用の場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="b1369-105">Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="b1369-106">手順 3 b:FileAct リアルタイム シナリオ用の場所に、FILEACT の受信を追加します。</span><span class="sxs-lookup"><span data-stu-id="b1369-106">Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="b1369-107">手順 3 C:FileAct リアルタイム シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="b1369-107">Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)  
  
-   [<span data-ttu-id="b1369-108">手順 3 D:FileAct リアルタイム シナリオ用に FILEACT 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="b1369-108">Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="b1369-109">手順 3 e:FileAct リアルタイム シナリオ用に Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="b1369-109">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)  
  
-   [<span data-ttu-id="b1369-110">手順 3 f:Sw-handlefileeventrequest メッセージをキャプチャする FileAct リアルタイム シナリオ用の FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="b1369-110">Step 3F: Add a FILE Send Port for the FileAct Real-Time Scenario to Capture Sw-HandleFileEventRequest Messages</span></span>](../../adapters-and-accelerators/fileact-interact/step-3f-add-file-send-port-to-get-sw-handlefileeventrequest-messages--fileact.md)