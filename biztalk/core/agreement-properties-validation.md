---
title: アグリーメントのプロパティの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d565c26-37ef-4aee-aebb-3152880242a1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38f03d5d504210d270e8892965bffa238ee49496
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359378"
---
# <a name="agreement-properties-validation"></a><span data-ttu-id="539ed-102">アグリーメントのプロパティの検証</span><span class="sxs-lookup"><span data-stu-id="539ed-102">Agreement Properties Validation</span></span>
<span data-ttu-id="539ed-103">アグリーメントのプロパティには、インターチェンジ、グループ、またはトランザクション セットの重複した制御番号のチェックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="539ed-103">Agreement properties include checks for duplicate control numbers for interchanges, groups, or transaction sets.</span></span> <span data-ttu-id="539ed-104">EDI 受信パイプラインは、アグリーメントのプロパティで有効になっている場合にのみ、それらの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="539ed-104">The EDI receive pipeline will perform these validations only if they are enabled in agreement properties.</span></span> <span data-ttu-id="539ed-105">次のような検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="539ed-105">These validations include:</span></span>  
  
-   <span data-ttu-id="539ed-106">重複したインターチェンジ制御番号のチェック (X12 では ISA13、EDIFACT では UNB5)。</span><span class="sxs-lookup"><span data-stu-id="539ed-106">Checking for a duplicate interchange control number (ISA13 in X12 or UNB5 in EDIFACT).</span></span> <span data-ttu-id="539ed-107">時間の値を日数で入力し、このチェックの有効な時間範囲を確立します。</span><span class="sxs-lookup"><span data-stu-id="539ed-107">You enter a time value (in days) to establish the valid time range for this check.</span></span>  
  
-   <span data-ttu-id="539ed-108">インターチェンジ内の重複したグループ制御番号のチェック (X12 では GS6、EDIFACT では UNB5)。</span><span class="sxs-lookup"><span data-stu-id="539ed-108">Checking for a duplicate group control number in an interchange (GS6 in X12 or UNG5 in EDIFACT)</span></span>  
  
-   <span data-ttu-id="539ed-109">機能グループ内の重複したトランザクション セット制御番号のチェック (X12 では ST2、EDIFACT では UNH1)</span><span class="sxs-lookup"><span data-stu-id="539ed-109">Checking for a duplicate transaction set control number in a functional group (ST2 in X12 or UNH1 in EDIFACT)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="539ed-110">参照</span><span class="sxs-lookup"><span data-stu-id="539ed-110">See Also</span></span>  
 [<span data-ttu-id="539ed-111">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="539ed-111">EDI Message Validation</span></span>](../core/edi-message-validation.md)