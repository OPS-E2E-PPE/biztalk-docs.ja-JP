---
title: MQSeries アダプターのプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90fa1355f17581c55645a375dcb782452cb55e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323700"
---
# <a name="mqseries-adapter-properties"></a><span data-ttu-id="74906-102">MQSeries アダプターのプロパティ</span><span class="sxs-lookup"><span data-stu-id="74906-102">MQSeries Adapter Properties</span></span>
<span data-ttu-id="74906-103">BizTalk オーケストレーションから MQSeries ヘッダー プロパティにアクセスするをプロジェクトに MQSeries.dll アセンブリへの参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74906-103">To access MQSeries header properties from a BizTalk orchestration, you must add a reference to the MQSeries.dll assembly to your project.</span></span> <span data-ttu-id="74906-104">このアセンブリが配置されているなど、MQSeries アダプターをインストールした場所[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="74906-104">This assembly is located where you installed the MQSeries adapter, for example, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="74906-105">MQSeries プロパティ スキーマを参照する追加のコンテキスト プロパティはさまざまな BizTalk Server 開発ツールを使用 (たとえば、**メッセージの割り当て**図形をオーケストレーション デザイナーで)。</span><span class="sxs-lookup"><span data-stu-id="74906-105">After you reference the MQSeries property schema, additional context properties are available to various BizTalk Server development tools (for example, the **Message Assignment** shape in Orchestration Designer).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74906-106">MQSeries ヘッダー プロパティを使用する場合は、IBM WebSphere MQ のドキュメントのガイドラインに従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="74906-106">Make sure that you follow the guidelines in the IBM WebSphere MQ documentation when you work with MQSeries header properties.</span></span>  
  
 <span data-ttu-id="74906-107">アダプターでは、一部の MQSeries プロパティが自動的に昇格させます。</span><span class="sxs-lookup"><span data-stu-id="74906-107">The adapter automatically promotes some MQSeries properties.</span></span> <span data-ttu-id="74906-108">アプリケーションとカスタム コンポーネントは、これらのプロパティは降格させないする必要があります。</span><span class="sxs-lookup"><span data-stu-id="74906-108">Your applications and custom components must avoid demoting these properties.</span></span> <span data-ttu-id="74906-109">カスタム パイプライン コンポーネントを使用して、追加のプロパティを昇格できます。</span><span class="sxs-lookup"><span data-stu-id="74906-109">You can promote additional properties by using custom pipeline components.</span></span> <span data-ttu-id="74906-110">自動的に昇格させたプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74906-110">The automatically promoted properties are as follows:</span></span>  
  
-   <span data-ttu-id="74906-111">**BizTalk_CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="74906-111">**BizTalk_CorrelationID**</span></span>  
  
-   <span data-ttu-id="74906-112">**MQMD_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="74906-112">**MQMD_CorrelId**</span></span>  
  
-   <span data-ttu-id="74906-113">**MQMD_MsgId**</span><span class="sxs-lookup"><span data-stu-id="74906-113">**MQMD_MsgId**</span></span>  
  
-   <span data-ttu-id="74906-114">**MQMD_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="74906-114">**MQMD_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="74906-115">**MQMD_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="74906-115">**MQMD_ReplyToQMgr**</span></span>  
  
-   <span data-ttu-id="74906-116">**MQXQH_RemoteQMgrName**</span><span class="sxs-lookup"><span data-stu-id="74906-116">**MQXQH_RemoteQMgrName**</span></span>  
  
-   <span data-ttu-id="74906-117">**MQXQH_RemoteQName**</span><span class="sxs-lookup"><span data-stu-id="74906-117">**MQXQH_RemoteQName**</span></span>  
  
-   <span data-ttu-id="74906-118">**MQXQH_MsgDesc_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="74906-118">**MQXQH_MsgDesc_CorrelId**</span></span>  
  
-   <span data-ttu-id="74906-119">**MQXQH_MsgDesc_MsgId**</span><span class="sxs-lookup"><span data-stu-id="74906-119">**MQXQH_MsgDesc_MsgId**</span></span>  
  
-   <span data-ttu-id="74906-120">**MQXQH_MsgDesc_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="74906-120">**MQXQH_MsgDesc_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="74906-121">**MQXQH_MsgDesc_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="74906-121">**MQXQH_MsgDesc_ReplyToQMgr**</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74906-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="74906-122">In This Section</span></span>  
  
-   [<span data-ttu-id="74906-123">プロパティのデータ型変換</span><span class="sxs-lookup"><span data-stu-id="74906-123">Data Type Conversion of Properties</span></span>](../core/data-type-conversion-of-properties.md)  
  
-   [<span data-ttu-id="74906-124">BizTalk Server 関連のプロパティ</span><span class="sxs-lookup"><span data-stu-id="74906-124">Properties Related to BizTalk Server</span></span>](../core/properties-related-to-biztalk-server.md)  
  
-   [<span data-ttu-id="74906-125">MQSeries コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="74906-125">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="74906-126">参照</span><span class="sxs-lookup"><span data-stu-id="74906-126">See Also</span></span>  
 [<span data-ttu-id="74906-127">MQSeries アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="74906-127">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)