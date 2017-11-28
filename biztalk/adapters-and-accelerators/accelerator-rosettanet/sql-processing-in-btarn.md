---
title: "BTARN での SQL 処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- LOBs
- SQL processing
- messages, message flow
- BTARN, SQL processing
ms.assetid: cfaf804f-3803-438e-a22e-50f487fe21c3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf1aba9f2d4d2ea77f369e76c277160739f7f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sql-processing-in-btarn"></a><span data-ttu-id="7fb11-102">BTARN での SQL 処理</span><span class="sxs-lookup"><span data-stu-id="7fb11-102">SQL Processing in BTARN</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="7fb11-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]基幹業務 (LOB) アプリケーションからのメッセージをルーティングする、SQL アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fb11-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses a SQL adapter to route a message from the line-of-business (LOB) application.</span></span> <span data-ttu-id="7fb11-104">LOB アプリケーションへのメッセージのルーティングには、SQL 送信ポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fb11-104">It uses a SQL send port to route a message to the LOB application.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="7fb11-105">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="7fb11-105">Message Flow</span></span>  
 <span data-ttu-id="7fb11-106">発信側または応答側コンピューターで、バックエンド LOB アプリケーション メッセージをルーティングしますの MessagesFromLOB テーブル、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="7fb11-106">On either the initiator or responder computer, the back-end LOB application routes a message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7fb11-107">MessagesFromLOB テーブルから、プライベート プロセスにメッセージを移動するのにには、SQL アダプタを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fb11-107"> uses a SQL adapter to move the message from the MessagesFromLOB table to the private process.</span></span> <span data-ttu-id="7fb11-108">詳細については、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ヘルプの「SQL アダプタ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fb11-108">For more information, see "SQL Adapter" in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="7fb11-109">既定の SQL アダプタを使用する代わりに、ファイル アダプタを使用してサービス コンテンツを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="7fb11-109">You can choose to use a File adapter to submit service content to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], instead of using the default SQL adapter.</span></span> <span data-ttu-id="7fb11-110">ファイル アダプタを使用する場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では添付ファイルがサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7fb11-110">If you choose to use a File adapter, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not support attachments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb11-111">参照</span><span class="sxs-lookup"><span data-stu-id="7fb11-111">See Also</span></span>  
 [<span data-ttu-id="7fb11-112">BTARN でのメッセージ処理</span><span class="sxs-lookup"><span data-stu-id="7fb11-112">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)