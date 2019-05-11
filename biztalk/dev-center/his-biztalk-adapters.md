---
title: Host Integration Server に付属の BizTalk アダプター |Microsoft Docs
description: 彼に含まれるアプリケーションをホスト、ホスト ファイル、DB2、および WebSphere MQ の BizTalk アダプターの概要
author: MandiOhlinger
manager: anneta
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.author: mandia
ms.openlocfilehash: 138e49965520505c2f45203836af7172dfd56612
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401535"
---
# <a name="biztalk-adapters-for-host-systems"></a><span data-ttu-id="0376d-103">BizTalk アダプターのホスト システム</span><span class="sxs-lookup"><span data-stu-id="0376d-103">BizTalk adapters for host systems</span></span>


## <a name="biztalk-adapter-for-host-applications"></a><span data-ttu-id="0376d-104">ホスト アプリケーション用 BizTalk アダプター</span><span class="sxs-lookup"><span data-stu-id="0376d-104">BizTalk Adapter for Host Applications</span></span>

<span data-ttu-id="0376d-105">ホスト アプリケーション用の Microsoft BizTalk Adapter は、BizTalk Server 用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="0376d-105">The Microsoft BizTalk Adapter for Host Applications is designed for BizTalk Server.</span></span> <span data-ttu-id="0376d-106">Windows-Initiated を処理するため、既存の IBM メインフレーム zSeries (CICS と IMS) またはミッドレンジ iSeries (RPG) サーバーのプログラムへの効率的なクライアント アクセスできる Microsoft トランザクション インテグレーター (TI) テクノロジに基づいています。</span><span class="sxs-lookup"><span data-stu-id="0376d-106">It is based on technology in Microsoft Transaction Integrator (TI) for Windows-Initiated Processing, which enables efficient client access to existing IBM mainframe zSeries (CICS and IMS) or midrange iSeries (RPG) server programs.</span></span> 

<span data-ttu-id="0376d-107">TI のデザイン ツールは、Visual Studio および BizTalk Server ソリューションを IT 開発者は、クライアント プロキシを定義するときに生産性の高いが有効にして、XSD スキーマの作成と統合されます。</span><span class="sxs-lookup"><span data-stu-id="0376d-107">The TI design tools are integrated with Visual Studio and BizTalk Server solutions, enabling IT developers to be highly productive when defining the client proxy and creating the XSD schema.</span></span> <span data-ttu-id="0376d-108">BizTalk Server 管理者、サポートを改善し、必要なリモート BizTalk Server ソリューションの展開シナリオをサポートする Microsoft 管理コンソール (MMC) スナップインで、既存の TI マネージャーが強化されました。</span><span class="sxs-lookup"><span data-stu-id="0376d-108">For BizTalk Server administrators, the existing TI Manager, Microsoft Management Console (MMC) snap-in, has been enhanced to improve supportability and support the required remote BizTalk Server solution deployment scenarios.</span></span>

<span data-ttu-id="0376d-109">参照してください[ホスト アプリケーション用 BizTalk アダプター](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="0376d-109">See [BizTalk Adapter for Host Applications](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx).</span></span> 

## <a name="biztalk-adapter-for-host-files"></a><span data-ttu-id="0376d-110">ホスト ファイル用の BizTalk アダプター</span><span class="sxs-lookup"><span data-stu-id="0376d-110">BizTalk Adapter for Host Files</span></span>
<span data-ttu-id="0376d-111">ホスト ファイル用の Microsoft BizTalk アダプターは、IT 組織にアクセスして、メインフレーム zSeries VSAM データセットと midrange iSeries 物理ファイルを含む、ホスト ファイル システムに格納されている情報を統合できるようにする高度なデータ アダプターです。</span><span class="sxs-lookup"><span data-stu-id="0376d-111">The Microsoft BizTalk Adapter for Host Files is an advanced data adapter that enables IT organizations to access and integrate information stored in host file systems, including mainframe zSeries VSAM datasets and midrange iSeries physical files.</span></span> 

<span data-ttu-id="0376d-112">Visual Studio デザイン ツールは、BizTalk アダプターの XSD としてエクスポートしているホスト プログラムで説明されているファイルのメタデータのマップを定義する、BizTalk Server ソリューション内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="0376d-112">Visual Studio design tools are used within a BizTalk Server solution to define a metadata map of the host program-described files, which is then exported as XSD for use with the BizTalk adapter.</span></span> <span data-ttu-id="0376d-113">ウィザードは、BizTalk Server 管理ツールに統合されて、構成、動的送信ポートと静的を定義し、応答を送信請求できるよう IT プロフェッショナルの受信ポート、簡略化された一連の SQL コマンド (SELECT、INSERT、UPDATE、DELETE に基づく).</span><span class="sxs-lookup"><span data-stu-id="0376d-113">The configuration wizards are integrated into the BizTalk Server administration tools, allowing IT professionals to define dynamic send ports and static and solicit response receive ports, based on a simplified set of SQL commands (SELECT, INSERT, UPDATE, DELETE).</span></span> 

<span data-ttu-id="0376d-114">この BizTalk アダプターは非リレーショナルのホストのデータセットとメンバーに SQL をマップするホスト ファイル用の Microsoft .NET Framework データ プロバイダーに基づきます。</span><span class="sxs-lookup"><span data-stu-id="0376d-114">This BizTalk adapter is based on the Microsoft .NET Framework Data Provider for Host Files that maps SQL to non-relational host datasets and members.</span></span> <span data-ttu-id="0376d-115">これにより、プログラマーが読み取るし、ホスト ファイル データ ソースを作成しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="0376d-115">This makes it easier for non-programmers to read and write host file data sources.</span></span>

<span data-ttu-id="0376d-116">参照してください[ホスト ファイル用の BizTalk アダプター](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="0376d-116">See [BizTalk Adapter for Host Files](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx).</span></span>

## <a name="biztalk-adapter-for-db2"></a><span data-ttu-id="0376d-117">BizTalk Adapter for DB2</span><span class="sxs-lookup"><span data-stu-id="0376d-117">BizTalk Adapter for DB2</span></span>
<span data-ttu-id="0376d-118">Microsoft BizTalk Adapter for DB2 は、it プロフェッショナルはリモート ホストのコンピューティング プラットフォーム、IBM メインフレーム zSeries と midrange iSeries (DB2/400)、および IBM DB2 の IBM DB2 データベース サーバーに格納されている重要なデータにアクセスできるようにするリレーショナル データベース アダプターUniversal Database (UDB) オープン プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="0376d-118">The Microsoft BizTalk Adapter for DB2 is a relational database adapter that enables IT professionals to access vital data stored in IBM DB2 database servers on remote host computing platforms, IBM mainframe zSeries and midrange iSeries (DB2/400), and also IBM DB2 Universal Database (UDB) on open platforms.</span></span> 

<span data-ttu-id="0376d-119">IT プロフェッショナルは、標準の SQL コマンドと BizTalk Server 管理ツールに組み込まれている構成ウィザードを使用して、データベース プログラミングの必要なしに、DB2 に読み書きするソリューションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0376d-119">Using standard SQL commands and a configuration wizard built into BizTalk Server administration tools, IT professionals can create solutions that read and write to DB2 without any need for database programming.</span></span> <span data-ttu-id="0376d-120">Microsoft .NET Framework Data Provider for DB2 に基づいては、動的送信ポート、および静的関数の広範な範囲をサポートし、応答を送信請求 DB2 アダプターの受信ポート。</span><span class="sxs-lookup"><span data-stu-id="0376d-120">The DB2 adapter, which is based on the Microsoft .NET Framework Data Provider for DB2, supports a broad range of functions, including dynamic send ports, and static and solicit response receive ports.</span></span>

<span data-ttu-id="0376d-121">参照してください[BizTalk Adapter for DB2](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="0376d-121">See [BizTalk Adapter for DB2](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx).</span></span>

## <a name="biztalk-adapter-for-websphere-mq"></a><span data-ttu-id="0376d-122">BizTalk Adapter for WebSphere MQ</span><span class="sxs-lookup"><span data-stu-id="0376d-122">BizTalk Adapter for WebSphere MQ</span></span>
<span data-ttu-id="0376d-123">Microsoft BizTalk Adapter for WebSphere MQ (クライアント ベース) では、IBM WebSphere MQ Client (クライアント ベース) と IBM WebSphere MQ 拡張トランザクション クライアント (拡張クライアント) Api を使用してリモートの MQSeries キュー マネージャーと通信します。</span><span class="sxs-lookup"><span data-stu-id="0376d-123">The Microsoft BizTalk Adapter for WebSphere MQ (Client-Based) uses IBM WebSphere MQ Client (Base-Client) and IBM WebSphere MQ Extended Transactional Client (Extended-Client) APIs to communicate with remote MQSeries Queue Managers.</span></span> <span data-ttu-id="0376d-124">アダプターにより、BizTalk Server のデプロイし、管理の WebSphere MQ サーバーの Windows を効率的に基幹業務でのメッセージを交換することがなく、非 Windows オペレーティング システムに展開されている MQSeries キュー マネージャーと直接通信するには企業全体にわたってアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="0376d-124">The adapter enables BizTalk Server to communicate directly with MQSeries Queue Managers deployed on non-Windows operating systems, without needing to deploy and manage WebSphere MQ Server for Windows, to efficiently exchange messages with line-of-business applications across the enterprise.</span></span> 

<span data-ttu-id="0376d-125">ベース クライアントを併用すると、アダプターはメッセージの配信のみを保証する非トランザクション メッセージの処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="0376d-125">When used with the Base-Client, the adapter provides non-transactional message processing, guaranteeing only the delivery of messages.</span></span> <span data-ttu-id="0376d-126">重複するメッセージを処理するために、受信側アプリケーションの役目です。</span><span class="sxs-lookup"><span data-stu-id="0376d-126">It is the responsibility of the application on the receiving end to handle any duplicate messages.</span></span> <span data-ttu-id="0376d-127">拡張クライアントと共に使用すると、アダプターはトランザクション メッセージがメッセージの 1 回、および専用の 1 回の配信を保証するために処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="0376d-127">When used with the Extended-Client, the adapter provides transactional message processing to guarantee once-and-only-once delivery of messages.</span></span>

<span data-ttu-id="0376d-128">参照してください[BizTalk Adapter for WebSphere MQ](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="0376d-128">See [BizTalk Adapter for WebSphere MQ](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx).</span></span>
