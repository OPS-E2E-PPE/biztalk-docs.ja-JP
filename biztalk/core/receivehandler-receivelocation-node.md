---
title: ReceiveHandler (ReceiveLocation ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveHandler node [binding file]
ms.assetid: dd105052-ec71-4762-aa74-e8cdb806a6bf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e865886624731414f979c77f3f2e898e417c8b11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268538"
---
# <a name="receivehandler-receivelocation-node"></a><span data-ttu-id="3ec11-102">ReceiveHandler (ReceiveLocation ノード)</span><span class="sxs-lookup"><span data-stu-id="3ec11-102">ReceiveHandler (ReceiveLocation Node)</span></span>
<span data-ttu-id="3ec11-103">バインド ファイルの ReceiveLocation ノードの ReceiveHandler ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられた受信ハンドラーに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ec11-103">The ReceiveHandler node of the ReceiveLocation node of a binding file contains specific information about the receive handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receivehandler-node"></a><span data-ttu-id="3ec11-104">ReceiveHandler ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="3ec11-104">Nodes in the ReceiveHandler node</span></span>  
 <span data-ttu-id="3ec11-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="3ec11-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="3ec11-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="3ec11-106">**Name**</span></span>|<span data-ttu-id="3ec11-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="3ec11-107">**Node Type**</span></span>|<span data-ttu-id="3ec11-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3ec11-108">**Data Type**</span></span>|<span data-ttu-id="3ec11-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="3ec11-109">**Description**</span></span>|<span data-ttu-id="3ec11-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="3ec11-110">**Restrictions**</span></span>|<span data-ttu-id="3ec11-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="3ec11-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="3ec11-112">名前</span><span class="sxs-lookup"><span data-stu-id="3ec11-112">Name</span></span>|<span data-ttu-id="3ec11-113">属性</span><span class="sxs-lookup"><span data-stu-id="3ec11-113">Attribute</span></span>|<span data-ttu-id="3ec11-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ec11-114">xs:string</span></span>|<span data-ttu-id="3ec11-115">トランスポートに関連付けられている受信ハンドラーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ec11-115">Specifies the name of the receive handler associated with the transport.</span></span>|<span data-ttu-id="3ec11-116">任意</span><span class="sxs-lookup"><span data-stu-id="3ec11-116">Not required</span></span>|<span data-ttu-id="3ec11-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="3ec11-117">Default value: empty</span></span>|  
|<span data-ttu-id="3ec11-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="3ec11-118">HostTrusted</span></span>|<span data-ttu-id="3ec11-119">属性</span><span class="sxs-lookup"><span data-stu-id="3ec11-119">Attribute</span></span>|<span data-ttu-id="3ec11-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="3ec11-120">xs:boolean</span></span>|<span data-ttu-id="3ec11-121">受信ハンドラーに関連付けられているホストが信頼されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ec11-121">Specifies whether the host associated with the receive handler is trusted.</span></span>|<span data-ttu-id="3ec11-122">必須</span><span class="sxs-lookup"><span data-stu-id="3ec11-122">Required</span></span>|<span data-ttu-id="3ec11-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="3ec11-123">Default value: none</span></span><br /><br /> <span data-ttu-id="3ec11-124">設定**true**ホストが信頼されている場合、それ以外の場合 'éý' **false**です。</span><span class="sxs-lookup"><span data-stu-id="3ec11-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="3ec11-125">TransportType (ReceiveHandler ノード)</span><span class="sxs-lookup"><span data-stu-id="3ec11-125">TransportType (ReceiveHandler Node)</span></span>](../core/transporttype-receivehandler-node.md)|<span data-ttu-id="3ec11-126">レコード</span><span class="sxs-lookup"><span data-stu-id="3ec11-126">Record</span></span>|<span data-ttu-id="3ec11-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="3ec11-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="3ec11-128">トランスポートの種類を指定します。これはこの受信ハンドラーと共に使用されるアダプターの名前でもあります。</span><span class="sxs-lookup"><span data-stu-id="3ec11-128">Specifies the transport type, which is also the name of the adapter used with this receive handler.</span></span>|<span data-ttu-id="3ec11-129">必須</span><span class="sxs-lookup"><span data-stu-id="3ec11-129">Required</span></span>|<span data-ttu-id="3ec11-130">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="3ec11-130">Default value: none</span></span>|