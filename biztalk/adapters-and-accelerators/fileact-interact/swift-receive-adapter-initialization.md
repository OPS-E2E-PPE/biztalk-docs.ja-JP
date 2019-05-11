---
title: SWIFT 受信アダプターの初期化 |Microsoft Docs
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
ms.openlocfilehash: 80d49a4ccc7c3595aaeca4a8068f8d76023e1763
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364467"
---
# <a name="swift-receive-adapter-initialization"></a><span data-ttu-id="321cd-102">SWIFT 受信アダプターの初期化</span><span class="sxs-lookup"><span data-stu-id="321cd-102">SWIFT Receive Adapter Initialization</span></span>
<span data-ttu-id="321cd-103">SWIFT サーバー アプリケーションの初期化プロセスが SWIFT クライアント アプリケーションと同様にします。</span><span class="sxs-lookup"><span data-stu-id="321cd-103">The initialization process for the SWIFT server application is similar to that for the SWIFT client application.</span></span> <span data-ttu-id="321cd-104">初期化の引数に渡されるコマンド ライン パラメーターとして、受信側実行可能ファイルです。</span><span class="sxs-lookup"><span data-stu-id="321cd-104">The initialization arguments are passed as command line parameters to the receiver executable.</span></span> <span data-ttu-id="321cd-105">設計時に、受信場所で構成されている、アプリケーション名は、コマンドライン引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="321cd-105">The application name, configured in the receive location during design time, is passed as a command line argument.</span></span> <span data-ttu-id="321cd-106">このアプリケーション名は、受信場所、構成されたプロパティを取得する URI の構築に使用されます。</span><span class="sxs-lookup"><span data-stu-id="321cd-106">This application name is used to construct the receive location URI to retrieve the configured properties.</span></span>  
  
 <span data-ttu-id="321cd-107">コマンドライン引数を使用する方法の詳細については、Microsoft では"構成の受信アダプター Environment 方法"トピックを参照してください。[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]インストールおよび構成ガイドです。</span><span class="sxs-lookup"><span data-stu-id="321cd-107">For information about using the command line argument, see the "How to Configure the Receive Adapter Environment" topic in Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] Installation and Configuration Guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="321cd-108">参照</span><span class="sxs-lookup"><span data-stu-id="321cd-108">See Also</span></span>  
 <span data-ttu-id="321cd-109">[SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="321cd-109">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="321cd-110">[SWIFT 受信アダプターの URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="321cd-110">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="321cd-111">[SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span><span class="sxs-lookup"><span data-stu-id="321cd-111">[SWIFT Receive Adapter Security Context](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span></span>  
 <span data-ttu-id="321cd-112">[SWIFT 受信アダプターの同期および遅延モード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span><span class="sxs-lookup"><span data-stu-id="321cd-112">[SWIFT Receive Adapter Synchronous and Deferred Modes](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span></span>  
 [<span data-ttu-id="321cd-113">SWIFT 受信アダプターのストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="321cd-113">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)