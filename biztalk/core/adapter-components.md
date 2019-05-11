---
title: アダプター コンポーネント |Microsoft Docs
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
ms.openlocfilehash: 215bb12537bbd0df859c59c8914c6cba63cd139a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361605"
---
# <a name="adapter-components"></a><span data-ttu-id="d5f27-102">アダプター コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d5f27-102">Adapter Components</span></span>
<span data-ttu-id="d5f27-103">カスタム アダプターでは、標準化された構成、管理、およびネイティブ アダプターで使用される設定のメカニズムを共有します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-103">A custom adapter shares the standardized configuration, management, and setup mechanisms used by the native adapters.</span></span> <span data-ttu-id="d5f27-104">使用して、アダプター フレームワークが標準化、カスタム アダプターが管理されている、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d5f27-104">With the standardization to the Adapter Framework, a custom adapter is managed by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="d5f27-105">カスタム アダプターの主要なコンポーネントを次に示します: アダプターのレジストリ ファイル、アダプターのデザイン時コンポーネントとアダプターの実行時コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d5f27-105">The following figure shows the main components of a custom adapter: the adapter registry file, the adapter design-time component, and the adapter run-time component.</span></span>  
  
 <span data-ttu-id="d5f27-106">![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")</span><span class="sxs-lookup"><span data-stu-id="d5f27-106">![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")</span></span>  
  
## <a name="adapter-registry-file"></a><span data-ttu-id="d5f27-107">アダプターのレジストリ ファイル</span><span class="sxs-lookup"><span data-stu-id="d5f27-107">Adapter Registry File</span></span>  
 <span data-ttu-id="d5f27-108">アダプターに関する特定の情報は、レジストリおよび BizTalk 管理データベースに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5f27-108">Certain information about adapters must be registered in the registry and the BizTalk Management database.</span></span> <span data-ttu-id="d5f27-109">アダプターのエイリアスなどの情報の受信ハンドラー、受信場所、およびトランスポートの種類はメタデータと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-109">Information such as an adapter's alias, receive hander, receive location, and transport type is called metadata.</span></span> <span data-ttu-id="d5f27-110">使用して手動でアダプター登録中にこれらのメタデータ エントリが作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d5f27-110">These metadata entries are created during manual adapter registration using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="d5f27-111">または、カスタム アダプターのレジストリ ファイルを生成するアダプター レジストリ ウィザード (AdapterRegistryWizard.exe) の SDK ユーティリティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-111">Alternatively, you can run the Adapter Registry Wizard (AdapterRegistryWizard.exe) SDK utility to generate a registry file for your custom adapter.</span></span> <span data-ttu-id="d5f27-112">このレジストリ ファイルをダブルクリックするか、クリックして**インポート**上、**ファイル**] メニューの [レジストリ エディター (regedit32.exe) を使用して、メタデータをレジストリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-112">Double-clicking this registry file or clicking **Import** on the **File** menu using the registry editor (regedit32.exe) writes the metadata into the registry.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5f27-113">このレジストリ ファイルを実行しても、BizTalk 管理データベースにアダプターの情報は追加されません。</span><span class="sxs-lookup"><span data-stu-id="d5f27-113">Running this registry file does not add adapter information to the BizTalk Management database.</span></span> <span data-ttu-id="d5f27-114">使用して手動で行う必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d5f27-114">You must do this manually by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="design-time-component"></a><span data-ttu-id="d5f27-115">デザイン時コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d5f27-115">Design-Time Component</span></span>  
 <span data-ttu-id="d5f27-116">カスタム アダプターのユーザー インターフェイス (UI) は、アダプター フレームワークを使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-116">The user interface (UI) for a custom adapter is implemented by using the Adapter Framework.</span></span> <span data-ttu-id="d5f27-117">これは、アダプターのアセンブリの一部として提供される XML スキーマから、UI がレンダリングされるため、生産性の高い UI 開発アプローチです。</span><span class="sxs-lookup"><span data-stu-id="d5f27-117">This is a productive approach to UI development because the UI is rendered from an XML schema provided as part of the adapter's assembly.</span></span> <span data-ttu-id="d5f27-118">アダプターのプロパティを構成するための UI に、スキーマの内容を変換する少量のコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="d5f27-118">A small amount of code is required to transform the contents of the schema into a UI to configure the adapter's properties.</span></span>  
  
 <span data-ttu-id="d5f27-119">アダプター メタデータの追加ウィザードでは、SQL アダプターなどのアプリケーション アダプターと通信する必要があるオーケストレーションをスキーマ、メッセージの種類、およびポートの種類などのアダプター メタデータを BizTalk プロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-119">For an orchestration needing to communicate with an application adapter such as the SQL adapter, the Add Adapter Metadata Wizard enables you to add adapter metadata, such as schemas, message types, and port types, to a BizTalk project.</span></span> <span data-ttu-id="d5f27-120">アプリケーション アダプターと共にアダプター メタデータの追加ウィザードを使用して、システムに対応するスキーマを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-120">Use the Add Adapter Metadata Wizard with application adapters to pull corresponding schemas into the system.</span></span> <span data-ttu-id="d5f27-121">(アダプター以外) を BizTalk プロジェクト内からこのウィザードを起動するには、プロジェクトを右クリックして**生成した項目の追加**、 をクリックして**アダプター メタデータの追加**と登録の一覧から選択します。アダプター メタデータをインポートするアダプター。</span><span class="sxs-lookup"><span data-stu-id="d5f27-121">To invoke this wizard from within a BizTalk (non-adapter) project, right-click the project, point to **Add Generated Items**, click **Add Adapter Metadata** and then select from the list of registered adapters to import the adapter metadata.</span></span>  
  
## <a name="run-time-component"></a><span data-ttu-id="d5f27-122">実行時コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d5f27-122">Run-Time Component</span></span>  
 <span data-ttu-id="d5f27-123">通常、アダプターがパブリックの 2 つの実行時コンポーネントで構成されます。 メッセージの受信者と、メッセージの送信者を実装するコンポーネントを実装するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d5f27-123">Typically an adapter consists of two public run-time components: the component that implements the message receiver and the component that implements the message sender.</span></span> <span data-ttu-id="d5f27-124">同じアセンブリ内、または 2 つの異なるアセンブリでは、これらのコンポーネントをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-124">These components may be deployed in the same assembly or in two different assemblies.</span></span>  
  
#### <a name="receive-adapter"></a><span data-ttu-id="d5f27-125">受信アダプター</span><span class="sxs-lookup"><span data-stu-id="d5f27-125">Receive Adapter</span></span>  
 <span data-ttu-id="d5f27-126">受信アダプターはメッセージの本文に、ネットワーク/データ ソースのストリームを添付して新しい BizTalk メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-126">A receive adapter is responsible for creating a new BizTalk message by attaching the network/data source stream to the message body.</span></span> <span data-ttu-id="d5f27-127">データを受信したし、をメッセージング エンジンには、そのメッセージを送信し、エンドポイントに関連するメタデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-127">It also adds any metadata pertinent to the endpoint over which the data was received, and then submits that message to the Messaging Engine.</span></span> <span data-ttu-id="d5f27-128">アダプターが、受信エンドポイントからデータを削除したりにデータが受理されたことを示すクライアントに適切な受信確認メッセージを送信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-128">The adapter deletes the data from the receive endpoint or sends the appropriate acknowledgment message to the client indicating that the data was accepted into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
#### <a name="send-adapter"></a><span data-ttu-id="d5f27-129">送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d5f27-129">Send Adapter</span></span>  
 <span data-ttu-id="d5f27-130">送信アダプターは BizTalk メッセージをその特定のトランスポート プロトコルを使用して、指定されたエンドポイントに送信するためです。</span><span class="sxs-lookup"><span data-stu-id="d5f27-130">A send adapter is responsible for sending a BizTalk message to the specified endpoint using its specific transport protocol.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f27-131">参照</span><span class="sxs-lookup"><span data-stu-id="d5f27-131">See Also</span></span>  
 [<span data-ttu-id="d5f27-132">アダプター フレームワークについて</span><span class="sxs-lookup"><span data-stu-id="d5f27-132">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)