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
ms.openlocfilehash: 0d9aca64afee9ed979b2eee58a5f2bdafb25b461
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011603"
---
# <a name="rnifsend"></a><span data-ttu-id="0df18-102">RNIFSend</span><span class="sxs-lookup"><span data-stu-id="0df18-102">RNIFSend</span></span>
<span data-ttu-id="0df18-103">このサンプルは、作業 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx ファイルが、RNIF 処理用メッセージを準備し、応答側の RNIFReceive.aspx ページにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0df18-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx file that prepares a message for RNIF processing, and sends the message to the RNIFReceive.aspx page at the responder.</span></span> <span data-ttu-id="0df18-104">ASPX ページをカスタマイズして、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0df18-104">You can customize the ASPX page to do the following:</span></span>  
  
- <span data-ttu-id="0df18-105">パフォーマンス カウンタの追加と削除</span><span class="sxs-lookup"><span data-stu-id="0df18-105">Add or remove performance counters</span></span>  
  
- <span data-ttu-id="0df18-106">機能の追加 (データベースへのデータの書き込みや追跡機能のカスタマイズなど)</span><span class="sxs-lookup"><span data-stu-id="0df18-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
- <span data-ttu-id="0df18-107">検証機能の追加</span><span class="sxs-lookup"><span data-stu-id="0df18-107">Add validation to the page</span></span>  
  
  <span data-ttu-id="0df18-108">このサンプルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>\sdk\webapplication\rnifsender のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="0df18-108">This sample is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\WebApplication\RNIFSender.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="0df18-109">使用例</span><span class="sxs-lookup"><span data-stu-id="0df18-109">Demonstrates</span></span>  
 <span data-ttu-id="0df18-110">このサンプルは、以下のような RNIF 処理用の送信メッセージを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0df18-110">This sample demonstrates how to prepare outgoing messages for RNIF processing, including the following:</span></span>  
  
-   <span data-ttu-id="0df18-111">MIME ヘッダーのデータを検証する</span><span class="sxs-lookup"><span data-stu-id="0df18-111">Validating the data for the MIME header</span></span>  
  
-   <span data-ttu-id="0df18-112">MIME ヘッダーと MIME 境界をページに追加する</span><span class="sxs-lookup"><span data-stu-id="0df18-112">Adding a MIME header and MIME boundaries to the message</span></span>  
  
-   <span data-ttu-id="0df18-113">取引先の RNIFReceive.aspx にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="0df18-113">Sending the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="0df18-114">返されたシグナル メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="0df18-114">Processing a returned signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df18-115">参照</span><span class="sxs-lookup"><span data-stu-id="0df18-115">See Also</span></span>  
 <span data-ttu-id="0df18-116">[送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="0df18-116">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="0df18-117">Web アプリケーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="0df18-117">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)