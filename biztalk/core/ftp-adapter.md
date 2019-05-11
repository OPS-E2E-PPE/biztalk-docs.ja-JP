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
ms.openlocfilehash: 96890b0778e5e7c0684e1e5e326f245460487dd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345295"
---
# <a name="ftp-adapter"></a><span data-ttu-id="29a61-102">FTP アダプター</span><span class="sxs-lookup"><span data-stu-id="29a61-102">FTP Adapter</span></span>
<span data-ttu-id="29a61-103">FTP アダプターは、FTP サーバーと Microsoft BizTalk Server の間でデータを交換しのさまざまな基幹業務アプリケーションとプラットフォームに格納されている重要なデータを統合できます。</span><span class="sxs-lookup"><span data-stu-id="29a61-103">The FTP adapter exchanges data between an FTP server and Microsoft BizTalk Server, and allows for the integration of vital data stored on a variety of platforms with line-of-business applications.</span></span> <span data-ttu-id="29a61-104">アダプターは、SOCKS4 経由での FTP サーバーまたは SOCKS5 プロキシ サーバーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="29a61-104">The adapter can connect to the FTP server via SOCKS4 or SOCKS5 proxy server.</span></span>  
  
 <span data-ttu-id="29a61-105">FTP アダプターは、FTP サーバーから BizTalk Server の多数のファイルを転送できます。</span><span class="sxs-lookup"><span data-stu-id="29a61-105">The FTP adapter can transfer a large number of files from an FTP server to BizTalk Server.</span></span> <span data-ttu-id="29a61-106">ファイルは、オーケストレーションの一部としてそのも転送できます。</span><span class="sxs-lookup"><span data-stu-id="29a61-106">It can also transfer files as part of an orchestration.</span></span>  
  
 <span data-ttu-id="29a61-107">FTP アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。</span><span class="sxs-lookup"><span data-stu-id="29a61-107">The FTP adapter consists of two adapters — a receive adapter and a send adapter.</span></span>  

<span data-ttu-id="29a61-108">このセクションの説明、FTP 受信し、送信アダプター、およびセキュリティとベスト プラクティスの情報。</span><span class="sxs-lookup"><span data-stu-id="29a61-108">This section describes the FTP receive and send adapters, as well as security and best-practice information.</span></span>  
  
 ## <a name="receive-adapter"></a><span data-ttu-id="29a61-109">受信アダプター</span><span class="sxs-lookup"><span data-stu-id="29a61-109">Receive adapter</span></span>  
  
 <span data-ttu-id="29a61-110">FTP 受信アダプターを使用する FTP サーバーからデータを移動する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="29a61-110">The FTP receive adapter enables you to move data from an FTP server to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="29a61-111">主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29a61-111">Key features include:</span></span>  
  
- <span data-ttu-id="29a61-112">必要に応じて、FTP サーバーからファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="29a61-112">Pulling files from the FTP server on demand</span></span>  
  
- <span data-ttu-id="29a61-113">構成可能なスケジュールに基づいてポーリングを実行しています。</span><span class="sxs-lookup"><span data-stu-id="29a61-113">Running polls based on a configurable schedule</span></span>  
  
- <span data-ttu-id="29a61-114">FTP サーバーにポーリングし、データに直接送信します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29a61-114">Polling the FTP server and sending data directly to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="29a61-115">IP アドレス、ポート、パスワード、およびホスト名として FTP サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="29a61-115">Specifying the FTP server as an IP address, port, password, and host name</span></span>  
  
- <span data-ttu-id="29a61-116">ファイルの配信を保証</span><span class="sxs-lookup"><span data-stu-id="29a61-116">Guaranteed file delivery</span></span>  
  
   <span data-ttu-id="29a61-117">また、FTP 受信アダプターとの連携、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールと BizTalk エクスプローラを構成および管理する各受信関数で、次の構成項目で構成されます。</span><span class="sxs-lookup"><span data-stu-id="29a61-117">The FTP receive adapter also works with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and BizTalk Explorer to configure and administer each receive function, which is composed of the following configuration items:</span></span>  
  
- <span data-ttu-id="29a61-118">FTP コマンド (たとえば、60 分) を実行するポーリング間隔</span><span class="sxs-lookup"><span data-stu-id="29a61-118">Poll interval to run an FTP command (for example, 60 minutes)</span></span>  
  
- <span data-ttu-id="29a61-119">特定の BizTalk へのドキュメントをルーティングする際に使用して情報の送信ポートまたは受信場所</span><span class="sxs-lookup"><span data-stu-id="29a61-119">Information with which to route the document to a specific BizTalk send port or receive location</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29a61-120">FTP 受信アダプタは、パーティション分割されたデータ セットからのファイルの受信をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="29a61-120">The FTP receive adapter does not support receiving files from a partitioned data set.</span></span>  
  
## <a name="send-adapter"></a><span data-ttu-id="29a61-121">送信アダプター</span><span class="sxs-lookup"><span data-stu-id="29a61-121">Send adapter</span></span>  
  
 <span data-ttu-id="29a61-122">FTP 送信アダプタからデータを移動することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]FTP サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="29a61-122">The FTP send adapter enables you to move data from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to an FTP server.</span></span> <span data-ttu-id="29a61-123">主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29a61-123">Key features include:</span></span>  
  
-   <span data-ttu-id="29a61-124">オンデマンドで送信を実行するには</span><span class="sxs-lookup"><span data-stu-id="29a61-124">Ability to run sends on demand</span></span>  
  
-   <span data-ttu-id="29a61-125">保証された配信</span><span class="sxs-lookup"><span data-stu-id="29a61-125">Guaranteed delivery</span></span>  
  
## <a name="supported-platforms"></a><span data-ttu-id="29a61-126">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="29a61-126">Supported platforms</span></span>  
<span data-ttu-id="29a61-127">FTP サーバーに、次のプラットフォームのいずれかに格納されている情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="29a61-127">Access information stored in an FTP server on any of the following platforms:</span></span>  

- [!INCLUDE[btsWinSvrNoVersion_md](../includes/btswinsvrnoversion-md.md)] <span data-ttu-id="29a61-128">2016</span><span class="sxs-lookup"><span data-stu-id="29a61-128">2016</span></span>

- [!INCLUDE[btsWinSrv2k12_md](../includes/btswinsrv2k12-md.md)] <span data-ttu-id="29a61-129">R2</span><span class="sxs-lookup"><span data-stu-id="29a61-129">R2</span></span>
  
- [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]  
  
- [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]  
  
- [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] <span data-ttu-id="29a61-130">2008</span><span class="sxs-lookup"><span data-stu-id="29a61-130">2008</span></span>  
  
- [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]  
  
- [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] <span data-ttu-id="29a61-131">2000 Service Pack 3 (SP3) 以降</span><span class="sxs-lookup"><span data-stu-id="29a61-131">2000 Service Pack 3 (SP3) and later</span></span>  
  
- <span data-ttu-id="29a61-132">Sun Solaris 9.0</span><span class="sxs-lookup"><span data-stu-id="29a61-132">Sun Solaris 9.0</span></span>  
  
- <span data-ttu-id="29a61-133">HP-UX</span><span class="sxs-lookup"><span data-stu-id="29a61-133">HP-UX</span></span>  
  
- <span data-ttu-id="29a61-134">LINUX (Redhat 7.x)</span><span class="sxs-lookup"><span data-stu-id="29a61-134">LINUX (Redhat 7.x)</span></span>  
  
- <span data-ttu-id="29a61-135">IBM Z/OS v1.9 (MVS)</span><span class="sxs-lookup"><span data-stu-id="29a61-135">IBM z/OS v1.9 (MVS)</span></span>  
  
- <span data-ttu-id="29a61-136">MVS を実行している IBM O/S 390</span><span class="sxs-lookup"><span data-stu-id="29a61-136">IBM O/S 390 running MVS</span></span>  
  
- <span data-ttu-id="29a61-137">AS/400 OS/400 V5R1</span><span class="sxs-lookup"><span data-stu-id="29a61-137">AS/400 OS/400 V5R1</span></span>  
  
- <span data-ttu-id="29a61-138">OS/i5 V5R4 (AS400)</span><span class="sxs-lookup"><span data-stu-id="29a61-138">i5/OS V5R4 (AS400)</span></span>  
  
- <span data-ttu-id="29a61-139">OS/i5 V6R1 (AS400)</span><span class="sxs-lookup"><span data-stu-id="29a61-139">i5/OS V6R1 (AS400)</span></span>  
  
- <span data-ttu-id="29a61-140">GXS ICS</span><span class="sxs-lookup"><span data-stu-id="29a61-140">GXS ICS</span></span>  
  
- <span data-ttu-id="29a61-141">AIX</span><span class="sxs-lookup"><span data-stu-id="29a61-141">AIX</span></span>  
  
  <span data-ttu-id="29a61-142">サービス パックが具体的にはされている場合を除き、すべてのサービス パックがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="29a61-142">All services packs are supported, unless the service pack is specifically listed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="29a61-143">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="29a61-143">In This Section</span></span>  
  
[<span data-ttu-id="29a61-144">FTP アダプターのベスト プラクティスと推奨事項</span><span class="sxs-lookup"><span data-stu-id="29a61-144">Best practices and recommendations for the FTP Adapter</span></span>](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)  

[<span data-ttu-id="29a61-145">FTP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="29a61-145">Configuring the FTP adapter</span></span>](../core/configuring-the-ftp-adapter.md)  

[<span data-ttu-id="29a61-146">FTP アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="29a61-146">FTP Adapter Property Schema and Properties</span></span>](../core/ftp-adapter-property-schema-and-properties.md)