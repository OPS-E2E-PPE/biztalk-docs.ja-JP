---
title: "RNIFReceive |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf1253b0-ceca-4e7a-91ed-3837bd904472
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57af8140157b901d7e6265fc26249c7fbfef0c46
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="rnifreceive"></a><span data-ttu-id="79c9b-102">RNIFReceive</span><span class="sxs-lookup"><span data-stu-id="79c9b-102">RNIFReceive</span></span>
<span data-ttu-id="79c9b-103">このサンプルは、RNIF メッセージを受信し、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] パブリック プロセスによって処理するためにそれを準備する有効な [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]® [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNIFReceive.aspx ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="79c9b-103">This sample provides a working [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx file that receives an RNIF message, and prepares it for processing by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public process.</span></span> <span data-ttu-id="79c9b-104">ASPX ページをカスタマイズして、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="79c9b-104">You can customize the ASPX page to do the following:</span></span>  
  
-   <span data-ttu-id="79c9b-105">パフォーマンス カウンタの追加と削除</span><span class="sxs-lookup"><span data-stu-id="79c9b-105">Add or remove performance counters</span></span>  
  
-   <span data-ttu-id="79c9b-106">機能の追加 (データベースへのデータの書き込みや追跡機能のカスタマイズなど)</span><span class="sxs-lookup"><span data-stu-id="79c9b-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
-   <span data-ttu-id="79c9b-107">検証機能の追加</span><span class="sxs-lookup"><span data-stu-id="79c9b-107">Add validation to the page</span></span>  
  
 <span data-ttu-id="79c9b-108">このサンプルに格納*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>\sdk\webapplication\rnifreceiver のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="79c9b-108">This sample is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\WebApplication\RNIFReceiver.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="79c9b-109">使用例</span><span class="sxs-lookup"><span data-stu-id="79c9b-109">Demonstrates</span></span>  
 <span data-ttu-id="79c9b-110">このサンプルは、以下を含み、パブリック プロセス用に着信メッセージを準備する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79c9b-110">This sample demonstrates how to prepare incoming messages for the public process, including the following:</span></span>  
  
-   <span data-ttu-id="79c9b-111">パートナーの RNIFSend.aspx からのメッセージの受信</span><span class="sxs-lookup"><span data-stu-id="79c9b-111">Receiving the message from the partner's RNIFSend.aspx</span></span>  
  
-   <span data-ttu-id="79c9b-112">MIME ヘッダーの検証</span><span class="sxs-lookup"><span data-stu-id="79c9b-112">Validating the MIME header</span></span>  
  
-   <span data-ttu-id="79c9b-113">メッセージからの MIME ヘッダーと境界の削除</span><span class="sxs-lookup"><span data-stu-id="79c9b-113">Removing the MIME header and boundaries from the message</span></span>  
  
-   <span data-ttu-id="79c9b-114">パートナーの RNIFReceive.aspx へのメッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="79c9b-114">Routing the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="79c9b-115">シグナル メッセージの返信</span><span class="sxs-lookup"><span data-stu-id="79c9b-115">Returning a signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c9b-116">参照</span><span class="sxs-lookup"><span data-stu-id="79c9b-116">See Also</span></span>  
 <span data-ttu-id="79c9b-117">[送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="79c9b-117">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="79c9b-118">Web アプリケーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="79c9b-118">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)