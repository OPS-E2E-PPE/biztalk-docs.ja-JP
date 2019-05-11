---
title: RNIFSend |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 780f7446-56c5-40bf-95e2-25d0cff12f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92ad9b7c0318a028b6b2f98a75eca1484014b305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282238"
---
# <a name="rnifsend"></a><span data-ttu-id="7b9c3-102">RNIFSend</span><span class="sxs-lookup"><span data-stu-id="7b9c3-102">RNIFSend</span></span>
<span data-ttu-id="7b9c3-103">このサンプルは、作業 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx ファイルが、RNIF 処理用メッセージを準備し、応答側の RNIFReceive.aspx ページにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7b9c3-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx file that prepares a message for RNIF processing, and sends the message to the RNIFReceive.aspx page at the responder.</span></span> <span data-ttu-id="7b9c3-104">次の ASPX ページをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="7b9c3-104">You can customize the ASPX page to do the following:</span></span>  
  
- <span data-ttu-id="7b9c3-105">追加または削除のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="7b9c3-105">Add or remove performance counters</span></span>  
  
- <span data-ttu-id="7b9c3-106">データベースへのデータの書き込みや追跡機能のカスタマイズなど、ページに機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="7b9c3-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
- <span data-ttu-id="7b9c3-107">検証ページを追加します。</span><span class="sxs-lookup"><span data-stu-id="7b9c3-107">Add validation to the page</span></span>  
  
  <span data-ttu-id="7b9c3-108">このサンプルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>\sdk\webapplication\rnifsender のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="7b9c3-108">This sample is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\WebApplication\RNIFSender.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="7b9c3-109">使用例</span><span class="sxs-lookup"><span data-stu-id="7b9c3-109">Demonstrates</span></span>  
 <span data-ttu-id="7b9c3-110">このサンプルでは、RNIF 処理には、次の送信メッセージを準備する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7b9c3-110">This sample demonstrates how to prepare outgoing messages for RNIF processing, including the following:</span></span>  
  
-   <span data-ttu-id="7b9c3-111">MIME ヘッダーのデータの検証</span><span class="sxs-lookup"><span data-stu-id="7b9c3-111">Validating the data for the MIME header</span></span>  
  
-   <span data-ttu-id="7b9c3-112">メッセージに MIME ヘッダーと MIME 境界を追加します。</span><span class="sxs-lookup"><span data-stu-id="7b9c3-112">Adding a MIME header and MIME boundaries to the message</span></span>  
  
-   <span data-ttu-id="7b9c3-113">パートナーの RNIFReceive.aspx にメッセージを送信</span><span class="sxs-lookup"><span data-stu-id="7b9c3-113">Sending the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="7b9c3-114">返されたシグナル メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="7b9c3-114">Processing a returned signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b9c3-115">参照</span><span class="sxs-lookup"><span data-stu-id="7b9c3-115">See Also</span></span>  
 <span data-ttu-id="7b9c3-116">[送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="7b9c3-116">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="7b9c3-117">Web アプリケーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="7b9c3-117">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)