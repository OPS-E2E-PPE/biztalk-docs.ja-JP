---
title: BizTalk adapter for BizTalk 内の SQL の用語集 |Microsoft Docs
description: 共通の用語と定義は、BizTalk Adapter pack (BAP) で SQL アダプターによって使用されます。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c364917e-b72b-49e4-9fc6-0fcfe43c8da7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a4ca26f8f1d2e18bdbf3ed02b1643f055fbeec1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369426"
---
# <a name="terms-used-by-the-sql-adapter"></a><span data-ttu-id="7754f-103">SQL アダプターによって使用される用語</span><span class="sxs-lookup"><span data-stu-id="7754f-103">Terms used by the SQL adapter</span></span>
<span data-ttu-id="7754f-104">次の用語と定義がで使用される[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="7754f-104">The following terms and definitions are used in [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] Help.</span></span>  
  
  
## <a name="a"></a><span data-ttu-id="7754f-105">A</span><span class="sxs-lookup"><span data-stu-id="7754f-105">A</span></span>  
  
<span data-ttu-id="7754f-106">**アダプター**</span><span class="sxs-lookup"><span data-stu-id="7754f-106">**adapter**</span></span>  
<span data-ttu-id="7754f-107">Exchange は、WCF ベースのコンポーネントがアプリケーション (基幹業務システムなど) 間でメッセージと BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="7754f-107">A WCF-based component that helps exchange messages between applications (for example, a line-of-business system) and BizTalk Server.</span></span> <span data-ttu-id="7754f-108">アダプターは、デザイン時コンポーネントとの受信と送信操作の実行時コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-108">The adapter consists of design-time components and run-time components for receive and send operations.</span></span>

<span data-ttu-id="7754f-109">**アダプター クライアント**</span><span class="sxs-lookup"><span data-stu-id="7754f-109">**adapter client**</span></span>  
<span data-ttu-id="7754f-110">アダプターを介して基幹業務 (LOB) システムと対話するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="7754f-110">An application that interacts with a line-of-business (LOB) system through the adapter.</span></span>    

  
## <a name="b"></a><span data-ttu-id="7754f-111">B</span><span class="sxs-lookup"><span data-stu-id="7754f-111">B</span></span>  
  
<span data-ttu-id="7754f-112">**バインド**</span><span class="sxs-lookup"><span data-stu-id="7754f-112">**binding**</span></span>  
<span data-ttu-id="7754f-113">ソフトウェア コンポーネントとレイヤーが一緒にリンクするプロセス。</span><span class="sxs-lookup"><span data-stu-id="7754f-113">A process by which software components and layers are linked together.</span></span> <span data-ttu-id="7754f-114">ネットワーク コンポーネントがインストールされている場合は、バインドのリレーションシップと、コンポーネントの依存関係が確立されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-114">When a network component is installed, the binding relationships and dependencies for the components are established.</span></span> <span data-ttu-id="7754f-115">バインドは、互いに通信するコンポーネントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7754f-115">Binding allows components to communicate with each other.</span></span> <span data-ttu-id="7754f-116">BizTalk server のオーケストレーション アダプターに依存しないエンドポイント (ポートまたはロールリンク) と物理アダプターに固有のエンドポイント (送信/受信ポートまたはパーティ) の間に確立したマップします。</span><span class="sxs-lookup"><span data-stu-id="7754f-116">In BizTalk Server, an established mapping between an orchestration adapter-agnostic endpoint (port or role link) and physical adapter-specific endpoints (send/receive ports or party).</span></span>

<span data-ttu-id="7754f-117">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="7754f-117">**BizTalk Server**</span></span>  
<span data-ttu-id="7754f-118">多様なソフトウェアを接続します。</span><span class="sxs-lookup"><span data-stu-id="7754f-118">Connects diverse software.</span></span> <span data-ttu-id="7754f-119">BizTalk Server には、作成し、そのソフトウェアを使用するプロセス ロジックを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7754f-119">BizTalk Server enables you to create and modify process logic that uses that software.</span></span> <span data-ttu-id="7754f-120">BizTalk Server では、インフォメーション ワーカーの実行中のプロセスを監視、取引先との対話およびその他のビジネス指向のタスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="7754f-120">BizTalk Server also enables information workers to monitor running processes, interact with trading partners, and perform other business-oriented tasks.</span></span>
  
 
## <a name="c"></a><span data-ttu-id="7754f-121">c</span><span class="sxs-lookup"><span data-stu-id="7754f-121">C</span></span>  
  
<span data-ttu-id="7754f-122">**チャネル**</span><span class="sxs-lookup"><span data-stu-id="7754f-122">**channel**</span></span>  
<span data-ttu-id="7754f-123">バインド要素の具象実装です。</span><span class="sxs-lookup"><span data-stu-id="7754f-123">A concrete implementation of a binding element.</span></span> <span data-ttu-id="7754f-124">バインディングは、構成を表し、チャネルはその構成に関連付けられた実装です。</span><span class="sxs-lookup"><span data-stu-id="7754f-124">The binding represents the configuration, and the channel is the implementation associated with that configuration.</span></span> <span data-ttu-id="7754f-125">そのため、各バインド要素に関連付けられたチャネルが存在します。</span><span class="sxs-lookup"><span data-stu-id="7754f-125">Therefore, there is a channel associated with each binding element.</span></span> <span data-ttu-id="7754f-126">チャネルが積み重ねられて、バインディングの具象実装を作成する: チャネル スタック。</span><span class="sxs-lookup"><span data-stu-id="7754f-126">Channels stack on top of each other to create the concrete implementation of the binding: the channel stack.</span></span>

<span data-ttu-id="7754f-127">**接続 URI**</span><span class="sxs-lookup"><span data-stu-id="7754f-127">**connection URI**</span></span>  
<span data-ttu-id="7754f-128">分散環境でのリソースを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="7754f-128">A string that identifies a resource in a distributed environment.</span></span> <span data-ttu-id="7754f-129">アダプターは、Uniform Resource Identifier (URI) LOB システムとの接続を確立するために必要な情報を含む接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="7754f-129">Adapters use a connection Uniform Resource Identifier (URI) that contains the information necessary to establish a connection with the LOB system.</span></span>

<span data-ttu-id="7754f-130">**コントラクト**</span><span class="sxs-lookup"><span data-stu-id="7754f-130">**contract**</span></span>  
<span data-ttu-id="7754f-131">コレクションと、サービスによって提供される操作にアクセスするために必要なメッセージの構造を指定します。</span><span class="sxs-lookup"><span data-stu-id="7754f-131">Specifies the collection and structure of messages required to access the operations offered by the service.</span></span>  
  
## <a name="d"></a><span data-ttu-id="7754f-132">D</span><span class="sxs-lookup"><span data-stu-id="7754f-132">D</span></span>  
  
<span data-ttu-id="7754f-133">**データ操作言語 (DML)**</span><span class="sxs-lookup"><span data-stu-id="7754f-133">**data manipulation language (DML)**</span></span>  
<span data-ttu-id="7754f-134">データの取得と操作に使用する SQL ステートメントのサブセット。</span><span class="sxs-lookup"><span data-stu-id="7754f-134">The subset of SQL statements that is used to retrieve and manipulate data.</span></span> <span data-ttu-id="7754f-135">DML ステートメントは、通常、SELECT、INSERT、UPDATE、または削除を開始します。</span><span class="sxs-lookup"><span data-stu-id="7754f-135">DML statements typically start with SELECT, INSERT, UPDATE, or DELETE.</span></span>

<span data-ttu-id="7754f-136">**デザイン時のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="7754f-136">**design-time experience**</span></span>  
<span data-ttu-id="7754f-137">プロシージャと、開発者がデザイン時の中に実行する操作メッセージ スキーマを取得するのにアダプター サービスの使用 BizTalk プロジェクト アドインを使用など。</span><span class="sxs-lookup"><span data-stu-id="7754f-137">Procedures and operations that a developer performs during design time; for example, using the Consume Adapter Service BizTalk Project Add-in to retrieve message schemas.</span></span> 
  
## <a name="e"></a><span data-ttu-id="7754f-138">E</span><span class="sxs-lookup"><span data-stu-id="7754f-138">E</span></span>  
  
<span data-ttu-id="7754f-139">**エンドポイント アドレス**</span><span class="sxs-lookup"><span data-stu-id="7754f-139">**endpoint address**</span></span>  
<span data-ttu-id="7754f-140">Windows Communication Foundation (WCF) サービス エンドポイントの場所を識別するネットワーク アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7754f-140">A network address that identifies the location of a Windows Communication Foundation (WCF) service endpoint.</span></span> <span data-ttu-id="7754f-141">アダプターのエンドポイント アドレスは、接続の Uniform Resource Identifier (URI) の場所と接続パラメーターを含むとして表されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-141">For an adapter, the endpoint address is expressed as a connection Uniform Resource Identifier (URI) that contains location and connection parameters.</span></span> <span data-ttu-id="7754f-142">アダプターは、基になる基幹業務 (LOB) システムへの接続を確立するためにこれらを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7754f-142">The adapter can use these to establish a connection to the underlying line-of-business (LOB) system.</span></span>

<span data-ttu-id="7754f-143">**エンタープライズ シングル サインオン システム (SSO)**</span><span class="sxs-lookup"><span data-stu-id="7754f-143">**Enterprise Single Sign-on system (SSO)**</span></span>  
<span data-ttu-id="7754f-144">SSO データベースをマスター シークレット サーバー、および 1 つまたは複数のエンタープライズ シングル サインオン (SSO) サーバー。</span><span class="sxs-lookup"><span data-stu-id="7754f-144">An SSO database, a master secret server, and one or more Enterprise Single Sign-On (SSO) servers.</span></span> <span data-ttu-id="7754f-145">これらのサーバーは、Windows と Windows 以外の資格情報のマッピング、SSO データベース内の資格情報を検索、および SSO システムの管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-145">These servers do the mapping between the Windows and non-Windows credentials, look up the credentials in the SSO database, and are used for administering the SSO system.</span></span> <span data-ttu-id="7754f-146">SSO データベースは、アダプターのカスタム構成データを保持するために構成ストアとしても使用されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-146">The SSO database is also used as a configuration store to hold custom configuration data for adapters.</span></span>

<span data-ttu-id="7754f-147">**拡張マークアップ言語 (XML)**</span><span class="sxs-lookup"><span data-stu-id="7754f-147">**Extensible Markup Language (XML)**</span></span>  
<span data-ttu-id="7754f-148">データを記述するように設計するマークアップ言語。</span><span class="sxs-lookup"><span data-stu-id="7754f-148">A markup language designed to describe data.</span></span> <span data-ttu-id="7754f-149">XML タグがあらかじめ定義されていません。</span><span class="sxs-lookup"><span data-stu-id="7754f-149">XML tags are not predefined.</span></span>  

  
## <a name="g"></a><span data-ttu-id="7754f-150">G</span><span class="sxs-lookup"><span data-stu-id="7754f-150">G</span></span>  
  
<span data-ttu-id="7754f-151">**グローバル アセンブリ キャッシュ (GAC)**</span><span class="sxs-lookup"><span data-stu-id="7754f-151">**global assembly cache (GAC)**</span></span>  
<span data-ttu-id="7754f-152">コンピューター上の多数のアプリケーション間で共有するためにインストールされたアセンブリを格納するマシン全体のコード キャッシュ。</span><span class="sxs-lookup"><span data-stu-id="7754f-152">A machine-wide code cache that stores assemblies specifically installed to be shared by many applications on the computer.</span></span> <span data-ttu-id="7754f-153">グローバル アセンブリ キャッシュに配置されたアプリケーションは、厳密な名前をいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7754f-153">Applications deployed in the global assembly cache must have a strong name.</span></span>
  
## <a name="i"></a><span data-ttu-id="7754f-154">I</span><span class="sxs-lookup"><span data-stu-id="7754f-154">I</span></span>  
  
<span data-ttu-id="7754f-155">**受信操作**</span><span class="sxs-lookup"><span data-stu-id="7754f-155">**inbound operation**</span></span>  
<span data-ttu-id="7754f-156">アダプターの基幹業務 (LOB) システムによって呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="7754f-156">An operation that is invoked by a line-of-business (LOB) system on the adapter.</span></span>  
  
  
## <a name="m"></a><span data-ttu-id="7754f-157">M</span><span class="sxs-lookup"><span data-stu-id="7754f-157">M</span></span>  
  
<span data-ttu-id="7754f-158">**metadata**</span><span class="sxs-lookup"><span data-stu-id="7754f-158">**metadata**</span></span>  
<span data-ttu-id="7754f-159">WCF では、サービスによって公開されるコントラクトの説明を参照します。</span><span class="sxs-lookup"><span data-stu-id="7754f-159">In WCF, refers to a description of the contract exposed by a service.</span></span> <span data-ttu-id="7754f-160">これは、サービスの説明と呼ばれます、WSDL ドキュメントで表されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-160">This is known as the service description and is expressed in a WSDL document.</span></span> <span data-ttu-id="7754f-161">アダプターによって公開されているメタデータ (インターフェイス) の説明に、基になる LOB システムを実行できる操作。</span><span class="sxs-lookup"><span data-stu-id="7754f-161">The metadata exposed by an adapter describes the (interface to) the operations that it can perform on the underlying LOB system.</span></span>

**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
<span data-ttu-id="7754f-162">使用して BizTalk アダプターを構築するための仕様では、標準の Web サービスのベースを開きます。</span><span class="sxs-lookup"><span data-stu-id="7754f-162">The specifications for building BizTalk adapters using open standards based on Web services.</span></span>  
  
## <a name="o"></a><span data-ttu-id="7754f-163">O</span><span class="sxs-lookup"><span data-stu-id="7754f-163">O</span></span>  
  
<span data-ttu-id="7754f-164">**one-way**</span><span class="sxs-lookup"><span data-stu-id="7754f-164">**one-way**</span></span>  
<span data-ttu-id="7754f-165">受信側では、メッセージが応答なしに送信します、送信側メッセージ交換パターン (MEP) が返されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-165">A message exchange pattern (MEP) in which the sender sends a message, but no response is returned by the receiver.</span></span> <span data-ttu-id="7754f-166">BizTalk Server では、Mep を通信パターンと呼びます。</span><span class="sxs-lookup"><span data-stu-id="7754f-166">In BizTalk Server, MEPs are referred to as communication patterns.</span></span>

<span data-ttu-id="7754f-167">**送信操作**</span><span class="sxs-lookup"><span data-stu-id="7754f-167">**outbound operation**</span></span>  
<span data-ttu-id="7754f-168">基幹業務 (LOB) システム上のアダプターによって呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="7754f-168">An operation that is invoked by the adapter on the line-of-business system (LOB).</span></span>

<span data-ttu-id="7754f-169">**output.cs**</span><span class="sxs-lookup"><span data-stu-id="7754f-169">**output.cs**</span></span>  
<span data-ttu-id="7754f-170">既定では、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) で作成されたファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="7754f-170">The default output file created by the ServiceModel Metadata Utility tool (svcutil.exe).</span></span> 

  
## <a name="p"></a><span data-ttu-id="7754f-171">P</span><span class="sxs-lookup"><span data-stu-id="7754f-171">P</span></span>  
  
<span data-ttu-id="7754f-172">**ポーリング**</span><span class="sxs-lookup"><span data-stu-id="7754f-172">**polling**</span></span>  
<span data-ttu-id="7754f-173">デバイス ドライバーを使用して複数のデバイスから送信するデータが含まれるかどうかの手法です。</span><span class="sxs-lookup"><span data-stu-id="7754f-173">A technique that device drivers use to find out from multiple devices whether they contain data to transmit.</span></span> <span data-ttu-id="7754f-174">デバイスは、ポーリングされた 1 つずつです。</span><span class="sxs-lookup"><span data-stu-id="7754f-174">The devices are polled one at a time.</span></span>

<span data-ttu-id="7754f-175">**proxy**</span><span class="sxs-lookup"><span data-stu-id="7754f-175">**proxy**</span></span>  
<span data-ttu-id="7754f-176">WCF では、サービスによって公開されるサービス コントラクトを実装するマネージ コード オブジェクトを指しています。</span><span class="sxs-lookup"><span data-stu-id="7754f-176">In WCF, refers to a managed-code object that implements the service contract exposed by a service.</span></span> <span data-ttu-id="7754f-177">WCF サービス モデルは、このようなプロキシの使用に基づきます。</span><span class="sxs-lookup"><span data-stu-id="7754f-177">The WCF service model is based on the use of such proxies.</span></span> <span data-ttu-id="7754f-178">WCF サービス モデルでは、サービス コントラクトは、.NET インターフェイスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-178">In the WCF service model, the service contract is expressed as a .NET interface.</span></span>

  
## <a name="r"></a><span data-ttu-id="7754f-179">R</span><span class="sxs-lookup"><span data-stu-id="7754f-179">R</span></span>    

<span data-ttu-id="7754f-180">**request-response**</span><span class="sxs-lookup"><span data-stu-id="7754f-180">**request-response**</span></span>  
<span data-ttu-id="7754f-181">メッセージ交換パターン (MEP) を送信側が要求メッセージを送信し、受信側から応答メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="7754f-181">A message exchange pattern (MEP) in which the sender sends a request message and expects a response message from the receiver.</span></span> <span data-ttu-id="7754f-182">BizTalk Server では、Mep を通信パターンと呼びます。</span><span class="sxs-lookup"><span data-stu-id="7754f-182">In BizTalk Server, MEPs are referred to as communication patterns.</span></span> <span data-ttu-id="7754f-183">によって、メッセージング テクノロジ、および要求メッセージ (受信または送信) の方向、要求/応答または送信請求-応答このパターンとも呼びます。</span><span class="sxs-lookup"><span data-stu-id="7754f-183">Depending on the messaging technology and the direction of the request message (inbound or outbound), this pattern is also called request-reply or solicit-response.</span></span>

<span data-ttu-id="7754f-184">**実行時のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="7754f-184">**run-time experience**</span></span>  
<span data-ttu-id="7754f-185">プロシージャと実行時、または、ソリューションをデプロイするときに、開発者によって実行される操作たとえば、BizTalk Server 管理コンソールから物理的なポート バインドを作成します。</span><span class="sxs-lookup"><span data-stu-id="7754f-185">Procedures and operations performed by a developer during run time or when deploying a solution; for example, creating a physical port binding from the BizTalk Server Administration console.</span></span>  


## <a name="s"></a><span data-ttu-id="7754f-186">S</span><span class="sxs-lookup"><span data-stu-id="7754f-186">S</span></span>  
  
<span data-ttu-id="7754f-187">**schema**</span><span class="sxs-lookup"><span data-stu-id="7754f-187">**schema**</span></span>  
<span data-ttu-id="7754f-188">メッセージの構造体。</span><span class="sxs-lookup"><span data-stu-id="7754f-188">The structure for a message.</span></span> <span data-ttu-id="7754f-189">スキーマは、複数のサブスキーマを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7754f-189">A schema can contain multiple subschema.</span></span>

<span data-ttu-id="7754f-190">**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)**</span><span class="sxs-lookup"><span data-stu-id="7754f-190">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span></span>  
<span data-ttu-id="7754f-191">WCF に付属するコマンド ライン ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="7754f-191">A command-line utility that is included with WCF.</span></span> <span data-ttu-id="7754f-192">アダプターなどの WCF サービスによって公開されるサービスの説明 (メタデータ) からのサービス モデルのプロキシ コードの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-192">It is used to create service model proxy code from the service description (metadata) that is exposed by a WCF service such as an adapter.</span></span> <span data-ttu-id="7754f-193">送信操作は、ツールは、WCF クライアント クラスとヘルパー コードを作成します。受信操作の場合は、ツールは、WCF サービス コントラクトとヘルパー コードを作成します。</span><span class="sxs-lookup"><span data-stu-id="7754f-193">For outbound operations, the tool creates a WCF client class and helper code; for inbound operations, the tool creates a WCF service contract and helper code.</span></span>

<span data-ttu-id="7754f-194">**SOAP (簡易オブジェクト アクセス プロトコル)**</span><span class="sxs-lookup"><span data-stu-id="7754f-194">**SOAP (Simple Object Access Protocol)**</span></span>  
<span data-ttu-id="7754f-195">交換するため、XML ベースの単純なプロトコルでは、構造化し、分散環境で情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7754f-195">A simple, XML-based protocol for exchanging structured and type information in decentralized, distributed environments.</span></span> <span data-ttu-id="7754f-196">WCF は、SOAP メッセージには、操作を呼び出すし、結果を返すには、クライアントとサービス間の交換に基づいています。</span><span class="sxs-lookup"><span data-stu-id="7754f-196">WCF is based on the exchange of SOAP messages between clients and services to invoke operations and return results.</span></span>

<span data-ttu-id="7754f-197">**SOAP メッセージ**</span><span class="sxs-lookup"><span data-stu-id="7754f-197">**SOAP message**</span></span>  
<span data-ttu-id="7754f-198">整形式 XML ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="7754f-198">A well-formed XML document.</span></span> <span data-ttu-id="7754f-199">SOAP エンベロープと SOAP エンコーディングの名前空間を使用し、後に、SOAP エンベロープ (ルート要素) の場合は、省略可能な SOAP ヘッダーと SOAP メッセージの本文で構成されますが、省略可能な XML 宣言を含めるかする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7754f-199">It should use the SOAP envelope and SOAP encoding namespaces and include an optional XML declaration, followed by a SOAP envelope (the root element), which is made up of an optional SOAP header and a SOAP message body.</span></span>

<span data-ttu-id="7754f-200">**SQL Server Integration Services (SSIS)**</span><span class="sxs-lookup"><span data-stu-id="7754f-200">**SQL Server Integration Services (SSIS)**</span></span>  
<span data-ttu-id="7754f-201">インポート、エクスポート、およびさまざまなデータ ソースからデータを変換するために使用するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="7754f-201">A component that is used to import, export, and transform data from different data sources.</span></span> <span data-ttu-id="7754f-202">以前データ変換サービス (DTS) と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="7754f-202">Previously called data transformation service (DTS).</span></span>

<span data-ttu-id="7754f-203">**strongly-typed data**</span><span class="sxs-lookup"><span data-stu-id="7754f-203">**strongly-typed data**</span></span>  
<span data-ttu-id="7754f-204">データ セットまたは基になるオブジェクトの種類にバインドされている結果セット。</span><span class="sxs-lookup"><span data-stu-id="7754f-204">A data set or result set that is bound to an underlying object type.</span></span> <span data-ttu-id="7754f-205">厳密に型指定された XML データ セット内の各行で構成されます、型指定された名前付きフィールドの基になるオブジェクトの種類に対応する要素。</span><span class="sxs-lookup"><span data-stu-id="7754f-205">Each row in a strongly-typed XML data set is composed of typed, named elements that correspond to fields of the underlying object type.</span></span> 

<span data-ttu-id="7754f-206">**synonym**</span><span class="sxs-lookup"><span data-stu-id="7754f-206">**synonym**</span></span>  
<span data-ttu-id="7754f-207">スキーマ スコープ オブジェクトの代替名。</span><span class="sxs-lookup"><span data-stu-id="7754f-207">An alternative name for a schema-scoped object.</span></span>  
  
 
## <a name="w"></a><span data-ttu-id="7754f-208">W</span><span class="sxs-lookup"><span data-stu-id="7754f-208">W</span></span>  
<span data-ttu-id="7754f-209">**WCF チャネル モデル**</span><span class="sxs-lookup"><span data-stu-id="7754f-209">**WCF channel model**</span></span>  
<span data-ttu-id="7754f-210">複数のインターフェイスとその他の種類に依存しているプログラミング モデル。</span><span class="sxs-lookup"><span data-stu-id="7754f-210">A programming model that relies on several interfaces and other types.</span></span> <span data-ttu-id="7754f-211">チャネルでは、メッセージを送受信するための低レベル プログラミング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="7754f-211">Channels provide a low-level programming model for sending and receiving messages.</span></span>

<span data-ttu-id="7754f-212">**WCF クライアント**</span><span class="sxs-lookup"><span data-stu-id="7754f-212">**WCF client**</span></span>  
<span data-ttu-id="7754f-213">メソッドとして、サービス操作を公開するクライアント アプリケーション構造体。</span><span class="sxs-lookup"><span data-stu-id="7754f-213">A client-application construct that exposes the service operations as methods.</span></span> <span data-ttu-id="7754f-214">アダプターによって公開されているメタデータから WCF クライアント クラスを生成するのに、アダプター サービス参照を Visual Studio プラグインの追加や、ServiceModel メタデータ ユーティリティ ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7754f-214">You can use the Add Adapter Service Reference Visual Studio Plug-in or the ServiceModel Metadata Utility Tool to generate a WCF client class from the metadata exposed by an adapter.</span></span>

<span data-ttu-id="7754f-215">**WCF サービス コントラクト**</span><span class="sxs-lookup"><span data-stu-id="7754f-215">**WCF service contract**</span></span>  
<span data-ttu-id="7754f-216">サービス コントラクトのマネージ コードの表現。</span><span class="sxs-lookup"><span data-stu-id="7754f-216">A managed-code representation of the service contract.</span></span> <span data-ttu-id="7754f-217">クラスおよびメソッドでは、サービス、操作、メッセージ、およびサービスと通信するために使用するデータ コントラクトを定義する属性付きインターフェイスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-217">It is expressed as an interface in which classes and methods are attributed to define the service, operation, message, and data contracts used to communicate with a service.</span></span> <span data-ttu-id="7754f-218">ServiceModel メタデータ ユーティリティ ツールまたは、Add Adapter Service Reference Visual Studio プラグインを使用すると、アダプターによって公開されているメタデータから WCF サービス コントラクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="7754f-218">You can use the ServiceModel Metadata Utility tool or the Add Adapter Service Reference Visual Studio Plug-in to generate a WCF service contract from the metadata exposed by an adapter.</span></span> <span data-ttu-id="7754f-219">LOB システムから操作を受信する WCF サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="7754f-219">You implement the WCF service contract to receive operations from an LOB system.</span></span>

<span data-ttu-id="7754f-220">**WCF サービス モデル**</span><span class="sxs-lookup"><span data-stu-id="7754f-220">**WCF service model**</span></span>  
<span data-ttu-id="7754f-221">サービスがマネージ コード オブジェクトとして表されている WCF プログラミング モデル。</span><span class="sxs-lookup"><span data-stu-id="7754f-221">A WCF programming model in which a service is represented as a managed code object.</span></span> <span data-ttu-id="7754f-222">サービスによって公開される操作は、厳密に型指定されたデータを持つメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-222">The operations exposed by the service are represented as methods with strongly-typed data.</span></span>

<span data-ttu-id="7754f-223">**厳密に型指定されたデータ**</span><span class="sxs-lookup"><span data-stu-id="7754f-223">**weakly-typed data**</span></span>  
<span data-ttu-id="7754f-224">データ セットまたは基になるオブジェクトの種類にバインドされていない結果セット。</span><span class="sxs-lookup"><span data-stu-id="7754f-224">A data set or result set that is not bound to an underlying object type.</span></span> <span data-ttu-id="7754f-225">厳密に型指定の XML データ セットの各行は、各要素の型と名前属性が記述する汎用の列のコレクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7754f-225">Each row in a weakly-typed XML data set is composed of a collection of generic columns in which attributes describe the name and type of each element.</span></span>

<span data-ttu-id="7754f-226">**Web サービス**</span><span class="sxs-lookup"><span data-stu-id="7754f-226">**Web services**</span></span>  
<span data-ttu-id="7754f-227">他のアプリケーションにデータとサービスを提供するアプリケーション ロジックの単位。</span><span class="sxs-lookup"><span data-stu-id="7754f-227">A unit of application logic providing data and services to other applications.</span></span> <span data-ttu-id="7754f-228">アプリケーションは、標準的な Web プロトコルとデータ形式など、HTTP、XML、および、各 XML Web サービスを実装する方法の独立した SOAP を使用して XML Web サービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7754f-228">Applications access XML Web services using standard Web protocols and data formats such as HTTP, XML, and SOAP, independent of how each XML Web service is implemented.</span></span> <span data-ttu-id="7754f-229">XML Web サービスは、コンポーネント ベースの開発の最も優れた面と、Web を組み合わせたし、は、Microsoft .NET プログラミング モデルの基礎となります。</span><span class="sxs-lookup"><span data-stu-id="7754f-229">XML Web services combine the best aspects of component-based development and the Web, and are a cornerstone of the Microsoft .NET programming model.</span></span>

<span data-ttu-id="7754f-230">**Web サービス記述言語 (WSDL)**</span><span class="sxs-lookup"><span data-stu-id="7754f-230">**Web Services Description Language (WSDL)**</span></span>  
<span data-ttu-id="7754f-231">メッセージの一連の動作をエンドポイントとしてサービスを記述する XML ベースの言語。</span><span class="sxs-lookup"><span data-stu-id="7754f-231">An XML-based language that describes a service as a set of endpoints that operate on messages.</span></span> <span data-ttu-id="7754f-232">WSDL ドキュメントは、サービス コントラクト、操作コントラクト、メッセージ コントラクト、およびデータ コントラクト、クライアントを使用する必要がありますをについて説明します。 サービスとのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7754f-232">The WSDL document describes the service contract, operation contracts, message contracts, and data contracts that a client must use to interface with the service.</span></span>

<span data-ttu-id="7754f-233">**Windows Communication Foundation (WCF)**</span><span class="sxs-lookup"><span data-stu-id="7754f-233">**Windows Communication Foundation (WCF)**</span></span>  
<span data-ttu-id="7754f-234">Microsoft のサービス指向の通信インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="7754f-234">A Microsoft service-oriented communication infrastructure.</span></span> <span data-ttu-id="7754f-235">本質的に、フレームワークでは、クライアントがサービス プログラミング モデルとプログラミング モデルのメッセージ交換のより細かい制御をチャネルに提供します。</span><span class="sxs-lookup"><span data-stu-id="7754f-235">The framework inherently provides clients with a service programming model and a channel programming model for finer control of message exchanges.</span></span>

## <a name="x"></a><span data-ttu-id="7754f-236">x</span><span class="sxs-lookup"><span data-stu-id="7754f-236">X</span></span>   
  
<span data-ttu-id="7754f-237">**XML スキーマ定義言語 (XSD)**</span><span class="sxs-lookup"><span data-stu-id="7754f-237">**XML Schema definition language (XSD)**</span></span>  
<span data-ttu-id="7754f-238">スキーマ言語。</span><span class="sxs-lookup"><span data-stu-id="7754f-238">A schema language.</span></span> <span data-ttu-id="7754f-239">XML スキーマでは、World Wide Web Consortium (W3C) XML Schema Part 1 に準拠する要素、属性、およびデータ型を定義します。Structures Recommendation、XML スキーマ定義言語の。</span><span class="sxs-lookup"><span data-stu-id="7754f-239">An XML Schema defines the elements, attributes, and data types that comply with the World Wide Web Consortium (W3C) XML Schema Part 1: Structures Recommendation for the XML Schema Definition Language.</span></span> <span data-ttu-id="7754f-240">W3C XML Schema Part 2:Datatypes recommendation 』 は、XML スキーマで使用されるデータ型を定義するための推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="7754f-240">The W3C XML Schema Part 2: Datatypes Recommendation is the recommendation for defining data types that are used in XML schemas.</span></span> <span data-ttu-id="7754f-241">XML スキーマ定義言語では、XML メッセージの構造とデータ型を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="7754f-241">The XML Schema definition language enables you to define the structure and data types for XML messages.</span></span>