---
title: Guest の設定の Edifact インターチェンジ制御番号を許容される上限に達した |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5d2dcc0-61fd-47c9-9339-8a85319c5398
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5063f4c62bdc32c84209d8b556b4778be4b6fd5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980491"
---
# <a name="max-limit-of-acceptable-edifact-interchange-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="843b4-102">Guest の設定の EDIFACT インターチェンジ制御番号が、許容される上限に到達しました</span><span class="sxs-lookup"><span data-stu-id="843b4-102">Max limit of acceptable Edifact interchange control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="843b4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="843b4-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="843b4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="843b4-104">Product Name</span></span>   |                                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                               |
| <span data-ttu-id="843b4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="843b4-105">Product Version</span></span> |                                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                           |
|    <span data-ttu-id="843b4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="843b4-106">Event ID</span></span>     |                                                                                                       -                                                                                                       |
|  <span data-ttu-id="843b4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="843b4-107">Event Source</span></span>   |                                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="843b4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="843b4-108"> EDI</span></span>                                                             |
|    <span data-ttu-id="843b4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="843b4-109">Component</span></span>    |                                                                                                  <span data-ttu-id="843b4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="843b4-110">EDI Engine</span></span>                                                                                                   |
|  <span data-ttu-id="843b4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="843b4-111">Symbolic Name</span></span>  |                                                                                          <span data-ttu-id="843b4-112">GlobalEdifactUnbNumberError</span><span class="sxs-lookup"><span data-stu-id="843b4-112">GlobalEdifactUnbNumberError</span></span>                                                                                          |
|  <span data-ttu-id="843b4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="843b4-113">Message Text</span></span>   | <span data-ttu-id="843b4-114">Guest の設定の EDIFACT インターチェンジ制御番号が、許容される上限に到達しました。</span><span class="sxs-lookup"><span data-stu-id="843b4-114">Max limit of acceptable Edifact interchange control number has reached for Guest settings.</span></span> <span data-ttu-id="843b4-115">パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [UNB 5] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="843b4-115">Reset counter by navigating to Global configuration receiver role screen, field UNB 5 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="843b4-116">説明</span><span class="sxs-lookup"><span data-stu-id="843b4-116">Explanation</span></span>  
 <span data-ttu-id="843b4-117">このエラー/警告/情報イベントは、グローバル設定で指定された ISA13 フィールドのインターチェンジ制御番号 (具体的には、UNB5.2 フィールドの参照番号) が許容される最大値よりも大きかったため、送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="843b4-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the interchange control number in the ISA13 field specified in the global settings, specifically the reference number in field UNB5.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="843b4-118">インターチェンジ制御番号の許容される上限値は、UNB5 の 3 つのフィールドの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="843b4-118">The maximum allowable value for the interchange control number depends upon the values of the three fields in UNB5.</span></span> <span data-ttu-id="843b4-119">最大文字数は、フィールド UNB5.2 の参照番号が 14 文字、UNB5.1 のプレフィックスが 13 文字、UNB5.3 のサフィックスが 13 文字、3 つすべてのフィールドの組み合わせで 14 文字です。</span><span class="sxs-lookup"><span data-stu-id="843b4-119">The maximum number of characters is 14 for the reference number in field UNB5.2, 13 for the prefix in UNB5.1 and 13 for the suffix in UNB5.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="843b4-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="843b4-120">User Action</span></span>  
 <span data-ttu-id="843b4-121">このエラーを解決するには、次のように、インターチェンジ制御番号の参照番号フィールド (UNB5.2) をリセットします。</span><span class="sxs-lookup"><span data-stu-id="843b4-121">To resolve this error, reset the reference number field (UNB5.2) of the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="843b4-122">[EDI グローバル プロパティ] ダイアログ ボックスで、[UNB セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="843b4-122">In the EDI Global Properties dialog box, open the UNB Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="843b4-123">UNB5 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="843b4-123">Click the Edit field associated with the UNB5 field.</span></span>  
  
3.  <span data-ttu-id="843b4-124">インターチェンジ制御番号 (UNB5.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="843b4-124">Set the middle field of the interchange control number (the reference number in UNB5.2) to a new value such that the field has an acceptable number of digits.</span></span>