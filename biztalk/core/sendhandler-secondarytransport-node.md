---
title: SendHandler (SecondaryTransport ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendHandler node [binding file]
ms.assetid: 32eb3e87-25ac-461e-9c09-3d6d9bcba3b2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58ab2b9f2ed41bd3fa132a73e28e38866ef18b53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254404"
---
# <a name="sendhandler-secondarytransport-node"></a><span data-ttu-id="7474c-102">SendHandler (SecondaryTransport ノード)</span><span class="sxs-lookup"><span data-stu-id="7474c-102">SendHandler (SecondaryTransport Node)</span></span>
<span data-ttu-id="7474c-103">バインド ファイルの SecondaryTransport ノードの SendHandler ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられている送信ハンドラーに関する特定の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7474c-103">The SendHandler node of the SecondaryTransport node of a binding file contains specific information about the send handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-sendhandler-node"></a><span data-ttu-id="7474c-104">SendHandler ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="7474c-104">Nodes in the SendHandler node</span></span>  
 <span data-ttu-id="7474c-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="7474c-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="7474c-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="7474c-106">**Name**</span></span>|<span data-ttu-id="7474c-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="7474c-107">**Node Type**</span></span>|<span data-ttu-id="7474c-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="7474c-108">**Data Type**</span></span>|<span data-ttu-id="7474c-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="7474c-109">**Description**</span></span>|<span data-ttu-id="7474c-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="7474c-110">**Restrictions**</span></span>|<span data-ttu-id="7474c-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="7474c-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="7474c-112">名前</span><span class="sxs-lookup"><span data-stu-id="7474c-112">Name</span></span>|<span data-ttu-id="7474c-113">属性</span><span class="sxs-lookup"><span data-stu-id="7474c-113">Attribute</span></span>|<span data-ttu-id="7474c-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="7474c-114">xs:string</span></span>|<span data-ttu-id="7474c-115">トランスポートに関連付けられている送信ハンドラーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7474c-115">Specifies the name of the send handler associated with the transport.</span></span>|<span data-ttu-id="7474c-116">任意</span><span class="sxs-lookup"><span data-stu-id="7474c-116">Not required</span></span>|<span data-ttu-id="7474c-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="7474c-117">Default value: empty</span></span>|  
|<span data-ttu-id="7474c-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="7474c-118">HostTrusted</span></span>|<span data-ttu-id="7474c-119">属性</span><span class="sxs-lookup"><span data-stu-id="7474c-119">Attribute</span></span>|<span data-ttu-id="7474c-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="7474c-120">xs:boolean</span></span>|<span data-ttu-id="7474c-121">送信ハンドラーに関連付けられているホストが信頼されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7474c-121">Specifies whether the host associated with the send handler is trusted.</span></span>|<span data-ttu-id="7474c-122">必須</span><span class="sxs-lookup"><span data-stu-id="7474c-122">Required</span></span>|<span data-ttu-id="7474c-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="7474c-123">Default value: none</span></span><br /><br /> <span data-ttu-id="7474c-124">設定**true**ホストが信頼されている場合がそれ以外の場合に設定**false**します。</span><span class="sxs-lookup"><span data-stu-id="7474c-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="7474c-125">TransportType (SendHandler ノード)</span><span class="sxs-lookup"><span data-stu-id="7474c-125">TransportType (SendHandler Node)</span></span>](../core/transporttype-sendhandler-node.md)|<span data-ttu-id="7474c-126">レコード</span><span class="sxs-lookup"><span data-stu-id="7474c-126">Record</span></span>|<span data-ttu-id="7474c-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="7474c-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="7474c-128">これは、この送信ハンドラーで使用するアダプターの名前でもトランスポートの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="7474c-128">Specifies the transport type, which is also the name of the adapter used with this send handler.</span></span>|<span data-ttu-id="7474c-129">必須</span><span class="sxs-lookup"><span data-stu-id="7474c-129">Required</span></span>|<span data-ttu-id="7474c-130">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="7474c-130">Default value: none</span></span>|