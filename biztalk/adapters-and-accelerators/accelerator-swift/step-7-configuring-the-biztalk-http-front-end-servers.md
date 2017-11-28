---
title: "手順 7: BizTalk HTTP フロント エンド サーバーの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, HTTP servers
- HTTP server, configuring
ms.assetid: 6b7e0b48-bb20-42f4-84a5-092ff3a02741
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5840099816149265711744373e08d3a9a9d91cd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a><span data-ttu-id="0761d-102">手順 7: BizTalk HTTP フロント エンド サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="0761d-102">Step 7: Configuring the BizTalk HTTP Front-End Servers</span></span>
<span data-ttu-id="0761d-103">このセクションは、Web サーバーの構成のガイドラインを示します、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]展開します。</span><span class="sxs-lookup"><span data-stu-id="0761d-103">This section provides guidelines on configuring the Web servers in your [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0761d-104">1 台のコンピューター展開では、このコンピューターは、1 つのメッセージングを行うと処理と同じコンピューターは。</span><span class="sxs-lookup"><span data-stu-id="0761d-104">In the single-computer deployment, this computer is the same computer as the one that does the messaging and processing.</span></span>  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a><span data-ttu-id="0761d-105">BizTalk HTTP フロント エンド サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="0761d-105">To configure the BizTalk HTTP front-end servers</span></span>  
  
1.  <span data-ttu-id="0761d-106">インターネット インフォメーション サービス (IIS) のインストールと ASP.NET です。</span><span class="sxs-lookup"><span data-stu-id="0761d-106">Install Internet Information Services (IIS) and ASP.NET.</span></span>  
  
2.  <span data-ttu-id="0761d-107">IIS マネージャーを開き、選択**Web サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="0761d-107">Open IIS Manager and select **Web Service Extensions**.</span></span> <span data-ttu-id="0761d-108">ASP.NET v1.1 と、ASP.NET 2.0 に設定されるように**許可**です。</span><span class="sxs-lookup"><span data-stu-id="0761d-108">Ensure that ASP.NET v1.1 and ASP.NET v2.0 are set to **Allowed**.</span></span>  
  
3.  <span data-ttu-id="0761d-109">いることを確認、**メッセージ キュー**サービス (MSMQ) と**ルーティング サポート**を追加/削除 からインストール[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバー/メッセージ キューの下のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="0761d-109">Ensure that the **Message Queuing** service (MSMQ) with **Routing Support** is installed from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under Application Server/Message Queuing.</span></span>  
  
4.  <span data-ttu-id="0761d-110">追加/削除 でネットワーク DTC アクセスが有効になっていることを確認[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバー カテゴリの下にあるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="0761d-110">Ensure that Network DTC access is enabled in the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="0761d-111">ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。</span><span class="sxs-lookup"><span data-stu-id="0761d-111">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span>  
  
5.  <span data-ttu-id="0761d-112">」の説明に従って、展開に Secure Sockets Layer (SSL) プロトコルを実装[サポート (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)です。</span><span class="sxs-lookup"><span data-stu-id="0761d-112">Implement the Secure Sockets Layer (SSL) protocol in your deployment, as described in [Supporting Secure Sockets Layer (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md).</span></span>  
  
6.  <span data-ttu-id="0761d-113">インストールし、Windows SharePoint Services 3.0 SP1 を構成します。</span><span class="sxs-lookup"><span data-stu-id="0761d-113">Install and configure Windows SharePoint Services 3.0 SP1.</span></span>  
  
7.  <span data-ttu-id="0761d-114">インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]」の説明に従って[BizTalk Accelerator for SWIFT HTTP フロント エンド サーバー上に構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)です。</span><span class="sxs-lookup"><span data-stu-id="0761d-114">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in [Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md).</span></span>  
  
 <span data-ttu-id="0761d-115">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0761d-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="0761d-116">Secure Sockets Layer (SSL) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="0761d-116">Supporting Secure Sockets Layer (SSL)</span></span>](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [<span data-ttu-id="0761d-117">インストールして、BizTalk HTTP フロント エンド サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="0761d-117">Installing and Configuring BizTalk HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [<span data-ttu-id="0761d-118">インストールと BizTalk Accelerator を HTTP フロント エンド サーバーに SWIFT の構成</span><span class="sxs-lookup"><span data-stu-id="0761d-118">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)