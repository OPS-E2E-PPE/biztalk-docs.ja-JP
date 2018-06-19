---
title: 送受信コンポーネントの RosettaNet accelerator を使用して、BizTalk Server での送信をカスタマイズする |Microsoft ドキュメント
description: 作成、カスタマイズ、または RosettaNet acclerator (BTARN) に送信し、BizTalk Server で受信ポートのプロパティを設定
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send components
- developing, send components
- developing, receive components
- receive components
ms.assetid: 78224a31-4eff-4a48-bcb9-deed388299f1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19dbd20fe8e032a31c3665670b6add61eec3c1f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209538"
---
# <a name="customizing-send-and-receive-components"></a><span data-ttu-id="88ea2-103">送受信コンポーネントの送信をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="88ea2-103">Customizing Send and Receive Components</span></span>
<span data-ttu-id="88ea2-104">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] の送受信コンポーネントのプロパティを作成、カスタマイズ、および設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="88ea2-104">The topics in this section describe how to create, customize, or set the properties of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] send and receive components.</span></span> <span data-ttu-id="88ea2-105">これらのコンポーネントには ASPX ページ、送信ポートと受信ポート、およびアダプターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="88ea2-105">These components include ASPX pages, send and receive ports, and adapters.</span></span>  
  
 <span data-ttu-id="88ea2-106">詳細については[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、し[RosettaNet accelerator に関する読み取り](learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md)です。</span><span class="sxs-lookup"><span data-stu-id="88ea2-106">For more information about [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], then [read about the RosettaNet accelerator](learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88ea2-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="88ea2-107">In This Section</span></span>  
  
-   [<span data-ttu-id="88ea2-108">ASPX ページの接続のタイムアウトの設定</span><span class="sxs-lookup"><span data-stu-id="88ea2-108">Setting the Connection Time-Out for an ASPX Page</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-the-connection-time-out-for-an-aspx-page.md)  
  
-   [<span data-ttu-id="88ea2-109">孤立したメッセージまたは重複メッセージを処理する送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="88ea2-109">Creating a Send Port to Handle Orphan or Duplicate Messages</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-send-port-to-handle-orphan-or-duplicate-messages.md)  
  
-   [<span data-ttu-id="88ea2-110">パブリック プロセス オーケストレーションと HTTP アダプターのタイムアウトの設定</span><span class="sxs-lookup"><span data-stu-id="88ea2-110">Setting Time-Outs for a Public-Process Orchestration and an HTTP Adapter</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter.md)