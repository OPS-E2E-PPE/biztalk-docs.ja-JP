---
title: FTP アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FTP adapters
ms.assetid: 878dc0b0-d1d8-405a-a697-654dd18ba08e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4663fa2615803b50bd8d9172c599665a787ecc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008459"
---
# <a name="ftp-adapter"></a><span data-ttu-id="2b4e6-102">FTP アダプタ</span><span class="sxs-lookup"><span data-stu-id="2b4e6-102">FTP Adapter</span></span>
<span data-ttu-id="2b4e6-103">FTP アダプターを使用すると、FTP サーバーと Microsoft BizTalk Server の間でデータを交換できます。これにより、基幹業務アプリケーションを搭載したさまざまなプラットフォームに保存されている重要なデータを統合できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-103">The FTP adapter exchanges data between an FTP server and Microsoft BizTalk Server, and allows for the integration of vital data stored on a variety of platforms with line-of-business applications.</span></span> <span data-ttu-id="2b4e6-104">アダプターは、SOCKS4 経由での FTP サーバーまたは SOCKS5 プロキシ サーバーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-104">The adapter can connect to the FTP server via SOCKS4 or SOCKS5 proxy server.</span></span>  
  
 <span data-ttu-id="2b4e6-105">FTP アダプターでは、FTP サーバーから BizTalk Server に多数のファイルを送信できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-105">The FTP adapter can transfer a large number of files from an FTP server to BizTalk Server.</span></span> <span data-ttu-id="2b4e6-106">また、ファイルをオーケストレーションの一部として送信できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-106">It can also transfer files as part of an orchestration.</span></span>  
  
 <span data-ttu-id="2b4e6-107">FTP アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-107">The FTP adapter consists of two adapters — a receive adapter and a send adapter.</span></span>  

<span data-ttu-id="2b4e6-108">このセクションでは、FTP 受信アダプタと FTP 送信アダプタ、およびセキュリティとベスト プラクティス情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-108">This section describes the FTP receive and send adapters, as well as security and best-practice information.</span></span>  
  
 ## <a name="receive-adapter"></a><span data-ttu-id="2b4e6-109">受信アダプター</span><span class="sxs-lookup"><span data-stu-id="2b4e6-109">Receive adapter</span></span>  
  
 <span data-ttu-id="2b4e6-110">FTP 受信アダプターを使用すると、FTP サーバーから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にデータを移動できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-110">The FTP receive adapter enables you to move data from an FTP server to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="2b4e6-111">主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-111">Key features include:</span></span>  
  
- <span data-ttu-id="2b4e6-112">要求時に FTP サーバーからファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-112">Pulling files from the FTP server on demand</span></span>  
  
- <span data-ttu-id="2b4e6-113">構成可能なスケジュールに基づいてポーリングを実行しています。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-113">Running polls based on a configurable schedule</span></span>  
  
- <span data-ttu-id="2b4e6-114">FTP サーバーにポーリングし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にデータを直接送信します。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-114">Polling the FTP server and sending data directly to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="2b4e6-115">FTP サーバーを IP アドレス、ポート、パスワード、およびホスト名で指定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-115">Specifying the FTP server as an IP address, port, password, and host name</span></span>  
  
- <span data-ttu-id="2b4e6-116">ファイルの配信を保証</span><span class="sxs-lookup"><span data-stu-id="2b4e6-116">Guaranteed file delivery</span></span>  
  
   <span data-ttu-id="2b4e6-117">また、FTP 受信アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールおよび BizTalk エクスプローラーと連動し、各受信機能を構成および管理します。この機能は、次の構成項目で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-117">The FTP receive adapter also works with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and BizTalk Explorer to configure and administer each receive function, which is composed of the following configuration items:</span></span>  
  
- <span data-ttu-id="2b4e6-118">FTP コマンドを実行するためのポーリング間隔 (例、60 分)</span><span class="sxs-lookup"><span data-stu-id="2b4e6-118">Poll interval to run an FTP command (for example, 60 minutes)</span></span>  
  
- <span data-ttu-id="2b4e6-119">ドキュメントを特定の BizTalk 送信ポートまたは受信場所にルーティングする際に使用する情報</span><span class="sxs-lookup"><span data-stu-id="2b4e6-119">Information with which to route the document to a specific BizTalk send port or receive location</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b4e6-120">FTP 受信アダプターは、パーティション分割されたデータ セットからのファイルの受信をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-120">The FTP receive adapter does not support receiving files from a partitioned data set.</span></span>  
  
## <a name="send-adapter"></a><span data-ttu-id="2b4e6-121">送信アダプター</span><span class="sxs-lookup"><span data-stu-id="2b4e6-121">Send adapter</span></span>  
  
 <span data-ttu-id="2b4e6-122">FTP 送信アダプターを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から FTP サーバーにデータを移動できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-122">The FTP send adapter enables you to move data from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to an FTP server.</span></span> <span data-ttu-id="2b4e6-123">主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-123">Key features include:</span></span>  
  
-   <span data-ttu-id="2b4e6-124">要求時に送信を実行する機能</span><span class="sxs-lookup"><span data-stu-id="2b4e6-124">Ability to run sends on demand</span></span>  
  
-   <span data-ttu-id="2b4e6-125">配信の保証</span><span class="sxs-lookup"><span data-stu-id="2b4e6-125">Guaranteed delivery</span></span>  
  
## <a name="supported-platforms"></a><span data-ttu-id="2b4e6-126">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="2b4e6-126">Supported platforms</span></span>  
<span data-ttu-id="2b4e6-127">FTP サーバーに、次のプラットフォームのいずれかに格納されている情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-127">Access information stored in an FTP server on any of the following platforms:</span></span>  

- [!INCLUDE[btsWinSvrNoVersion_md](../includes/btswinsvrnoversion-md.md)]<span data-ttu-id="2b4e6-128"> 2016</span><span class="sxs-lookup"><span data-stu-id="2b4e6-128"> 2016</span></span>

- [!INCLUDE[btsWinSrv2k12_md](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="2b4e6-129"> R2</span><span class="sxs-lookup"><span data-stu-id="2b4e6-129"> R2</span></span>
  
- [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]  
  
- [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]  
  
- [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]<span data-ttu-id="2b4e6-130"> 2008</span><span class="sxs-lookup"><span data-stu-id="2b4e6-130"> 2008</span></span>  
  
- [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]  
  
- [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]<span data-ttu-id="2b4e6-131"> 2000 Service Pack 3 (SP3) 以降</span><span class="sxs-lookup"><span data-stu-id="2b4e6-131"> 2000 Service Pack 3 (SP3) and later</span></span>  
  
- <span data-ttu-id="2b4e6-132">Sun Solaris 9.0</span><span class="sxs-lookup"><span data-stu-id="2b4e6-132">Sun Solaris 9.0</span></span>  
  
- <span data-ttu-id="2b4e6-133">HP-UX</span><span class="sxs-lookup"><span data-stu-id="2b4e6-133">HP-UX</span></span>  
  
- <span data-ttu-id="2b4e6-134">Linux (Redhat 7.x)</span><span class="sxs-lookup"><span data-stu-id="2b4e6-134">LINUX (Redhat 7.x)</span></span>  
  
- <span data-ttu-id="2b4e6-135">IBM z/OS v1.9 (MVS)</span><span class="sxs-lookup"><span data-stu-id="2b4e6-135">IBM z/OS v1.9 (MVS)</span></span>  
  
- <span data-ttu-id="2b4e6-136">MVS を実行している IBM O/S 390</span><span class="sxs-lookup"><span data-stu-id="2b4e6-136">IBM O/S 390 running MVS</span></span>  
  
- <span data-ttu-id="2b4e6-137">AS/400 OS/400 V5R1</span><span class="sxs-lookup"><span data-stu-id="2b4e6-137">AS/400 OS/400 V5R1</span></span>  
  
- <span data-ttu-id="2b4e6-138">i5/OS V5R4 (AS400)</span><span class="sxs-lookup"><span data-stu-id="2b4e6-138">i5/OS V5R4 (AS400)</span></span>  
  
- <span data-ttu-id="2b4e6-139">i5/OS V6R1 (AS400)</span><span class="sxs-lookup"><span data-stu-id="2b4e6-139">i5/OS V6R1 (AS400)</span></span>  
  
- <span data-ttu-id="2b4e6-140">GXS ICS</span><span class="sxs-lookup"><span data-stu-id="2b4e6-140">GXS ICS</span></span>  
  
- <span data-ttu-id="2b4e6-141">AIX</span><span class="sxs-lookup"><span data-stu-id="2b4e6-141">AIX</span></span>  
  
  <span data-ttu-id="2b4e6-142">サービス パックが特に記載されていない限り、すべてのサービス パックがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2b4e6-142">All services packs are supported, unless the service pack is specifically listed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b4e6-143">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2b4e6-143">In This Section</span></span>  
  
[<span data-ttu-id="2b4e6-144">FTP アダプターのベスト プラクティスと推奨事項</span><span class="sxs-lookup"><span data-stu-id="2b4e6-144">Best practices and recommendations for the FTP Adapter</span></span>](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)  

[<span data-ttu-id="2b4e6-145">FTP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="2b4e6-145">Configuring the FTP adapter</span></span>](../core/configuring-the-ftp-adapter.md)  

[<span data-ttu-id="2b4e6-146">FTP アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="2b4e6-146">FTP Adapter Property Schema and Properties</span></span>](../core/ftp-adapter-property-schema-and-properties.md)