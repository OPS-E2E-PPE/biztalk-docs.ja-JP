---
title: SWIFT 受信アダプターの初期化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce53aff3-6189-4033-b318-d703037518e0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35ed17325252f1954f20cb25f963a5bd7a57d5e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224202"
---
# <a name="swift-receive-adapter-initialization"></a><span data-ttu-id="01b18-102">SWIFT 受信アダプターの初期化</span><span class="sxs-lookup"><span data-stu-id="01b18-102">SWIFT Receive Adapter Initialization</span></span>
<span data-ttu-id="01b18-103">迅速な対応サーバー アプリケーションの初期化プロセスでは、SWIFT クライアント アプリケーションのと似ています。</span><span class="sxs-lookup"><span data-stu-id="01b18-103">The initialization process for the SWIFT server application is similar to that for the SWIFT client application.</span></span> <span data-ttu-id="01b18-104">初期化の引数に渡されるコマンド ライン パラメーターとして、受信側実行可能ファイルです。</span><span class="sxs-lookup"><span data-stu-id="01b18-104">The initialization arguments are passed as command line parameters to the receiver executable.</span></span> <span data-ttu-id="01b18-105">デザイン時に、受信場所で構成されている、アプリケーション名は、コマンドラインの引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="01b18-105">The application name, configured in the receive location during design time, is passed as a command line argument.</span></span> <span data-ttu-id="01b18-106">このアプリケーションの名前は、受信場所の構成済みのプロパティを取得する URI を構築するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="01b18-106">This application name is used to construct the receive location URI to retrieve the configured properties.</span></span>  
  
 <span data-ttu-id="01b18-107">コマンドライン引数を使用する方法の詳細については、Microsoft では「方法を構成、受信アダプタの環境」トピックを参照して[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]インストールおよび構成ガイドします。</span><span class="sxs-lookup"><span data-stu-id="01b18-107">For information about using the command line argument, see the "How to Configure the Receive Adapter Environment" topic in Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] Installation and Configuration Guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b18-108">参照</span><span class="sxs-lookup"><span data-stu-id="01b18-108">See Also</span></span>  
 <span data-ttu-id="01b18-109">[SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="01b18-109">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="01b18-110">[SWIFT 受信アダプター URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="01b18-110">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="01b18-111">[SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span><span class="sxs-lookup"><span data-stu-id="01b18-111">[SWIFT Receive Adapter Security Context](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span></span>  
 <span data-ttu-id="01b18-112">[SWIFT 受信アダプターの同期および遅延モード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span><span class="sxs-lookup"><span data-stu-id="01b18-112">[SWIFT Receive Adapter Synchronous and Deferred Modes](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span></span>  
 [<span data-ttu-id="01b18-113">SWIFT 受信アダプター ストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="01b18-113">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)