---
title: EncryptionCert (SendPort ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EncryptionCert node [binding file]
ms.assetid: 83dff67e-1b3c-4c3d-91a2-d826a498635f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd51f4b339c5bdd228c692fffd7e6c487bb8c0ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="encryptioncert-sendport-node"></a><span data-ttu-id="9b97f-102">EncryptionCert (SendPort ノード)</span><span class="sxs-lookup"><span data-stu-id="9b97f-102">EncryptionCert (SendPort Node)</span></span>
<span data-ttu-id="9b97f-103">バインド ファイルの SendPort ノードの EncryptionCert ノードには、バインド ファイルと共にエクスポートされる送信ポートで使用される暗号化証明書に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="9b97f-103">The EncryptionCert node of the SendPort node of a binding file contains information about the encryption certificate used with a send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-encryptioncert-node"></a><span data-ttu-id="9b97f-104">EncryptionCert ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="9b97f-104">Nodes in the EncryptionCert node</span></span>  
 <span data-ttu-id="9b97f-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="9b97f-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="9b97f-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="9b97f-106">**Name**</span></span>|<span data-ttu-id="9b97f-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="9b97f-107">**Node Type**</span></span>|<span data-ttu-id="9b97f-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9b97f-108">**Data Type**</span></span>|<span data-ttu-id="9b97f-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="9b97f-109">**Description**</span></span>|<span data-ttu-id="9b97f-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="9b97f-110">**Restrictions**</span></span>|<span data-ttu-id="9b97f-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9b97f-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="9b97f-112">LongName</span><span class="sxs-lookup"><span data-stu-id="9b97f-112">LongName</span></span>|<span data-ttu-id="9b97f-113">属性</span><span class="sxs-lookup"><span data-stu-id="9b97f-113">Attribute</span></span>|<span data-ttu-id="9b97f-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b97f-114">xs:string</span></span>|<span data-ttu-id="9b97f-115">証明書の長い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b97f-115">Specifies the long name of the certificate.</span></span>|<span data-ttu-id="9b97f-116">任意</span><span class="sxs-lookup"><span data-stu-id="9b97f-116">Not required</span></span>|<span data-ttu-id="9b97f-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="9b97f-117">Default value: empty</span></span>|  
|<span data-ttu-id="9b97f-118">ShortName</span><span class="sxs-lookup"><span data-stu-id="9b97f-118">ShortName</span></span>|<span data-ttu-id="9b97f-119">属性</span><span class="sxs-lookup"><span data-stu-id="9b97f-119">Attribute</span></span>|<span data-ttu-id="9b97f-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b97f-120">xs:string</span></span>|<span data-ttu-id="9b97f-121">証明書の短い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b97f-121">Specifies the short name of the certificate.</span></span>|<span data-ttu-id="9b97f-122">任意</span><span class="sxs-lookup"><span data-stu-id="9b97f-122">Not required</span></span>|<span data-ttu-id="9b97f-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="9b97f-123">Default value: empty</span></span>|  
|<span data-ttu-id="9b97f-124">UsageType</span><span class="sxs-lookup"><span data-stu-id="9b97f-124">UsageType</span></span>|<span data-ttu-id="9b97f-125">属性</span><span class="sxs-lookup"><span data-stu-id="9b97f-125">Attribute</span></span>|<span data-ttu-id="9b97f-126">CertUsageType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="9b97f-126">CertUsageType (SimpleType)</span></span>|<span data-ttu-id="9b97f-127">この証明書の用途を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b97f-127">Specifies the intended usage of this certificate</span></span>|<span data-ttu-id="9b97f-128">必須</span><span class="sxs-lookup"><span data-stu-id="9b97f-128">Required</span></span>|<span data-ttu-id="9b97f-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="9b97f-129">Default value: none</span></span><br /><br /> <span data-ttu-id="9b97f-130">使用可能な値で使用できる、 [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)列挙します。</span><span class="sxs-lookup"><span data-stu-id="9b97f-130">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx) enumeration.</span></span>|  
|<span data-ttu-id="9b97f-131">ThumbPrint</span><span class="sxs-lookup"><span data-stu-id="9b97f-131">ThumbPrint</span></span>|<span data-ttu-id="9b97f-132">属性</span><span class="sxs-lookup"><span data-stu-id="9b97f-132">Attribute</span></span>|<span data-ttu-id="9b97f-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b97f-133">xs:string</span></span>|<span data-ttu-id="9b97f-134">証明書の拇印または一意の ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b97f-134">Specifies the thumbprint, or unique ID, of the certificate.</span></span>|<span data-ttu-id="9b97f-135">任意</span><span class="sxs-lookup"><span data-stu-id="9b97f-135">Not required</span></span>|<span data-ttu-id="9b97f-136">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="9b97f-136">Default value: empty</span></span>|