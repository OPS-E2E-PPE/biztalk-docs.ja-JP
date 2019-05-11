---
title: BizTalk での mySAP アダプターの用語集 |Microsoft Docs
description: 共通の用語と定義は、BizTalk Adapter pack (BAP) での mySAP アダプターによって使用されます。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87db79be-e242-40fa-9897-8915e6fb5cae
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15d2c077fefc89e779e0ea12b121a8c8bcba8024
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373349"
---
# <a name="glossary"></a><span data-ttu-id="41cff-103">用語集</span><span class="sxs-lookup"><span data-stu-id="41cff-103">Glossary</span></span>
<span data-ttu-id="41cff-104">次の用語と定義がで使用される[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="41cff-104">The following terms and definitions are used in [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
## <a name="a"></a><span data-ttu-id="41cff-105">A</span><span class="sxs-lookup"><span data-stu-id="41cff-105">A</span></span>  
  
<span data-ttu-id="41cff-106">**アダプター**</span><span class="sxs-lookup"><span data-stu-id="41cff-106">**adapter**</span></span>  
<span data-ttu-id="41cff-107">Exchange は、WCF ベースのコンポーネントがアプリケーション (基幹業務システムなど) 間でメッセージと BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="41cff-107">A WCF-based component that helps exchange messages between applications (for example, a line-of-business system) and BizTalk Server.</span></span> <span data-ttu-id="41cff-108">アダプターは、デザイン時コンポーネントとの受信と送信操作の実行時コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-108">The adapter consists of design-time components and run-time components for receive and send operations.</span></span>

<span data-ttu-id="41cff-109">**アダプター クライアント**</span><span class="sxs-lookup"><span data-stu-id="41cff-109">**adapter client**</span></span>  
<span data-ttu-id="41cff-110">アダプターを介して基幹業務 (LOB) システムと対話するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="41cff-110">An application that interacts with a line-of-business (LOB) system through the adapter.</span></span>

<span data-ttu-id="41cff-111">**Programming (ABAP) 高度なビジネス アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="41cff-111">**Advanced Business Application Programming (ABAP)**</span></span>  
<span data-ttu-id="41cff-112">SAP のプログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="41cff-112">The SAP programming language.</span></span>  
  
## <a name="b"></a><span data-ttu-id="41cff-113">B</span><span class="sxs-lookup"><span data-stu-id="41cff-113">B</span></span>  
  
<span data-ttu-id="41cff-114">**Bapi (ビジネス アプリケーション プログラミング インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="41cff-114">**BAPIs (Business Application Programming Interfaces)**</span></span>  
<span data-ttu-id="41cff-115">SAP と他のシステム間でビジネスを交換する SAP システムによって公開されている標準のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="41cff-115">Standard interfaces exposed by the SAP system to exchange business between SAP and other systems.</span></span> <span data-ttu-id="41cff-116">Bapi を使用して、インターネットまたはローカル ネットワーク経由で相互に接続している別のコンポーネントを統合します。</span><span class="sxs-lookup"><span data-stu-id="41cff-116">BAPIs are used to integrate different components, which are connected to each other over a local network or on the Internet.</span></span>

<span data-ttu-id="41cff-117">**バインド**</span><span class="sxs-lookup"><span data-stu-id="41cff-117">**binding**</span></span>  
<span data-ttu-id="41cff-118">ソフトウェア コンポーネントとレイヤーが一緒にリンクするプロセス。</span><span class="sxs-lookup"><span data-stu-id="41cff-118">A process by which software components and layers are linked together.</span></span> <span data-ttu-id="41cff-119">ネットワーク コンポーネントがインストールされている場合は、バインドのリレーションシップと、コンポーネントの依存関係が確立されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-119">When a network component is installed, the binding relationships and dependencies for the components are established.</span></span> <span data-ttu-id="41cff-120">バインドは、互いに通信するコンポーネントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="41cff-120">Binding allows components to communicate with each other.</span></span> <span data-ttu-id="41cff-121">BizTalk server のオーケストレーション アダプターに依存しないエンドポイント (ポートまたはロールリンク) と物理アダプターに固有のエンドポイント (送信/受信ポートまたはパーティ) の間に確立したマップします。</span><span class="sxs-lookup"><span data-stu-id="41cff-121">In BizTalk Server, an established mapping between an orchestration adapter-agnostic endpoint (port or role link) and physical adapter-specific endpoints (send/receive ports or party).</span></span>

<span data-ttu-id="41cff-122">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="41cff-122">**BizTalk Server**</span></span>  
<span data-ttu-id="41cff-123">多様なソフトウェアを接続します。</span><span class="sxs-lookup"><span data-stu-id="41cff-123">Connects diverse software.</span></span> <span data-ttu-id="41cff-124">BizTalk Server には、作成し、そのソフトウェアを使用するプロセス ロジックを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="41cff-124">BizTalk Server enables you to create and modify process logic that uses that software.</span></span> <span data-ttu-id="41cff-125">BizTalk Server では、インフォメーション ワーカーの実行中のプロセスを監視、取引先との対話およびその他のビジネス指向のタスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="41cff-125">BizTalk Server also enables information workers to monitor running processes, interact with trading partners, and perform other business-oriented tasks.</span></span>

<span data-ttu-id="41cff-126">**ビジネス オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="41cff-126">**business object**</span></span>  
<span data-ttu-id="41cff-127">SAP データとオブジェクト指向モデルをプロセスにカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="41cff-127">Encapsulates SAP data and processes in an object-oriented model.</span></span> <span data-ttu-id="41cff-128">外部クライアントでは、ビジネス オブジェクトのアプリケーション インターフェイス (Bapi)、オブジェクトを操作する (およびその基になる SAP アイテム) が呼び出されるメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="41cff-128">External clients invoke methods called business object application interfaces (BAPIs) to act on the object (and its underlying SAP artifacts).</span></span> <span data-ttu-id="41cff-129">既定では、SAP アダプターは、アプリケーションを使用するビジネス オブジェクトを公開しません。</span><span class="sxs-lookup"><span data-stu-id="41cff-129">By default, the SAP adapter does not expose business objects to consuming applications.</span></span> <span data-ttu-id="41cff-130">ビジネス オブジェクトでは、クライアントの操作に使用できるのみです。</span><span class="sxs-lookup"><span data-stu-id="41cff-130">Business objects are only available for client operations.</span></span>

<span data-ttu-id="41cff-131">**ビジネス オブジェクト リポジトリ (BOR)**</span><span class="sxs-lookup"><span data-stu-id="41cff-131">**Business Object Repository (BOR)**</span></span>  
<span data-ttu-id="41cff-132">SAP ビジネス オブジェクトの種類と SAP インターフェイス型では、SAP R/3 システムに常駐 (メソッドや属性を使用)、コンポーネントのすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="41cff-132">Contains all of the SAP business object types and SAP interface types, as well as their components (such as methods and attributes), resident on the SAP R/3 system.</span></span>  
  
## <a name="c"></a><span data-ttu-id="41cff-133">c</span><span class="sxs-lookup"><span data-stu-id="41cff-133">C</span></span>  
  
<span data-ttu-id="41cff-134">**チャネル**</span><span class="sxs-lookup"><span data-stu-id="41cff-134">**channel**</span></span>  
<span data-ttu-id="41cff-135">バインド要素の具象実装です。</span><span class="sxs-lookup"><span data-stu-id="41cff-135">A concrete implementation of a binding element.</span></span> <span data-ttu-id="41cff-136">バインディングは、構成を表し、チャネルはその構成に関連付けられた実装です。</span><span class="sxs-lookup"><span data-stu-id="41cff-136">The binding represents the configuration, and the channel is the implementation associated with that configuration.</span></span> <span data-ttu-id="41cff-137">そのため、各バインド要素に関連付けられたチャネルが存在します。</span><span class="sxs-lookup"><span data-stu-id="41cff-137">Therefore, there is a channel associated with each binding element.</span></span> <span data-ttu-id="41cff-138">チャネルが積み重ねられて、バインディングの具象実装を作成する: チャネル スタック。</span><span class="sxs-lookup"><span data-stu-id="41cff-138">Channels stack on top of each other to create the concrete implementation of the binding: the channel stack.</span></span>

<span data-ttu-id="41cff-139">**コード ページ**コード ポイントのマトリックスでは基本的にします。</span><span class="sxs-lookup"><span data-stu-id="41cff-139">**code page** Essentially a matrix of code points.</span></span> <span data-ttu-id="41cff-140">文字を含む、データベースのすべてのデータは、バイト シーケンスとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-140">All data in the database, including characters, is stored as byte sequences.</span></span> <span data-ttu-id="41cff-141">文字データ、コード ページはバイトのシーケンスと、文字間のマッピングです。</span><span class="sxs-lookup"><span data-stu-id="41cff-141">For character data, a code page is the mapping between a byte sequence and a character.</span></span>

<span data-ttu-id="41cff-142">**接続 URI**</span><span class="sxs-lookup"><span data-stu-id="41cff-142">**connection URI**</span></span>  
<span data-ttu-id="41cff-143">分散環境でのリソースを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="41cff-143">A string that identifies a resource in a distributed environment.</span></span> <span data-ttu-id="41cff-144">アダプターは、Uniform Resource Identifier (URI) LOB システムとの接続を確立するために必要な情報を含む接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="41cff-144">Adapters use a connection Uniform Resource Identifier (URI) that contains the information necessary to establish a connection with the LOB system.</span></span>

<span data-ttu-id="41cff-145">**コントラクト**</span><span class="sxs-lookup"><span data-stu-id="41cff-145">**contract**</span></span>  
<span data-ttu-id="41cff-146">コレクションと、サービスによって提供される操作にアクセスするために必要なメッセージの構造を指定します。</span><span class="sxs-lookup"><span data-stu-id="41cff-146">Specifies the collection and structure of messages required to access the operations offered by the service.</span></span>
  
####  <a name="D"></a> <span data-ttu-id="41cff-147">D</span><span class="sxs-lookup"><span data-stu-id="41cff-147">D</span></span>  
  
<span data-ttu-id="41cff-148">**デザイン時のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="41cff-148">**design-time experience**</span></span>  
<span data-ttu-id="41cff-149">プロシージャと、開発者がデザイン時の中に実行する操作メッセージ スキーマを取得するのにアダプター サービスの使用 BizTalk プロジェクト アドインを使用など。</span><span class="sxs-lookup"><span data-stu-id="41cff-149">Procedures and operations that a developer performs during design time; for example, using the Consume Adapter Service BizTalk Project Add-in to retrieve message schemas.</span></span>  
  
## <a name="e"></a><span data-ttu-id="41cff-150">E</span><span class="sxs-lookup"><span data-stu-id="41cff-150">E</span></span>  
<span data-ttu-id="41cff-151">**エンドポイント アドレス**</span><span class="sxs-lookup"><span data-stu-id="41cff-151">**endpoint address**</span></span>  
<span data-ttu-id="41cff-152">Windows Communication Foundation (WCF) サービス エンドポイントの場所を識別するネットワーク アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="41cff-152">A network address that identifies the location of a Windows Communication Foundation (WCF) service endpoint.</span></span> <span data-ttu-id="41cff-153">アダプターのエンドポイント アドレスは、接続の Uniform Resource Identifier (URI) の場所と接続パラメーターを含むとして表されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-153">For an adapter, the endpoint address is expressed as a connection Uniform Resource Identifier (URI) that contains location and connection parameters.</span></span> <span data-ttu-id="41cff-154">アダプターは、基になる基幹業務 (LOB) システムへの接続を確立するためにこれらを使用できます。</span><span class="sxs-lookup"><span data-stu-id="41cff-154">The adapter can use these to establish a connection to the underlying line-of-business (LOB) system.</span></span>

<span data-ttu-id="41cff-155">**エンタープライズ シングル サインオン システム (SSO)**</span><span class="sxs-lookup"><span data-stu-id="41cff-155">**Enterprise Single Sign-on system (SSO)**</span></span>  
<span data-ttu-id="41cff-156">SSO データベースをマスター シークレット サーバー、および 1 つまたは複数のエンタープライズ シングル サインオン (SSO) サーバー。</span><span class="sxs-lookup"><span data-stu-id="41cff-156">An SSO database, a master secret server, and one or more Enterprise Single Sign-On (SSO) servers.</span></span> <span data-ttu-id="41cff-157">これらのサーバーは、Windows と Windows 以外の資格情報のマッピング、SSO データベース内の資格情報を検索、および SSO システムの管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-157">These servers do the mapping between the Windows and non-Windows credentials, look up the credentials in the SSO database, and are used for administering the SSO system.</span></span> <span data-ttu-id="41cff-158">SSO データベースは、アダプターのカスタム構成データを保持するために構成ストアとしても使用されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-158">The SSO database is also used as a configuration store to hold custom configuration data for adapters.</span></span>

<span data-ttu-id="41cff-159">**拡張マークアップ言語 (XML)**</span><span class="sxs-lookup"><span data-stu-id="41cff-159">**Extensible Markup Language (XML)**</span></span>  
<span data-ttu-id="41cff-160">データを記述するように設計するマークアップ言語。</span><span class="sxs-lookup"><span data-stu-id="41cff-160">A markup language designed to describe data.</span></span> <span data-ttu-id="41cff-161">XML タグがあらかじめ定義されていません。</span><span class="sxs-lookup"><span data-stu-id="41cff-161">XML tags are not predefined.</span></span>  
  
## <a name="f"></a><span data-ttu-id="41cff-162">F</span><span class="sxs-lookup"><span data-stu-id="41cff-162">F</span></span>  
  
<span data-ttu-id="41cff-163">**関数モジュール**</span><span class="sxs-lookup"><span data-stu-id="41cff-163">**function modules**</span></span>  
<span data-ttu-id="41cff-164">ABAP プログラムとしての SAP システムで定義されたプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="41cff-164">Procedures defined in an SAP system as ABAP programs.</span></span> <span data-ttu-id="41cff-165">これらは、関数モジュールの論理的なグループが含まれている関数グループの一部です。</span><span class="sxs-lookup"><span data-stu-id="41cff-165">These are part of function groups that contain a logical grouping of function modules.</span></span> <span data-ttu-id="41cff-166">関数モジュールには、SAP クライアントを再利用し、グローバル関数をカプセル化が有効にします。</span><span class="sxs-lookup"><span data-stu-id="41cff-166">Function modules enable SAP clients to reuse and encapsulate global functions.</span></span>
  
## <a name="g"></a><span data-ttu-id="41cff-167">G</span><span class="sxs-lookup"><span data-stu-id="41cff-167">G</span></span>  
  
<span data-ttu-id="41cff-168">**グローバル アセンブリ キャッシュ (GAC)**</span><span class="sxs-lookup"><span data-stu-id="41cff-168">**global assembly cache (GAC)**</span></span>  
<span data-ttu-id="41cff-169">コンピューター上の多数のアプリケーション間で共有するためにインストールされたアセンブリを格納するマシン全体のコード キャッシュ。</span><span class="sxs-lookup"><span data-stu-id="41cff-169">A machine-wide code cache that stores assemblies specifically installed to be shared by many applications on the computer.</span></span> <span data-ttu-id="41cff-170">グローバル アセンブリ キャッシュに配置されたアプリケーションは、厳密な名前をいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="41cff-170">Applications deployed in the global assembly cache must have a strong name.</span></span>
  
## <a name="i"></a><span data-ttu-id="41cff-171">I</span><span class="sxs-lookup"><span data-stu-id="41cff-171">I</span></span>  
  
<span data-ttu-id="41cff-172">**受信操作**</span><span class="sxs-lookup"><span data-stu-id="41cff-172">**inbound operation**</span></span>  
<span data-ttu-id="41cff-173">アダプターの基幹業務 (LOB) システムによって呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="41cff-173">An operation that is invoked by a line-of-business (LOB) system on the adapter.</span></span>
  
<span data-ttu-id="41cff-174">**中間ドキュメント (IDOC)**</span><span class="sxs-lookup"><span data-stu-id="41cff-174">**intermediate document (IDOC)**</span></span>  
<span data-ttu-id="41cff-175">R/3、R/2 SAP 以外のシステム間でデータを交換するために使用する構造化ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="41cff-175">A structured document that is used to exchange data between R/3, R/2 and non-SAP systems.</span></span>  
  
## <a name="m"></a><span data-ttu-id="41cff-176">M</span><span class="sxs-lookup"><span data-stu-id="41cff-176">M</span></span>  
  
<span data-ttu-id="41cff-177">**metadata**</span><span class="sxs-lookup"><span data-stu-id="41cff-177">**metadata**</span></span>  
<span data-ttu-id="41cff-178">WCF では、サービスによって公開されるコントラクトの説明を参照します。</span><span class="sxs-lookup"><span data-stu-id="41cff-178">In WCF, refers to a description of the contract exposed by a service.</span></span> <span data-ttu-id="41cff-179">これは、サービスの説明と呼ばれます、WSDL ドキュメントで表されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-179">This is known as the service description and is expressed in a WSDL document.</span></span> <span data-ttu-id="41cff-180">アダプターによって公開されているメタデータ (インターフェイス) の説明に、基になる基幹業務 (LOB) システムを実行できる操作。</span><span class="sxs-lookup"><span data-stu-id="41cff-180">The metadata exposed by an adapter describes the (interface to) the operations that it can perform on the underlying line-of-business (LOB) system.</span></span>

**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
<span data-ttu-id="41cff-181">使用して BizTalk アダプターを構築するための仕様では、標準の Web サービスのベースを開きます。</span><span class="sxs-lookup"><span data-stu-id="41cff-181">The specifications for building BizTalk adapters using open standards based on Web services.</span></span>  
  
## <a name="o"></a><span data-ttu-id="41cff-182">O</span><span class="sxs-lookup"><span data-stu-id="41cff-182">O</span></span>  
  
<span data-ttu-id="41cff-183">**one-way**</span><span class="sxs-lookup"><span data-stu-id="41cff-183">**one-way**</span></span>  
<span data-ttu-id="41cff-184">受信側では、メッセージが応答なしに送信します、送信側メッセージ交換パターン (MEP) が返されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-184">A message exchange pattern (MEP) in which the sender sends a message, but no response is returned by the receiver.</span></span> <span data-ttu-id="41cff-185">BizTalk Server では、Mep を通信パターンと呼びます。</span><span class="sxs-lookup"><span data-stu-id="41cff-185">In BizTalk Server, MEPs are referred to as communication patterns.</span></span>

<span data-ttu-id="41cff-186">**送信操作**</span><span class="sxs-lookup"><span data-stu-id="41cff-186">**outbound operation**</span></span>  
<span data-ttu-id="41cff-187">基幹業務 (LOB) システム上のアダプターによって呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="41cff-187">An operation that is invoked by the adapter on the line-of-business system (LOB).</span></span>
  
<span data-ttu-id="41cff-188">**output.cs**</span><span class="sxs-lookup"><span data-stu-id="41cff-188">**output.cs**</span></span>  
<span data-ttu-id="41cff-189">既定では、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) で作成されたファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="41cff-189">The default output file created by the ServiceModel Metadata Utility tool (svcutil.exe).</span></span>  
  
## <a name="p"></a><span data-ttu-id="41cff-190">P</span><span class="sxs-lookup"><span data-stu-id="41cff-190">P</span></span>  
  
<span data-ttu-id="41cff-191">**ポーリング**</span><span class="sxs-lookup"><span data-stu-id="41cff-191">**polling**</span></span>  
<span data-ttu-id="41cff-192">デバイス ドライバーを使用して複数のデバイスから送信するデータが含まれるかどうかの手法です。</span><span class="sxs-lookup"><span data-stu-id="41cff-192">A technique that device drivers use to find out from multiple devices whether they contain data to transmit.</span></span> <span data-ttu-id="41cff-193">デバイスは、ポーリングされた 1 つずつです。</span><span class="sxs-lookup"><span data-stu-id="41cff-193">The devices are polled one at a time.</span></span>

<span data-ttu-id="41cff-194">**プログラム ID**</span><span class="sxs-lookup"><span data-stu-id="41cff-194">**program ID**</span></span>  
<span data-ttu-id="41cff-195">構成済みのゲートウェイでの RFC を送信する一意のチャネル。</span><span class="sxs-lookup"><span data-stu-id="41cff-195">Unique channel to send an RFC in the configured gateway.</span></span> <span data-ttu-id="41cff-196">プログラム ID またはホスト名と、プログラム ID に指定された、SAP ゲートウェイ サービスは、(RfcAccept) を使用して、登録パラメーターと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41cff-196">The program ID or host name and the SAP gateway service, provided for the program ID, must match the registration parameters (via RfcAccept).</span></span>

<span data-ttu-id="41cff-197">**proxy**</span><span class="sxs-lookup"><span data-stu-id="41cff-197">**proxy**</span></span>  
<span data-ttu-id="41cff-198">WCF では、サービスによって公開されるサービス コントラクトを実装するマネージ コード オブジェクトを指しています。</span><span class="sxs-lookup"><span data-stu-id="41cff-198">In WCF, refers to a managed-code object that implements the service contract exposed by a service.</span></span> <span data-ttu-id="41cff-199">WCF サービス モデルは、このようなプロキシの使用に基づきます。</span><span class="sxs-lookup"><span data-stu-id="41cff-199">The WCF service model is based on the use of such proxies.</span></span> <span data-ttu-id="41cff-200">WCF サービス モデルでは、サービス コントラクトは、.NET インターフェイスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-200">In the WCF service model, the service contract is expressed as a .NET interface.</span></span>
  
## <a name="r"></a><span data-ttu-id="41cff-201">R</span><span class="sxs-lookup"><span data-stu-id="41cff-201">R</span></span>  
  
<span data-ttu-id="41cff-202">**リモート関数呼び出し (RFC)**</span><span class="sxs-lookup"><span data-stu-id="41cff-202">**Remote Function Call (RFC)**</span></span>  
<span data-ttu-id="41cff-203">クライアントとサーバー間のデータ交換のプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="41cff-203">A procedure for data exchange between a client and server.</span></span> <span data-ttu-id="41cff-204">通常、クライアントが、サーバーのプログラムを呼び出すし、サーバーは、TCP/IP 接続経由で結果を返します。</span><span class="sxs-lookup"><span data-stu-id="41cff-204">Typically the client calls a server program, and the server returns the results via a TCP/IP connection.</span></span>
  
<span data-ttu-id="41cff-205">**request-response**</span><span class="sxs-lookup"><span data-stu-id="41cff-205">**request-response**</span></span>  
<span data-ttu-id="41cff-206">メッセージ交換パターン (MEP) を送信側が要求メッセージを送信し、受信側から応答メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="41cff-206">A message exchange pattern (MEP) in which the sender sends a request message and expects a response message from the receiver.</span></span> <span data-ttu-id="41cff-207">BizTalk Server では、Mep を通信パターンと呼びます。</span><span class="sxs-lookup"><span data-stu-id="41cff-207">In BizTalk Server, MEPs are referred to as communication patterns.</span></span> <span data-ttu-id="41cff-208">によって、メッセージング テクノロジ、および要求メッセージ (受信または送信) の方向、要求/応答または送信請求-応答このパターンとも呼びます。</span><span class="sxs-lookup"><span data-stu-id="41cff-208">Depending on the messaging technology and the direction of the request message (inbound or outbound), this pattern is also called request-reply or solicit-response.</span></span>

<span data-ttu-id="41cff-209">**実行時のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="41cff-209">**run-time experience**</span></span>  
<span data-ttu-id="41cff-210">プロシージャと実行時、または、ソリューションをデプロイするときに、開発者によって実行される操作たとえば、BizTalk Server 管理コンソールから物理的なポート バインドを作成します。</span><span class="sxs-lookup"><span data-stu-id="41cff-210">Procedures and operations performed by a developer during run time or when deploying a solution; For example, creating a physical port binding from the BizTalk Server Administration console.</span></span>
  
## <a name="s"></a><span data-ttu-id="41cff-211">S</span><span class="sxs-lookup"><span data-stu-id="41cff-211">S</span></span>  
  
<span data-ttu-id="41cff-212">**schema**</span><span class="sxs-lookup"><span data-stu-id="41cff-212">**schema**</span></span>  
<span data-ttu-id="41cff-213">メッセージの構造体。</span><span class="sxs-lookup"><span data-stu-id="41cff-213">The structure for a message.</span></span> <span data-ttu-id="41cff-214">スキーマは、複数のサブスキーマを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="41cff-214">A schema can contain multiple subschema.</span></span>
  
<span data-ttu-id="41cff-215">**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)**</span><span class="sxs-lookup"><span data-stu-id="41cff-215">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span></span>  
<span data-ttu-id="41cff-216">WCF に付属するコマンド ライン ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="41cff-216">A command-line utility that is included with WCF.</span></span> <span data-ttu-id="41cff-217">アダプターなどの WCF サービスによって公開されるサービスの説明 (メタデータ) からのサービス モデルのプロキシ コードの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-217">It is used to create service model proxy code from the service description (metadata) that is exposed by a WCF service such as an adapter.</span></span> <span data-ttu-id="41cff-218">送信操作は、ツールは、WCF クライアント クラスとヘルパー コードを作成します。受信操作の場合は、ツールは、WCF サービス コントラクトとヘルパー コードを作成します。</span><span class="sxs-lookup"><span data-stu-id="41cff-218">For outbound operations, the tool creates a WCF client class and helper code; for inbound operations, the tool creates a WCF service contract and helper code.</span></span>

<span data-ttu-id="41cff-219">**SOAP (簡易オブジェクト アクセス プロトコル)**</span><span class="sxs-lookup"><span data-stu-id="41cff-219">**SOAP (Simple Object Access Protocol)**</span></span>  
<span data-ttu-id="41cff-220">交換するため、XML ベースの単純なプロトコルでは、構造化し、分散環境で情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="41cff-220">A simple, XML-based protocol for exchanging structured and type information in decentralized, distributed environments.</span></span> <span data-ttu-id="41cff-221">WCF は、SOAP メッセージには、操作を呼び出すし、結果を返すには、クライアントとサービス間の交換に基づいています。</span><span class="sxs-lookup"><span data-stu-id="41cff-221">WCF is based on the exchange of SOAP messages between clients and services to invoke operations and return results.</span></span>

<span data-ttu-id="41cff-222">**SOAP メッセージ**</span><span class="sxs-lookup"><span data-stu-id="41cff-222">**SOAP message**</span></span>  
<span data-ttu-id="41cff-223">整形式 XML ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="41cff-223">A well-formed XML document.</span></span> <span data-ttu-id="41cff-224">SOAP エンベロープと SOAP エンコーディングの名前空間を使用し、後に、SOAP エンベロープ (ルート要素) の場合は、省略可能な SOAP ヘッダーと SOAP メッセージの本文で構成されますが、省略可能な XML 宣言を含めるかする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41cff-224">It should use the SOAP envelope and SOAP encoding namespaces and include an optional XML declaration, followed by a SOAP envelope (the root element), which is made up of an optional SOAP header and a SOAP message body.</span></span>

<span data-ttu-id="41cff-225">**SQL Server Integration Services (SSIS)**</span><span class="sxs-lookup"><span data-stu-id="41cff-225">**SQL Server Integration Services (SSIS)**</span></span>  
<span data-ttu-id="41cff-226">インポート、エクスポート、およびさまざまなデータ ソースからデータを変換するために使用するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="41cff-226">A component that is used to import, export, and transform data from different data sources.</span></span> <span data-ttu-id="41cff-227">以前データ変換サービス (DTS) と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="41cff-227">Previously called data transformation service (DTS).</span></span>
  
<span data-ttu-id="41cff-228">**strongly-typed data**</span><span class="sxs-lookup"><span data-stu-id="41cff-228">**strongly-typed data**</span></span>  
<span data-ttu-id="41cff-229">データ セットまたは基になるオブジェクトの種類にバインドされている結果セット。</span><span class="sxs-lookup"><span data-stu-id="41cff-229">A data set or result set that is bound to an underlying object type.</span></span> <span data-ttu-id="41cff-230">厳密に型指定された XML データ セット内の各行で構成されます、型指定された名前付きフィールドの基になるオブジェクトの種類に対応する要素。</span><span class="sxs-lookup"><span data-stu-id="41cff-230">Each row in a strongly-typed XML data set is composed of typed, named elements that correspond to fields of the underlying object type.</span></span>

  
## <a name="t"></a><span data-ttu-id="41cff-231">T</span><span class="sxs-lookup"><span data-stu-id="41cff-231">T</span></span>  
  
<span data-ttu-id="41cff-232">**トランザクション ID (TID)**</span><span class="sxs-lookup"><span data-stu-id="41cff-232">**transaction ID (TID)**</span></span>  
<span data-ttu-id="41cff-233">作業 (LUW) の各論理ユニットで SAP を関連付けるグローバルに一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="41cff-233">A globally-unique identifier that SAP associates with each logical unit of work (LUW).</span></span>  
  
 
## <a name="w"></a><span data-ttu-id="41cff-234">W</span><span class="sxs-lookup"><span data-stu-id="41cff-234">W</span></span>  
  
<span data-ttu-id="41cff-235">**WCF チャネル モデル**</span><span class="sxs-lookup"><span data-stu-id="41cff-235">**WCF channel model**</span></span>  
<span data-ttu-id="41cff-236">複数のインターフェイスとその他の種類に依存しているプログラミング モデル。</span><span class="sxs-lookup"><span data-stu-id="41cff-236">A programming model that relies on several interfaces and other types.</span></span> <span data-ttu-id="41cff-237">チャネルでは、メッセージを送受信するための低レベル プログラミング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="41cff-237">Channels provide a low-level programming model for sending and receiving messages.</span></span>
  
<span data-ttu-id="41cff-238">**WCF クライアント**</span><span class="sxs-lookup"><span data-stu-id="41cff-238">**WCF client**</span></span>  
<span data-ttu-id="41cff-239">メソッドとして、サービス操作を公開するクライアント アプリケーション構造体。</span><span class="sxs-lookup"><span data-stu-id="41cff-239">A client-application construct that exposes the service operations as methods.</span></span> <span data-ttu-id="41cff-240">アダプターによって公開されているメタデータから WCF クライアント クラスを生成するのに、アダプター サービス参照を Visual Studio プラグインの追加や、ServiceModel メタデータ ユーティリティ ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="41cff-240">You can use the Add Adapter Service Reference Visual Studio Plug-in or the ServiceModel Metadata Utility Tool to generate a WCF client class from the metadata exposed by an adapter.</span></span>

<span data-ttu-id="41cff-241">**WCF サービス コントラクト**</span><span class="sxs-lookup"><span data-stu-id="41cff-241">**WCF service contract**</span></span>  
<span data-ttu-id="41cff-242">サービス コントラクトのマネージ コードの表現。</span><span class="sxs-lookup"><span data-stu-id="41cff-242">A managed-code representation of the service contract.</span></span> <span data-ttu-id="41cff-243">クラスおよびメソッドでは、サービス、操作、メッセージ、およびサービスと通信するために使用するデータ コントラクトを定義する属性付きインターフェイスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-243">It is expressed as an interface in which classes and methods are attributed to define the service, operation, message, and data contracts used to communicate with a service.</span></span> <span data-ttu-id="41cff-244">ServiceModel メタデータ ユーティリティ ツールまたは、Add Adapter Service Reference Visual Studio プラグインを使用すると、アダプターによって公開されているメタデータから WCF サービス コントラクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="41cff-244">You can use the ServiceModel Metadata Utility tool or the Add Adapter Service Reference Visual Studio Plug-in to generate a WCF service contract from the metadata exposed by an adapter.</span></span> <span data-ttu-id="41cff-245">LOB システムから操作を受信する WCF サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="41cff-245">You implement the WCF service contract to receive operations from an LOB system.</span></span>

<span data-ttu-id="41cff-246">**WCF サービス モデル**</span><span class="sxs-lookup"><span data-stu-id="41cff-246">**WCF service model**</span></span>  
<span data-ttu-id="41cff-247">サービスがマネージ コード オブジェクトとして表されている WCF プログラミング モデル。</span><span class="sxs-lookup"><span data-stu-id="41cff-247">A WCF programming model in which a service is represented as a managed code object.</span></span> <span data-ttu-id="41cff-248">サービスによって公開される操作は、厳密に型指定されたデータを持つメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-248">The operations exposed by the service are represented as methods with strongly-typed data.</span></span>

<span data-ttu-id="41cff-249">**厳密に型指定されたデータ**</span><span class="sxs-lookup"><span data-stu-id="41cff-249">**weakly-typed data**</span></span>  
<span data-ttu-id="41cff-250">データ セットまたは基になるオブジェクトの種類にバインドされていない結果セット。</span><span class="sxs-lookup"><span data-stu-id="41cff-250">A data set or result set that is not bound to an underlying object type.</span></span> <span data-ttu-id="41cff-251">厳密に型指定の XML データ セットの各行は、各要素の型と名前属性が記述する汎用の列のコレクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="41cff-251">Each row in a weakly-typed XML data set is composed of a collection of generic columns in which attributes describe the name and type of each element.</span></span>

<span data-ttu-id="41cff-252">**Web サービス**</span><span class="sxs-lookup"><span data-stu-id="41cff-252">**Web services**</span></span>  
<span data-ttu-id="41cff-253">他のアプリケーションにデータとサービスを提供するアプリケーション ロジックの単位。</span><span class="sxs-lookup"><span data-stu-id="41cff-253">A unit of application logic providing data and services to other applications.</span></span> <span data-ttu-id="41cff-254">アプリケーションは、標準的な Web プロトコルとデータ形式など、HTTP、XML、および、各 XML Web サービスを実装する方法の独立した SOAP を使用して XML Web サービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="41cff-254">Applications access XML Web services using standard Web protocols and data formats such as HTTP, XML, and SOAP, independent of how each XML Web service is implemented.</span></span> <span data-ttu-id="41cff-255">XML Web サービスは、コンポーネント ベースの開発の最も優れた面と、Web を組み合わせたし、は、Microsoft .NET プログラミング モデルの基礎となります。</span><span class="sxs-lookup"><span data-stu-id="41cff-255">XML Web services combine the best aspects of component-based development and the Web, and are a cornerstone of the Microsoft .NET programming model.</span></span>

<span data-ttu-id="41cff-256">**Web サービス記述言語 (WSDL)**</span><span class="sxs-lookup"><span data-stu-id="41cff-256">**Web Services Description Language (WSDL)**</span></span>  
<span data-ttu-id="41cff-257">メッセージの一連の動作をエンドポイントとしてサービスを記述する XML ベースの言語。</span><span class="sxs-lookup"><span data-stu-id="41cff-257">An XML-based language that describes a service as a set of endpoints that operate on messages.</span></span> <span data-ttu-id="41cff-258">WSDL ドキュメントは、サービス コントラクト、操作コントラクト、メッセージ コントラクト、およびデータ コントラクト、クライアントを使用する必要がありますをについて説明します。 サービスとのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="41cff-258">The WSDL document describes the service contract, operation contracts, message contracts, and data contracts that a client must use to interface with the service.</span></span>

<span data-ttu-id="41cff-259">**Windows Communication Framework (WCF)**</span><span class="sxs-lookup"><span data-stu-id="41cff-259">**Windows Communication Framework (WCF)**</span></span>  
<span data-ttu-id="41cff-260">Microsoft のサービス指向の通信インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="41cff-260">A Microsoft service-oriented communication infrastructure.</span></span> <span data-ttu-id="41cff-261">本質的に、フレームワークでは、クライアントがサービス プログラミング モデルとプログラミング モデルのメッセージ交換のより細かい制御をチャネルに提供します。</span><span class="sxs-lookup"><span data-stu-id="41cff-261">The framework inherently provides clients with a service programming model and a channel programming model for finer control of message exchanges.</span></span>

<span data-ttu-id="41cff-262">**Ws-metadata Exchange (MEX) エンドポイント**</span><span class="sxs-lookup"><span data-stu-id="41cff-262">**WS-Metadata Exchange (MEX) endpoint**</span></span>  
<span data-ttu-id="41cff-263">アダプターなどの WCF サービスによって公開されるエンドポイントを実装する、 **IMetadataExchange**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="41cff-263">An endpoint exposed by a WCF service, such as an adapter, that implements the **IMetadataExchange** interface.</span></span> <span data-ttu-id="41cff-264">ターゲット システムに、アダプターによって公開される操作のサービスの説明 (WSDL) を取得する WS メタデータ交換エンドポイントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="41cff-264">A WS-Metadata Exchange endpoint can be used to retrieve a service description (WSDL) for operations exposed by an adapter on the target system.</span></span>  
  
## <a name="x"></a><span data-ttu-id="41cff-265">x</span><span class="sxs-lookup"><span data-stu-id="41cff-265">X</span></span>  
  
<span data-ttu-id="41cff-266">**XML スキーマ定義言語 (XSD)**</span><span class="sxs-lookup"><span data-stu-id="41cff-266">**XML Schema definition language (XSD)**</span></span>  
<span data-ttu-id="41cff-267">スキーマ言語。</span><span class="sxs-lookup"><span data-stu-id="41cff-267">A schema language.</span></span> <span data-ttu-id="41cff-268">XML スキーマでは、World Wide Web Consortium (W3C) XML Schema Part 1 に準拠する要素、属性、およびデータ型を定義します。Structures Recommendation、XML スキーマ定義言語の。</span><span class="sxs-lookup"><span data-stu-id="41cff-268">An XML Schema defines the elements, attributes, and data types that comply with the World Wide Web Consortium (W3C) XML Schema Part 1: Structures Recommendation for the XML Schema Definition Language.</span></span> <span data-ttu-id="41cff-269">W3C XML Schema Part 2:Datatypes recommendation 』 は、XML スキーマで使用されるデータ型を定義するための推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="41cff-269">The W3C XML Schema Part 2: Datatypes Recommendation is the recommendation for defining data types that are used in XML schemas.</span></span> <span data-ttu-id="41cff-270">XML スキーマ定義言語では、XML メッセージの構造とデータ型を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="41cff-270">The XML Schema definition language enables you to define the structure and data types for XML messages.</span></span>