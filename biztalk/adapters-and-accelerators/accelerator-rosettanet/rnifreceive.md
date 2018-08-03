---
title: RNIFReceive |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf1253b0-ceca-4e7a-91ed-3837bd904472
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d54b66c42fae286ec748ef560c461a22124165b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991779"
---
# <a name="rnifreceive"></a><span data-ttu-id="ae8ad-102">RNIFReceive</span><span class="sxs-lookup"><span data-stu-id="ae8ad-102">RNIFReceive</span></span>
<span data-ttu-id="ae8ad-103">このサンプルは、作業 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx ファイルを RNIF メッセージを受信して処理用に準備する、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パブリック プロセス。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx file that receives an RNIF message, and prepares it for processing by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public process.</span></span> <span data-ttu-id="ae8ad-104">ASPX ページをカスタマイズして、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-104">You can customize the ASPX page to do the following:</span></span>  
  
- <span data-ttu-id="ae8ad-105">パフォーマンス カウンタの追加と削除</span><span class="sxs-lookup"><span data-stu-id="ae8ad-105">Add or remove performance counters</span></span>  
  
- <span data-ttu-id="ae8ad-106">機能の追加 (データベースへのデータの書き込みや追跡機能のカスタマイズなど)</span><span class="sxs-lookup"><span data-stu-id="ae8ad-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
- <span data-ttu-id="ae8ad-107">検証機能の追加</span><span class="sxs-lookup"><span data-stu-id="ae8ad-107">Add validation to the page</span></span>  
  
  <span data-ttu-id="ae8ad-108">このサンプルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>\sdk\webapplication\rnifreceiver のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-108">This sample is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\WebApplication\RNIFReceiver.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ae8ad-109">使用例</span><span class="sxs-lookup"><span data-stu-id="ae8ad-109">Demonstrates</span></span>  
 <span data-ttu-id="ae8ad-110">このサンプルは、以下を含み、パブリック プロセス用に着信メッセージを準備する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-110">This sample demonstrates how to prepare incoming messages for the public process, including the following:</span></span>  
  
-   <span data-ttu-id="ae8ad-111">パートナーの RNIFSend.aspx からのメッセージの受信</span><span class="sxs-lookup"><span data-stu-id="ae8ad-111">Receiving the message from the partner's RNIFSend.aspx</span></span>  
  
-   <span data-ttu-id="ae8ad-112">MIME ヘッダーの検証</span><span class="sxs-lookup"><span data-stu-id="ae8ad-112">Validating the MIME header</span></span>  
  
-   <span data-ttu-id="ae8ad-113">メッセージからの MIME ヘッダーと境界の削除</span><span class="sxs-lookup"><span data-stu-id="ae8ad-113">Removing the MIME header and boundaries from the message</span></span>  
  
-   <span data-ttu-id="ae8ad-114">パートナーの RNIFReceive.aspx へのメッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="ae8ad-114">Routing the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="ae8ad-115">シグナル メッセージの返信</span><span class="sxs-lookup"><span data-stu-id="ae8ad-115">Returning a signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8ad-116">参照</span><span class="sxs-lookup"><span data-stu-id="ae8ad-116">See Also</span></span>  
 <span data-ttu-id="ae8ad-117">[送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="ae8ad-117">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="ae8ad-118">Web アプリケーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="ae8ad-118">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)