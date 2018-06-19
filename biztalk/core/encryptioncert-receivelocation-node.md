---
title: EncryptionCert (ReceiveLocation ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EncryptionCert node [binding file]
ms.assetid: 04dc4021-8cd9-45e7-8339-8f22e29f4be6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4d0ff769c7a8ca297800f427c4ebbae48a8640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240514"
---
# <a name="encryptioncert-receivelocation-node"></a><span data-ttu-id="566f7-102">EncryptionCert (ReceiveLocation ノード)</span><span class="sxs-lookup"><span data-stu-id="566f7-102">EncryptionCert (ReceiveLocation Node)</span></span>
<span data-ttu-id="566f7-103">バインド ファイルの ReceiveLocation ノードの EncryptionCert ノードには、そのバインド ファイルと共にエクスポートされる受信場所で使用される暗号化証明書に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="566f7-103">The EncryptionCert node of the ReceiveLocation node of a binding file contains information about the encryption certificate used with a receive location that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-encryptioncert-node"></a><span data-ttu-id="566f7-104">EncryptionCert ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="566f7-104">Nodes in the EncryptionCert node</span></span>  
 <span data-ttu-id="566f7-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="566f7-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="566f7-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="566f7-106">**Name**</span></span>|<span data-ttu-id="566f7-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="566f7-107">**Node Type**</span></span>|<span data-ttu-id="566f7-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="566f7-108">**Data Type**</span></span>|<span data-ttu-id="566f7-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="566f7-109">**Description**</span></span>|<span data-ttu-id="566f7-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="566f7-110">**Restrictions**</span></span>|<span data-ttu-id="566f7-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="566f7-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="566f7-112">LongName</span><span class="sxs-lookup"><span data-stu-id="566f7-112">LongName</span></span>|<span data-ttu-id="566f7-113">属性</span><span class="sxs-lookup"><span data-stu-id="566f7-113">Attribute</span></span>|<span data-ttu-id="566f7-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="566f7-114">xs:string</span></span>|<span data-ttu-id="566f7-115">証明書の長い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="566f7-115">Specifies the long name of the certificate.</span></span>|<span data-ttu-id="566f7-116">任意</span><span class="sxs-lookup"><span data-stu-id="566f7-116">Not required</span></span>|<span data-ttu-id="566f7-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="566f7-117">Default value: empty</span></span>|  
|<span data-ttu-id="566f7-118">ShortName</span><span class="sxs-lookup"><span data-stu-id="566f7-118">ShortName</span></span>|<span data-ttu-id="566f7-119">属性</span><span class="sxs-lookup"><span data-stu-id="566f7-119">Attribute</span></span>|<span data-ttu-id="566f7-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="566f7-120">xs:string</span></span>|<span data-ttu-id="566f7-121">証明書の短い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="566f7-121">Specifies the short name of the certificate.</span></span>|<span data-ttu-id="566f7-122">任意</span><span class="sxs-lookup"><span data-stu-id="566f7-122">Not required</span></span>|<span data-ttu-id="566f7-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="566f7-123">Default value: empty</span></span>|  
|<span data-ttu-id="566f7-124">UsageType</span><span class="sxs-lookup"><span data-stu-id="566f7-124">UsageType</span></span>|<span data-ttu-id="566f7-125">属性</span><span class="sxs-lookup"><span data-stu-id="566f7-125">Attribute</span></span>|<span data-ttu-id="566f7-126">CertUsageType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="566f7-126">CertUsageType (SimpleType)</span></span>|<span data-ttu-id="566f7-127">この証明書の用途を指定します。</span><span class="sxs-lookup"><span data-stu-id="566f7-127">Specifies the intended usage of this certificate</span></span>|<span data-ttu-id="566f7-128">必須</span><span class="sxs-lookup"><span data-stu-id="566f7-128">Required</span></span>|<span data-ttu-id="566f7-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="566f7-129">Default value: none</span></span><br /><br /> <span data-ttu-id="566f7-130">使用可能な値で使用できる、 [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)列挙します。</span><span class="sxs-lookup"><span data-stu-id="566f7-130">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx) enumeration.</span></span>|  
|<span data-ttu-id="566f7-131">ThumbPrint</span><span class="sxs-lookup"><span data-stu-id="566f7-131">ThumbPrint</span></span>|<span data-ttu-id="566f7-132">属性</span><span class="sxs-lookup"><span data-stu-id="566f7-132">Attribute</span></span>|<span data-ttu-id="566f7-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="566f7-133">xs:string</span></span>|<span data-ttu-id="566f7-134">証明書の拇印または一意の ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="566f7-134">Specifies the thumbprint, or unique ID, of the certificate.</span></span>|<span data-ttu-id="566f7-135">任意</span><span class="sxs-lookup"><span data-stu-id="566f7-135">Not required</span></span>|<span data-ttu-id="566f7-136">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="566f7-136">Default value: empty</span></span>|