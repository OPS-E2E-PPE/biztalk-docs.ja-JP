---
title: チュートリアル 2:.NET からエコー アダプターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e489c79-51b4-4067-9584-67c67f86aedd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74319b2c1b547fabf77aff94450e0bc28453eca9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363073"
---
# <a name="tutorial-2-consume-the-echo-adapter-from-net"></a><span data-ttu-id="53fb9-102">チュートリアル 2:.NET からエコー アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="53fb9-102">Tutorial 2: Consume the Echo Adapter from .NET</span></span>
<span data-ttu-id="53fb9-103">このセクションでは、.NET からエコー アダプターによって公開される、受信と送信操作を使用するための手順では。</span><span class="sxs-lookup"><span data-stu-id="53fb9-103">This section gives the steps for consuming the inbound and outbound operations exposed by the Echo adapter from .NET.</span></span> <span data-ttu-id="53fb9-104">エコー アダプターを開発した[チュートリアル 1。エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="53fb9-104">The Echo adapter was developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53fb9-105">エコー アダプターとテストのコードで BizTalk のインストール ファイルに含まれている`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`または`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`します。</span><span class="sxs-lookup"><span data-stu-id="53fb9-105">The Echo Adapter and test code is included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="53fb9-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="53fb9-106">In This Section</span></span>  
  
-   [<span data-ttu-id="53fb9-107">ステップ 1: エコー アダプターの送信ハンドラーをテストする</span><span class="sxs-lookup"><span data-stu-id="53fb9-107">Step 1: Test Outbound Handler of the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md)  
  
-   [<span data-ttu-id="53fb9-108">手順 2:エコー アダプターの受信ハンドラーをテストする</span><span class="sxs-lookup"><span data-stu-id="53fb9-108">Step 2: Test Inbound Handler of the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="53fb9-109">参照</span><span class="sxs-lookup"><span data-stu-id="53fb9-109">See Also</span></span>  
 <span data-ttu-id="53fb9-110">[チュートリアル 1:エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="53fb9-110">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="53fb9-111">WCF LOB アダプター SDK のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="53fb9-111">WCF LOB Adapter SDK Tutorials</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)