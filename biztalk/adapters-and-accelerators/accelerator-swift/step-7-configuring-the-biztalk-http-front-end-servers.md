---
title: 手順 7:BizTalk HTTP フロント エンド サーバーの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, HTTP servers
- HTTP server, configuring
ms.assetid: 6b7e0b48-bb20-42f4-84a5-092ff3a02741
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 038f20096247e952b10d95c6823cb0749d3b1a71
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377021"
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a><span data-ttu-id="d0484-102">手順 7:BizTalk HTTP フロント エンド サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="d0484-102">Step 7: Configuring the BizTalk HTTP Front-End Servers</span></span>
<span data-ttu-id="d0484-103">このセクションで Web サーバーの構成のガイドラインを提供します、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]展開します。</span><span class="sxs-lookup"><span data-stu-id="d0484-103">This section provides guidelines on configuring the Web servers in your [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0484-104">1 台のコンピューターの展開では、このコンピューターは、もう 1 つは、メッセージング処理と同じコンピューターは。</span><span class="sxs-lookup"><span data-stu-id="d0484-104">In the single-computer deployment, this computer is the same computer as the one that does the messaging and processing.</span></span>  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a><span data-ttu-id="d0484-105">BizTalk HTTP フロント エンド サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="d0484-105">To configure the BizTalk HTTP front-end servers</span></span>  
  
1. <span data-ttu-id="d0484-106">インターネット インフォメーション サービス (IIS) のインストールと ASP.NET です。</span><span class="sxs-lookup"><span data-stu-id="d0484-106">Install Internet Information Services (IIS) and ASP.NET.</span></span>  
  
2. <span data-ttu-id="d0484-107">IIS マネージャーを開き、選択**Web サービス拡張**します。</span><span class="sxs-lookup"><span data-stu-id="d0484-107">Open IIS Manager and select **Web Service Extensions**.</span></span> <span data-ttu-id="d0484-108">ASP.NET 1.1 および ASP.NET v2.0 に設定されていることを確認**許可**します。</span><span class="sxs-lookup"><span data-stu-id="d0484-108">Ensure that ASP.NET v1.1 and ASP.NET v2.0 are set to **Allowed**.</span></span>  
  
3. <span data-ttu-id="d0484-109">いることを確認、**メッセージ キュー**サービス (MSMQ) と**ルーティング サポート**から追加/削除がインストールされている[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバー/メッセージ キューの下のコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d0484-109">Ensure that the **Message Queuing** service (MSMQ) with **Routing Support** is installed from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under Application Server/Message Queuing.</span></span>  
  
4. <span data-ttu-id="d0484-110">追加/削除 でネットワーク DTC アクセスが有効であることを確認[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバーのカテゴリの下にあるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d0484-110">Ensure that Network DTC access is enabled in the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="d0484-111">ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。</span><span class="sxs-lookup"><span data-stu-id="d0484-111">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span>  
  
5. <span data-ttu-id="d0484-112">」の説明に従って、展開に Secure Sockets Layer (SSL) プロトコルを実装[サポート Secure Sockets Layer (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0484-112">Implement the Secure Sockets Layer (SSL) protocol in your deployment, as described in [Supporting Secure Sockets Layer (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md).</span></span>  
  
6. <span data-ttu-id="d0484-113">インストールし、Windows SharePoint Services 3.0 SP1 を構成します。</span><span class="sxs-lookup"><span data-stu-id="d0484-113">Install and configure Windows SharePoint Services 3.0 SP1.</span></span>  
  
7. <span data-ttu-id="d0484-114">インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]」の説明に従って[BizTalk Accelerator for SWIFT を HTTP フロント エンド サーバー上に構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0484-114">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in [Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md).</span></span>  
  
   <span data-ttu-id="d0484-115">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d0484-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="d0484-116">Secure Sockets Layer (SSL) のサポート</span><span class="sxs-lookup"><span data-stu-id="d0484-116">Supporting Secure Sockets Layer (SSL)</span></span>](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [<span data-ttu-id="d0484-117">インストールして、BizTalk HTTP フロント エンド サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d0484-117">Installing and Configuring BizTalk HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [<span data-ttu-id="d0484-118">HTTP フロントエンド サーバーに BizTalk Accelerator for SWIFT をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="d0484-118">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)