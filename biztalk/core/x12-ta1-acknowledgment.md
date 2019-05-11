---
title: X12 TA1 受信確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68568a1a-3669-46f4-8edc-8d057b012544
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a168a4112e861ea6b33b232883d320be2aa1ba82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394752"
---
# <a name="x12-ta1-acknowledgment"></a><span data-ttu-id="9a12e-102">X12 TA1 確認</span><span class="sxs-lookup"><span data-stu-id="9a12e-102">X12 TA1 Acknowledgment</span></span>
<span data-ttu-id="9a12e-103">X12 TA1 技術確認のインターチェンジ ヘッダーとトレーラー、アドレス受信者による処理の状態を報告します。</span><span class="sxs-lookup"><span data-stu-id="9a12e-103">The X12 TA1 technical acknowledgment reports the status of the processing of an interchange header and trailer by the address receiver.</span></span> <span data-ttu-id="9a12e-104">ISA および IEA が X12 でエンコードされたメッセージの有効な場合、肯定 TA1 確認が送信されますが、任意の他のコンテンツのステータスです。</span><span class="sxs-lookup"><span data-stu-id="9a12e-104">When the ISA and IEA of the X12-encoded message are valid, a positive TA1 ACK is sent, whatever the status of the other content is.</span></span> <span data-ttu-id="9a12e-105">それ以外の場合は、エラー コードで TA1 確認が送信されます。</span><span class="sxs-lookup"><span data-stu-id="9a12e-105">If not, TA1 ACK with an error code is sent.</span></span>  
  
 <span data-ttu-id="9a12e-106">X12 TA1 受信確認は、x12 _ に準拠している\<バージョン番号\>>_ta1.xsd スキーマ。</span><span class="sxs-lookup"><span data-stu-id="9a12e-106">The X12 TA1 acknowledgment conforms to the X12_\<version number\>_TA1.xsd schema.</span></span> <span data-ttu-id="9a12e-107">TA1 確認は、ISA/IEA エンベロープ内で送信されます。</span><span class="sxs-lookup"><span data-stu-id="9a12e-107">The TA1 ACK is sent inside an ISA/IEA envelope.</span></span> <span data-ttu-id="9a12e-108">ISA および IEA は、他のインターチェンジと違いはありません。</span><span class="sxs-lookup"><span data-stu-id="9a12e-108">The ISA and IEA are no different than any other interchange.</span></span>  
  
 <span data-ttu-id="9a12e-109">TA1 確認のインターチェンジ内のセグメントは、次の表に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a12e-109">The segments within the interchange of a TA1 ACK are shown in the following table.</span></span>  
  
|<span data-ttu-id="9a12e-110">TA1 のフィールド</span><span class="sxs-lookup"><span data-stu-id="9a12e-110">Field in TA1</span></span>|<span data-ttu-id="9a12e-111">フィールドの名前</span><span class="sxs-lookup"><span data-stu-id="9a12e-111">Name of Field</span></span>|<span data-ttu-id="9a12e-112">受信したインターチェンジにマップされています。</span><span class="sxs-lookup"><span data-stu-id="9a12e-112">Mapped to Incoming Interchange</span></span>|<span data-ttu-id="9a12e-113">値</span><span class="sxs-lookup"><span data-stu-id="9a12e-113">Value</span></span>|  
|------------------|-------------------|------------------------------------|-----------|  
|<span data-ttu-id="9a12e-114">TA101</span><span class="sxs-lookup"><span data-stu-id="9a12e-114">TA101</span></span>|<span data-ttu-id="9a12e-115">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="9a12e-115">Interchange control number</span></span>|<span data-ttu-id="9a12e-116">ISA13 - インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="9a12e-116">ISA13 - Interchange control number</span></span>|-|  
|<span data-ttu-id="9a12e-117">TA102</span><span class="sxs-lookup"><span data-stu-id="9a12e-117">TA102</span></span>|<span data-ttu-id="9a12e-118">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="9a12e-118">Interchange Date</span></span>|<span data-ttu-id="9a12e-119">Isa09-インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="9a12e-119">ISA09 Interchange Date</span></span>|-|  
|<span data-ttu-id="9a12e-120">TA103</span><span class="sxs-lookup"><span data-stu-id="9a12e-120">TA103</span></span>|<span data-ttu-id="9a12e-121">インターチェンジ時刻</span><span class="sxs-lookup"><span data-stu-id="9a12e-121">Interchange Time</span></span>|<span data-ttu-id="9a12e-122">ISA10 – Interchange Time</span><span class="sxs-lookup"><span data-stu-id="9a12e-122">ISA10 – Interchange Time</span></span>|-|  
|<span data-ttu-id="9a12e-123">TA104</span><span class="sxs-lookup"><span data-stu-id="9a12e-123">TA104</span></span>|<span data-ttu-id="9a12e-124">インターチェンジ確認コード \*</span><span class="sxs-lookup"><span data-stu-id="9a12e-124">Interchange ACK Code\*</span></span>|<span data-ttu-id="9a12e-125">なし</span><span class="sxs-lookup"><span data-stu-id="9a12e-125">N/A</span></span>|<span data-ttu-id="9a12e-126">エンジンの動作:A、E、または R</span><span class="sxs-lookup"><span data-stu-id="9a12e-126">Engine behavior: A, E, or R</span></span><br /><br /> <span data-ttu-id="9a12e-127">A = 受理します。</span><span class="sxs-lookup"><span data-stu-id="9a12e-127">A = Accept</span></span><br /><br /> <span data-ttu-id="9a12e-128">E = インターチェンジはエラーありで受理</span><span class="sxs-lookup"><span data-stu-id="9a12e-128">E = Interchange accepted with errors</span></span><br /><br /> <span data-ttu-id="9a12e-129">R = インターチェンジを拒否/中断</span><span class="sxs-lookup"><span data-stu-id="9a12e-129">R = Interchange rejected/suspended</span></span>|  
|<span data-ttu-id="9a12e-130">TA105</span><span class="sxs-lookup"><span data-stu-id="9a12e-130">TA105</span></span>|<span data-ttu-id="9a12e-131">インターチェンジ通知コード</span><span class="sxs-lookup"><span data-stu-id="9a12e-131">Interchange Note Code</span></span>|<span data-ttu-id="9a12e-132">なし</span><span class="sxs-lookup"><span data-stu-id="9a12e-132">N/A</span></span>|<span data-ttu-id="9a12e-133">結果のエラー コードを処理します。</span><span class="sxs-lookup"><span data-stu-id="9a12e-133">Processing result error code.</span></span> <span data-ttu-id="9a12e-134">**注:** 内のテーブルを参照してください。 [X12 TA1 受信確認エラー コード](../core/x12-ta1-acknowledgment-error-codes.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a12e-134">**Note:**  See table in [X12 TA1 Acknowledgment Error Codes](../core/x12-ta1-acknowledgment-error-codes.md).</span></span>|  
  
 <span data-ttu-id="9a12e-135">\* データ要素の検証に基づくエンジンの動作セキュリティおよび認証情報を除くは、これは構成情報の文字列比較に基づきます。</span><span class="sxs-lookup"><span data-stu-id="9a12e-135">\* Engine behavior is based off data element validation; except for security and authentication information, which will be based off string comparisons in configuration information.</span></span>