---
title: Microsoft BizTalk LoadGen 2007 ツールの使用 |Microsoft ドキュメント
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
ms.openlocfilehash: 2dcf55b2371387ffd52139724d74a118d52ce999
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007203"
---
# <a name="using-the-microsoft-biztalk-loadgen-2007-tool"></a><span data-ttu-id="99e63-102">Microsoft BizTalk LoadGen 2007 ツールの使用</span><span class="sxs-lookup"><span data-stu-id="99e63-102">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>
<span data-ttu-id="99e63-103">Microsoft BizTalk LoadGen 2007 ツールは、開発者や IT プロフェッショナルが BizTalk Server 上で負荷をシミュレートできるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="99e63-103">The Microsoft BizTalk LoadGen 2007 Tool is intended for developers and IT professionals to simulate load on a BizTalk Server.</span></span> <span data-ttu-id="99e63-104">このツールを使用することにより、負荷をシミュレートし、BizTalk の展開に対するパフォーマンスとストレスを測定できます。</span><span class="sxs-lookup"><span data-stu-id="99e63-104">Using this tool, you can simulate load to instrument performance and stress against a BizTalk deployment.</span></span> <span data-ttu-id="99e63-105">さらに、開発者はこのツールを拡張して、カスタム トランスポートの負荷をシミュレートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="99e63-105">In addition, this tool may also be extended by developers to simulate load for custom transports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99e63-106">ダウンロード[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)です。</span><span class="sxs-lookup"><span data-stu-id="99e63-106">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span> 
  
 <span data-ttu-id="99e63-107">このツールはテスト環境でのみ使用してください。実稼働環境では使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="99e63-107">This tool should be used in a test environment only, and should not be used in a production environment.</span></span> <span data-ttu-id="99e63-108">このツールは "現状のまま" 提供されるものであり、サポート対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="99e63-108">This tool is provided "as-is" and is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99e63-109">MSMQ アダプターと BizTalk Server 負荷生成ツールを使用できますが、追加の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e63-109">You can use BizTalk Server Load Generation Tool with the MSMQ adapter, but you must do some additional steps.</span></span> <span data-ttu-id="99e63-110">手順については、次を参照してください。 [MSMQ での LoadGen 2007 を使用して](../core/using-loadgen-2007-with-msmq.md)です。</span><span class="sxs-lookup"><span data-stu-id="99e63-110">For instructions, see [Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99e63-111">LoadGen は、64 ビット コンピューターでサポートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99e63-111">LoadGen may not be supported on 64-bit computers.</span></span> <span data-ttu-id="99e63-112">リモートの 32 ビット コンピューターで LoadGen を実行することにより、64 ビット サーバーに対応した負荷を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="99e63-112">You can use LoadGen remotely running on a 32-bit computer to generate load against a 64-bit server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e63-113">参照</span><span class="sxs-lookup"><span data-stu-id="99e63-113">See Also</span></span>  
 [<span data-ttu-id="99e63-114">オーバードライブ ロード テスト</span><span class="sxs-lookup"><span data-stu-id="99e63-114">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)