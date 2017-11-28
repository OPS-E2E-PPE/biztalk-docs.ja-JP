---
title: "Microsoft BizTalk LoadGen 2007 ツールの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LoadGen tool, how to
- LoadGen tool, test environments
ms.assetid: d1973a26-1c98-4261-bd9a-6357cdb19ccf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b93018f093bbdffed64c44060f445a30d37344c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-microsoft-biztalk-loadgen-2007-tool"></a><span data-ttu-id="4d671-102">Microsoft BizTalk LoadGen 2007 ツールの使用</span><span class="sxs-lookup"><span data-stu-id="4d671-102">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>
<span data-ttu-id="4d671-103">Microsoft BizTalk LoadGen 2007 ツールは、開発者や IT プロフェッショナルが BizTalk Server 上で負荷をシミュレートできるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="4d671-103">The Microsoft BizTalk LoadGen 2007 Tool is intended for developers and IT professionals to simulate load on a BizTalk Server.</span></span> <span data-ttu-id="4d671-104">このツールを使用することにより、負荷をシミュレートし、BizTalk の展開に対するパフォーマンスとストレスを測定できます。</span><span class="sxs-lookup"><span data-stu-id="4d671-104">Using this tool, you can simulate load to instrument performance and stress against a BizTalk deployment.</span></span> <span data-ttu-id="4d671-105">さらに、開発者はこのツールを拡張して、カスタム トランスポートの負荷をシミュレートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4d671-105">In addition, this tool may also be extended by developers to simulate load for custom transports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d671-106">LoadGen 2007 ツールはダウンロード[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841)です。</span><span class="sxs-lookup"><span data-stu-id="4d671-106">The LoadGen 2007 tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span></span> <span data-ttu-id="4d671-107">このツールの以前のバージョン、BizTalk Server 2004 負荷生成ツールは、ダウンロード[http://go.microsoft.com/fwlink/?LinkId=108999](http://go.microsoft.com/fwlink/?LinkId=108999)です。</span><span class="sxs-lookup"><span data-stu-id="4d671-107">The previous version of this tool, the BizTalk Server 2004 Load Generation Tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=108999](http://go.microsoft.com/fwlink/?LinkId=108999).</span></span>  
  
 <span data-ttu-id="4d671-108">このツールはテスト環境でのみ使用してください。実稼働環境では使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="4d671-108">This tool should be used in a test environment only, and should not be used in a production environment.</span></span> <span data-ttu-id="4d671-109">このツールは "現状のまま" 提供されるものであり、サポート対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="4d671-109">This tool is provided "as-is" and is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d671-110">BizTalk Server 2004 負荷生成ツールは MSMQ アダプターと組み合わせて使用できますが、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d671-110">You can use BizTalk Server 2004 Load Generation Tool with the MSMQ adapter, but you must do some additional steps.</span></span> <span data-ttu-id="4d671-111">手順については、次を参照してください。 [MSMQ での LoadGen 2007 を使用して](../core/using-loadgen-2007-with-msmq.md)です。</span><span class="sxs-lookup"><span data-stu-id="4d671-111">For instructions, see [Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d671-112">LoadGen は、64 ビット コンピューターに対応していません。</span><span class="sxs-lookup"><span data-stu-id="4d671-112">LoadGen is not supported on 64-bit computers.</span></span> <span data-ttu-id="4d671-113">リモートの 32 ビット コンピューターで LoadGen を実行することにより、64 ビット サーバーに対応した負荷を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="4d671-113">You can use LoadGen remotely running on a 32-bit computer to generate load against a 64-bit server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d671-114">参照</span><span class="sxs-lookup"><span data-stu-id="4d671-114">See Also</span></span>  
 [<span data-ttu-id="4d671-115">オーバー ドライブ ロード テスト</span><span class="sxs-lookup"><span data-stu-id="4d671-115">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)