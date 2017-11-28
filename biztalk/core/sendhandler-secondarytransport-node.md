---
title: "SendHandler (SecondaryTransport ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SendHandler node [binding file]
ms.assetid: 32eb3e87-25ac-461e-9c09-3d6d9bcba3b2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f5ecdbb1860c9132133835b8928f85b1e0e1cfb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sendhandler-secondarytransport-node"></a><span data-ttu-id="c477a-102">SendHandler (SecondaryTransport ノード)</span><span class="sxs-lookup"><span data-stu-id="c477a-102">SendHandler (SecondaryTransport Node)</span></span>
<span data-ttu-id="c477a-103">バインド ファイルの SecondaryTransport ノードの SendHandler ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられた送信ハンドラーに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c477a-103">The SendHandler node of the SecondaryTransport node of a binding file contains specific information about the send handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-sendhandler-node"></a><span data-ttu-id="c477a-104">SendHandler ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="c477a-104">Nodes in the SendHandler node</span></span>  
 <span data-ttu-id="c477a-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="c477a-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="c477a-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="c477a-106">**Name**</span></span>|<span data-ttu-id="c477a-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="c477a-107">**Node Type**</span></span>|<span data-ttu-id="c477a-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c477a-108">**Data Type**</span></span>|<span data-ttu-id="c477a-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="c477a-109">**Description**</span></span>|<span data-ttu-id="c477a-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="c477a-110">**Restrictions**</span></span>|<span data-ttu-id="c477a-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="c477a-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="c477a-112">名前</span><span class="sxs-lookup"><span data-stu-id="c477a-112">Name</span></span>|<span data-ttu-id="c477a-113">属性</span><span class="sxs-lookup"><span data-stu-id="c477a-113">Attribute</span></span>|<span data-ttu-id="c477a-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="c477a-114">xs:string</span></span>|<span data-ttu-id="c477a-115">トランスポートに関連付けられている送信ハンドラーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c477a-115">Specifies the name of the send handler associated with the transport.</span></span>|<span data-ttu-id="c477a-116">任意</span><span class="sxs-lookup"><span data-stu-id="c477a-116">Not required</span></span>|<span data-ttu-id="c477a-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="c477a-117">Default value: empty</span></span>|  
|<span data-ttu-id="c477a-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="c477a-118">HostTrusted</span></span>|<span data-ttu-id="c477a-119">属性</span><span class="sxs-lookup"><span data-stu-id="c477a-119">Attribute</span></span>|<span data-ttu-id="c477a-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="c477a-120">xs:boolean</span></span>|<span data-ttu-id="c477a-121">送信ハンドラーに関連付けられているホストが信頼されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c477a-121">Specifies whether the host associated with the send handler is trusted.</span></span>|<span data-ttu-id="c477a-122">必須</span><span class="sxs-lookup"><span data-stu-id="c477a-122">Required</span></span>|<span data-ttu-id="c477a-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="c477a-123">Default value: none</span></span><br /><br /> <span data-ttu-id="c477a-124">設定**true**ホストが信頼されている場合、それ以外の場合 'éý' **false**です。</span><span class="sxs-lookup"><span data-stu-id="c477a-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="c477a-125">TransportType (SendHandler ノード)</span><span class="sxs-lookup"><span data-stu-id="c477a-125">TransportType (SendHandler Node)</span></span>](../core/transporttype-sendhandler-node.md)|<span data-ttu-id="c477a-126">レコード</span><span class="sxs-lookup"><span data-stu-id="c477a-126">Record</span></span>|<span data-ttu-id="c477a-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="c477a-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="c477a-128">トランスポートの種類を指定します。これはこの送信ハンドラーと共に使用されるアダプターの名前でもあります。</span><span class="sxs-lookup"><span data-stu-id="c477a-128">Specifies the transport type, which is also the name of the adapter used with this send handler.</span></span>|<span data-ttu-id="c477a-129">必須</span><span class="sxs-lookup"><span data-stu-id="c477a-129">Required</span></span>|<span data-ttu-id="c477a-130">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="c477a-130">Default value: none</span></span>|