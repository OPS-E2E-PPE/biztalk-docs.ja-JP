---
title: パーティのトランザクション セット制御番号に達した許容される Edifact 上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a64cc5d3-a845-4044-9c6e-879ecda15fce
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58c2495b0e7eecf7c16ecdf067ed03d8e1a333d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347452"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-party"></a><span data-ttu-id="e73fe-102">パーティの許容の Edifact トランザクション セット制御番号の上限に達した</span><span class="sxs-lookup"><span data-stu-id="e73fe-102">Max limit of acceptable Edifact transaction set control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="e73fe-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e73fe-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e73fe-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e73fe-104">Product Name</span></span>   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| <span data-ttu-id="e73fe-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e73fe-105">Product Version</span></span> |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    <span data-ttu-id="e73fe-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e73fe-106">Event ID</span></span>     |                                                                                                -                                                                                                 |
|  <span data-ttu-id="e73fe-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e73fe-107">Event Source</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e73fe-108">EDI</span><span class="sxs-lookup"><span data-stu-id="e73fe-108">EDI</span></span>                                                      |
|    <span data-ttu-id="e73fe-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e73fe-109">Component</span></span>    |                                                                                            <span data-ttu-id="e73fe-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e73fe-110">EDI Engine</span></span>                                                                                            |
|  <span data-ttu-id="e73fe-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e73fe-111">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="e73fe-112">GlobalEdifactUnhNumberError</span><span class="sxs-lookup"><span data-stu-id="e73fe-112">GlobalEdifactUnhNumberError</span></span>                                                                                    |
|  <span data-ttu-id="e73fe-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e73fe-113">Message Text</span></span>   | <span data-ttu-id="e73fe-114">パーティのトランザクション セット制御番号に達した許容される Edifact 上限{0}します。</span><span class="sxs-lookup"><span data-stu-id="e73fe-114">Max limit of acceptable Edifact transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="e73fe-115">Party in receiver role のパートナー アグリーメント マネージャーで UNH 1 フィールドに移動して、カウンターをリセットします。</span><span class="sxs-lookup"><span data-stu-id="e73fe-115">Reset counter by navigating to Party in receiver role screen, field UNH 1 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e73fe-116">説明</span><span class="sxs-lookup"><span data-stu-id="e73fe-116">Explanation</span></span>  
 <span data-ttu-id="e73fe-117">このエラー/警告/情報イベントは、送信パイプラインがパーティ設定で、フィールド UNH1.2 の参照番号では具体的には指定された UNH1 フィールドのトランザクション セット制御番号があるために、送信インターチェンジを処理できませんでしたことを示します。許容される最大値より大きい。</span><span class="sxs-lookup"><span data-stu-id="e73fe-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the transaction set control number in the UNH1 field specified in the party settings, specifically the reference number in field UNH1.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="e73fe-118">トランザクション セット制御番号の最大許容値は UNH1 の 3 つのフィールドの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="e73fe-118">The maximum allowable value for the transaction set control number depends upon the values of the three fields in UNH1.</span></span> <span data-ttu-id="e73fe-119">最大文字数が、フィールド UNH1.2、unh1.1 のプレフィックスと、UNH1.3 のサフィックスの 13 および 14 を組み合わせた 3 つのフィールドの参照番号が 14 文字です。</span><span class="sxs-lookup"><span data-stu-id="e73fe-119">The maximum number of characters is 14 for the reference number in field UNH1.2, 13 for the prefix in UNH1.1 and 13 for the suffix in UNH1.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e73fe-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e73fe-120">User Action</span></span>  
 <span data-ttu-id="e73fe-121">このエラーを解決するには、次のように、トランザクション セット制御番号の参照番号フィールド (UNH1.2) をリセットします。</span><span class="sxs-lookup"><span data-stu-id="e73fe-121">To resolve this error, reset the reference number field (UNH1.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="e73fe-122">インターチェンジに対して解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、[UNG および UNH セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="e73fe-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNG and UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="e73fe-123">UNH1 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e73fe-123">Click the Edit field associated with the UNH1 field.</span></span>  
  
3.  <span data-ttu-id="e73fe-124">トランザクション セット制御番号 (UNH1.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="e73fe-124">Set the middle field of the transaction set control number (the reference number in UNH1.2) to a new value such that the field has an acceptable number of digits.</span></span>