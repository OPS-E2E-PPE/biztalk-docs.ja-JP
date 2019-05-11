---
title: EncryptionCert (ReceiveLocation ノード) |Microsoft Docs
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
ms.openlocfilehash: 139a970ddcfe4c4a26c8f4f7e0600ed714358f83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349573"
---
# <a name="encryptioncert-receivelocation-node"></a><span data-ttu-id="76d09-102">EncryptionCert (ReceiveLocation ノード)</span><span class="sxs-lookup"><span data-stu-id="76d09-102">EncryptionCert (ReceiveLocation Node)</span></span>
<span data-ttu-id="76d09-103">バインド ファイルの ReceiveLocation ノードの EncryptionCert ノードには、バインド ファイルと共にエクスポートされる受信場所で使用される暗号化証明書に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="76d09-103">The EncryptionCert node of the ReceiveLocation node of a binding file contains information about the encryption certificate used with a receive location that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-encryptioncert-node"></a><span data-ttu-id="76d09-104">EncryptionCert ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="76d09-104">Nodes in the EncryptionCert node</span></span>  
 <span data-ttu-id="76d09-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="76d09-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="76d09-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="76d09-106">**Name**</span></span>|<span data-ttu-id="76d09-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="76d09-107">**Node Type**</span></span>|<span data-ttu-id="76d09-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="76d09-108">**Data Type**</span></span>|<span data-ttu-id="76d09-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="76d09-109">**Description**</span></span>|<span data-ttu-id="76d09-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="76d09-110">**Restrictions**</span></span>|<span data-ttu-id="76d09-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="76d09-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="76d09-112">LongName</span><span class="sxs-lookup"><span data-stu-id="76d09-112">LongName</span></span>|<span data-ttu-id="76d09-113">属性</span><span class="sxs-lookup"><span data-stu-id="76d09-113">Attribute</span></span>|<span data-ttu-id="76d09-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="76d09-114">xs:string</span></span>|<span data-ttu-id="76d09-115">証明書の長い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="76d09-115">Specifies the long name of the certificate.</span></span>|<span data-ttu-id="76d09-116">任意</span><span class="sxs-lookup"><span data-stu-id="76d09-116">Not required</span></span>|<span data-ttu-id="76d09-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="76d09-117">Default value: empty</span></span>|  
|<span data-ttu-id="76d09-118">ShortName</span><span class="sxs-lookup"><span data-stu-id="76d09-118">ShortName</span></span>|<span data-ttu-id="76d09-119">属性</span><span class="sxs-lookup"><span data-stu-id="76d09-119">Attribute</span></span>|<span data-ttu-id="76d09-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="76d09-120">xs:string</span></span>|<span data-ttu-id="76d09-121">証明書の短い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="76d09-121">Specifies the short name of the certificate.</span></span>|<span data-ttu-id="76d09-122">任意</span><span class="sxs-lookup"><span data-stu-id="76d09-122">Not required</span></span>|<span data-ttu-id="76d09-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="76d09-123">Default value: empty</span></span>|  
|<span data-ttu-id="76d09-124">UsageType</span><span class="sxs-lookup"><span data-stu-id="76d09-124">UsageType</span></span>|<span data-ttu-id="76d09-125">属性</span><span class="sxs-lookup"><span data-stu-id="76d09-125">Attribute</span></span>|<span data-ttu-id="76d09-126">CertUsageType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="76d09-126">CertUsageType (SimpleType)</span></span>|<span data-ttu-id="76d09-127">この証明書の使用目的を指定します</span><span class="sxs-lookup"><span data-stu-id="76d09-127">Specifies the intended usage of this certificate</span></span>|<span data-ttu-id="76d09-128">必須</span><span class="sxs-lookup"><span data-stu-id="76d09-128">Required</span></span>|<span data-ttu-id="76d09-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="76d09-129">Default value: none</span></span><br /><br /> <span data-ttu-id="76d09-130">使用可能な値で使用できる、 [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)列挙体。</span><span class="sxs-lookup"><span data-stu-id="76d09-130">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx) enumeration.</span></span>|  
|<span data-ttu-id="76d09-131">拇印</span><span class="sxs-lookup"><span data-stu-id="76d09-131">ThumbPrint</span></span>|<span data-ttu-id="76d09-132">属性</span><span class="sxs-lookup"><span data-stu-id="76d09-132">Attribute</span></span>|<span data-ttu-id="76d09-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="76d09-133">xs:string</span></span>|<span data-ttu-id="76d09-134">拇印または証明書の一意の ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="76d09-134">Specifies the thumbprint, or unique ID, of the certificate.</span></span>|<span data-ttu-id="76d09-135">任意</span><span class="sxs-lookup"><span data-stu-id="76d09-135">Not required</span></span>|<span data-ttu-id="76d09-136">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="76d09-136">Default value: empty</span></span>|