---
title: "SWIFT 受信アダプター セキュリティ コンテキスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3db2b534-db9d-4075-aaad-0974b024dc71
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b381ba9b4e0e1d53eca8e6cdd01b9770eb82372f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-receive-adapter-security-context"></a><span data-ttu-id="680ae-102">SWIFT 受信アダプター セキュリティ コンテキスト</span><span class="sxs-lookup"><span data-stu-id="680ae-102">SWIFT Receive Adapter Security Context</span></span>
<span data-ttu-id="680ae-103">送信アダプターとは異なり、受信アダプターは、SWIFTNet リンク (SNL/RA) コマンド プロンプトから起動 (SWIFTNet 開始)。</span><span class="sxs-lookup"><span data-stu-id="680ae-103">The Receiver adapter, unlike send adapter, is started from the SWIFTNet Link (SNL/RA) command prompt (SWIFTNet start).</span></span> <span data-ttu-id="680ae-104">SNL/RA 構成ファイル (paramconfig) では、実行可能ファイルの受信アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="680ae-104">The receive adapter executable is configured in the SNL/RA configuration file (paramconfig).</span></span> <span data-ttu-id="680ae-105">スタートアップ時にアダプターでは、コマンド ライン パラメーターに基づく SNL ライブラリを初期化します。</span><span class="sxs-lookup"><span data-stu-id="680ae-105">The adapter on startup initializes the SNL library based on the command line parameter.</span></span> <span data-ttu-id="680ae-106">後で使用するには、構成値がキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="680ae-106">The configuration values are cached for later use.</span></span>  
  
 <span data-ttu-id="680ae-107">次の図は、受信アダプター セキュリティ コンテキストの構成を示します。</span><span class="sxs-lookup"><span data-stu-id="680ae-107">The following figure shows the configuration of the receive adapter security context.</span></span>  
  
 <span data-ttu-id="680ae-108">![SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")</span><span class="sxs-lookup"><span data-stu-id="680ae-108">![SWIFT receive adapter security context](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="680ae-109">参照</span><span class="sxs-lookup"><span data-stu-id="680ae-109">See Also</span></span>  
 <span data-ttu-id="680ae-110">[SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="680ae-110">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="680ae-111">[SWIFT 受信アダプター URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="680ae-111">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="680ae-112">[SWIFT 受信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="680ae-112">[SWIFT Receive Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span></span>  
 <span data-ttu-id="680ae-113">[SWIFT 受信アダプターの同期および遅延モード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span><span class="sxs-lookup"><span data-stu-id="680ae-113">[SWIFT Receive Adapter Synchronous and Deferred Modes](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span></span>  
 [<span data-ttu-id="680ae-114">SWIFT 受信アダプター ストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="680ae-114">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)