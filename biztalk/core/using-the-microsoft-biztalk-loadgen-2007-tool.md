---
title: Microsoft BizTalk LoadGen 2007 ツールを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1973a26-1c98-4261-bd9a-6357cdb19ccf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba37985ad0841f0bc6b39bb9a5958b625033f168
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396000"
---
# <a name="using-the-microsoft-biztalk-loadgen-2007-tool"></a><span data-ttu-id="80c98-102">Microsoft BizTalk LoadGen 2007 ツールを使用</span><span class="sxs-lookup"><span data-stu-id="80c98-102">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>
<span data-ttu-id="80c98-103">Microsoft BizTalk LoadGen 2007 ツールが開発者向けし、BizTalk Server 上の負荷をシミュレートするために IT プロフェッショナル。</span><span class="sxs-lookup"><span data-stu-id="80c98-103">The Microsoft BizTalk LoadGen 2007 Tool is intended for developers and IT professionals to simulate load on a BizTalk Server.</span></span> <span data-ttu-id="80c98-104">このツールを使用して、インストルメント化のパフォーマンスとストレス BizTalk 展開に対する負荷をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="80c98-104">Using this tool, you can simulate load to instrument performance and stress against a BizTalk deployment.</span></span> <span data-ttu-id="80c98-105">さらに、このツールは、カスタム トランスポートの負荷をシミュレートする開発者も拡張可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80c98-105">In addition, this tool may also be extended by developers to simulate load for custom transports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80c98-106">ダウンロード[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)します。</span><span class="sxs-lookup"><span data-stu-id="80c98-106">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span> 
  
 <span data-ttu-id="80c98-107">このツールは、テスト環境でのみで使用する必要があり、運用環境では使用しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="80c98-107">This tool should be used in a test environment only, and should not be used in a production environment.</span></span> <span data-ttu-id="80c98-108">このツールが提供される"としてでは"はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="80c98-108">This tool is provided "as-is" and is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80c98-109">MSMQ アダプターでは、BizTalk Server の負荷生成ツールを使用できますが、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80c98-109">You can use BizTalk Server Load Generation Tool with the MSMQ adapter, but you must do some additional steps.</span></span> <span data-ttu-id="80c98-110">手順については、次を参照してください。 [MSMQ での LoadGen 2007 を使用して](../core/using-loadgen-2007-with-msmq.md)します。</span><span class="sxs-lookup"><span data-stu-id="80c98-110">For instructions, see [Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80c98-111">64 ビット コンピューターで LoadGen をサポートしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80c98-111">LoadGen may not be supported on 64-bit computers.</span></span> <span data-ttu-id="80c98-112">64 ビット サーバー上の負荷を生成するのに 32 ビット コンピューターでリモートで実行されている LoadGen を使用できます。</span><span class="sxs-lookup"><span data-stu-id="80c98-112">You can use LoadGen remotely running on a 32-bit computer to generate load against a 64-bit server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c98-113">参照</span><span class="sxs-lookup"><span data-stu-id="80c98-113">See Also</span></span>  
 [<span data-ttu-id="80c98-114">オーバードライブ ロード テスト</span><span class="sxs-lookup"><span data-stu-id="80c98-114">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)