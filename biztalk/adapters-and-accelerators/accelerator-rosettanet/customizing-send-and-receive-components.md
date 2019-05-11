---
title: 送受信コンポーネントの RosettaNet アクセラレータを使用して、BizTalk Server での送信のカスタマイズ |Microsoft Docs
description: 作成、カスタマイズ、または、RosettaNet acclerator (BTARN) に送信し、BizTalk Server での受信ポートのプロパティを設定
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
ms.openlocfilehash: 1127eed100389f548c7a4b579a44ee84120529e2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283777"
---
# <a name="customizing-send-and-receive-components"></a><span data-ttu-id="971ad-103">送受信コンポーネントのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="971ad-103">Customizing Send and Receive Components</span></span>
<span data-ttu-id="971ad-104">このセクションのトピックでは、作成、カスタマイズ、または Microsoft® のプロパティを設定する方法を説明[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]コンポーネントを送受信します。</span><span class="sxs-lookup"><span data-stu-id="971ad-104">The topics in this section describe how to create, customize, or set the properties of Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] send and receive components.</span></span> <span data-ttu-id="971ad-105">これらのコンポーネントは、送信、およびポート、およびアダプターを受信する ASPX ページが含まれます。</span><span class="sxs-lookup"><span data-stu-id="971ad-105">These components include ASPX pages, send and receive ports, and adapters.</span></span>  
  
 <span data-ttu-id="971ad-106">詳細については[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、し[RosettaNet アクセラレータについて](learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md)します。</span><span class="sxs-lookup"><span data-stu-id="971ad-106">For more information about [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], then [read about the RosettaNet accelerator](learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="971ad-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="971ad-107">In This Section</span></span>  
  
-   [<span data-ttu-id="971ad-108">ASPX ページのタイムアウトの設定</span><span class="sxs-lookup"><span data-stu-id="971ad-108">Setting the Connection Time-Out for an ASPX Page</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-the-connection-time-out-for-an-aspx-page.md)  
  
-   [<span data-ttu-id="971ad-109">孤立したメッセージまたは重複メッセージを処理する送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="971ad-109">Creating a Send Port to Handle Orphan or Duplicate Messages</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-send-port-to-handle-orphan-or-duplicate-messages.md)  
  
-   [<span data-ttu-id="971ad-110">パブリック プロセス オーケストレーションと HTTP アダプタのタイムアウト設定</span><span class="sxs-lookup"><span data-stu-id="971ad-110">Setting Time-Outs for a Public-Process Orchestration and an HTTP Adapter</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter.md)