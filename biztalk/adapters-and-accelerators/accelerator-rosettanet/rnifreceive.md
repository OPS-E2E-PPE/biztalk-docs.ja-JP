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
ms.openlocfilehash: b2c949f87f74881da64475c74c6e26099359f925
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282253"
---
# <a name="rnifreceive"></a><span data-ttu-id="d211a-102">RNIFReceive</span><span class="sxs-lookup"><span data-stu-id="d211a-102">RNIFReceive</span></span>
<span data-ttu-id="d211a-103">このサンプルは、作業 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx ファイルを RNIF メッセージを受信して処理用に準備する、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パブリック プロセス。</span><span class="sxs-lookup"><span data-stu-id="d211a-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx file that receives an RNIF message, and prepares it for processing by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public process.</span></span> <span data-ttu-id="d211a-104">次の ASPX ページをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="d211a-104">You can customize the ASPX page to do the following:</span></span>  
  
- <span data-ttu-id="d211a-105">追加または削除のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="d211a-105">Add or remove performance counters</span></span>  
  
- <span data-ttu-id="d211a-106">データベースへのデータの書き込みや追跡機能のカスタマイズなど、ページに機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="d211a-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
- <span data-ttu-id="d211a-107">検証ページを追加します。</span><span class="sxs-lookup"><span data-stu-id="d211a-107">Add validation to the page</span></span>  
  
  <span data-ttu-id="d211a-108">このサンプルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>\sdk\webapplication\rnifreceiver のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="d211a-108">This sample is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\WebApplication\RNIFReceiver.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d211a-109">使用例</span><span class="sxs-lookup"><span data-stu-id="d211a-109">Demonstrates</span></span>  
 <span data-ttu-id="d211a-110">このサンプルでは、パブリック プロセスは、次のように受信メッセージを準備する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d211a-110">This sample demonstrates how to prepare incoming messages for the public process, including the following:</span></span>  
  
-   <span data-ttu-id="d211a-111">パートナーの RNIFSend.aspx からメッセージを受信</span><span class="sxs-lookup"><span data-stu-id="d211a-111">Receiving the message from the partner's RNIFSend.aspx</span></span>  
  
-   <span data-ttu-id="d211a-112">MIME ヘッダーの検証</span><span class="sxs-lookup"><span data-stu-id="d211a-112">Validating the MIME header</span></span>  
  
-   <span data-ttu-id="d211a-113">メッセージから MIME ヘッダーと境界を削除します。</span><span class="sxs-lookup"><span data-stu-id="d211a-113">Removing the MIME header and boundaries from the message</span></span>  
  
-   <span data-ttu-id="d211a-114">パートナーの RNIFReceive.aspx にメッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="d211a-114">Routing the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="d211a-115">シグナル メッセージを返す</span><span class="sxs-lookup"><span data-stu-id="d211a-115">Returning a signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d211a-116">参照</span><span class="sxs-lookup"><span data-stu-id="d211a-116">See Also</span></span>  
 <span data-ttu-id="d211a-117">[送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="d211a-117">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="d211a-118">Web アプリケーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="d211a-118">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)