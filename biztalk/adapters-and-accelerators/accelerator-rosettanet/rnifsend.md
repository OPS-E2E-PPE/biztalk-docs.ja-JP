---
title: "RNIFSend |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 780f7446-56c5-40bf-95e2-25d0cff12f12
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1762c30d6524a777a862492701ff0b8a8731a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rnifsend"></a><span data-ttu-id="f6109-102">RNIFSend</span><span class="sxs-lookup"><span data-stu-id="f6109-102">RNIFSend</span></span>
<span data-ttu-id="f6109-103">このサンプルには、RNIF 処理用のメッセージを作成して応答側の RNIFReceive.aspx ページに送信する作業用の [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="f6109-103">This sample provides a working [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx file that prepares a message for RNIF processing, and sends the message to the RNIFReceive.aspx page at the responder.</span></span> <span data-ttu-id="f6109-104">ASPX ページをカスタマイズして、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6109-104">You can customize the ASPX page to do the following:</span></span>  
  
-   <span data-ttu-id="f6109-105">パフォーマンス カウンタの追加と削除</span><span class="sxs-lookup"><span data-stu-id="f6109-105">Add or remove performance counters</span></span>  
  
-   <span data-ttu-id="f6109-106">機能の追加 (データベースへのデータの書き込みや追跡機能のカスタマイズなど)</span><span class="sxs-lookup"><span data-stu-id="f6109-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
-   <span data-ttu-id="f6109-107">検証機能の追加</span><span class="sxs-lookup"><span data-stu-id="f6109-107">Add validation to the page</span></span>  
  
 <span data-ttu-id="f6109-108">このサンプルに格納*\<ドライブ >*: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for \sdk\webapplication\rnifsender です。</span><span class="sxs-lookup"><span data-stu-id="f6109-108">This sample is located in *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\WebApplication\RNIFSender.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="f6109-109">使用例</span><span class="sxs-lookup"><span data-stu-id="f6109-109">Demonstrates</span></span>  
 <span data-ttu-id="f6109-110">このサンプルは、以下のような RNIF 処理用の送信メッセージを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6109-110">This sample demonstrates how to prepare outgoing messages for RNIF processing, including the following:</span></span>  
  
-   <span data-ttu-id="f6109-111">MIME ヘッダーのデータを検証する</span><span class="sxs-lookup"><span data-stu-id="f6109-111">Validating the data for the MIME header</span></span>  
  
-   <span data-ttu-id="f6109-112">MIME ヘッダーと MIME 境界をページに追加する</span><span class="sxs-lookup"><span data-stu-id="f6109-112">Adding a MIME header and MIME boundaries to the message</span></span>  
  
-   <span data-ttu-id="f6109-113">取引先の RNIFReceive.aspx にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="f6109-113">Sending the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="f6109-114">返されたシグナル メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="f6109-114">Processing a returned signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6109-115">参照</span><span class="sxs-lookup"><span data-stu-id="f6109-115">See Also</span></span>  
 <span data-ttu-id="f6109-116">[送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="f6109-116">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="f6109-117">Web アプリケーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="f6109-117">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)