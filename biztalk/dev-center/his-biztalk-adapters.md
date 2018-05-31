---
title: Host Integration Server に付属の BizTalk アダプター |Microsoft ドキュメント
description: 彼に含まれているアプリケーションのホスト、ホスト ファイル、DB2、および WebSphere MQ の BizTalk アダプターの概要
author: MandiOhlinger
manager: anneta
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.author: mandia
ms.openlocfilehash: 26f2bf48c9a1268aace041776ff3895c8f3b3aa5
ms.sourcegitcommit: 75d35f6f230f0846c29a4b146c6d5b074e60b13c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2017
ms.locfileid: "22645182"
---
# <a name="biztalk-adapters-for-host-systems"></a><span data-ttu-id="9b420-103">BizTalk アダプターのホスト システム</span><span class="sxs-lookup"><span data-stu-id="9b420-103">BizTalk adapters for host systems</span></span>


## <a name="biztalk-adapter-for-host-applications"></a><span data-ttu-id="9b420-104">BizTalk Adapter for ホスト アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9b420-104">BizTalk Adapter for Host Applications</span></span>

<span data-ttu-id="9b420-105">Microsoft BizTalk Adapter for ホスト アプリケーションは、BizTalk Server に適しています。</span><span class="sxs-lookup"><span data-stu-id="9b420-105">The Microsoft BizTalk Adapter for Host Applications is designed for BizTalk Server.</span></span> <span data-ttu-id="9b420-106">Windows-Initiated を処理するため、既存の IBM メインフレーム zSeries (CICS と IMS) またはミッドレンジ iSeries (RPG) サーバーのプログラムに効率的なクライアント アクセスを有効にする Microsoft トランザクション インテグレーター (TI) テクノロジに基づいています。</span><span class="sxs-lookup"><span data-stu-id="9b420-106">It is based on technology in Microsoft Transaction Integrator (TI) for Windows-Initiated Processing, which enables efficient client access to existing IBM mainframe zSeries (CICS and IMS) or midrange iSeries (RPG) server programs.</span></span> 

<span data-ttu-id="9b420-107">TI デザイン ツールは、Visual Studio および IT 開発者はクライアント プロキシを定義するときに、高い生産性を向上して、XSD スキーマを作成する、BizTalk Server ソリューションと統合されます。</span><span class="sxs-lookup"><span data-stu-id="9b420-107">The TI design tools are integrated with Visual Studio and BizTalk Server solutions, enabling IT developers to be highly productive when defining the client proxy and creating the XSD schema.</span></span> <span data-ttu-id="9b420-108">BizTalk Server 管理者のサポートを改善し、必要なリモート BizTalk Server ソリューションの展開シナリオをサポートする Microsoft 管理コンソール (MMC) スナップインで、既存の TI マネージャーが強化されました。</span><span class="sxs-lookup"><span data-stu-id="9b420-108">For BizTalk Server administrators, the existing TI Manager, Microsoft Management Console (MMC) snap-in, has been enhanced to improve supportability and support the required remote BizTalk Server solution deployment scenarios.</span></span>

<span data-ttu-id="9b420-109">参照してください[ホスト アプリケーション用の BizTalk アダプター](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="9b420-109">See [BizTalk Adapter for Host Applications](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx).</span></span> 

## <a name="biztalk-adapter-for-host-files"></a><span data-ttu-id="9b420-110">ホスト ファイル用の BizTalk アダプター</span><span class="sxs-lookup"><span data-stu-id="9b420-110">BizTalk Adapter for Host Files</span></span>
<span data-ttu-id="9b420-111">Microsoft BizTalk Adapter for ホスト ファイルは、IT 組織にアクセスし、メインフレーム zSeries VSAM データセットおよびミッドレンジ iSeries 物理ファイルをなど、ホスト ファイル システムに格納された情報を統合できるようにする高度なデータ アダプターです。</span><span class="sxs-lookup"><span data-stu-id="9b420-111">The Microsoft BizTalk Adapter for Host Files is an advanced data adapter that enables IT organizations to access and integrate information stored in host file systems, including mainframe zSeries VSAM datasets and midrange iSeries physical files.</span></span> 

<span data-ttu-id="9b420-112">Visual Studio デザイン ツールは、BizTalk アダプターの XSD としてエクスポートしているホスト プログラムで説明されているファイルのメタデータのマップを定義する、BizTalk Server ソリューション内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b420-112">Visual Studio design tools are used within a BizTalk Server solution to define a metadata map of the host program-described files, which is then exported as XSD for use with the BizTalk adapter.</span></span> <span data-ttu-id="9b420-113">ウィザードは、BizTalk Server 管理ツールに統合されて、構成できるようにする IT プロフェッショナルは動的送信ポートと静的を定義し、送信請求応答受信ポート、簡略化された一連の SQL コマンド (SELECT、INSERT、UPDATE、DELETE に基づく).</span><span class="sxs-lookup"><span data-stu-id="9b420-113">The configuration wizards are integrated into the BizTalk Server administration tools, allowing IT professionals to define dynamic send ports and static and solicit response receive ports, based on a simplified set of SQL commands (SELECT, INSERT, UPDATE, DELETE).</span></span> 

<span data-ttu-id="9b420-114">この BizTalk アダプターは、SQL をリレーショナルでないホスト データセットおよびメンバーにマップされるホスト ファイルの Microsoft .NET Framework データ プロバイダーに基づいています。</span><span class="sxs-lookup"><span data-stu-id="9b420-114">This BizTalk adapter is based on the Microsoft .NET Framework Data Provider for Host Files that maps SQL to non-relational host datasets and members.</span></span> <span data-ttu-id="9b420-115">これにより、プログラマでない読み書きするホスト ファイル データ ソースを簡単にします。</span><span class="sxs-lookup"><span data-stu-id="9b420-115">This makes it easier for non-programmers to read and write host file data sources.</span></span>

<span data-ttu-id="9b420-116">参照してください[ホスト ファイル用の BizTalk アダプター](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="9b420-116">See [BizTalk Adapter for Host Files](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx).</span></span>

## <a name="biztalk-adapter-for-db2"></a><span data-ttu-id="9b420-117">BizTalk Adapter for DB2</span><span class="sxs-lookup"><span data-stu-id="9b420-117">BizTalk Adapter for DB2</span></span>
<span data-ttu-id="9b420-118">Microsoft BizTalk Adapter for DB2 は、it プロフェッショナルをコンピューティング プラットフォーム、IBM メインフレーム zSeries とミッドレンジ iSeries (DB2/400)、および IBM DB2 のリモート ホスト上の IBM DB2 データベース サーバーに格納されている重要なデータにアクセスできるようにするリレーショナル データベース アダプターUniversal Database (UDB) オープン プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="9b420-118">The Microsoft BizTalk Adapter for DB2 is a relational database adapter that enables IT professionals to access vital data stored in IBM DB2 database servers on remote host computing platforms, IBM mainframe zSeries and midrange iSeries (DB2/400), and also IBM DB2 Universal Database (UDB) on open platforms.</span></span> 

<span data-ttu-id="9b420-119">標準の SQL コマンドと BizTalk Server 管理ツールに組み込まれた構成ウィザードを使用して、IT プロフェッショナルは、読み取りし、データベース プログラミングすることがなく DB2 への書き込みをソリューションに作成できます。</span><span class="sxs-lookup"><span data-stu-id="9b420-119">Using standard SQL commands and a configuration wizard built into BizTalk Server administration tools, IT professionals can create solutions that read and write to DB2 without any need for database programming.</span></span> <span data-ttu-id="9b420-120">DB2 アダプターは、Microsoft .NET Framework Data Provider for DB2 に基づいては、動的送信ポートと静的など、機能の広範な範囲のサポートおよび送信請求応答の受信ポート。</span><span class="sxs-lookup"><span data-stu-id="9b420-120">The DB2 adapter, which is based on the Microsoft .NET Framework Data Provider for DB2, supports a broad range of functions, including dynamic send ports, and static and solicit response receive ports.</span></span>

<span data-ttu-id="9b420-121">参照してください[BizTalk Adapter for DB2](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="9b420-121">See [BizTalk Adapter for DB2](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx).</span></span>

## <a name="biztalk-adapter-for-websphere-mq"></a><span data-ttu-id="9b420-122">BizTalk Adapter for WebSphere MQ</span><span class="sxs-lookup"><span data-stu-id="9b420-122">BizTalk Adapter for WebSphere MQ</span></span>
<span data-ttu-id="9b420-123">Microsoft BizTalk Adapter for WebSphere MQ (クライアント ベース) は、リモートの MQSeries キュー マネージャーとの通信に IBM WebSphere MQ Client (クライアント ベース) と IBM WebSphere MQ 拡張トランザクションのクライアント (拡張クライアント) Api を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b420-123">The Microsoft BizTalk Adapter for WebSphere MQ (Client-Based) uses IBM WebSphere MQ Client (Base-Client) and IBM WebSphere MQ Extended Transactional Client (Extended-Client) APIs to communicate with remote MQSeries Queue Managers.</span></span> <span data-ttu-id="9b420-124">アダプターにより、展開および WebSphere MQ Server for Windows、効率的とメッセージを交換基幹業務を管理することがなく Windows 以外のオペレーティング システムに展開されている MQSeries キュー マネージャーと直接通信するために BizTalk Server企業全体にわたるアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="9b420-124">The adapter enables BizTalk Server to communicate directly with MQSeries Queue Managers deployed on non-Windows operating systems, without needing to deploy and manage WebSphere MQ Server for Windows, to efficiently exchange messages with line-of-business applications across the enterprise.</span></span> 

<span data-ttu-id="9b420-125">ベース クライアントに使用する場合、アダプターは、メッセージの配信のみを保証する非トランザクション メッセージの処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="9b420-125">When used with the Base-Client, the adapter provides non-transactional message processing, guaranteeing only the delivery of messages.</span></span> <span data-ttu-id="9b420-126">重複するメッセージを処理する受信側では、アプリケーションの役割です。</span><span class="sxs-lookup"><span data-stu-id="9b420-126">It is the responsibility of the application on the receiving end to handle any duplicate messages.</span></span> <span data-ttu-id="9b420-127">拡張されたクライアントに使用する場合、アダプターはトランザクション メッセージがメッセージを 1 回と-専用の 1 回だけ配信を保証するために処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="9b420-127">When used with the Extended-Client, the adapter provides transactional message processing to guarantee once-and-only-once delivery of messages.</span></span>

<span data-ttu-id="9b420-128">参照してください[BizTalk Adapter for WebSphere MQ](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="9b420-128">See [BizTalk Adapter for WebSphere MQ](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx).</span></span>
