---
title: MySAP アダプターは、BizTalk の用語集 |Microsoft ドキュメント
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
ms.openlocfilehash: 976a8b885e02846e3927f55a6cf287a8f9414085
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218834"
---
# <a name="glossary"></a><span data-ttu-id="e5f4b-103">用語集</span><span class="sxs-lookup"><span data-stu-id="e5f4b-103">Glossary</span></span>
<span data-ttu-id="e5f4b-104">次の用語と定義がで使用される[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-104">The following terms and definitions are used in [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
## <a name="a"></a><span data-ttu-id="e5f4b-105">A</span><span class="sxs-lookup"><span data-stu-id="e5f4b-105">A</span></span>  
  
<span data-ttu-id="e5f4b-106">**アダプター**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-106">**adapter**</span></span>  
<span data-ttu-id="e5f4b-107">(たとえば、基幹業務システムなど) のアプリケーション間でメッセージの交換は、WCF ベースのコンポーネントと BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-107">A WCF-based component that helps exchange messages between applications (for example, a line-of-business system) and BizTalk Server.</span></span> <span data-ttu-id="e5f4b-108">送受信の操作に使用するデザイン時コンポーネントと実行時コンポーネントから構成されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-108">The adapter consists of design-time components and run-time components for receive and send operations.</span></span>

<span data-ttu-id="e5f4b-109">**アダプターのクライアント**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-109">**adapter client**</span></span>  
<span data-ttu-id="e5f4b-110">アダプターにより、基幹業務 (LOB) システムと対話するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-110">An application that interacts with a line-of-business (LOB) system through the adapter.</span></span>

<span data-ttu-id="e5f4b-111">**高度なビジネス アプリケーション (ABAP) のプログラミング**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-111">**Advanced Business Application Programming (ABAP)**</span></span>  
<span data-ttu-id="e5f4b-112">SAP のプログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-112">The SAP programming language.</span></span>  
  
## <a name="b"></a><span data-ttu-id="e5f4b-113">B</span><span class="sxs-lookup"><span data-stu-id="e5f4b-113">B</span></span>  
  
<span data-ttu-id="e5f4b-114">**Bapi (ビジネス アプリケーション プログラミング インターフェイス)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-114">**BAPIs (Business Application Programming Interfaces)**</span></span>  
<span data-ttu-id="e5f4b-115">SAP とその他のシステムの間のビジネスを交換する SAP システムによって公開される標準のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-115">Standard interfaces exposed by the SAP system to exchange business between SAP and other systems.</span></span> <span data-ttu-id="e5f4b-116">Bapi は、ローカル ネットワークまたはインターネット上に、相互に接続されている別のコンポーネントを統合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-116">BAPIs are used to integrate different components, which are connected to each other over a local network or on the Internet.</span></span>

<span data-ttu-id="e5f4b-117">**バインド**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-117">**binding**</span></span>  
<span data-ttu-id="e5f4b-118">ソフトウェアのコンポーネントとレイヤーを相互に関連付けるプロセス。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-118">A process by which software components and layers are linked together.</span></span> <span data-ttu-id="e5f4b-119">ネットワーク コンポーネントをインストールした場合、そのコンポーネントに対して、バインドのリレーションシップと依存関係が確立されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-119">When a network component is installed, the binding relationships and dependencies for the components are established.</span></span> <span data-ttu-id="e5f4b-120">バインドによって、コンポーネントの相互通信が可能となります。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-120">Binding allows components to communicate with each other.</span></span> <span data-ttu-id="e5f4b-121">BizTalk Server では、アダプターを問わないオーケストレーションのエンドポイント (ポートまたはロールリンク) と、アダプター固有の物理的なエンドポイント (送受信ポートまたはパーティ) との間に確立したマップを言います。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-121">In BizTalk Server, an established mapping between an orchestration adapter-agnostic endpoint (port or role link) and physical adapter-specific endpoints (send/receive ports or party).</span></span>

<span data-ttu-id="e5f4b-122">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-122">**BizTalk Server**</span></span>  
<span data-ttu-id="e5f4b-123">多様なソフトウェアを接続します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-123">Connects diverse software.</span></span> <span data-ttu-id="e5f4b-124">BizTalk Server を使用すると、作成し、そのソフトウェアを使用するプロセス ロジックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-124">BizTalk Server enables you to create and modify process logic that uses that software.</span></span> <span data-ttu-id="e5f4b-125">また、インフォメーション ワーカーは BizTalk Server を使用して、実行中のプロセスを監視したり、取引先と連携したり、他のビジネス志向のタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-125">BizTalk Server also enables information workers to monitor running processes, interact with trading partners, and perform other business-oriented tasks.</span></span>

<span data-ttu-id="e5f4b-126">**ビジネス オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-126">**business object**</span></span>  
<span data-ttu-id="e5f4b-127">SAP データとオブジェクト指向のモデル内のプロセスをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-127">Encapsulates SAP data and processes in an object-oriented model.</span></span> <span data-ttu-id="e5f4b-128">外部のクライアントは、ビジネス オブジェクトのアプリケーション インターフェイス オブジェクトを操作するには、(Bapi) (とその基になる SAP アイテム) で呼び出されるメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-128">External clients invoke methods called business object application interfaces (BAPIs) to act on the object (and its underlying SAP artifacts).</span></span> <span data-ttu-id="e5f4b-129">既定では、SAP アダプターは、アプリケーションを使用するビジネス オブジェクトを公開しません。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-129">By default, the SAP adapter does not expose business objects to consuming applications.</span></span> <span data-ttu-id="e5f4b-130">ビジネス オブジェクトでは、クライアント操作に使用できるのみです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-130">Business objects are only available for client operations.</span></span>

<span data-ttu-id="e5f4b-131">**ビジネス オブジェクト リポジトリ (どれ)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-131">**Business Object Repository (BOR)**</span></span>  
<span data-ttu-id="e5f4b-132">SAP ビジネス オブジェクトの種類と SAP インターフェイスの型だけでなくなどのコンポーネント (メソッド、および属性)、SAP R/3 システム上のすべてが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-132">Contains all of the SAP business object types and SAP interface types, as well as their components (such as methods and attributes), resident on the SAP R/3 system.</span></span>  
  
## <a name="c"></a><span data-ttu-id="e5f4b-133">C</span><span class="sxs-lookup"><span data-stu-id="e5f4b-133">C</span></span>  
  
<span data-ttu-id="e5f4b-134">**チャネル**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-134">**channel**</span></span>  
<span data-ttu-id="e5f4b-135">バインド要素の具象実装です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-135">A concrete implementation of a binding element.</span></span> <span data-ttu-id="e5f4b-136">バインディングは、構成を表し、チャネルがその構成に関連付けられた実装です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-136">The binding represents the configuration, and the channel is the implementation associated with that configuration.</span></span> <span data-ttu-id="e5f4b-137">したがって、各バインド要素に関連付けられているチャネルが存在します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-137">Therefore, there is a channel associated with each binding element.</span></span> <span data-ttu-id="e5f4b-138">チャネルが積み重ねられて、バインディングの具象実装を作成する: チャネル スタックです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-138">Channels stack on top of each other to create the concrete implementation of the binding: the channel stack.</span></span>

<span data-ttu-id="e5f4b-139">**コード ページ**コード ポイントのマトリックスでは基本的にします。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-139">**code page** Essentially a matrix of code points.</span></span> <span data-ttu-id="e5f4b-140">文字を含む、データベースのすべてのデータは、バイト シーケンスとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-140">All data in the database, including characters, is stored as byte sequences.</span></span> <span data-ttu-id="e5f4b-141">文字データ、コード ページは、バイトのシーケンス、および文字の間のマッピングです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-141">For character data, a code page is the mapping between a byte sequence and a character.</span></span>

<span data-ttu-id="e5f4b-142">**接続 URI**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-142">**connection URI**</span></span>  
<span data-ttu-id="e5f4b-143">分散環境でのリソースを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-143">A string that identifies a resource in a distributed environment.</span></span> <span data-ttu-id="e5f4b-144">アダプターは、Uniform Resource Identifier () を LOB システムとの接続を確立するために必要な情報を含む接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-144">Adapters use a connection Uniform Resource Identifier (URI) that contains the information necessary to establish a connection with the LOB system.</span></span>

<span data-ttu-id="e5f4b-145">**コントラクト**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-145">**contract**</span></span>  
<span data-ttu-id="e5f4b-146">コレクションと、サービスによって提供される操作へのアクセスに必要なメッセージの構造を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-146">Specifies the collection and structure of messages required to access the operations offered by the service.</span></span>
  
####  <a name="D"></a><span data-ttu-id="e5f4b-147">D</span><span class="sxs-lookup"><span data-stu-id="e5f4b-147">D</span></span>  
  
<span data-ttu-id="e5f4b-148">**デザイン時機能**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-148">**design-time experience**</span></span>  
<span data-ttu-id="e5f4b-149">プロシージャおよびデザイン時に、開発者を実行する操作たとえばを使用してアダプター サービスの使用する BizTalk プロジェクト アドイン メッセージ スキーマを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-149">Procedures and operations that a developer performs during design time; for example, using the Consume Adapter Service BizTalk Project Add-in to retrieve message schemas.</span></span>  
  
## <a name="e"></a><span data-ttu-id="e5f4b-150">E</span><span class="sxs-lookup"><span data-stu-id="e5f4b-150">E</span></span>  
<span data-ttu-id="e5f4b-151">**エンドポイント アドレス**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-151">**endpoint address**</span></span>  
<span data-ttu-id="e5f4b-152">Windows Communication Foundation (WCF) サービス エンドポイントの場所を識別するネットワーク アドレス。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-152">A network address that identifies the location of a Windows Communication Foundation (WCF) service endpoint.</span></span> <span data-ttu-id="e5f4b-153">アダプターの場合、エンドポイントのアドレスは、接続の識別子 URI (Uniform Resource) の場所と接続パラメーターを含むとして表されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-153">For an adapter, the endpoint address is expressed as a connection Uniform Resource Identifier (URI) that contains location and connection parameters.</span></span> <span data-ttu-id="e5f4b-154">アダプターは、基になる基幹業務 (LOB) システムへの接続を確立するためにこれらを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-154">The adapter can use these to establish a connection to the underlying line-of-business (LOB) system.</span></span>

<span data-ttu-id="e5f4b-155">**エンタープライズ シングル サインオン システム (SSO)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-155">**Enterprise Single Sign-on system (SSO)**</span></span>  
<span data-ttu-id="e5f4b-156">SSO データベース (1 つ)、マスター シークレット サーバー (1 つ)、およびエンタープライズ シングル サインオン (SSO) サーバー (複数可)。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-156">An SSO database, a master secret server, and one or more Enterprise Single Sign-On (SSO) servers.</span></span> <span data-ttu-id="e5f4b-157">これらのサーバーで、Windows 資格情報と Windows 以外の資格情報のマッピング、SSO データベース内の資格情報の検索、および SSO システムの管理を行います。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-157">These servers do the mapping between the Windows and non-Windows credentials, look up the credentials in the SSO database, and are used for administering the SSO system.</span></span> <span data-ttu-id="e5f4b-158">SSO データベースは、アダプターのカスタム構成データを保存する構成ストアとしても使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-158">The SSO database is also used as a configuration store to hold custom configuration data for adapters.</span></span>

<span data-ttu-id="e5f4b-159">**拡張マークアップ言語 (XML)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-159">**Extensible Markup Language (XML)**</span></span>  
<span data-ttu-id="e5f4b-160">データを記述するように設計マークアップ言語。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-160">A markup language designed to describe data.</span></span> <span data-ttu-id="e5f4b-161">XML タグがあらかじめ定義されていません。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-161">XML tags are not predefined.</span></span>  
  
## <a name="f"></a><span data-ttu-id="e5f4b-162">F</span><span class="sxs-lookup"><span data-stu-id="e5f4b-162">F</span></span>  
  
<span data-ttu-id="e5f4b-163">**関数モジュール**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-163">**function modules**</span></span>  
<span data-ttu-id="e5f4b-164">ABAP プログラムとして、SAP システムで定義されたプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-164">Procedures defined in an SAP system as ABAP programs.</span></span> <span data-ttu-id="e5f4b-165">これらは、関数モジュールの論理的なグループを含む関数のグループの一部です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-165">These are part of function groups that contain a logical grouping of function modules.</span></span> <span data-ttu-id="e5f4b-166">関数モジュールには、SAP クライアントを再利用して、グローバル関数をカプセル化が有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-166">Function modules enable SAP clients to reuse and encapsulate global functions.</span></span>
  
## <a name="g"></a><span data-ttu-id="e5f4b-167">G</span><span class="sxs-lookup"><span data-stu-id="e5f4b-167">G</span></span>  
  
<span data-ttu-id="e5f4b-168">**グローバル アセンブリ キャッシュ (GAC)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-168">**global assembly cache (GAC)**</span></span>  
<span data-ttu-id="e5f4b-169">コンピューター上の多数のアプリケーション間で共有するためにインストールされたアセンブリを格納するマシン全体のコード キャッシュ。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-169">A machine-wide code cache that stores assemblies specifically installed to be shared by many applications on the computer.</span></span> <span data-ttu-id="e5f4b-170">グローバル アセンブリ キャッシュに配置されたアプリケーションは、厳密な名前をいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-170">Applications deployed in the global assembly cache must have a strong name.</span></span>
  
## <a name="i"></a><span data-ttu-id="e5f4b-171">I</span><span class="sxs-lookup"><span data-stu-id="e5f4b-171">I</span></span>  
  
<span data-ttu-id="e5f4b-172">**受信操作**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-172">**inbound operation**</span></span>  
<span data-ttu-id="e5f4b-173">アダプターの基幹業務 (LOB) システムによって呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-173">An operation that is invoked by a line-of-business (LOB) system on the adapter.</span></span>
  
<span data-ttu-id="e5f4b-174">**中間ドキュメント (IDOC)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-174">**intermediate document (IDOC)**</span></span>  
<span data-ttu-id="e5f4b-175">R/3、R/2 および非 SAP システムの間でデータ交換に使用される構造化ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-175">A structured document that is used to exchange data between R/3, R/2 and non-SAP systems.</span></span>  
  
## <a name="m"></a><span data-ttu-id="e5f4b-176">M</span><span class="sxs-lookup"><span data-stu-id="e5f4b-176">M</span></span>  
  
<span data-ttu-id="e5f4b-177">**メタデータ**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-177">**metadata**</span></span>  
<span data-ttu-id="e5f4b-178">WCF では、サービスによって公開されるコントラクトの説明を参照します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-178">In WCF, refers to a description of the contract exposed by a service.</span></span> <span data-ttu-id="e5f4b-179">これは、サービスの説明と呼ばは WSDL ドキュメントで表現されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-179">This is known as the service description and is expressed in a WSDL document.</span></span> <span data-ttu-id="e5f4b-180">アダプターによって公開されるメタデータは、(インターフェイス) を説明します。 操作を基になるの基幹業務 (LOB) システムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-180">The metadata exposed by an adapter describes the (interface to) the operations that it can perform on the underlying line-of-business (LOB) system.</span></span>

**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
<span data-ttu-id="e5f4b-181">Web サービスに基づいたオープンな標準を使用して BizTalk アダプターを構築するための仕様です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-181">The specifications for building BizTalk adapters using open standards based on Web services.</span></span>  
  
## <a name="o"></a><span data-ttu-id="e5f4b-182">O</span><span class="sxs-lookup"><span data-stu-id="e5f4b-182">O</span></span>  
  
<span data-ttu-id="e5f4b-183">**一方向**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-183">**one-way**</span></span>  
<span data-ttu-id="e5f4b-184">送信者が、メッセージは、応答がないを送信するメッセージ交換パターン (MEP) が、受信側によって返されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-184">A message exchange pattern (MEP) in which the sender sends a message, but no response is returned by the receiver.</span></span> <span data-ttu-id="e5f4b-185">BizTalk Server では、Mep を通信パターンと呼びます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-185">In BizTalk Server, MEPs are referred to as communication patterns.</span></span>

<span data-ttu-id="e5f4b-186">**送信操作**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-186">**outbound operation**</span></span>  
<span data-ttu-id="e5f4b-187">基幹業務 (LOB) をシステム上のアダプターによって呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-187">An operation that is invoked by the adapter on the line-of-business system (LOB).</span></span>
  
<span data-ttu-id="e5f4b-188">**output.cs**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-188">**output.cs**</span></span>  
<span data-ttu-id="e5f4b-189">既定値は、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) で作成されたファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-189">The default output file created by the ServiceModel Metadata Utility tool (svcutil.exe).</span></span>  
  
## <a name="p"></a><span data-ttu-id="e5f4b-190">P</span><span class="sxs-lookup"><span data-stu-id="e5f4b-190">P</span></span>  
  
<span data-ttu-id="e5f4b-191">**ポーリング**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-191">**polling**</span></span>  
<span data-ttu-id="e5f4b-192">デバイス ドライバーを使用して複数のデバイスから送信するデータが含まれているかどうかを技法。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-192">A technique that device drivers use to find out from multiple devices whether they contain data to transmit.</span></span> <span data-ttu-id="e5f4b-193">デバイスは、ポーリングされた 1 つずつです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-193">The devices are polled one at a time.</span></span>

<span data-ttu-id="e5f4b-194">**プログラム ID**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-194">**program ID**</span></span>  
<span data-ttu-id="e5f4b-195">構成されたゲートウェイで RFC を送信する一意のチャネル。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-195">Unique channel to send an RFC in the configured gateway.</span></span> <span data-ttu-id="e5f4b-196">プログラム ID またはホスト名と指定されたプログラム ID、SAP ゲートウェイ サービスは、(RfcAccept) 経由で登録パラメーターに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-196">The program ID or host name and the SAP gateway service, provided for the program ID, must match the registration parameters (via RfcAccept).</span></span>

<span data-ttu-id="e5f4b-197">**プロキシ**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-197">**proxy**</span></span>  
<span data-ttu-id="e5f4b-198">WCF では、サービスによって公開されるサービス コントラクトを実装するマネージ コード オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-198">In WCF, refers to a managed-code object that implements the service contract exposed by a service.</span></span> <span data-ttu-id="e5f4b-199">WCF サービス モデルは、このようなプロキシの使用に基づきます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-199">The WCF service model is based on the use of such proxies.</span></span> <span data-ttu-id="e5f4b-200">WCF サービス モデルでは、サービス コントラクトは、.NET インターフェイスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-200">In the WCF service model, the service contract is expressed as a .NET interface.</span></span>
  
## <a name="r"></a><span data-ttu-id="e5f4b-201">R</span><span class="sxs-lookup"><span data-stu-id="e5f4b-201">R</span></span>  
  
<span data-ttu-id="e5f4b-202">**リモート関数呼び出し (RFC)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-202">**Remote Function Call (RFC)**</span></span>  
<span data-ttu-id="e5f4b-203">クライアントとサーバー間のデータ交換のプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-203">A procedure for data exchange between a client and server.</span></span> <span data-ttu-id="e5f4b-204">通常、クライアントが、サーバーのプログラムを呼び出すし、サーバーは、TCP/IP 接続を経由して、結果を返します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-204">Typically the client calls a server program, and the server returns the results via a TCP/IP connection.</span></span>
  
<span data-ttu-id="e5f4b-205">**要求-応答**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-205">**request-response**</span></span>  
<span data-ttu-id="e5f4b-206">メッセージ交換パターン (MEP) を送信元要求メッセージを送信し、受信側からの応答メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-206">A message exchange pattern (MEP) in which the sender sends a request message and expects a response message from the receiver.</span></span> <span data-ttu-id="e5f4b-207">BizTalk Server では、Mep を通信パターンと呼びます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-207">In BizTalk Server, MEPs are referred to as communication patterns.</span></span> <span data-ttu-id="e5f4b-208">メッセージング テクノロジとに応じて、要求メッセージ (受信または送信) の方向、要求/応答または送信請求-応答このパターンが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-208">Depending on the messaging technology and the direction of the request message (inbound or outbound), this pattern is also called request-reply or solicit-response.</span></span>

<span data-ttu-id="e5f4b-209">**実行時のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-209">**run-time experience**</span></span>  
<span data-ttu-id="e5f4b-210">プロシージャと実行時に、または、ソリューションを展開するときに、開発者が実行される操作たとえば、BizTalk Server 管理コンソールから、物理ポートのバインドを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-210">Procedures and operations performed by a developer during run time or when deploying a solution; For example, creating a physical port binding from the BizTalk Server Administration console.</span></span>
  
## <a name="s"></a><span data-ttu-id="e5f4b-211">S</span><span class="sxs-lookup"><span data-stu-id="e5f4b-211">S</span></span>  
  
<span data-ttu-id="e5f4b-212">**スキーマ**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-212">**schema**</span></span>  
<span data-ttu-id="e5f4b-213">メッセージの構造。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-213">The structure for a message.</span></span> <span data-ttu-id="e5f4b-214">スキーマには、複数のサブスキーマを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-214">A schema can contain multiple subschema.</span></span>
  
<span data-ttu-id="e5f4b-215">**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-215">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span></span>  
<span data-ttu-id="e5f4b-216">WCF に含まれているコマンド ライン ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-216">A command-line utility that is included with WCF.</span></span> <span data-ttu-id="e5f4b-217">アダプターなどの WCF サービスによって公開されるサービスの説明 (メタデータ) からサービス モデルのプロキシ コードの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-217">It is used to create service model proxy code from the service description (metadata) that is exposed by a WCF service such as an adapter.</span></span> <span data-ttu-id="e5f4b-218">送信処理は、ツールの作成、WCF クライアント クラスとヘルパー コード。受信操作は、WCF サービス コントラクトとヘルパー コードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-218">For outbound operations, the tool creates a WCF client class and helper code; for inbound operations, the tool creates a WCF service contract and helper code.</span></span>

<span data-ttu-id="e5f4b-219">**SOAP (簡易オブジェクト アクセス プロトコル)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-219">**SOAP (Simple Object Access Protocol)**</span></span>  
<span data-ttu-id="e5f4b-220">交換するため、XML ベースの単純なプロトコルでは、構造化し、分散環境で情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-220">A simple, XML-based protocol for exchanging structured and type information in decentralized, distributed environments.</span></span> <span data-ttu-id="e5f4b-221">WCF は、SOAP メッセージに操作を呼び出すし、結果を返すには、クライアントとサービス間の交換に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-221">WCF is based on the exchange of SOAP messages between clients and services to invoke operations and return results.</span></span>

<span data-ttu-id="e5f4b-222">**SOAP メッセージ**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-222">**SOAP message**</span></span>  
<span data-ttu-id="e5f4b-223">整形式 XML ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-223">A well-formed XML document.</span></span> <span data-ttu-id="e5f4b-224">SOAP エンベロープと SOAP エンコーディングの名前空間、XML 宣言 (省略可能)、実際の SOAP エンベロープ (ルート要素)、SOAP ヘッダー (省略可能) および SOAP メッセージ本文で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-224">It should use the SOAP envelope and SOAP encoding namespaces and include an optional XML declaration, followed by a SOAP envelope (the root element), which is made up of an optional SOAP header and a SOAP message body.</span></span>

<span data-ttu-id="e5f4b-225">**SQL Server Integration Services (SSIS)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-225">**SQL Server Integration Services (SSIS)**</span></span>  
<span data-ttu-id="e5f4b-226">インポート、エクスポート、およびさまざまなデータ ソースからデータを変換に使用されるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-226">A component that is used to import, export, and transform data from different data sources.</span></span> <span data-ttu-id="e5f4b-227">以前のデータ変換サービス (DTS) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-227">Previously called data transformation service (DTS).</span></span>
  
<span data-ttu-id="e5f4b-228">**厳密に型指定されたデータ**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-228">**strongly-typed data**</span></span>  
<span data-ttu-id="e5f4b-229">データ セットまたは基になるオブジェクトの種類にバインドされている結果セットです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-229">A data set or result set that is bound to an underlying object type.</span></span> <span data-ttu-id="e5f4b-230">厳密に型指定された XML データ セット内の各行で構成されます入力すると、基になるオブジェクトの種類のフィールドに対応する要素の名前します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-230">Each row in a strongly-typed XML data set is composed of typed, named elements that correspond to fields of the underlying object type.</span></span>

  
## <a name="t"></a><span data-ttu-id="e5f4b-231">T</span><span class="sxs-lookup"><span data-stu-id="e5f4b-231">T</span></span>  
  
<span data-ttu-id="e5f4b-232">**トランザクション ID (TID)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-232">**transaction ID (TID)**</span></span>  
<span data-ttu-id="e5f4b-233">SAP とを関連付ける作業 (LUW) のそれぞれの論理単位グローバルに一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-233">A globally-unique identifier that SAP associates with each logical unit of work (LUW).</span></span>  
  
 
## <a name="w"></a><span data-ttu-id="e5f4b-234">W</span><span class="sxs-lookup"><span data-stu-id="e5f4b-234">W</span></span>  
  
<span data-ttu-id="e5f4b-235">**WCF チャネル モデル**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-235">**WCF channel model**</span></span>  
<span data-ttu-id="e5f4b-236">複数のインターフェイスとその他の種類に依存しているプログラミング モデルです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-236">A programming model that relies on several interfaces and other types.</span></span> <span data-ttu-id="e5f4b-237">チャネルは、メッセージを送受信するための低レベル プログラミング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-237">Channels provide a low-level programming model for sending and receiving messages.</span></span>
  
<span data-ttu-id="e5f4b-238">**WCF クライアント**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-238">**WCF client**</span></span>  
<span data-ttu-id="e5f4b-239">メソッドとサービス操作を公開するクライアント アプリケーション構造体。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-239">A client-application construct that exposes the service operations as methods.</span></span> <span data-ttu-id="e5f4b-240">アダプターによって公開されるメタデータから WCF クライアント クラスを生成するのには、アダプター サービス参照を Visual Studio プラグインの追加または ServiceModel メタデータ ユーティリティ ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-240">You can use the Add Adapter Service Reference Visual Studio Plug-in or the ServiceModel Metadata Utility Tool to generate a WCF client class from the metadata exposed by an adapter.</span></span>

<span data-ttu-id="e5f4b-241">**WCF サービス コントラクト**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-241">**WCF service contract**</span></span>  
<span data-ttu-id="e5f4b-242">サービス コントラクトのマネージ コード表現。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-242">A managed-code representation of the service contract.</span></span> <span data-ttu-id="e5f4b-243">表されますインターフェイス クラスおよびメソッドでは、関数に起因するサービス、操作、メッセージ、およびサービスとの通信に使用されるデータ コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-243">It is expressed as an interface in which classes and methods are attributed to define the service, operation, message, and data contracts used to communicate with a service.</span></span> <span data-ttu-id="e5f4b-244">アダプターによって公開されるメタデータから WCF サービス コントラクトを生成するのには、ServiceModel メタデータ ユーティリティ ツールまたは、アダプター サービス参照を Visual Studio プラグインの追加を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-244">You can use the ServiceModel Metadata Utility tool or the Add Adapter Service Reference Visual Studio Plug-in to generate a WCF service contract from the metadata exposed by an adapter.</span></span> <span data-ttu-id="e5f4b-245">LOB システムから、操作を受信する WCF サービス コントラクトを実装するとします。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-245">You implement the WCF service contract to receive operations from an LOB system.</span></span>

<span data-ttu-id="e5f4b-246">**WCF サービスのモデル**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-246">**WCF service model**</span></span>  
<span data-ttu-id="e5f4b-247">サービスがマネージ コード オブジェクトとして表される WCF プログラミング モデルです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-247">A WCF programming model in which a service is represented as a managed code object.</span></span> <span data-ttu-id="e5f4b-248">サービスによって公開される操作は、厳密に型指定されたデータを持つメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-248">The operations exposed by the service are represented as methods with strongly-typed data.</span></span>

<span data-ttu-id="e5f4b-249">**弱い型指定のデータ**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-249">**weakly-typed data**</span></span>  
<span data-ttu-id="e5f4b-250">データ セットまたは基になるオブジェクトの種類にバインドされていない結果セットです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-250">A data set or result set that is not bound to an underlying object type.</span></span> <span data-ttu-id="e5f4b-251">弱い型指定の XML データ セット内の各行は、各要素の型と名前属性が記述される汎用の列のコレクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-251">Each row in a weakly-typed XML data set is composed of a collection of generic columns in which attributes describe the name and type of each element.</span></span>

<span data-ttu-id="e5f4b-252">**Web サービス**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-252">**Web services**</span></span>  
<span data-ttu-id="e5f4b-253">他のアプリケーションにデータやサービスを提供するアプリケーション ロジックの単位。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-253">A unit of application logic providing data and services to other applications.</span></span> <span data-ttu-id="e5f4b-254">アプリケーションは、標準的な Web プロトコルとデータ形式など、HTTP、XML、および各 XML Web サービスの実装方法に依存しない、SOAP を使用する XML Web サービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-254">Applications access XML Web services using standard Web protocols and data formats such as HTTP, XML, and SOAP, independent of how each XML Web service is implemented.</span></span> <span data-ttu-id="e5f4b-255">XML Web サービスはコンポーネント ベースの開発と Web の最も優れた面を組み合わせたもので、Microsoft .NET プログラミング モデルの中核になります。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-255">XML Web services combine the best aspects of component-based development and the Web, and are a cornerstone of the Microsoft .NET programming model.</span></span>

<span data-ttu-id="e5f4b-256">**Web サービス記述言語 (WSDL)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-256">**Web Services Description Language (WSDL)**</span></span>  
<span data-ttu-id="e5f4b-257">メッセージに対して、一連の動作をエンドポイントとしてサービスを記述する XML ベースの言語です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-257">An XML-based language that describes a service as a set of endpoints that operate on messages.</span></span> <span data-ttu-id="e5f4b-258">WSDL ドキュメントは、サービス コントラクト、操作のコントラクト、メッセージ コントラクト、およびデータ コントラクト、クライアントを使用する必要がありますをについて説明します。 サービスとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-258">The WSDL document describes the service contract, operation contracts, message contracts, and data contracts that a client must use to interface with the service.</span></span>

<span data-ttu-id="e5f4b-259">**Windows Communication Framework (WCF)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-259">**Windows Communication Framework (WCF)**</span></span>  
<span data-ttu-id="e5f4b-260">Microsoft のサービス指向の通信インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-260">A Microsoft service-oriented communication infrastructure.</span></span> <span data-ttu-id="e5f4b-261">本質的に、フレームワークは、プログラミング モデル、およびプログラミング モデルのメッセージ交換のさらに細かく制御チャネルのサービスとクライアントを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-261">The framework inherently provides clients with a service programming model and a channel programming model for finer control of message exchanges.</span></span>

<span data-ttu-id="e5f4b-262">**Ws-metadata Exchange (MEX) エンドポイント**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-262">**WS-Metadata Exchange (MEX) endpoint**</span></span>  
<span data-ttu-id="e5f4b-263">実装する、アダプターなどの WCF サービスによって公開されるエンドポイント、 **IMetadataExchange**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-263">An endpoint exposed by a WCF service, such as an adapter, that implements the **IMetadataExchange** interface.</span></span> <span data-ttu-id="e5f4b-264">WS メタデータ交換エンドポイントは、サービス記述言語 (WSDL) を取得するターゲット システムにアダプターによって公開される操作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-264">A WS-Metadata Exchange endpoint can be used to retrieve a service description (WSDL) for operations exposed by an adapter on the target system.</span></span>  
  
## <a name="x"></a><span data-ttu-id="e5f4b-265">×</span><span class="sxs-lookup"><span data-stu-id="e5f4b-265">X</span></span>  
  
<span data-ttu-id="e5f4b-266">**XML スキーマ定義言語 (XSD)**</span><span class="sxs-lookup"><span data-stu-id="e5f4b-266">**XML Schema definition language (XSD)**</span></span>  
<span data-ttu-id="e5f4b-267">スキーマ言語。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-267">A schema language.</span></span> <span data-ttu-id="e5f4b-268">World Wide Web Consortium (W3C) XML Schema Part 1 に準拠している要素、属性、およびデータ型を定義する XML スキーマ: XML スキーマ定義言語の構造の推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-268">An XML Schema defines the elements, attributes, and data types that comply with the World Wide Web Consortium (W3C) XML Schema Part 1: Structures Recommendation for the XML Schema Definition Language.</span></span> <span data-ttu-id="e5f4b-269">W3C XML Schema Part 2: Datatypes recommendation 』 は、勧告の XML スキーマで使用されるデータ型を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-269">The W3C XML Schema Part 2: Datatypes Recommendation is the recommendation for defining data types that are used in XML schemas.</span></span> <span data-ttu-id="e5f4b-270">XSD (XML Schema Definition) 言語により、XML メッセージの構造とデータ型を定義できます。</span><span class="sxs-lookup"><span data-stu-id="e5f4b-270">The XML Schema definition language enables you to define the structure and data types for XML messages.</span></span>