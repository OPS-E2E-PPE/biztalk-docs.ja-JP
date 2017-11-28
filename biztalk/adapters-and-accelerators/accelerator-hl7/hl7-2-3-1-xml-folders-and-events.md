---
title: "HL7 2.3.1 XML フォルダーとイベント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events, HL7 2.XML versions
- HL7, default sub-folders
- HL7, events
ms.assetid: b3598cc5-46d6-489a-84a7-266ee3c40276
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79b25e0563f404d0f8b0600829398729a6c80e65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-231-xml-folders-and-events"></a><span data-ttu-id="35859-102">HL7 2.3.1 XML フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="35859-102">HL7 2.3.1 XML Folders and Events</span></span>
<span data-ttu-id="35859-103">次の表では、HL7 version 2.3.1 フォルダー内の XML でエンコードされたメッセージのセットアップ ウィザードによって作成されるサブフォルダーが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="35859-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3.1 folder for XML-encoded messages.</span></span> <span data-ttu-id="35859-104">これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="35859-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="35859-105">サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="35859-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="35859-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="35859-106">Subfolder</span></span>|<span data-ttu-id="35859-107">イベント</span><span class="sxs-lookup"><span data-stu-id="35859-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="35859-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="35859-108">Patient Administration</span></span>|<span data-ttu-id="35859-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="35859-109">A01-A51</span></span>|  
|<span data-ttu-id="35859-110">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="35859-110">Order Entry</span></span>|<span data-ttu-id="35859-111">O01 O02、Q06、R0R、RAR、RDR、RER、RGR V01 V04</span><span class="sxs-lookup"><span data-stu-id="35859-111">O01,O02,Q06,R0R,RAR,RDR,RER,RGR, V01-V04</span></span>|  
|<span data-ttu-id="35859-112">Query</span><span class="sxs-lookup"><span data-stu-id="35859-112">Query</span></span>|<span data-ttu-id="35859-113">CNQ、Q01 Q03、Q05、Q07 Q09、R07、R08、R09</span><span class="sxs-lookup"><span data-stu-id="35859-113">CNQ, Q01-Q03, Q05, Q07-Q09, R07,R08,R09</span></span>|  
|<span data-ttu-id="35859-114">財務管理</span><span class="sxs-lookup"><span data-stu-id="35859-114">Financial Management</span></span>|<span data-ttu-id="35859-115">P01 P06</span><span class="sxs-lookup"><span data-stu-id="35859-115">P01-P06</span></span>|  
|<span data-ttu-id="35859-116">監視レポート</span><span class="sxs-lookup"><span data-stu-id="35859-116">Observation Reporting</span></span>|<span data-ttu-id="35859-117">C01 C12 P06、P07、P09、R01 R06、W01 W02</span><span class="sxs-lookup"><span data-stu-id="35859-117">C01-C12,P06,P07,P09,R01-R06, W01,W02</span></span>|  
|<span data-ttu-id="35859-118">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="35859-118">Master Files</span></span>|<span data-ttu-id="35859-119">M01 M11 の MFA</span><span class="sxs-lookup"><span data-stu-id="35859-119">M01-M11, MFA</span></span>|  
|<span data-ttu-id="35859-120">医療レコード/Information Management</span><span class="sxs-lookup"><span data-stu-id="35859-120">Medical Records/Information Management</span></span>|<span data-ttu-id="35859-121">T01 T12 が同時</span><span class="sxs-lookup"><span data-stu-id="35859-121">T01-T12</span></span>|  
|<span data-ttu-id="35859-122">スケジュール</span><span class="sxs-lookup"><span data-stu-id="35859-122">Schedule</span></span>|<span data-ttu-id="35859-123">S01 S26</span><span class="sxs-lookup"><span data-stu-id="35859-123">S01-S26</span></span>|  
|<span data-ttu-id="35859-124">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="35859-124">Patient Referral</span></span>|<span data-ttu-id="35859-125">I01 I15</span><span class="sxs-lookup"><span data-stu-id="35859-125">I01-I15</span></span>|  
|<span data-ttu-id="35859-126">治療</span><span class="sxs-lookup"><span data-stu-id="35859-126">Patient Care</span></span>|<span data-ttu-id="35859-127">PC1 PCH、PCJ、問題、PCL</span><span class="sxs-lookup"><span data-stu-id="35859-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="35859-128">ネットワークの管理</span><span class="sxs-lookup"><span data-stu-id="35859-128">Network Management</span></span>|<span data-ttu-id="35859-129">N01、N02</span><span class="sxs-lookup"><span data-stu-id="35859-129">N01,N02</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35859-130">参照</span><span class="sxs-lookup"><span data-stu-id="35859-130">See Also</span></span>  
 [<span data-ttu-id="35859-131">HL7 2. XML スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="35859-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)