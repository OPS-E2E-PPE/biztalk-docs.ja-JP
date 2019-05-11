---
title: BTARN での SQL 処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- LOBs
- SQL processing
- messages, message flow
- BTARN, SQL processing
ms.assetid: cfaf804f-3803-438e-a22e-50f487fe21c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adbf3e0cfdc397b94383d7e0241eeddad045572d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281726"
---
# <a name="sql-processing-in-btarn"></a><span data-ttu-id="24758-102">BTARN での SQL 処理</span><span class="sxs-lookup"><span data-stu-id="24758-102">SQL Processing in BTARN</span></span>
<span data-ttu-id="24758-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]基幹業務 (LOB) アプリケーションからのメッセージをルーティングする SQL アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="24758-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses a SQL adapter to route a message from the line-of-business (LOB) application.</span></span> <span data-ttu-id="24758-104">SQL 送信ポートを使用して LOB アプリケーションにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="24758-104">It uses a SQL send port to route a message to the LOB application.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="24758-105">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="24758-105">Message Flow</span></span>  
 <span data-ttu-id="24758-106">バックエンドの LOB アプリケーションがの MessagesFromLOB テーブルにメッセージをルーティング、発信側または応答側コンピュータ、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="24758-106">On either the initiator or responder computer, the back-end LOB application routes a message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="24758-107">SQL アダプターを使用して、プライベート プロセスに MessagesFromLOB テーブルからメッセージを移動します。</span><span class="sxs-lookup"><span data-stu-id="24758-107">uses a SQL adapter to move the message from the MessagesFromLOB table to the private process.</span></span> <span data-ttu-id="24758-108">詳細については、BizTalk Server ヘルプの「SQL アダプタ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24758-108">For more information, see "SQL Adapter" in BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="24758-109">ファイル アダプターを使用して、サービス コンテンツを送信することもできます[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]既定の SQL アダプタを使用する代わりにします。</span><span class="sxs-lookup"><span data-stu-id="24758-109">You can choose to use a File adapter to submit service content to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], instead of using the default SQL adapter.</span></span> <span data-ttu-id="24758-110">ファイル アダプターを使用する場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]は添付ファイルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="24758-110">If you choose to use a File adapter, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not support attachments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24758-111">参照</span><span class="sxs-lookup"><span data-stu-id="24758-111">See Also</span></span>  
 [<span data-ttu-id="24758-112">BTARN でのメッセージ処理</span><span class="sxs-lookup"><span data-stu-id="24758-112">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)