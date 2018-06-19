---
title: アダプター コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 383e8bcb-2b4d-40f9-9e98-f49e8d6f30f7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2a5f2a78a9ea555d22f585c0aa50eda65b6c287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225330"
---
# <a name="adapter-components"></a><span data-ttu-id="43cdf-102">アダプター コンポーネント</span><span class="sxs-lookup"><span data-stu-id="43cdf-102">Adapter Components</span></span>
<span data-ttu-id="43cdf-103">カスタム アダプターは、ネイティブ アダプターで使用される標準化された構成、管理、および設定のメカニズムを共有します。</span><span class="sxs-lookup"><span data-stu-id="43cdf-103">A custom adapter shares the standardized configuration, management, and setup mechanisms used by the native adapters.</span></span> <span data-ttu-id="43cdf-104">アダプター フレームワークが標準化されているため、カスタム アダプターは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで管理されます。</span><span class="sxs-lookup"><span data-stu-id="43cdf-104">With the standardization to the Adapter Framework, a custom adapter is managed by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="43cdf-105">次の図は、カスタム アダプターの主要なコンポーネントを示しています。 アダプターのレジストリ ファイル、アダプターのデザイン時コンポーネントとアダプターの実行時コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="43cdf-105">The following figure shows the main components of a custom adapter: the adapter registry file, the adapter design-time component, and the adapter run-time component.</span></span>  
  
 ![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")  
  
## <a name="adapter-registry-file"></a><span data-ttu-id="43cdf-106">アダプターのレジストリ ファイル</span><span class="sxs-lookup"><span data-stu-id="43cdf-106">Adapter Registry File</span></span>  
 <span data-ttu-id="43cdf-107">アダプターに関する特定の情報は、レジストリおよび BizTalk 管理データベースに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43cdf-107">Certain information about adapters must be registered in the registry and the BizTalk Management database.</span></span> <span data-ttu-id="43cdf-108">アダプターのエイリアス、受信ハンドラー、受信場所、トランスポートの種類などの情報はメタデータと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="43cdf-108">Information such as an adapter's alias, receive hander, receive location, and transport type is called metadata.</span></span> <span data-ttu-id="43cdf-109">これらのメタデータ エントリは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して手動でアダプターを登録する際に作成されます。</span><span class="sxs-lookup"><span data-stu-id="43cdf-109">These metadata entries are created during manual adapter registration using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="43cdf-110">代わりに、カスタム アダプターのレジストリ ファイルを生成するアダプター レジストリ ウィザード (AdapterRegistryWizard.exe) の SDK ユーティリティを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="43cdf-110">Alternatively, you can run the Adapter Registry Wizard (AdapterRegistryWizard.exe) SDK utility to generate a registry file for your custom adapter.</span></span> <span data-ttu-id="43cdf-111">このレジストリ ファイルをダブルクリックするかをクリックすると**インポート**上、**ファイル**] メニューの [レジストリ エディター (regedit32.exe) を使用して、メタデータをレジストリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="43cdf-111">Double-clicking this registry file or clicking **Import** on the **File** menu using the registry editor (regedit32.exe) writes the metadata into the registry.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43cdf-112">このレジストリ ファイルを実行しても、アダプター情報は BizTalk 管理データベースに追加されません。</span><span class="sxs-lookup"><span data-stu-id="43cdf-112">Running this registry file does not add adapter information to the BizTalk Management database.</span></span> <span data-ttu-id="43cdf-113">アダプター情報の追加は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して手動で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="43cdf-113">You must do this manually by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="design-time-component"></a><span data-ttu-id="43cdf-114">デザイン時コンポーネント</span><span class="sxs-lookup"><span data-stu-id="43cdf-114">Design-Time Component</span></span>  
 <span data-ttu-id="43cdf-115">カスタム アダプターのユーザー インターフェイス (UI) を実装するには、アダプター フレームワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="43cdf-115">The user interface (UI) for a custom adapter is implemented by using the Adapter Framework.</span></span> <span data-ttu-id="43cdf-116">UI は、アダプターのアセンブリの一部として提供される XML スキーマから表示されます。したがって、この方法を使用すると UI を効率的に開発できます。</span><span class="sxs-lookup"><span data-stu-id="43cdf-116">This is a productive approach to UI development because the UI is rendered from an XML schema provided as part of the adapter's assembly.</span></span> <span data-ttu-id="43cdf-117">少量のコードでスキーマのコンテンツを UI に変換し、アダプターのプロパティを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="43cdf-117">A small amount of code is required to transform the contents of the schema into a UI to configure the adapter's properties.</span></span>  
  
 <span data-ttu-id="43cdf-118">SQL アダプターなどのアプリケーション アダプターと通信する必要があるオーケストレーションの場合は、アダプター メタデータの追加ウィザードを使用して、スキーマ、メッセージの種類、ポートの種類などのアダプター メタデータを BizTalk プロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="43cdf-118">For an orchestration needing to communicate with an application adapter such as the SQL adapter, the Add Adapter Metadata Wizard enables you to add adapter metadata, such as schemas, message types, and port types, to a BizTalk project.</span></span> <span data-ttu-id="43cdf-119">アプリケーション アダプターのアダプター メタデータの追加ウィザードを使用して、対応するスキーマをシステムに組み込みます。</span><span class="sxs-lookup"><span data-stu-id="43cdf-119">Use the Add Adapter Metadata Wizard with application adapters to pull corresponding schemas into the system.</span></span> <span data-ttu-id="43cdf-120">(非アダプター) を BizTalk プロジェクト内からこのウィザードを起動するには、プロジェクトを右クリックし、順にポイント**生成した項目の追加**、 をクリックして**アダプター メタデータの追加**およびの一覧から選択が登録されます。アダプター メタデータをインポートするアダプター。</span><span class="sxs-lookup"><span data-stu-id="43cdf-120">To invoke this wizard from within a BizTalk (non-adapter) project, right-click the project, point to **Add Generated Items**, click **Add Adapter Metadata** and then select from the list of registered adapters to import the adapter metadata.</span></span>  
  
## <a name="run-time-component"></a><span data-ttu-id="43cdf-121">実行時コンポーネント</span><span class="sxs-lookup"><span data-stu-id="43cdf-121">Run-Time Component</span></span>  
 <span data-ttu-id="43cdf-122">通常、アダプターが 2 つのパブリック実行時コンポーネントで構成されます。 メッセージの受信者と、メッセージの送信者を実装するコンポーネントを実装するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="43cdf-122">Typically an adapter consists of two public run-time components: the component that implements the message receiver and the component that implements the message sender.</span></span> <span data-ttu-id="43cdf-123">これらのコンポーネントは、同一のアセンブリまたは 2 つの異なるアセンブリに展開できます。</span><span class="sxs-lookup"><span data-stu-id="43cdf-123">These components may be deployed in the same assembly or in two different assemblies.</span></span>  
  
#### <a name="receive-adapter"></a><span data-ttu-id="43cdf-124">受信アダプター</span><span class="sxs-lookup"><span data-stu-id="43cdf-124">Receive Adapter</span></span>  
 <span data-ttu-id="43cdf-125">受信アダプターは、ネットワーク/データ ソース ストリームをメッセージ本文に添付して新しい BizTalk メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="43cdf-125">A receive adapter is responsible for creating a new BizTalk message by attaching the network/data source stream to the message body.</span></span> <span data-ttu-id="43cdf-126">また、データの受信元エンドポイントに関するメタデータを追加して、そのメッセージをメッセージング エンジンに送信します。</span><span class="sxs-lookup"><span data-stu-id="43cdf-126">It also adds any metadata pertinent to the endpoint over which the data was received, and then submits that message to the Messaging Engine.</span></span> <span data-ttu-id="43cdf-127">アダプターは、受信エンドポイントからデータを削除したり、適切な確認メッセージをクライアントに送信して、データが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で受理されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="43cdf-127">The adapter deletes the data from the receive endpoint or sends the appropriate acknowledgment message to the client indicating that the data was accepted into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
#### <a name="send-adapter"></a><span data-ttu-id="43cdf-128">送信アダプター</span><span class="sxs-lookup"><span data-stu-id="43cdf-128">Send Adapter</span></span>  
 <span data-ttu-id="43cdf-129">送信アダプターは、特定のトランスポート プロトコルを使用して指定のエンドポイントに BizTalk メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="43cdf-129">A send adapter is responsible for sending a BizTalk message to the specified endpoint using its specific transport protocol.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43cdf-130">参照</span><span class="sxs-lookup"><span data-stu-id="43cdf-130">See Also</span></span>  
 [<span data-ttu-id="43cdf-131">アダプター フレームワークとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="43cdf-131">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)