---
title: "MQSeries アダプターのプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQXQH_RemoteQName property [MQSeries adapters]
- MQMD_ReplyToQ property [MQSeries adapters]
- configuring [MQSeries adapters], properties
- MQXQH_MsgDesc_ReplyToQMgr property [MQSeries adapters]
- UserHttpHeaders property [MQSeries adapters]
- MQMD_CorrelId property [MQSeries adapters]
- MQXQH_MsgDesc_MsgId property [MQSeries adapters]
- MQXQH_MsgDesc_ReplyToQ property [MQSeries adapters]
- SubmissionHandle property [MQSeries adapters]
- BizTalk_CorrelationID property [MQSeries adapters]
- MQMD_ReplyToQMgr property [MQSeries adapters]
- EnableChunkedEncoding property [MQSeries adapters]
- MQSeries adapters, properties
- MQXQH_MsgDesc_CorrelId property [MQSeries adapters]
- MQXQH_RemoteQMgrName property [MQSeries adapters]
- MQMD_MsgId property [MQSeries adapters]
ms.assetid: c3cfbc8c-4c9b-431e-b0b6-4c065a69ce6b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fae8cc1ed67f077b6ae12945da10c58cf0f147da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-properties"></a><span data-ttu-id="3dace-102">MQSeries アダプターのプロパティ</span><span class="sxs-lookup"><span data-stu-id="3dace-102">MQSeries Adapter Properties</span></span>
<span data-ttu-id="3dace-103">BizTalk オーケストレーションから MQSeries ヘッダー プロパティにアクセスするには、プロジェクトに MQSeries.dll アセンブリへの参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dace-103">To access MQSeries header properties from a BizTalk orchestration, you must add a reference to the MQSeries.dll assembly to your project.</span></span> <span data-ttu-id="3dace-104">このアセンブリは、MQSeries アダプターをインストールした場所 ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] など) にあります。</span><span class="sxs-lookup"><span data-stu-id="3dace-104">This assembly is located where you installed the MQSeries adapter, for example, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="3dace-105">MQSeries プロパティ スキーマを参照すると、追加のコンテキスト プロパティはさまざまな BizTalk Server 開発ツールを使用 (たとえば、**メッセージの割り当て**図形をオーケストレーション デザイナーで)。</span><span class="sxs-lookup"><span data-stu-id="3dace-105">After you reference the MQSeries property schema, additional context properties are available to various BizTalk Server development tools (for example, the **Message Assignment** shape in Orchestration Designer).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3dace-106">MQSeries ヘッダー プロパティを使用する場合は、IBM WebSphere MQ のドキュメントに記載されているガイドラインに従うようにしてください。</span><span class="sxs-lookup"><span data-stu-id="3dace-106">Make sure that you follow the guidelines in the IBM WebSphere MQ documentation when you work with MQSeries header properties.</span></span>  
  
 <span data-ttu-id="3dace-107">アダプタでは、一部の MQSeries プロパティを自動的に昇格させます。</span><span class="sxs-lookup"><span data-stu-id="3dace-107">The adapter automatically promotes some MQSeries properties.</span></span> <span data-ttu-id="3dace-108">アプリケーションやカスタム コンポーネントでは、このように昇格されたプロパティを降格しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dace-108">Your applications and custom components must avoid demoting these properties.</span></span> <span data-ttu-id="3dace-109">また、カスタム パイプライン コンポーネントを使用して、追加のプロパティを昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="3dace-109">You can promote additional properties by using custom pipeline components.</span></span> <span data-ttu-id="3dace-110">自動的に昇格されるプロパティは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3dace-110">The automatically promoted properties are as follows:</span></span>  
  
-   <span data-ttu-id="3dace-111">**BizTalk_CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="3dace-111">**BizTalk_CorrelationID**</span></span>  
  
-   <span data-ttu-id="3dace-112">**MQMD_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="3dace-112">**MQMD_CorrelId**</span></span>  
  
-   <span data-ttu-id="3dace-113">**MQMD_MsgId**</span><span class="sxs-lookup"><span data-stu-id="3dace-113">**MQMD_MsgId**</span></span>  
  
-   <span data-ttu-id="3dace-114">**MQMD_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="3dace-114">**MQMD_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="3dace-115">**MQMD_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="3dace-115">**MQMD_ReplyToQMgr**</span></span>  
  
-   <span data-ttu-id="3dace-116">**MQXQH_RemoteQMgrName**</span><span class="sxs-lookup"><span data-stu-id="3dace-116">**MQXQH_RemoteQMgrName**</span></span>  
  
-   <span data-ttu-id="3dace-117">**MQXQH_RemoteQName**</span><span class="sxs-lookup"><span data-stu-id="3dace-117">**MQXQH_RemoteQName**</span></span>  
  
-   <span data-ttu-id="3dace-118">**MQXQH_MsgDesc_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="3dace-118">**MQXQH_MsgDesc_CorrelId**</span></span>  
  
-   <span data-ttu-id="3dace-119">**MQXQH_MsgDesc_MsgId**</span><span class="sxs-lookup"><span data-stu-id="3dace-119">**MQXQH_MsgDesc_MsgId**</span></span>  
  
-   <span data-ttu-id="3dace-120">**MQXQH_MsgDesc_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="3dace-120">**MQXQH_MsgDesc_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="3dace-121">**MQXQH_MsgDesc_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="3dace-121">**MQXQH_MsgDesc_ReplyToQMgr**</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3dace-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3dace-122">In This Section</span></span>  
  
-   [<span data-ttu-id="3dace-123">プロパティのデータ型の変換</span><span class="sxs-lookup"><span data-stu-id="3dace-123">Data Type Conversion of Properties</span></span>](../core/data-type-conversion-of-properties.md)  
  
-   [<span data-ttu-id="3dace-124">BizTalk Server に関連するプロパティ</span><span class="sxs-lookup"><span data-stu-id="3dace-124">Properties Related to BizTalk Server</span></span>](../core/properties-related-to-biztalk-server.md)  
  
-   [<span data-ttu-id="3dace-125">MQSeries コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="3dace-125">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="3dace-126">参照</span><span class="sxs-lookup"><span data-stu-id="3dace-126">See Also</span></span>  
 [<span data-ttu-id="3dace-127">MQSeries アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="3dace-127">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)