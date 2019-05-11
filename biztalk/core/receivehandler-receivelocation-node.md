---
title: ReceiveHandler (ReceiveLocation ノード) |Microsoft Docs
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
ms.openlocfilehash: e04d45b94641703b045a3d3d8d571d7586424c57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398169"
---
# <a name="receivehandler-receivelocation-node"></a><span data-ttu-id="51bb8-102">ReceiveHandler (ReceiveLocation ノード)</span><span class="sxs-lookup"><span data-stu-id="51bb8-102">ReceiveHandler (ReceiveLocation Node)</span></span>
<span data-ttu-id="51bb8-103">バインド ファイルの ReceiveLocation ノードの ReceiveHandler ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられている受信ハンドラーに関する特定の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="51bb8-103">The ReceiveHandler node of the ReceiveLocation node of a binding file contains specific information about the receive handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receivehandler-node"></a><span data-ttu-id="51bb8-104">ReceiveHandler ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="51bb8-104">Nodes in the ReceiveHandler node</span></span>  
 <span data-ttu-id="51bb8-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="51bb8-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="51bb8-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="51bb8-106">**Name**</span></span>|<span data-ttu-id="51bb8-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="51bb8-107">**Node Type**</span></span>|<span data-ttu-id="51bb8-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="51bb8-108">**Data Type**</span></span>|<span data-ttu-id="51bb8-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="51bb8-109">**Description**</span></span>|<span data-ttu-id="51bb8-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="51bb8-110">**Restrictions**</span></span>|<span data-ttu-id="51bb8-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="51bb8-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="51bb8-112">名前</span><span class="sxs-lookup"><span data-stu-id="51bb8-112">Name</span></span>|<span data-ttu-id="51bb8-113">属性</span><span class="sxs-lookup"><span data-stu-id="51bb8-113">Attribute</span></span>|<span data-ttu-id="51bb8-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="51bb8-114">xs:string</span></span>|<span data-ttu-id="51bb8-115">トランスポートに関連付けられている受信ハンドラーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="51bb8-115">Specifies the name of the receive handler associated with the transport.</span></span>|<span data-ttu-id="51bb8-116">任意</span><span class="sxs-lookup"><span data-stu-id="51bb8-116">Not required</span></span>|<span data-ttu-id="51bb8-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="51bb8-117">Default value: empty</span></span>|  
|<span data-ttu-id="51bb8-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="51bb8-118">HostTrusted</span></span>|<span data-ttu-id="51bb8-119">属性</span><span class="sxs-lookup"><span data-stu-id="51bb8-119">Attribute</span></span>|<span data-ttu-id="51bb8-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="51bb8-120">xs:boolean</span></span>|<span data-ttu-id="51bb8-121">受信ハンドラーに関連付けられているホストが信頼されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="51bb8-121">Specifies whether the host associated with the receive handler is trusted.</span></span>|<span data-ttu-id="51bb8-122">必須</span><span class="sxs-lookup"><span data-stu-id="51bb8-122">Required</span></span>|<span data-ttu-id="51bb8-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="51bb8-123">Default value: none</span></span><br /><br /> <span data-ttu-id="51bb8-124">設定**true**ホストが信頼されている場合がそれ以外の場合に設定**false**します。</span><span class="sxs-lookup"><span data-stu-id="51bb8-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="51bb8-125">TransportType (ReceiveHandler ノード)</span><span class="sxs-lookup"><span data-stu-id="51bb8-125">TransportType (ReceiveHandler Node)</span></span>](../core/transporttype-receivehandler-node.md)|<span data-ttu-id="51bb8-126">レコード</span><span class="sxs-lookup"><span data-stu-id="51bb8-126">Record</span></span>|<span data-ttu-id="51bb8-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="51bb8-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="51bb8-128">これで使用するアダプターの名前でもあるトランスポートの種類を指定します。 受信ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="51bb8-128">Specifies the transport type, which is also the name of the adapter used with this receive handler.</span></span>|<span data-ttu-id="51bb8-129">必須</span><span class="sxs-lookup"><span data-stu-id="51bb8-129">Required</span></span>|<span data-ttu-id="51bb8-130">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="51bb8-130">Default value: none</span></span>|