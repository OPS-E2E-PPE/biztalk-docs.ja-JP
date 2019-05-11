---
title: BizTalk Adapter for Oracle Database では、BizTalk の用語集 |Microsoft Docs
description: 共通の用語と定義は、BizTalk Adapter pack (BAP) での Oracle データベース アダプターによって使用されます。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d386cd36-d8e4-4e5e-806e-0d02e042344f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2a89bfcfcf387ed6451f795a9e5f83c174eca74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376527"
---
# <a name="glossary"></a><span data-ttu-id="64ba7-103">用語集</span><span class="sxs-lookup"><span data-stu-id="64ba7-103">Glossary</span></span>
<span data-ttu-id="64ba7-104">次の用語と定義がで使用される[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-104">The following terms and definitions are used in [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>    
  
## <a name="a"></a><span data-ttu-id="64ba7-105">A</span><span class="sxs-lookup"><span data-stu-id="64ba7-105">A</span></span>  
  
<span data-ttu-id="64ba7-106">**アダプター**</span><span class="sxs-lookup"><span data-stu-id="64ba7-106">**adapter**</span></span>  
<span data-ttu-id="64ba7-107">Exchange は、WCF ベースのコンポーネントがアプリケーション (基幹業務システムなど) 間でメッセージと BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="64ba7-107">A WCF-based component that helps exchange messages between applications (for example, a line-of-business system) and BizTalk Server.</span></span> <span data-ttu-id="64ba7-108">アダプターは、デザイン時コンポーネントとの受信と送信操作の実行時コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-108">The adapter consists of design-time components and run-time components for receive and send operations.</span></span>

<span data-ttu-id="64ba7-109">**アダプター クライアント**</span><span class="sxs-lookup"><span data-stu-id="64ba7-109">**adapter client**</span></span>  
<span data-ttu-id="64ba7-110">アダプターを介して基幹業務 (LOB) システムと対話するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="64ba7-110">An application that interacts with a line-of-business (LOB) system through the adapter.</span></span>  
  
## <a name="b"></a><span data-ttu-id="64ba7-111">B</span><span class="sxs-lookup"><span data-stu-id="64ba7-111">B</span></span>  
  
<span data-ttu-id="64ba7-112">**BFILE**</span><span class="sxs-lookup"><span data-stu-id="64ba7-112">**BFILE**</span></span>  
<span data-ttu-id="64ba7-113">Oracle データベースの外部のファイル システムに格納されている Lob のバイナリ ファイルにアクセスできるようにする Oracle データ型。</span><span class="sxs-lookup"><span data-stu-id="64ba7-113">An Oracle data type that enables access to binary file LOBs that are stored in file systems external to the Oracle database.</span></span> <span data-ttu-id="64ba7-114">BFILE 列は、サーバーのファイル システム上のデータを含むファイル名とディレクトリの名前を表す BFILE ロケーターを格納します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-114">A BFILE column stores a BFILE locator, which represents the directory name and file name that contains the data on the server file system.</span></span>

<span data-ttu-id="64ba7-115">**バイナリ ラージ オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="64ba7-115">**binary large object**</span></span>  
1.  <span data-ttu-id="64ba7-116">大規模なフィールドの値、予期しないテーブルのサイズ、および formless、アプリケーションの観点からはデータによって特徴付けビットマップなどのデータの大きな部分。</span><span class="sxs-lookup"><span data-stu-id="64ba7-116">A large piece of data, such as a bitmap, characterized by large field values, an unpredictable table size, and data that is formless from the perspective of an application.</span></span>
2.  <span data-ttu-id="64ba7-117">BLOB の構造を指定するキーワードには、データのブロックに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="64ba7-117">A keyword that designates the BLOB structure that contains information about a block of data.</span></span>

<span data-ttu-id="64ba7-118">**バインド**</span><span class="sxs-lookup"><span data-stu-id="64ba7-118">**binding**</span></span>  
<span data-ttu-id="64ba7-119">ソフトウェア コンポーネントとレイヤーが一緒にリンクするプロセス。</span><span class="sxs-lookup"><span data-stu-id="64ba7-119">A process by which software components and layers are linked together.</span></span> <span data-ttu-id="64ba7-120">ネットワーク コンポーネントがインストールされている場合は、バインドのリレーションシップと、コンポーネントの依存関係が確立されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-120">When a network component is installed, the binding relationships and dependencies for the components are established.</span></span> <span data-ttu-id="64ba7-121">バインドは、互いに通信するコンポーネントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-121">Binding allows components to communicate with each other.</span></span> <span data-ttu-id="64ba7-122">BizTalk server のオーケストレーション アダプターに依存しないエンドポイント (ポートまたはロールリンク) と物理アダプターに固有のエンドポイント (送信/受信ポートまたはパーティ) の間に確立したマップします。</span><span class="sxs-lookup"><span data-stu-id="64ba7-122">In BizTalk Server, an established mapping between an orchestration adapter-agnostic endpoint (port or role link) and physical adapter-specific endpoints (send/receive ports or party).</span></span>

<span data-ttu-id="64ba7-123">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="64ba7-123">**BizTalk Server**</span></span>  
<span data-ttu-id="64ba7-124">多様なソフトウェアを接続します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-124">Connects diverse software.</span></span> <span data-ttu-id="64ba7-125">BizTalk Server には、作成し、そのソフトウェアを使用するプロセス ロジックを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-125">BizTalk Server enables you to create and modify process logic that uses that software.</span></span> <span data-ttu-id="64ba7-126">BizTalk Server では、インフォメーション ワーカーの実行中のプロセスを監視、取引先との対話およびその他のビジネス指向のタスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-126">BizTalk Server also enables information workers to monitor running processes, interact with trading partners, and perform other business-oriented tasks.</span></span>
  
## <a name="c"></a><span data-ttu-id="64ba7-127">c</span><span class="sxs-lookup"><span data-stu-id="64ba7-127">C</span></span>  
  
<span data-ttu-id="64ba7-128">**チャネル**</span><span class="sxs-lookup"><span data-stu-id="64ba7-128">**channel**</span></span>  
<span data-ttu-id="64ba7-129">バインド要素の具象実装です。</span><span class="sxs-lookup"><span data-stu-id="64ba7-129">A concrete implementation of a binding element.</span></span> <span data-ttu-id="64ba7-130">バインディングは、構成を表し、チャネルはその構成に関連付けられた実装です。</span><span class="sxs-lookup"><span data-stu-id="64ba7-130">The binding represents the configuration, and the channel is the implementation associated with that configuration.</span></span> <span data-ttu-id="64ba7-131">そのため、各バインド要素に関連付けられたチャネルが存在します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-131">Therefore, there is a channel associated with each binding element.</span></span> <span data-ttu-id="64ba7-132">チャネルが積み重ねられて、バインディングの具象実装を作成する: チャネル スタック。</span><span class="sxs-lookup"><span data-stu-id="64ba7-132">Channels stack on top of each other to create the concrete implementation of the binding: the channel stack.</span></span>

<span data-ttu-id="64ba7-133">**接続 URI**</span><span class="sxs-lookup"><span data-stu-id="64ba7-133">**connection URI**</span></span>  
<span data-ttu-id="64ba7-134">分散環境でのリソースを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="64ba7-134">A string that identifies a resource in a distributed environment.</span></span> <span data-ttu-id="64ba7-135">アダプターは、Uniform Resource Identifier (URI) LOB システムとの接続を確立するために必要な情報を含む接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-135">Adapters use a connection Uniform Resource Identifier (URI) that contains the information necessary to establish a connection with the LOB system.</span></span>

<span data-ttu-id="64ba7-136">**コントラクト**</span><span class="sxs-lookup"><span data-stu-id="64ba7-136">**contract**</span></span>  
<span data-ttu-id="64ba7-137">コレクションと、サービスによって提供される操作にアクセスするために必要なメッセージの構造を指定します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-137">Specifies the collection and structure of messages required to access the operations offered by the service.</span></span>  
  
## <a name="d"></a><span data-ttu-id="64ba7-138">D</span><span class="sxs-lookup"><span data-stu-id="64ba7-138">D</span></span>  
  
<span data-ttu-id="64ba7-139">**データ操作言語 (DML)**</span><span class="sxs-lookup"><span data-stu-id="64ba7-139">**data manipulation language (DML)**</span></span>  
<span data-ttu-id="64ba7-140">データの取得と操作に使用する SQL ステートメントのサブセット。</span><span class="sxs-lookup"><span data-stu-id="64ba7-140">The subset of SQL statements that is used to retrieve and manipulate data.</span></span> <span data-ttu-id="64ba7-141">DML ステートメントは、通常、SELECT、INSERT、UPDATE、または削除を開始します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-141">DML statements typically start with SELECT, INSERT, UPDATE, or DELETE.</span></span>

<span data-ttu-id="64ba7-142">**デザイン時のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="64ba7-142">**design-time experience**</span></span>  
<span data-ttu-id="64ba7-143">プロシージャと、開発者がデザイン時の中に実行する操作メッセージ スキーマを取得するのにアダプター サービスの使用 BizTalk プロジェクト アドインを使用など。</span><span class="sxs-lookup"><span data-stu-id="64ba7-143">Procedures and operations that a developer performs during design time; for example, using the Consume Adapter Service BizTalk Project Add-in to retrieve message schemas.</span></span>  
  
## <a name="e"></a><span data-ttu-id="64ba7-144">E</span><span class="sxs-lookup"><span data-stu-id="64ba7-144">E</span></span>  
  
<span data-ttu-id="64ba7-145">**エンドポイント アドレス**</span><span class="sxs-lookup"><span data-stu-id="64ba7-145">**endpoint address**</span></span>  
<span data-ttu-id="64ba7-146">Windows Communication Foundation (WCF) サービス エンドポイントの場所を識別するネットワーク アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-146">A network address that identifies the location of a Windows Communication Foundation (WCF) service endpoint.</span></span> <span data-ttu-id="64ba7-147">アダプターのエンドポイント アドレスは、接続の Uniform Resource Identifier (URI) の場所と接続パラメーターを含むとして表されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-147">For an adapter, the endpoint address is expressed as a connection Uniform Resource Identifier (URI) that contains location and connection parameters.</span></span> <span data-ttu-id="64ba7-148">アダプターは、基になる基幹業務 (LOB) システムへの接続を確立するためにこれらを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-148">The adapter can use these to establish a connection to the underlying line-of-business (LOB) system.</span></span>

<span data-ttu-id="64ba7-149">**エンタープライズ シングル サインオン システム (SSO)**</span><span class="sxs-lookup"><span data-stu-id="64ba7-149">**Enterprise Single Sign-on system (SSO)**</span></span>  
<span data-ttu-id="64ba7-150">SSO データベースをマスター シークレット サーバー、および 1 つまたは複数のエンタープライズ シングル サインオン (SSO) サーバー。</span><span class="sxs-lookup"><span data-stu-id="64ba7-150">An SSO database, a master secret server, and one or more Enterprise Single Sign-On (SSO) servers.</span></span> <span data-ttu-id="64ba7-151">これらのサーバーは、Windows と Windows 以外の資格情報のマッピング、SSO データベース内の資格情報を検索、および SSO システムの管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-151">These servers do the mapping between the Windows and non-Windows credentials, look up the credentials in the SSO database, and are used for administering the SSO system.</span></span> <span data-ttu-id="64ba7-152">SSO データベースは、アダプターのカスタム構成データを保持するために構成ストアとしても使用されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-152">The SSO database is also used as a configuration store to hold custom configuration data for adapters.</span></span>

<span data-ttu-id="64ba7-153">**拡張マークアップ言語 (XML)**</span><span class="sxs-lookup"><span data-stu-id="64ba7-153">**Extensible Markup Language (XML)**</span></span>  
<span data-ttu-id="64ba7-154">データを記述するように設計するマークアップ言語。</span><span class="sxs-lookup"><span data-stu-id="64ba7-154">A markup language designed to describe data.</span></span> <span data-ttu-id="64ba7-155">XML タグがあらかじめ定義されていません。</span><span class="sxs-lookup"><span data-stu-id="64ba7-155">XML tags are not predefined.</span></span>  
  
## <a name="g"></a><span data-ttu-id="64ba7-156">G</span><span class="sxs-lookup"><span data-stu-id="64ba7-156">G</span></span>  
  
<span data-ttu-id="64ba7-157">**グローバル アセンブリ キャッシュ (GAC)**</span><span class="sxs-lookup"><span data-stu-id="64ba7-157">**global assembly cache (GAC)**</span></span>  
<span data-ttu-id="64ba7-158">コンピューター上の多数のアプリケーション間で共有するためにインストールされたアセンブリを格納するマシン全体のコード キャッシュ。</span><span class="sxs-lookup"><span data-stu-id="64ba7-158">A machine-wide code cache that stores assemblies specifically installed to be shared by many applications on the computer.</span></span> <span data-ttu-id="64ba7-159">グローバル アセンブリ キャッシュに配置されたアプリケーションは、厳密な名前をいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="64ba7-159">Applications deployed in the global assembly cache must have a strong name.</span></span>
  
## <a name="i"></a><span data-ttu-id="64ba7-160">I</span><span class="sxs-lookup"><span data-stu-id="64ba7-160">I</span></span>  
  
<span data-ttu-id="64ba7-161">**受信操作**</span><span class="sxs-lookup"><span data-stu-id="64ba7-161">**inbound operation**</span></span>  
<span data-ttu-id="64ba7-162">アダプターの基幹業務 (LOB) システムによって呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="64ba7-162">An operation that is invoked by a line-of-business (LOB) system on the adapter.</span></span>  
  
## <a name="l"></a><span data-ttu-id="64ba7-163">L</span><span class="sxs-lookup"><span data-stu-id="64ba7-163">L</span></span>  
  
<span data-ttu-id="64ba7-164">**ローカルの名前付けメソッド**</span><span class="sxs-lookup"><span data-stu-id="64ba7-164">**local naming method**</span></span>  
<span data-ttu-id="64ba7-165">Oracle の Oracle データベース アダプターでサポートされているメソッドの名前を付けします。</span><span class="sxs-lookup"><span data-stu-id="64ba7-165">The Oracle naming method that is supported by the Oracle Database adapter.</span></span> <span data-ttu-id="64ba7-166">この名前付けの方法では、Oracle クライアントは、ローカルの tnsnames.ora ファイル内のエントリに net サービス名を解決します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-166">In this naming method, the Oracle client resolves the net service name to an entry in the local tnsnames.ora file.</span></span>  
  
## <a name="m"></a><span data-ttu-id="64ba7-167">M</span><span class="sxs-lookup"><span data-stu-id="64ba7-167">M</span></span>  
  
<span data-ttu-id="64ba7-168">**metadata**</span><span class="sxs-lookup"><span data-stu-id="64ba7-168">**metadata**</span></span>  
<span data-ttu-id="64ba7-169">WCF では、サービスによって公開されるコントラクトの説明を参照します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-169">In WCF, refers to a description of the contract exposed by a service.</span></span> <span data-ttu-id="64ba7-170">これは、サービスの説明と呼ばれます、WSDL ドキュメントで表されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-170">This is known as the service description and is expressed in a WSDL document.</span></span> <span data-ttu-id="64ba7-171">アダプターによって公開されているメタデータ (インターフェイス) の説明に、基になる LOB システムを実行できる操作。</span><span class="sxs-lookup"><span data-stu-id="64ba7-171">The metadata exposed by an adapter describes the (interface to) the operations that it can perform on the underlying LOB system.</span></span>

**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
<span data-ttu-id="64ba7-172">使用して BizTalk アダプターを構築するための仕様では、標準の Web サービスのベースを開きます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-172">The specifications for building BizTalk adapters using open standards based on Web services.</span></span>  
  
## <a name="n"></a><span data-ttu-id="64ba7-173">N</span><span class="sxs-lookup"><span data-stu-id="64ba7-173">N</span></span>  
  
<span data-ttu-id="64ba7-174">**名前付けメソッド**</span><span class="sxs-lookup"><span data-stu-id="64ba7-174">**naming method**</span></span>  
<span data-ttu-id="64ba7-175">Oracle の名前付け方法は、Oracle クライアントが Oracle database service (インスタンス) の接続情報を取得する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-175">Oracle naming methods determine how the Oracle client obtains connection information for an Oracle database service (instance).</span></span> <span data-ttu-id="64ba7-176">Oracle Net Configuration Assistant を使用して特定の名前付け方法を使用する Oracle クライアントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-176">You can configure the Oracle client to use specific naming methods by using the Oracle Net Configuration Assistant.</span></span> <span data-ttu-id="64ba7-177">Oracle データベース アダプターには、ローカルの名前付け方法がサポートしています。</span><span class="sxs-lookup"><span data-stu-id="64ba7-177">The Oracle Database adapter supports the Local Naming method.</span></span>

<span data-ttu-id="64ba7-178">**net サービス名**</span><span class="sxs-lookup"><span data-stu-id="64ba7-178">**net service name**</span></span>  
<span data-ttu-id="64ba7-179">Oracle データベースの接続情報を取得する、Oracle クライアントによって使用される別名です。</span><span class="sxs-lookup"><span data-stu-id="64ba7-179">An alias used by the Oracle client to obtain connection information for the Oracle database.</span></span> <span data-ttu-id="64ba7-180">接続 URI の接続文字列プロパティの 1 つとして net サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-180">You supply a net service name as one of the connection properties in the connection URI.</span></span>  
  
## <a name="o"></a><span data-ttu-id="64ba7-181">O</span><span class="sxs-lookup"><span data-stu-id="64ba7-181">O</span></span>  
  
<span data-ttu-id="64ba7-182">**one-way**</span><span class="sxs-lookup"><span data-stu-id="64ba7-182">**one-way**</span></span>  
<span data-ttu-id="64ba7-183">受信側では、メッセージが応答なしに送信します、送信側メッセージ交換パターン (MEP) が返されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-183">A message exchange pattern (MEP) in which the sender sends a message, but no response is returned by the receiver.</span></span> <span data-ttu-id="64ba7-184">BizTalk Server では、Mep を通信パターンと呼びます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-184">In BizTalk Server, MEPs are referred to as communication patterns.</span></span>

<span data-ttu-id="64ba7-185">**送信操作**</span><span class="sxs-lookup"><span data-stu-id="64ba7-185">**outbound operation**</span></span>  
<span data-ttu-id="64ba7-186">基幹業務 (LOB) システム上のアダプターによって呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="64ba7-186">An operation that is invoked by the adapter on the line-of-business system (LOB).</span></span>

<span data-ttu-id="64ba7-187">**output.cs**</span><span class="sxs-lookup"><span data-stu-id="64ba7-187">**output.cs**</span></span>  
<span data-ttu-id="64ba7-188">既定では、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) で作成されたファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-188">The default output file created by the ServiceModel Metadata Utility tool (svcutil.exe).</span></span>  
  
## <a name="p"></a><span data-ttu-id="64ba7-189">P</span><span class="sxs-lookup"><span data-stu-id="64ba7-189">P</span></span>  
  
<span data-ttu-id="64ba7-190">**ポーリング**</span><span class="sxs-lookup"><span data-stu-id="64ba7-190">**polling**</span></span>  
<span data-ttu-id="64ba7-191">デバイス ドライバーを使用して複数のデバイスから送信するデータが含まれるかどうかの手法です。</span><span class="sxs-lookup"><span data-stu-id="64ba7-191">A technique that device drivers use to find out from multiple devices whether they contain data to transmit.</span></span> <span data-ttu-id="64ba7-192">デバイスは、ポーリングされた 1 つずつです。</span><span class="sxs-lookup"><span data-stu-id="64ba7-192">The devices are polled one at a time.</span></span>

<span data-ttu-id="64ba7-193">**proxy**</span><span class="sxs-lookup"><span data-stu-id="64ba7-193">**proxy**</span></span>  
<span data-ttu-id="64ba7-194">WCF では、サービスによって公開されるサービス コントラクトを実装するマネージ コード オブジェクトを指しています。</span><span class="sxs-lookup"><span data-stu-id="64ba7-194">In WCF, refers to a managed-code object that implements the service contract exposed by a service.</span></span> <span data-ttu-id="64ba7-195">WCF サービス モデルは、このようなプロキシの使用に基づきます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-195">The WCF service model is based on the use of such proxies.</span></span> <span data-ttu-id="64ba7-196">WCF サービス モデルでは、サービス コントラクトは、.NET インターフェイスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-196">In the WCF service model, the service contract is expressed as a .NET interface.</span></span>
  
## <a name="r"></a><span data-ttu-id="64ba7-197">R</span><span class="sxs-lookup"><span data-stu-id="64ba7-197">R</span></span>  
  
<span data-ttu-id="64ba7-198">**REF CURSOR**</span><span class="sxs-lookup"><span data-stu-id="64ba7-198">**REF CURSOR**</span></span>  
<span data-ttu-id="64ba7-199">PL/SQL の Oracle データ型の結果セットで、Oracle データベースへのポインターを表します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-199">An Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="64ba7-200">REF CURSOR 型では、入力と出力のデータのストリーミングを有効し、は、大量のデータとの間の PL/SQL コード ブロックを転送するために最適です。</span><span class="sxs-lookup"><span data-stu-id="64ba7-200">A REF CURSOR type enables input and output streaming of data, and is ideal for transferring large amounts of data to and from a PL/SQL code block.</span></span>

<span data-ttu-id="64ba7-201">**request-response**</span><span class="sxs-lookup"><span data-stu-id="64ba7-201">**request-response**</span></span>  
<span data-ttu-id="64ba7-202">メッセージ交換パターン (MEP) を送信側が要求メッセージを送信し、受信側から応答メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="64ba7-202">A message exchange pattern (MEP) in which the sender sends a request message and expects a response message from the receiver.</span></span> <span data-ttu-id="64ba7-203">BizTalk Server では、Mep を通信パターンと呼びます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-203">In BizTalk Server, MEPs are referred to as communication patterns.</span></span> <span data-ttu-id="64ba7-204">によって、メッセージング テクノロジ、および要求メッセージ (受信または送信) の方向、要求/応答または送信請求-応答このパターンとも呼びます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-204">Depending on the messaging technology and the direction of the request message (inbound or outbound), this pattern is also called request-reply or solicit-response.</span></span>

<span data-ttu-id="64ba7-205">**実行時のエクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="64ba7-205">**run-time experience**</span></span>  
<span data-ttu-id="64ba7-206">プロシージャと実行時、または、ソリューションをデプロイするときに、開発者によって実行される操作たとえば、BizTalk Server 管理コンソールから物理的なポート バインドを作成します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-206">Procedures and operations performed by a developer during run time or when deploying a solution; for example, creating a physical port binding from the BizTalk Server Administration console.</span></span>  
  
## <a name="s"></a><span data-ttu-id="64ba7-207">S</span><span class="sxs-lookup"><span data-stu-id="64ba7-207">S</span></span>  
  
<span data-ttu-id="64ba7-208">**schema**</span><span class="sxs-lookup"><span data-stu-id="64ba7-208">**schema**</span></span>  
<span data-ttu-id="64ba7-209">メッセージの構造体。</span><span class="sxs-lookup"><span data-stu-id="64ba7-209">The structure for a message.</span></span> <span data-ttu-id="64ba7-210">スキーマは、複数のサブスキーマを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-210">A schema can contain multiple subschema.</span></span>

<span data-ttu-id="64ba7-211">**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)**</span><span class="sxs-lookup"><span data-stu-id="64ba7-211">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span></span>  
<span data-ttu-id="64ba7-212">WCF に付属するコマンド ライン ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="64ba7-212">A command-line utility that is included with WCF.</span></span> <span data-ttu-id="64ba7-213">アダプターなどの WCF サービスによって公開されるサービスの説明 (メタデータ) からのサービス モデルのプロキシ コードの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-213">It is used to create service model proxy code from the service description (metadata) that is exposed by a WCF service such as an adapter.</span></span> <span data-ttu-id="64ba7-214">送信操作は、ツールは、WCF クライアント クラスとヘルパー コードを作成します。受信操作の場合は、ツールは、WCF サービス コントラクトとヘルパー コードを作成します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-214">For outbound operations, the tool creates a WCF client class and helper code; for inbound operations, the tool creates a WCF service contract and helper code.</span></span>

<span data-ttu-id="64ba7-215">**SOAP (簡易オブジェクト アクセス プロトコル)**</span><span class="sxs-lookup"><span data-stu-id="64ba7-215">**SOAP (Simple Object Access Protocol)**</span></span>  
<span data-ttu-id="64ba7-216">交換するため、XML ベースの単純なプロトコルでは、構造化し、分散環境で情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-216">A simple, XML-based protocol for exchanging structured and type information in decentralized, distributed environments.</span></span> <span data-ttu-id="64ba7-217">WCF は、SOAP メッセージには、操作を呼び出すし、結果を返すには、クライアントとサービス間の交換に基づいています。</span><span class="sxs-lookup"><span data-stu-id="64ba7-217">WCF is based on the exchange of SOAP messages between clients and services to invoke operations and return results.</span></span>

<span data-ttu-id="64ba7-218">**SOAP メッセージ**</span><span class="sxs-lookup"><span data-stu-id="64ba7-218">**SOAP message**</span></span>  
<span data-ttu-id="64ba7-219">整形式 XML ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="64ba7-219">A well-formed XML document.</span></span> <span data-ttu-id="64ba7-220">SOAP エンベロープと SOAP エンコーディングの名前空間を使用し、後に、SOAP エンベロープ (ルート要素) の場合は、省略可能な SOAP ヘッダーと SOAP メッセージの本文で構成されますが、省略可能な XML 宣言を含めるかする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64ba7-220">It should use the SOAP envelope and SOAP encoding namespaces and include an optional XML declaration, followed by a SOAP envelope (the root element), which is made up of an optional SOAP header and a SOAP message body.</span></span>

<span data-ttu-id="64ba7-221">**SQL Server Integration Services (SSIS)**</span><span class="sxs-lookup"><span data-stu-id="64ba7-221">**SQL Server Integration Services (SSIS)**</span></span>  
<span data-ttu-id="64ba7-222">インポート、エクスポート、およびさまざまなデータ ソースからデータを変換するために使用するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="64ba7-222">A component that is used to import, export, and transform data from different data sources.</span></span> <span data-ttu-id="64ba7-223">以前データ変換サービス (DTS) と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="64ba7-223">Previously called data transformation service (DTS).</span></span>

<span data-ttu-id="64ba7-224">**strongly-typed data**</span><span class="sxs-lookup"><span data-stu-id="64ba7-224">**strongly-typed data**</span></span>  
<span data-ttu-id="64ba7-225">データ セットまたは基になるオブジェクトの種類にバインドされている結果セット。</span><span class="sxs-lookup"><span data-stu-id="64ba7-225">A data set or result set that is bound to an underlying object type.</span></span> <span data-ttu-id="64ba7-226">厳密に型指定された XML データ セット内の各行で構成されます、型指定された名前付きフィールドの基になるオブジェクトの種類に対応する要素。</span><span class="sxs-lookup"><span data-stu-id="64ba7-226">Each row in a strongly-typed XML data set is composed of typed, named elements that correspond to fields of the underlying object type.</span></span>  
 
## <a name="w"></a><span data-ttu-id="64ba7-227">W</span><span class="sxs-lookup"><span data-stu-id="64ba7-227">W</span></span>  
<span data-ttu-id="64ba7-228">**WCF チャネル モデル**</span><span class="sxs-lookup"><span data-stu-id="64ba7-228">**WCF channel model**</span></span>  
<span data-ttu-id="64ba7-229">複数のインターフェイスとその他の種類に依存しているプログラミング モデル。</span><span class="sxs-lookup"><span data-stu-id="64ba7-229">A programming model that relies on several interfaces and other types.</span></span> <span data-ttu-id="64ba7-230">チャネルでは、メッセージを送受信するための低レベル プログラミング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-230">Channels provide a low-level programming model for sending and receiving messages.</span></span>

<span data-ttu-id="64ba7-231">**WCF クライアント**</span><span class="sxs-lookup"><span data-stu-id="64ba7-231">**WCF client**</span></span>  
<span data-ttu-id="64ba7-232">メソッドとして、サービス操作を公開するクライアント アプリケーション構造体。</span><span class="sxs-lookup"><span data-stu-id="64ba7-232">A client-application construct that exposes the service operations as methods.</span></span> <span data-ttu-id="64ba7-233">アダプターによって公開されているメタデータから WCF クライアント クラスを生成するのに、アダプター サービス参照を Visual Studio プラグインの追加や、ServiceModel メタデータ ユーティリティ ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-233">You can use the Add Adapter Service Reference Visual Studio Plug-in or the ServiceModel Metadata Utility Tool to generate a WCF client class from the metadata exposed by an adapter.</span></span>

<span data-ttu-id="64ba7-234">**WCF サービス コントラクト**</span><span class="sxs-lookup"><span data-stu-id="64ba7-234">**WCF service contract**</span></span>  
<span data-ttu-id="64ba7-235">サービス コントラクトのマネージ コードの表現。</span><span class="sxs-lookup"><span data-stu-id="64ba7-235">A managed-code representation of the service contract.</span></span> <span data-ttu-id="64ba7-236">クラスおよびメソッドでは、サービス、操作、メッセージ、およびサービスと通信するために使用するデータ コントラクトを定義する属性付きインターフェイスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-236">It is expressed as an interface in which classes and methods are attributed to define the service, operation, message, and data contracts used to communicate with a service.</span></span> <span data-ttu-id="64ba7-237">ServiceModel メタデータ ユーティリティ ツールまたは、Add Adapter Service Reference Visual Studio プラグインを使用すると、アダプターによって公開されているメタデータから WCF サービス コントラクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-237">You can use the ServiceModel Metadata Utility tool or the Add Adapter Service Reference Visual Studio Plug-in to generate a WCF service contract from the metadata exposed by an adapter.</span></span> <span data-ttu-id="64ba7-238">LOB システムから操作を受信する WCF サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-238">You implement the WCF service contract to receive operations from an LOB system.</span></span>

<span data-ttu-id="64ba7-239">**WCF サービス モデル**</span><span class="sxs-lookup"><span data-stu-id="64ba7-239">**WCF service model**</span></span>  
<span data-ttu-id="64ba7-240">サービスがマネージ コード オブジェクトとして表されている WCF プログラミング モデル。</span><span class="sxs-lookup"><span data-stu-id="64ba7-240">A WCF programming model in which a service is represented as a managed code object.</span></span> <span data-ttu-id="64ba7-241">サービスによって公開される操作は、厳密に型指定されたデータを持つメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-241">The operations exposed by the service are represented as methods with strongly-typed data.</span></span>

<span data-ttu-id="64ba7-242">**厳密に型指定されたデータ**</span><span class="sxs-lookup"><span data-stu-id="64ba7-242">**weakly-typed data**</span></span>  
<span data-ttu-id="64ba7-243">データ セットまたは基になるオブジェクトの種類にバインドされていない結果セット。</span><span class="sxs-lookup"><span data-stu-id="64ba7-243">A data set or result set that is not bound to an underlying object type.</span></span> <span data-ttu-id="64ba7-244">厳密に型指定の XML データ セットの各行は、各要素の型と名前属性が記述する汎用の列のコレクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-244">Each row in a weakly-typed XML data set is composed of a collection of generic columns in which attributes describe the name and type of each element.</span></span>

<span data-ttu-id="64ba7-245">**Web サービス**</span><span class="sxs-lookup"><span data-stu-id="64ba7-245">**Web services**</span></span>  
<span data-ttu-id="64ba7-246">他のアプリケーションにデータとサービスを提供するアプリケーション ロジックの単位。</span><span class="sxs-lookup"><span data-stu-id="64ba7-246">A unit of application logic providing data and services to other applications.</span></span> <span data-ttu-id="64ba7-247">アプリケーションは、標準的な Web プロトコルとデータ形式など、HTTP、XML、および、各 XML Web サービスを実装する方法の独立した SOAP を使用して XML Web サービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="64ba7-247">Applications access XML Web services using standard Web protocols and data formats such as HTTP, XML, and SOAP, independent of how each XML Web service is implemented.</span></span> <span data-ttu-id="64ba7-248">XML Web サービスは、コンポーネント ベースの開発の最も優れた面と、Web を組み合わせたし、は、Microsoft .NET プログラミング モデルの基礎となります。</span><span class="sxs-lookup"><span data-stu-id="64ba7-248">XML Web services combine the best aspects of component-based development and the Web, and are a cornerstone of the Microsoft .NET programming model.</span></span>

<span data-ttu-id="64ba7-249">**Web サービス記述言語 (WSDL)**</span><span class="sxs-lookup"><span data-stu-id="64ba7-249">**Web Services Description Language (WSDL)**</span></span>  
<span data-ttu-id="64ba7-250">メッセージの一連の動作をエンドポイントとしてサービスを記述する XML ベースの言語。</span><span class="sxs-lookup"><span data-stu-id="64ba7-250">An XML-based language that describes a service as a set of endpoints that operate on messages.</span></span> <span data-ttu-id="64ba7-251">WSDL ドキュメントは、サービス コントラクト、操作コントラクト、メッセージ コントラクト、およびデータ コントラクト、クライアントを使用する必要がありますをについて説明します。 サービスとのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="64ba7-251">The WSDL document describes the service contract, operation contracts, message contracts, and data contracts that a client must use to interface with the service.</span></span>

<span data-ttu-id="64ba7-252">**Windows Communication Foundation (WCF)**</span><span class="sxs-lookup"><span data-stu-id="64ba7-252">**Windows Communication Foundation (WCF)**</span></span>  
<span data-ttu-id="64ba7-253">Microsoft のサービス指向の通信インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="64ba7-253">A Microsoft service-oriented communication infrastructure.</span></span> <span data-ttu-id="64ba7-254">本質的に、フレームワークでは、クライアントがサービス プログラミング モデルとプログラミング モデルのメッセージ交換のより細かい制御をチャネルに提供します。</span><span class="sxs-lookup"><span data-stu-id="64ba7-254">The framework inherently provides clients with a service programming model and a channel programming model for finer control of message exchanges.</span></span>

<span data-ttu-id="64ba7-255">**Ws-metadata Exchange (MEX) エンドポイント**</span><span class="sxs-lookup"><span data-stu-id="64ba7-255">**WS-Metadata Exchange (MEX) endpoint**</span></span>  
<span data-ttu-id="64ba7-256">アダプターなどの WCF サービスによって公開されるエンドポイントを実装する、 **IMetadataExchange**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="64ba7-256">An endpoint exposed by a WCF service, such as an adapter, that implements the **IMetadataExchange** interface.</span></span> <span data-ttu-id="64ba7-257">ターゲット システムに、アダプターによって公開される操作のサービスの説明 (WSDL) を取得する WS メタデータ交換エンドポイントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-257">A WS-Metadata Exchange endpoint can be used to retrieve a service description (WSDL) for operations exposed by an adapter on the target system.</span></span>
  
## <a name="x"></a><span data-ttu-id="64ba7-258">x</span><span class="sxs-lookup"><span data-stu-id="64ba7-258">X</span></span>  
  
<span data-ttu-id="64ba7-259">**XML スキーマ定義言語 (XSD)**</span><span class="sxs-lookup"><span data-stu-id="64ba7-259">**XML Schema definition language (XSD)**</span></span>  
<span data-ttu-id="64ba7-260">スキーマ言語。</span><span class="sxs-lookup"><span data-stu-id="64ba7-260">A schema language.</span></span> <span data-ttu-id="64ba7-261">XML スキーマでは、World Wide Web Consortium (W3C) XML Schema Part 1 に準拠する要素、属性、およびデータ型を定義します。Structures Recommendation、XML スキーマ定義言語の。</span><span class="sxs-lookup"><span data-stu-id="64ba7-261">An XML Schema defines the elements, attributes, and data types that comply with the World Wide Web Consortium (W3C) XML Schema Part 1: Structures Recommendation for the XML Schema Definition Language.</span></span> <span data-ttu-id="64ba7-262">W3C XML Schema Part 2:Datatypes recommendation 』 は、XML スキーマで使用されるデータ型を定義するための推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="64ba7-262">The W3C XML Schema Part 2: Datatypes Recommendation is the recommendation for defining data types that are used in XML schemas.</span></span> <span data-ttu-id="64ba7-263">XML スキーマ定義言語では、XML メッセージの構造とデータ型を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="64ba7-263">The XML Schema definition language enables you to define the structure and data types for XML messages.</span></span>