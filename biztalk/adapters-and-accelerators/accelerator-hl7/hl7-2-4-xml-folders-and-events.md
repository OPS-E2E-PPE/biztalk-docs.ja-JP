---
title: HL7 2.4 XML フォルダーとイベント |Microsoft ドキュメント
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
ms.openlocfilehash: 10c9445a1d5c7978b526fd0347dc6defa3214640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204810"
---
# <a name="hl7-24-xml-folders-and-events"></a><span data-ttu-id="9b2fd-102">HL7 2.4 XML フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="9b2fd-102">HL7 2.4 XML Folders and Events</span></span>
<span data-ttu-id="9b2fd-103">次の表では、HL7 バージョン 2.4 フォルダー内の XML でエンコードされたメッセージのセットアップ ウィザードによって作成されるサブフォルダーが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9b2fd-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.4 folder for XML-encoded messages.</span></span> <span data-ttu-id="9b2fd-104">これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="9b2fd-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="9b2fd-105">サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b2fd-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="9b2fd-106">サブ フォルダー</span><span class="sxs-lookup"><span data-stu-id="9b2fd-106">Sub folder</span></span>|<span data-ttu-id="9b2fd-107">イベント</span><span class="sxs-lookup"><span data-stu-id="9b2fd-107">Events</span></span>|  
|----------------|------------|  
|<span data-ttu-id="9b2fd-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="9b2fd-108">Patient Administration</span></span>|<span data-ttu-id="9b2fd-109">A01 A62 K21、K22、K23、K24 Q21 Q24</span><span class="sxs-lookup"><span data-stu-id="9b2fd-109">A01-A62, K21,K22,K23,K24,Q21-Q24</span></span>|  
|<span data-ttu-id="9b2fd-110">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="9b2fd-110">Order Entry</span></span>|<span data-ttu-id="9b2fd-111">O01 O22 Q06、Q26 Q30、RAR、RDR、RER、RGR、権限が必要です、V01 V04、Z73 Z74</span><span class="sxs-lookup"><span data-stu-id="9b2fd-111">O01-O22, Q06, Q26-Q30, RAR,RDR,RER,RGR,ROR, V01-V04, Z73, Z74</span></span>|  
|<span data-ttu-id="9b2fd-112">Query</span><span class="sxs-lookup"><span data-stu-id="9b2fd-112">Query</span></span>|<span data-ttu-id="9b2fd-113">J01 J02、K11、K13、K15、Q01 Q05、Q07 Q09、Q11、Q13、Q15 Q17、R07 R09 Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="9b2fd-113">J01,J02,K11,K13,K15, Q01-Q05, Q07-Q09, Q11,Q13,Q15-Q17, R07-R09, Z75-Z99</span></span>|  
|<span data-ttu-id="9b2fd-114">財務管理</span><span class="sxs-lookup"><span data-stu-id="9b2fd-114">Financial Management</span></span>|<span data-ttu-id="9b2fd-115">P01 ~ P06、P10</span><span class="sxs-lookup"><span data-stu-id="9b2fd-115">P01~P06, P10</span></span>|  
|<span data-ttu-id="9b2fd-116">監視レポート</span><span class="sxs-lookup"><span data-stu-id="9b2fd-116">Observation Reporting</span></span>|<span data-ttu-id="9b2fd-117">C01 C12 P07、P08、P09、R01、R02、R04、R21、W01 W02</span><span class="sxs-lookup"><span data-stu-id="9b2fd-117">C01-C12, P07,P08,P09, R01,R02,R04, R21, W01, W02</span></span>|  
|<span data-ttu-id="9b2fd-118">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="9b2fd-118">Master Files</span></span>|<span data-ttu-id="9b2fd-119">M01 M12 の MFA</span><span class="sxs-lookup"><span data-stu-id="9b2fd-119">M01-M12, MFA</span></span>|  
|<span data-ttu-id="9b2fd-120">医療レコード/Information Management</span><span class="sxs-lookup"><span data-stu-id="9b2fd-120">Medical Records/Information Management</span></span>|<span data-ttu-id="9b2fd-121">T01 T12 が同時</span><span class="sxs-lookup"><span data-stu-id="9b2fd-121">T01-T12</span></span>|  
|<span data-ttu-id="9b2fd-122">スケジューリング</span><span class="sxs-lookup"><span data-stu-id="9b2fd-122">Scheduling</span></span>|<span data-ttu-id="9b2fd-123">S01 S26</span><span class="sxs-lookup"><span data-stu-id="9b2fd-123">S01-S26</span></span>|  
|<span data-ttu-id="9b2fd-124">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="9b2fd-124">Patient Referral</span></span>|<span data-ttu-id="9b2fd-125">I01 I15</span><span class="sxs-lookup"><span data-stu-id="9b2fd-125">I01-I15</span></span>|  
|<span data-ttu-id="9b2fd-126">治療</span><span class="sxs-lookup"><span data-stu-id="9b2fd-126">Patient Care</span></span>|<span data-ttu-id="9b2fd-127">PC1 PCH、PCJ、問題、PCL</span><span class="sxs-lookup"><span data-stu-id="9b2fd-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="9b2fd-128">医療研究所のオートメーション</span><span class="sxs-lookup"><span data-stu-id="9b2fd-128">Clinical Laboratory Automation</span></span>|<span data-ttu-id="9b2fd-129">U01 U13</span><span class="sxs-lookup"><span data-stu-id="9b2fd-129">U01-U13</span></span>|  
|<span data-ttu-id="9b2fd-130">アプリケーション管理</span><span class="sxs-lookup"><span data-stu-id="9b2fd-130">Application Management</span></span>|<span data-ttu-id="9b2fd-131">N01、N02</span><span class="sxs-lookup"><span data-stu-id="9b2fd-131">N01,N02</span></span>|  
|<span data-ttu-id="9b2fd-132">人事管理</span><span class="sxs-lookup"><span data-stu-id="9b2fd-132">Personnel Management</span></span>|<span data-ttu-id="9b2fd-133">B01 B06、K25、Q25</span><span class="sxs-lookup"><span data-stu-id="9b2fd-133">B01-B06, K25,Q25</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b2fd-134">参照</span><span class="sxs-lookup"><span data-stu-id="9b2fd-134">See Also</span></span>  
 [<span data-ttu-id="9b2fd-135">HL7 2. XML スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b2fd-135">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)