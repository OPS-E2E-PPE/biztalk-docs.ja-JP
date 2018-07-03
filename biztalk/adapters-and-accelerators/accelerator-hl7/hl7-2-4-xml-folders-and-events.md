---
title: HL7 2.4 XML のフォルダーとイベント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events, HL7 2.XML versions
- HL7, default sub-folders
- HL7, events
ms.assetid: bc6c5d75-66c7-4269-bfb9-59cab5999a73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e7665a5101f5b49abd9ba087bd07cf799384c2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993291"
---
# <a name="hl7-24-xml-folders-and-events"></a><span data-ttu-id="62389-102">HL7 2.4 XML のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="62389-102">HL7 2.4 XML Folders and Events</span></span>
<span data-ttu-id="62389-103">次の表は、XML エンコード メッセージの HL7 バージョン 2.4 のフォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="62389-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.4 folder for XML-encoded messages.</span></span> <span data-ttu-id="62389-104">これらのサブフォルダーは、Microsoft BizTalk Accelerator for HL7 のために使用するスキーマを含めることが ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証する、解析し、このテーブルの [イベント] 列に表示されるイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="62389-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="62389-105">サブフォルダー名には、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="62389-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="62389-106">サブ フォルダー</span><span class="sxs-lookup"><span data-stu-id="62389-106">Sub folder</span></span>|<span data-ttu-id="62389-107">イベント</span><span class="sxs-lookup"><span data-stu-id="62389-107">Events</span></span>|  
|----------------|------------|  
|<span data-ttu-id="62389-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="62389-108">Patient Administration</span></span>|<span data-ttu-id="62389-109">A01 A62、K21、K22、K23、K24、Q21 Q24</span><span class="sxs-lookup"><span data-stu-id="62389-109">A01-A62, K21,K22,K23,K24,Q21-Q24</span></span>|  
|<span data-ttu-id="62389-110">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="62389-110">Order Entry</span></span>|<span data-ttu-id="62389-111">O01 O22、Q06、Q26 Q30、RAR、RDR、RER、RGR、権限が必要です、V01 V04、Z73、Z74</span><span class="sxs-lookup"><span data-stu-id="62389-111">O01-O22, Q06, Q26-Q30, RAR,RDR,RER,RGR,ROR, V01-V04, Z73, Z74</span></span>|  
|<span data-ttu-id="62389-112">Query</span><span class="sxs-lookup"><span data-stu-id="62389-112">Query</span></span>|<span data-ttu-id="62389-113">J01、J02、K11、K13、K15、Q01 Q05、Q07 Q09、Q11、Q13、Q15 Q17、R07 R09、Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="62389-113">J01,J02,K11,K13,K15, Q01-Q05, Q07-Q09, Q11,Q13,Q15-Q17, R07-R09, Z75-Z99</span></span>|  
|<span data-ttu-id="62389-114">財務管理</span><span class="sxs-lookup"><span data-stu-id="62389-114">Financial Management</span></span>|<span data-ttu-id="62389-115">P01 ~ P06、P10</span><span class="sxs-lookup"><span data-stu-id="62389-115">P01~P06, P10</span></span>|  
|<span data-ttu-id="62389-116">監視レポート</span><span class="sxs-lookup"><span data-stu-id="62389-116">Observation Reporting</span></span>|<span data-ttu-id="62389-117">C01 C12、P07、P08、P09、R01、R02、R04、R21、W01、W02</span><span class="sxs-lookup"><span data-stu-id="62389-117">C01-C12, P07,P08,P09, R01,R02,R04, R21, W01, W02</span></span>|  
|<span data-ttu-id="62389-118">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="62389-118">Master Files</span></span>|<span data-ttu-id="62389-119">M01 M12 の MFA</span><span class="sxs-lookup"><span data-stu-id="62389-119">M01-M12, MFA</span></span>|  
|<span data-ttu-id="62389-120">医療記録の管理</span><span class="sxs-lookup"><span data-stu-id="62389-120">Medical Records/Information Management</span></span>|<span data-ttu-id="62389-121">T01 T12</span><span class="sxs-lookup"><span data-stu-id="62389-121">T01-T12</span></span>|  
|<span data-ttu-id="62389-122">スケジューリング</span><span class="sxs-lookup"><span data-stu-id="62389-122">Scheduling</span></span>|<span data-ttu-id="62389-123">S01 S26</span><span class="sxs-lookup"><span data-stu-id="62389-123">S01-S26</span></span>|  
|<span data-ttu-id="62389-124">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="62389-124">Patient Referral</span></span>|<span data-ttu-id="62389-125">I01 I15</span><span class="sxs-lookup"><span data-stu-id="62389-125">I01-I15</span></span>|  
|<span data-ttu-id="62389-126">患者のケア</span><span class="sxs-lookup"><span data-stu-id="62389-126">Patient Care</span></span>|<span data-ttu-id="62389-127">PC1 PCH PCJ、問題、PCL</span><span class="sxs-lookup"><span data-stu-id="62389-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="62389-128">臨床試験の自動化</span><span class="sxs-lookup"><span data-stu-id="62389-128">Clinical Laboratory Automation</span></span>|<span data-ttu-id="62389-129">U01 U13</span><span class="sxs-lookup"><span data-stu-id="62389-129">U01-U13</span></span>|  
|<span data-ttu-id="62389-130">アプリケーション管理</span><span class="sxs-lookup"><span data-stu-id="62389-130">Application Management</span></span>|<span data-ttu-id="62389-131">N01、N02</span><span class="sxs-lookup"><span data-stu-id="62389-131">N01,N02</span></span>|  
|<span data-ttu-id="62389-132">人事管理</span><span class="sxs-lookup"><span data-stu-id="62389-132">Personnel Management</span></span>|<span data-ttu-id="62389-133">B01 B06 K25、Q25</span><span class="sxs-lookup"><span data-stu-id="62389-133">B01-B06, K25,Q25</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62389-134">参照</span><span class="sxs-lookup"><span data-stu-id="62389-134">See Also</span></span>  
 [<span data-ttu-id="62389-135">HL7 2. XML スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="62389-135">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)