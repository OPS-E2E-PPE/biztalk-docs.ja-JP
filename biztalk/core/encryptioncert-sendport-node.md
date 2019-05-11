---
title: EncryptionCert (SendPort ノード) |Microsoft Docs
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
ms.openlocfilehash: a314490ecb9b92babab690e892ee7ce11ebfdec4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349494"
---
# <a name="encryptioncert-sendport-node"></a><span data-ttu-id="32a93-102">EncryptionCert (SendPort ノード)</span><span class="sxs-lookup"><span data-stu-id="32a93-102">EncryptionCert (SendPort Node)</span></span>
<span data-ttu-id="32a93-103">バインド ファイルの SendPort ノードの EncryptionCert ノードには、バインド ファイルと共にエクスポートされる送信ポートで使用される暗号化証明書に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="32a93-103">The EncryptionCert node of the SendPort node of a binding file contains information about the encryption certificate used with a send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-encryptioncert-node"></a><span data-ttu-id="32a93-104">EncryptionCert ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="32a93-104">Nodes in the EncryptionCert node</span></span>  
 <span data-ttu-id="32a93-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="32a93-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="32a93-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="32a93-106">**Name**</span></span>|<span data-ttu-id="32a93-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="32a93-107">**Node Type**</span></span>|<span data-ttu-id="32a93-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="32a93-108">**Data Type**</span></span>|<span data-ttu-id="32a93-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="32a93-109">**Description**</span></span>|<span data-ttu-id="32a93-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="32a93-110">**Restrictions**</span></span>|<span data-ttu-id="32a93-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="32a93-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="32a93-112">LongName</span><span class="sxs-lookup"><span data-stu-id="32a93-112">LongName</span></span>|<span data-ttu-id="32a93-113">属性</span><span class="sxs-lookup"><span data-stu-id="32a93-113">Attribute</span></span>|<span data-ttu-id="32a93-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="32a93-114">xs:string</span></span>|<span data-ttu-id="32a93-115">証明書の長い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="32a93-115">Specifies the long name of the certificate.</span></span>|<span data-ttu-id="32a93-116">任意</span><span class="sxs-lookup"><span data-stu-id="32a93-116">Not required</span></span>|<span data-ttu-id="32a93-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="32a93-117">Default value: empty</span></span>|  
|<span data-ttu-id="32a93-118">ShortName</span><span class="sxs-lookup"><span data-stu-id="32a93-118">ShortName</span></span>|<span data-ttu-id="32a93-119">属性</span><span class="sxs-lookup"><span data-stu-id="32a93-119">Attribute</span></span>|<span data-ttu-id="32a93-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="32a93-120">xs:string</span></span>|<span data-ttu-id="32a93-121">証明書の短い名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="32a93-121">Specifies the short name of the certificate.</span></span>|<span data-ttu-id="32a93-122">任意</span><span class="sxs-lookup"><span data-stu-id="32a93-122">Not required</span></span>|<span data-ttu-id="32a93-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="32a93-123">Default value: empty</span></span>|  
|<span data-ttu-id="32a93-124">UsageType</span><span class="sxs-lookup"><span data-stu-id="32a93-124">UsageType</span></span>|<span data-ttu-id="32a93-125">属性</span><span class="sxs-lookup"><span data-stu-id="32a93-125">Attribute</span></span>|<span data-ttu-id="32a93-126">CertUsageType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="32a93-126">CertUsageType (SimpleType)</span></span>|<span data-ttu-id="32a93-127">この証明書の使用目的を指定します</span><span class="sxs-lookup"><span data-stu-id="32a93-127">Specifies the intended usage of this certificate</span></span>|<span data-ttu-id="32a93-128">必須</span><span class="sxs-lookup"><span data-stu-id="32a93-128">Required</span></span>|<span data-ttu-id="32a93-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="32a93-129">Default value: none</span></span><br /><br /> <span data-ttu-id="32a93-130">使用可能な値で使用できる、 [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)列挙体。</span><span class="sxs-lookup"><span data-stu-id="32a93-130">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx) enumeration.</span></span>|  
|<span data-ttu-id="32a93-131">拇印</span><span class="sxs-lookup"><span data-stu-id="32a93-131">ThumbPrint</span></span>|<span data-ttu-id="32a93-132">属性</span><span class="sxs-lookup"><span data-stu-id="32a93-132">Attribute</span></span>|<span data-ttu-id="32a93-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="32a93-133">xs:string</span></span>|<span data-ttu-id="32a93-134">拇印または証明書の一意の ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="32a93-134">Specifies the thumbprint, or unique ID, of the certificate.</span></span>|<span data-ttu-id="32a93-135">任意</span><span class="sxs-lookup"><span data-stu-id="32a93-135">Not required</span></span>|<span data-ttu-id="32a93-136">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="32a93-136">Default value: empty</span></span>|