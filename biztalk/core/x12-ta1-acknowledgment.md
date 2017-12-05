---
title: "X12 TA1 受信確認 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68568a1a-3669-46f4-8edc-8d057b012544
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6a3de45744b40335999c1471165ff851ec60664
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="x12-ta1-acknowledgment"></a><span data-ttu-id="269ad-102">X12 TA1 確認</span><span class="sxs-lookup"><span data-stu-id="269ad-102">X12 TA1 Acknowledgment</span></span>
<span data-ttu-id="269ad-103">X12 TA1 技術確認では、アドレス受信者によるインターチェンジ ヘッダーおよびトレーラの処理状態が報告されます。</span><span class="sxs-lookup"><span data-stu-id="269ad-103">The X12 TA1 technical acknowledgment reports the status of the processing of an interchange header and trailer by the address receiver.</span></span> <span data-ttu-id="269ad-104">X12 でエンコードされたメッセージの ISA および IEA が有効な場合は、他のコンテンツの状態に関係なく、肯定 TA1 確認が送信されます。</span><span class="sxs-lookup"><span data-stu-id="269ad-104">When the ISA and IEA of the X12-encoded message are valid, a positive TA1 ACK is sent, whatever the status of the other content is.</span></span> <span data-ttu-id="269ad-105">ISA および IEA が無効な場合は、TA1 確認がエラー コードと共に送信されます。</span><span class="sxs-lookup"><span data-stu-id="269ad-105">If not, TA1 ACK with an error code is sent.</span></span>  
  
 <span data-ttu-id="269ad-106">X12 TA1 受信確認は、x12 _ に準拠している\<バージョン番号\>>_ta1.xsd スキーマです。</span><span class="sxs-lookup"><span data-stu-id="269ad-106">The X12 TA1 acknowledgment conforms to the X12_\<version number\>_TA1.xsd schema.</span></span> <span data-ttu-id="269ad-107">TA1 確認は、ISA/IEA エンベロープ内で送信されます。</span><span class="sxs-lookup"><span data-stu-id="269ad-107">The TA1 ACK is sent inside an ISA/IEA envelope.</span></span> <span data-ttu-id="269ad-108">ISA および IEA は、他のインターチェンジと違いはありません。</span><span class="sxs-lookup"><span data-stu-id="269ad-108">The ISA and IEA are no different than any other interchange.</span></span>  
  
 <span data-ttu-id="269ad-109">TA1 確認のインターチェンジ内のセグメントを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="269ad-109">The segments within the interchange of a TA1 ACK are shown in the following table.</span></span>  
  
|<span data-ttu-id="269ad-110">TA1 のフィールド</span><span class="sxs-lookup"><span data-stu-id="269ad-110">Field in TA1</span></span>|<span data-ttu-id="269ad-111">フィールドの名前</span><span class="sxs-lookup"><span data-stu-id="269ad-111">Name of Field</span></span>|<span data-ttu-id="269ad-112">マップされる受信インターチェンジ</span><span class="sxs-lookup"><span data-stu-id="269ad-112">Mapped to Incoming Interchange</span></span>|<span data-ttu-id="269ad-113">値</span><span class="sxs-lookup"><span data-stu-id="269ad-113">Value</span></span>|  
|------------------|-------------------|------------------------------------|-----------|  
|<span data-ttu-id="269ad-114">TA101</span><span class="sxs-lookup"><span data-stu-id="269ad-114">TA101</span></span>|<span data-ttu-id="269ad-115">インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="269ad-115">Interchange control number</span></span>|<span data-ttu-id="269ad-116">ISA13 - インターチェンジ制御番号</span><span class="sxs-lookup"><span data-stu-id="269ad-116">ISA13 - Interchange control number</span></span>|-|  
|<span data-ttu-id="269ad-117">TA102</span><span class="sxs-lookup"><span data-stu-id="269ad-117">TA102</span></span>|<span data-ttu-id="269ad-118">インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="269ad-118">Interchange Date</span></span>|<span data-ttu-id="269ad-119">ISA09 - インターチェンジ日付</span><span class="sxs-lookup"><span data-stu-id="269ad-119">ISA09 Interchange Date</span></span>|-|  
|<span data-ttu-id="269ad-120">TA103</span><span class="sxs-lookup"><span data-stu-id="269ad-120">TA103</span></span>|<span data-ttu-id="269ad-121">インターチェンジ時刻</span><span class="sxs-lookup"><span data-stu-id="269ad-121">Interchange Time</span></span>|<span data-ttu-id="269ad-122">ISA10 - インターチェンジ時刻</span><span class="sxs-lookup"><span data-stu-id="269ad-122">ISA10 – Interchange Time</span></span>|-|  
|<span data-ttu-id="269ad-123">TA104</span><span class="sxs-lookup"><span data-stu-id="269ad-123">TA104</span></span>|<span data-ttu-id="269ad-124">インターチェンジ確認コード*</span><span class="sxs-lookup"><span data-stu-id="269ad-124">Interchange ACK Code*</span></span>|<span data-ttu-id="269ad-125">なし</span><span class="sxs-lookup"><span data-stu-id="269ad-125">N/A</span></span>|<span data-ttu-id="269ad-126">エンジンの動作: A、E、または R</span><span class="sxs-lookup"><span data-stu-id="269ad-126">Engine behavior: A, E, or R</span></span><br /><br /> <span data-ttu-id="269ad-127">A = 受理</span><span class="sxs-lookup"><span data-stu-id="269ad-127">A = Accept</span></span><br /><br /> <span data-ttu-id="269ad-128">E = インターチェンジを受理 (ただしエラーが発生)</span><span class="sxs-lookup"><span data-stu-id="269ad-128">E = Interchange accepted with errors</span></span><br /><br /> <span data-ttu-id="269ad-129">R = インターチェンジを拒否/中断</span><span class="sxs-lookup"><span data-stu-id="269ad-129">R = Interchange rejected/suspended</span></span>|  
|<span data-ttu-id="269ad-130">TA105</span><span class="sxs-lookup"><span data-stu-id="269ad-130">TA105</span></span>|<span data-ttu-id="269ad-131">インターチェンジ通知コード</span><span class="sxs-lookup"><span data-stu-id="269ad-131">Interchange Note Code</span></span>|<span data-ttu-id="269ad-132">なし</span><span class="sxs-lookup"><span data-stu-id="269ad-132">N/A</span></span>|<span data-ttu-id="269ad-133">処理結果のエラー コード</span><span class="sxs-lookup"><span data-stu-id="269ad-133">Processing result error code.</span></span> <span data-ttu-id="269ad-134">**注:**でテーブルを参照してください[X12 TA1 受信確認エラー コード](../core/x12-ta1-acknowledgment-error-codes.md)です。</span><span class="sxs-lookup"><span data-stu-id="269ad-134">**Note:**  See table in [X12 TA1 Acknowledgment Error Codes](../core/x12-ta1-acknowledgment-error-codes.md).</span></span>|  
  
 <span data-ttu-id="269ad-135">\*データ要素の検証はエンジンの動作に基づいてセキュリティおよび認証情報を除くこれは基づきます構成情報で文字列を比較します。</span><span class="sxs-lookup"><span data-stu-id="269ad-135">\* Engine behavior is based off data element validation; except for security and authentication information, which will be based off string comparisons in configuration information.</span></span>