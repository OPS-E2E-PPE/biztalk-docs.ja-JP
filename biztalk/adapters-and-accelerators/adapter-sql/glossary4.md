---
title: BizTalk Adapter for BizTalk 内の SQL の用語集 |Microsoft ドキュメント
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
ms.openlocfilehash: c5ef402e2f2b106d68e400103ae6a997e6d35774
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226210"
---
# <a name="terms-used-by-the-sql-adapter"></a><span data-ttu-id="997ca-103">SQL アダプターによって使用される用語</span><span class="sxs-lookup"><span data-stu-id="997ca-103">Terms used by the SQL adapter</span></span>
<span data-ttu-id="997ca-104">次の用語と定義がで使用される[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="997ca-104">The following terms and definitions are used in [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] Help.</span></span>  
  
  
## <a name="a"></a><span data-ttu-id="997ca-105">A</span><span class="sxs-lookup"><span data-stu-id="997ca-105">A</span></span>  
  
<span data-ttu-id="997ca-106">**アダプター**</span><span class="sxs-lookup"><span data-stu-id="997ca-106">**adapter**</span></span>  
<span data-ttu-id="997ca-107">(たとえば、基幹業務システムなど) のアプリケーション間でメッセージの交換は、WCF ベースのコンポーネントと BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="997ca-107">A WCF-based component that helps exchange messages between applications (for example, a line-of-business system) and BizTalk Server.</span></span> <span data-ttu-id="997ca-108">送受信の操作に使用するデザイン時コンポーネントと実行時コンポーネントから構成されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-108">The adapter consists of design-time components and run-time components for receive and send operations.</span></span>

<span data-ttu-id="997ca-109">**アダプターのクライアント**</span><span class="sxs-lookup"><span data-stu-id="997ca-109">**adapter client**</span></span>  
<span data-ttu-id="997ca-110">アダプターにより、基幹業務 (LOB) システムと対話するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="997ca-110">An application that interacts with a line-of-business (LOB) system through the adapter.</span></span>    

  
## <a name="b"></a><span data-ttu-id="997ca-111">B</span><span class="sxs-lookup"><span data-stu-id="997ca-111">B</span></span>  
  
<span data-ttu-id="997ca-112">**バインド**</span><span class="sxs-lookup"><span data-stu-id="997ca-112">**binding**</span></span>  
<span data-ttu-id="997ca-113">ソフトウェアのコンポーネントとレイヤーを相互に関連付けるプロセス。</span><span class="sxs-lookup"><span data-stu-id="997ca-113">A process by which software components and layers are linked together.</span></span> <span data-ttu-id="997ca-114">ネットワーク コンポーネントをインストールした場合、そのコンポーネントに対して、バインドのリレーションシップと依存関係が確立されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-114">When a network component is installed, the binding relationships and dependencies for the components are established.</span></span> <span data-ttu-id="997ca-115">バインドによって、コンポーネントの相互通信が可能となります。</span><span class="sxs-lookup"><span data-stu-id="997ca-115">Binding allows components to communicate with each other.</span></span> <span data-ttu-id="997ca-116">BizTalk Server では、アダプターを問わないオーケストレーションのエンドポイント (ポートまたはロールリンク) と、アダプター固有の物理的なエンドポイント (送受信ポートまたはパーティ) との間に確立したマップを言います。</span><span class="sxs-lookup"><span data-stu-id="997ca-116">In BizTalk Server, an established mapping between an orchestration adapter-agnostic endpoint (port or role link) and physical adapter-specific endpoints (send/receive ports or party).</span></span>

<span data-ttu-id="997ca-117">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="997ca-117">**BizTalk Server**</span></span>  
<span data-ttu-id="997ca-118">多様なソフトウェアを接続します。</span><span class="sxs-lookup"><span data-stu-id="997ca-118">Connects diverse software.</span></span> <span data-ttu-id="997ca-119">BizTalk Server を使用すると、作成し、そのソフトウェアを使用するプロセス ロジックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="997ca-119">BizTalk Server enables you to create and modify process logic that uses that software.</span></span> <span data-ttu-id="997ca-120">また、インフォメーション ワーカーは BizTalk Server を使用して、実行中のプロセスを監視したり、取引先と連携したり、他のビジネス志向のタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="997ca-120">BizTalk Server also enables information workers to monitor running processes, interact with trading partners, and perform other business-oriented tasks.</span></span>
  
 
## <a name="c"></a><span data-ttu-id="997ca-121">C</span><span class="sxs-lookup"><span data-stu-id="997ca-121">C</span></span>  
  
<span data-ttu-id="997ca-122">**チャネル**</span><span class="sxs-lookup"><span data-stu-id="997ca-122">**channel**</span></span>  
<span data-ttu-id="997ca-123">バインド要素の具象実装です。</span><span class="sxs-lookup"><span data-stu-id="997ca-123">A concrete implementation of a binding element.</span></span> <span data-ttu-id="997ca-124">バインディングは、構成を表し、チャネルがその構成に関連付けられた実装です。</span><span class="sxs-lookup"><span data-stu-id="997ca-124">The binding represents the configuration, and the channel is the implementation associated with that configuration.</span></span> <span data-ttu-id="997ca-125">したがって、各バインド要素に関連付けられているチャネルが存在します。</span><span class="sxs-lookup"><span data-stu-id="997ca-125">Therefore, there is a channel associated with each binding element.</span></span> <span data-ttu-id="997ca-126">チャネルが積み重ねられて、バインディングの具象実装を作成する: チャネル スタックです。</span><span class="sxs-lookup"><span data-stu-id="997ca-126">Channels stack on top of each other to create the concrete implementation of the binding: the channel stack.</span></span>

<span data-ttu-id="997ca-127">**接続 URI**</span><span class="sxs-lookup"><span data-stu-id="997ca-127">**connection URI**</span></span>  
<span data-ttu-id="997ca-128">分散環境でのリソースを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="997ca-128">A string that identifies a resource in a distributed environment.</span></span> <span data-ttu-id="997ca-129">アダプターは、Uniform Resource Identifier () を LOB システムとの接続を確立するために必要な情報を含む接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="997ca-129">Adapters use a connection Uniform Resource Identifier (URI) that contains the information necessary to establish a connection with the LOB system.</span></span>

<span data-ttu-id="997ca-130">**コントラクト**</span><span class="sxs-lookup"><span data-stu-id="997ca-130">**contract**</span></span>  
<span data-ttu-id="997ca-131">コレクションと、サービスによって提供される操作へのアクセスに必要なメッセージの構造を指定します。</span><span class="sxs-lookup"><span data-stu-id="997ca-131">Specifies the collection and structure of messages required to access the operations offered by the service.</span></span>  
  
## <a name="d"></a><span data-ttu-id="997ca-132">D</span><span class="sxs-lookup"><span data-stu-id="997ca-132">D</span></span>  
  
<span data-ttu-id="997ca-133">**データ操作言語 (DML)**</span><span class="sxs-lookup"><span data-stu-id="997ca-133">**data manipulation language (DML)**</span></span>  
<span data-ttu-id="997ca-134">データの取得と操作に使用する SQL ステートメントのサブセット。</span><span class="sxs-lookup"><span data-stu-id="997ca-134">The subset of SQL statements that is used to retrieve and manipulate data.</span></span> <span data-ttu-id="997ca-135">通常、DML ステートメントは、SELECT、INSERT、UPDATE、または DELETE で開始します。</span><span class="sxs-lookup"><span data-stu-id="997ca-135">DML statements typically start with SELECT, INSERT, UPDATE, or DELETE.</span></span>

<span data-ttu-id="997ca-136">**デザイン時機能**</span><span class="sxs-lookup"><span data-stu-id="997ca-136">**design-time experience**</span></span>  
<span data-ttu-id="997ca-137">プロシージャおよびデザイン時に、開発者を実行する操作たとえばを使用してアダプター サービスの使用する BizTalk プロジェクト アドイン メッセージ スキーマを取得します。</span><span class="sxs-lookup"><span data-stu-id="997ca-137">Procedures and operations that a developer performs during design time; for example, using the Consume Adapter Service BizTalk Project Add-in to retrieve message schemas.</span></span> 
  
## <a name="e"></a><span data-ttu-id="997ca-138">E</span><span class="sxs-lookup"><span data-stu-id="997ca-138">E</span></span>  
  
<span data-ttu-id="997ca-139">**エンドポイント アドレス**</span><span class="sxs-lookup"><span data-stu-id="997ca-139">**endpoint address**</span></span>  
<span data-ttu-id="997ca-140">Windows Communication Foundation (WCF) サービス エンドポイントの場所を識別するネットワーク アドレス。</span><span class="sxs-lookup"><span data-stu-id="997ca-140">A network address that identifies the location of a Windows Communication Foundation (WCF) service endpoint.</span></span> <span data-ttu-id="997ca-141">アダプターの場合、エンドポイントのアドレスは、接続の識別子 URI (Uniform Resource) の場所と接続パラメーターを含むとして表されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-141">For an adapter, the endpoint address is expressed as a connection Uniform Resource Identifier (URI) that contains location and connection parameters.</span></span> <span data-ttu-id="997ca-142">アダプターは、基になる基幹業務 (LOB) システムへの接続を確立するためにこれらを使用できます。</span><span class="sxs-lookup"><span data-stu-id="997ca-142">The adapter can use these to establish a connection to the underlying line-of-business (LOB) system.</span></span>

<span data-ttu-id="997ca-143">**エンタープライズ シングル サインオン システム (SSO)**</span><span class="sxs-lookup"><span data-stu-id="997ca-143">**Enterprise Single Sign-on system (SSO)**</span></span>  
<span data-ttu-id="997ca-144">SSO データベース (1 つ)、マスター シークレット サーバー (1 つ)、およびエンタープライズ シングル サインオン (SSO) サーバー (複数可)。</span><span class="sxs-lookup"><span data-stu-id="997ca-144">An SSO database, a master secret server, and one or more Enterprise Single Sign-On (SSO) servers.</span></span> <span data-ttu-id="997ca-145">これらのサーバーで、Windows 資格情報と Windows 以外の資格情報のマッピング、SSO データベース内の資格情報の検索、および SSO システムの管理を行います。</span><span class="sxs-lookup"><span data-stu-id="997ca-145">These servers do the mapping between the Windows and non-Windows credentials, look up the credentials in the SSO database, and are used for administering the SSO system.</span></span> <span data-ttu-id="997ca-146">SSO データベースは、アダプターのカスタム構成データを保存する構成ストアとしても使用されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-146">The SSO database is also used as a configuration store to hold custom configuration data for adapters.</span></span>

<span data-ttu-id="997ca-147">**拡張マークアップ言語 (XML)**</span><span class="sxs-lookup"><span data-stu-id="997ca-147">**Extensible Markup Language (XML)**</span></span>  
<span data-ttu-id="997ca-148">データを記述するように設計マークアップ言語。</span><span class="sxs-lookup"><span data-stu-id="997ca-148">A markup language designed to describe data.</span></span> <span data-ttu-id="997ca-149">XML タグがあらかじめ定義されていません。</span><span class="sxs-lookup"><span data-stu-id="997ca-149">XML tags are not predefined.</span></span>  

  
## <a name="g"></a><span data-ttu-id="997ca-150">G</span><span class="sxs-lookup"><span data-stu-id="997ca-150">G</span></span>  
  
<span data-ttu-id="997ca-151">**グローバル アセンブリ キャッシュ (GAC)**</span><span class="sxs-lookup"><span data-stu-id="997ca-151">**global assembly cache (GAC)**</span></span>  
<span data-ttu-id="997ca-152">コンピューター上の多数のアプリケーション間で共有するためにインストールされたアセンブリを格納するマシン全体のコード キャッシュ。</span><span class="sxs-lookup"><span data-stu-id="997ca-152">A machine-wide code cache that stores assemblies specifically installed to be shared by many applications on the computer.</span></span> <span data-ttu-id="997ca-153">グローバル アセンブリ キャッシュに配置されたアプリケーションは、厳密な名前をいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="997ca-153">Applications deployed in the global assembly cache must have a strong name.</span></span>
  
## <a name="i"></a><span data-ttu-id="997ca-154">I</span><span class="sxs-lookup"><span data-stu-id="997ca-154">I</span></span>  
  
<span data-ttu-id="997ca-155">**受信操作**</span><span class="sxs-lookup"><span data-stu-id="997ca-155">**inbound operation**</span></span>  
<span data-ttu-id="997ca-156">アダプターの基幹業務 (LOB) システムによって呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="997ca-156">An operation that is invoked by a line-of-business (LOB) system on the adapter.</span></span>  
  
  
## <a name="m"></a><span data-ttu-id="997ca-157">M</span><span class="sxs-lookup"><span data-stu-id="997ca-157">M</span></span>  
  
<span data-ttu-id="997ca-158">**メタデータ**</span><span class="sxs-lookup"><span data-stu-id="997ca-158">**metadata**</span></span>  
<span data-ttu-id="997ca-159">WCF では、サービスによって公開されるコントラクトの説明を参照します。</span><span class="sxs-lookup"><span data-stu-id="997ca-159">In WCF, refers to a description of the contract exposed by a service.</span></span> <span data-ttu-id="997ca-160">これは、サービスの説明と呼ばは WSDL ドキュメントで表現されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-160">This is known as the service description and is expressed in a WSDL document.</span></span> <span data-ttu-id="997ca-161">アダプターによって公開されるメタデータは、(インターフェイス) を説明します。 それが基になるの LOB システムで実行する操作。</span><span class="sxs-lookup"><span data-stu-id="997ca-161">The metadata exposed by an adapter describes the (interface to) the operations that it can perform on the underlying LOB system.</span></span>

**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
<span data-ttu-id="997ca-162">Web サービスに基づいたオープンな標準を使用して BizTalk アダプターを構築するための仕様です。</span><span class="sxs-lookup"><span data-stu-id="997ca-162">The specifications for building BizTalk adapters using open standards based on Web services.</span></span>  
  
## <a name="o"></a><span data-ttu-id="997ca-163">O</span><span class="sxs-lookup"><span data-stu-id="997ca-163">O</span></span>  
  
<span data-ttu-id="997ca-164">**一方向**</span><span class="sxs-lookup"><span data-stu-id="997ca-164">**one-way**</span></span>  
<span data-ttu-id="997ca-165">送信者が、メッセージは、応答がないを送信するメッセージ交換パターン (MEP) が、受信側によって返されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-165">A message exchange pattern (MEP) in which the sender sends a message, but no response is returned by the receiver.</span></span> <span data-ttu-id="997ca-166">BizTalk Server では、Mep を通信パターンと呼びます。</span><span class="sxs-lookup"><span data-stu-id="997ca-166">In BizTalk Server, MEPs are referred to as communication patterns.</span></span>

<span data-ttu-id="997ca-167">**送信操作**</span><span class="sxs-lookup"><span data-stu-id="997ca-167">**outbound operation**</span></span>  
<span data-ttu-id="997ca-168">基幹業務 (LOB) をシステム上のアダプターによって呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="997ca-168">An operation that is invoked by the adapter on the line-of-business system (LOB).</span></span>

<span data-ttu-id="997ca-169">**output.cs**</span><span class="sxs-lookup"><span data-stu-id="997ca-169">**output.cs**</span></span>  
<span data-ttu-id="997ca-170">既定値は、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) で作成されたファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="997ca-170">The default output file created by the ServiceModel Metadata Utility tool (svcutil.exe).</span></span> 

  
## <a name="p"></a><span data-ttu-id="997ca-171">P</span><span class="sxs-lookup"><span data-stu-id="997ca-171">P</span></span>  
  
<span data-ttu-id="997ca-172">**ポーリング**</span><span class="sxs-lookup"><span data-stu-id="997ca-172">**polling**</span></span>  
<span data-ttu-id="997ca-173">デバイス ドライバーを使用して複数のデバイスから送信するデータが含まれているかどうかを技法。</span><span class="sxs-lookup"><span data-stu-id="997ca-173">A technique that device drivers use to find out from multiple devices whether they contain data to transmit.</span></span> <span data-ttu-id="997ca-174">デバイスは、ポーリングされた 1 つずつです。</span><span class="sxs-lookup"><span data-stu-id="997ca-174">The devices are polled one at a time.</span></span>

<span data-ttu-id="997ca-175">**プロキシ**</span><span class="sxs-lookup"><span data-stu-id="997ca-175">**proxy**</span></span>  
<span data-ttu-id="997ca-176">WCF では、サービスによって公開されるサービス コントラクトを実装するマネージ コード オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="997ca-176">In WCF, refers to a managed-code object that implements the service contract exposed by a service.</span></span> <span data-ttu-id="997ca-177">WCF サービス モデルは、このようなプロキシの使用に基づきます。</span><span class="sxs-lookup"><span data-stu-id="997ca-177">The WCF service model is based on the use of such proxies.</span></span> <span data-ttu-id="997ca-178">WCF サービス モデルでは、サービス コントラクトは、.NET インターフェイスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-178">In the WCF service model, the service contract is expressed as a .NET interface.</span></span>

  
## <a name="r"></a><span data-ttu-id="997ca-179">R</span><span class="sxs-lookup"><span data-stu-id="997ca-179">R</span></span>    

<span data-ttu-id="997ca-180">**要求-応答**</span><span class="sxs-lookup"><span data-stu-id="997ca-180">**request-response**</span></span>  
<span data-ttu-id="997ca-181">メッセージ交換パターン (MEP) を送信元要求メッセージを送信し、受信側からの応答メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="997ca-181">A message exchange pattern (MEP) in which the sender sends a request message and expects a response message from the receiver.</span></span> <span data-ttu-id="997ca-182">BizTalk Server では、Mep を通信パターンと呼びます。</span><span class="sxs-lookup"><span data-stu-id="997ca-182">In BizTalk Server, MEPs are referred to as communication patterns.</span></span> <span data-ttu-id="997ca-183">メッセージング テクノロジとに応じて、要求メッセージ (受信または送信) の方向、要求/応答または送信請求-応答このパターンが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-183">Depending on the messaging technology and the direction of the request message (inbound or outbound), this pattern is also called request-reply or solicit-response.</span></span>

<span data-ttu-id="997ca-184">**実行時のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="997ca-184">**run-time experience**</span></span>  
<span data-ttu-id="997ca-185">プロシージャと実行時に、または、ソリューションを展開するときに、開発者が実行される操作たとえば、BizTalk Server 管理コンソールから、物理ポートのバインドを作成します。</span><span class="sxs-lookup"><span data-stu-id="997ca-185">Procedures and operations performed by a developer during run time or when deploying a solution; for example, creating a physical port binding from the BizTalk Server Administration console.</span></span>  


## <a name="s"></a><span data-ttu-id="997ca-186">S</span><span class="sxs-lookup"><span data-stu-id="997ca-186">S</span></span>  
  
<span data-ttu-id="997ca-187">**スキーマ**</span><span class="sxs-lookup"><span data-stu-id="997ca-187">**schema**</span></span>  
<span data-ttu-id="997ca-188">メッセージの構造。</span><span class="sxs-lookup"><span data-stu-id="997ca-188">The structure for a message.</span></span> <span data-ttu-id="997ca-189">スキーマには、複数のサブスキーマを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="997ca-189">A schema can contain multiple subschema.</span></span>

<span data-ttu-id="997ca-190">**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)**</span><span class="sxs-lookup"><span data-stu-id="997ca-190">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span></span>  
<span data-ttu-id="997ca-191">WCF に含まれているコマンド ライン ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="997ca-191">A command-line utility that is included with WCF.</span></span> <span data-ttu-id="997ca-192">アダプターなどの WCF サービスによって公開されるサービスの説明 (メタデータ) からサービス モデルのプロキシ コードの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-192">It is used to create service model proxy code from the service description (metadata) that is exposed by a WCF service such as an adapter.</span></span> <span data-ttu-id="997ca-193">送信処理は、ツールの作成、WCF クライアント クラスとヘルパー コード。受信操作は、WCF サービス コントラクトとヘルパー コードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-193">For outbound operations, the tool creates a WCF client class and helper code; for inbound operations, the tool creates a WCF service contract and helper code.</span></span>

<span data-ttu-id="997ca-194">**SOAP (簡易オブジェクト アクセス プロトコル)**</span><span class="sxs-lookup"><span data-stu-id="997ca-194">**SOAP (Simple Object Access Protocol)**</span></span>  
<span data-ttu-id="997ca-195">交換するため、XML ベースの単純なプロトコルでは、構造化し、分散環境で情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="997ca-195">A simple, XML-based protocol for exchanging structured and type information in decentralized, distributed environments.</span></span> <span data-ttu-id="997ca-196">WCF は、SOAP メッセージに操作を呼び出すし、結果を返すには、クライアントとサービス間の交換に基づいています。</span><span class="sxs-lookup"><span data-stu-id="997ca-196">WCF is based on the exchange of SOAP messages between clients and services to invoke operations and return results.</span></span>

<span data-ttu-id="997ca-197">**SOAP メッセージ**</span><span class="sxs-lookup"><span data-stu-id="997ca-197">**SOAP message**</span></span>  
<span data-ttu-id="997ca-198">整形式 XML ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="997ca-198">A well-formed XML document.</span></span> <span data-ttu-id="997ca-199">SOAP エンベロープと SOAP エンコーディングの名前空間、XML 宣言 (省略可能)、実際の SOAP エンベロープ (ルート要素)、SOAP ヘッダー (省略可能) および SOAP メッセージ本文で構成されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-199">It should use the SOAP envelope and SOAP encoding namespaces and include an optional XML declaration, followed by a SOAP envelope (the root element), which is made up of an optional SOAP header and a SOAP message body.</span></span>

<span data-ttu-id="997ca-200">**SQL Server Integration Services (SSIS)**</span><span class="sxs-lookup"><span data-stu-id="997ca-200">**SQL Server Integration Services (SSIS)**</span></span>  
<span data-ttu-id="997ca-201">インポート、エクスポート、およびさまざまなデータ ソースからデータを変換に使用されるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="997ca-201">A component that is used to import, export, and transform data from different data sources.</span></span> <span data-ttu-id="997ca-202">以前のデータ変換サービス (DTS) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="997ca-202">Previously called data transformation service (DTS).</span></span>

<span data-ttu-id="997ca-203">**厳密に型指定されたデータ**</span><span class="sxs-lookup"><span data-stu-id="997ca-203">**strongly-typed data**</span></span>  
<span data-ttu-id="997ca-204">データ セットまたは基になるオブジェクトの種類にバインドされている結果セットです。</span><span class="sxs-lookup"><span data-stu-id="997ca-204">A data set or result set that is bound to an underlying object type.</span></span> <span data-ttu-id="997ca-205">厳密に型指定された XML データ セット内の各行で構成されます入力すると、基になるオブジェクトの種類のフィールドに対応する要素の名前します。</span><span class="sxs-lookup"><span data-stu-id="997ca-205">Each row in a strongly-typed XML data set is composed of typed, named elements that correspond to fields of the underlying object type.</span></span> 

<span data-ttu-id="997ca-206">**シノニム**</span><span class="sxs-lookup"><span data-stu-id="997ca-206">**synonym**</span></span>  
<span data-ttu-id="997ca-207">スキーマ スコープ オブジェクトの代替名です。</span><span class="sxs-lookup"><span data-stu-id="997ca-207">An alternative name for a schema-scoped object.</span></span>  
  
 
## <a name="w"></a><span data-ttu-id="997ca-208">W</span><span class="sxs-lookup"><span data-stu-id="997ca-208">W</span></span>  
<span data-ttu-id="997ca-209">**WCF チャネル モデル**</span><span class="sxs-lookup"><span data-stu-id="997ca-209">**WCF channel model**</span></span>  
<span data-ttu-id="997ca-210">複数のインターフェイスとその他の種類に依存しているプログラミング モデルです。</span><span class="sxs-lookup"><span data-stu-id="997ca-210">A programming model that relies on several interfaces and other types.</span></span> <span data-ttu-id="997ca-211">チャネルは、メッセージを送受信するための低レベル プログラミング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="997ca-211">Channels provide a low-level programming model for sending and receiving messages.</span></span>

<span data-ttu-id="997ca-212">**WCF クライアント**</span><span class="sxs-lookup"><span data-stu-id="997ca-212">**WCF client**</span></span>  
<span data-ttu-id="997ca-213">メソッドとサービス操作を公開するクライアント アプリケーション構造体。</span><span class="sxs-lookup"><span data-stu-id="997ca-213">A client-application construct that exposes the service operations as methods.</span></span> <span data-ttu-id="997ca-214">アダプターによって公開されるメタデータから WCF クライアント クラスを生成するのには、アダプター サービス参照を Visual Studio プラグインの追加または ServiceModel メタデータ ユーティリティ ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="997ca-214">You can use the Add Adapter Service Reference Visual Studio Plug-in or the ServiceModel Metadata Utility Tool to generate a WCF client class from the metadata exposed by an adapter.</span></span>

<span data-ttu-id="997ca-215">**WCF サービス コントラクト**</span><span class="sxs-lookup"><span data-stu-id="997ca-215">**WCF service contract**</span></span>  
<span data-ttu-id="997ca-216">サービス コントラクトのマネージ コード表現。</span><span class="sxs-lookup"><span data-stu-id="997ca-216">A managed-code representation of the service contract.</span></span> <span data-ttu-id="997ca-217">表されますインターフェイス クラスおよびメソッドでは、関数に起因するサービス、操作、メッセージ、およびサービスとの通信に使用されるデータ コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="997ca-217">It is expressed as an interface in which classes and methods are attributed to define the service, operation, message, and data contracts used to communicate with a service.</span></span> <span data-ttu-id="997ca-218">アダプターによって公開されるメタデータから WCF サービス コントラクトを生成するのには、ServiceModel メタデータ ユーティリティ ツールまたは、アダプター サービス参照を Visual Studio プラグインの追加を使用できます。</span><span class="sxs-lookup"><span data-stu-id="997ca-218">You can use the ServiceModel Metadata Utility tool or the Add Adapter Service Reference Visual Studio Plug-in to generate a WCF service contract from the metadata exposed by an adapter.</span></span> <span data-ttu-id="997ca-219">LOB システムから、操作を受信する WCF サービス コントラクトを実装するとします。</span><span class="sxs-lookup"><span data-stu-id="997ca-219">You implement the WCF service contract to receive operations from an LOB system.</span></span>

<span data-ttu-id="997ca-220">**WCF サービスのモデル**</span><span class="sxs-lookup"><span data-stu-id="997ca-220">**WCF service model**</span></span>  
<span data-ttu-id="997ca-221">サービスがマネージ コード オブジェクトとして表される WCF プログラミング モデルです。</span><span class="sxs-lookup"><span data-stu-id="997ca-221">A WCF programming model in which a service is represented as a managed code object.</span></span> <span data-ttu-id="997ca-222">サービスによって公開される操作は、厳密に型指定されたデータを持つメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-222">The operations exposed by the service are represented as methods with strongly-typed data.</span></span>

<span data-ttu-id="997ca-223">**弱い型指定のデータ**</span><span class="sxs-lookup"><span data-stu-id="997ca-223">**weakly-typed data**</span></span>  
<span data-ttu-id="997ca-224">データ セットまたは基になるオブジェクトの種類にバインドされていない結果セットです。</span><span class="sxs-lookup"><span data-stu-id="997ca-224">A data set or result set that is not bound to an underlying object type.</span></span> <span data-ttu-id="997ca-225">弱い型指定の XML データ セット内の各行は、各要素の型と名前属性が記述される汎用の列のコレクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="997ca-225">Each row in a weakly-typed XML data set is composed of a collection of generic columns in which attributes describe the name and type of each element.</span></span>

<span data-ttu-id="997ca-226">**Web サービス**</span><span class="sxs-lookup"><span data-stu-id="997ca-226">**Web services**</span></span>  
<span data-ttu-id="997ca-227">他のアプリケーションにデータやサービスを提供するアプリケーション ロジックの単位。</span><span class="sxs-lookup"><span data-stu-id="997ca-227">A unit of application logic providing data and services to other applications.</span></span> <span data-ttu-id="997ca-228">アプリケーションは、標準的な Web プロトコルとデータ形式など、HTTP、XML、および各 XML Web サービスの実装方法に依存しない、SOAP を使用する XML Web サービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="997ca-228">Applications access XML Web services using standard Web protocols and data formats such as HTTP, XML, and SOAP, independent of how each XML Web service is implemented.</span></span> <span data-ttu-id="997ca-229">XML Web サービスはコンポーネント ベースの開発と Web の最も優れた面を組み合わせたもので、Microsoft .NET プログラミング モデルの中核になります。</span><span class="sxs-lookup"><span data-stu-id="997ca-229">XML Web services combine the best aspects of component-based development and the Web, and are a cornerstone of the Microsoft .NET programming model.</span></span>

<span data-ttu-id="997ca-230">**Web サービス記述言語 (WSDL)**</span><span class="sxs-lookup"><span data-stu-id="997ca-230">**Web Services Description Language (WSDL)**</span></span>  
<span data-ttu-id="997ca-231">メッセージに対して、一連の動作をエンドポイントとしてサービスを記述する XML ベースの言語です。</span><span class="sxs-lookup"><span data-stu-id="997ca-231">An XML-based language that describes a service as a set of endpoints that operate on messages.</span></span> <span data-ttu-id="997ca-232">WSDL ドキュメントは、サービス コントラクト、操作のコントラクト、メッセージ コントラクト、およびデータ コントラクト、クライアントを使用する必要がありますをについて説明します。 サービスとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="997ca-232">The WSDL document describes the service contract, operation contracts, message contracts, and data contracts that a client must use to interface with the service.</span></span>

<span data-ttu-id="997ca-233">**Windows Communication Foundation (WCF)**</span><span class="sxs-lookup"><span data-stu-id="997ca-233">**Windows Communication Foundation (WCF)**</span></span>  
<span data-ttu-id="997ca-234">Microsoft のサービス指向の通信インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="997ca-234">A Microsoft service-oriented communication infrastructure.</span></span> <span data-ttu-id="997ca-235">本質的に、フレームワークは、プログラミング モデル、およびプログラミング モデルのメッセージ交換のさらに細かく制御チャネルのサービスとクライアントを提供します。</span><span class="sxs-lookup"><span data-stu-id="997ca-235">The framework inherently provides clients with a service programming model and a channel programming model for finer control of message exchanges.</span></span>

## <a name="x"></a><span data-ttu-id="997ca-236">×</span><span class="sxs-lookup"><span data-stu-id="997ca-236">X</span></span>   
  
<span data-ttu-id="997ca-237">**XML スキーマ定義言語 (XSD)**</span><span class="sxs-lookup"><span data-stu-id="997ca-237">**XML Schema definition language (XSD)**</span></span>  
<span data-ttu-id="997ca-238">スキーマ言語。</span><span class="sxs-lookup"><span data-stu-id="997ca-238">A schema language.</span></span> <span data-ttu-id="997ca-239">World Wide Web Consortium (W3C) XML Schema Part 1 に準拠している要素、属性、およびデータ型を定義する XML スキーマ: XML スキーマ定義言語の構造の推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="997ca-239">An XML Schema defines the elements, attributes, and data types that comply with the World Wide Web Consortium (W3C) XML Schema Part 1: Structures Recommendation for the XML Schema Definition Language.</span></span> <span data-ttu-id="997ca-240">W3C XML Schema Part 2: Datatypes recommendation 』 は、勧告の XML スキーマで使用されるデータ型を定義します。</span><span class="sxs-lookup"><span data-stu-id="997ca-240">The W3C XML Schema Part 2: Datatypes Recommendation is the recommendation for defining data types that are used in XML schemas.</span></span> <span data-ttu-id="997ca-241">XSD (XML Schema Definition) 言語により、XML メッセージの構造とデータ型を定義できます。</span><span class="sxs-lookup"><span data-stu-id="997ca-241">The XML Schema definition language enables you to define the structure and data types for XML messages.</span></span>