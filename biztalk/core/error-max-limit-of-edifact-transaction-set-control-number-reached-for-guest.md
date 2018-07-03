---
title: 許容される Edifact トランザクション セット制御番号に達した Guest の設定の上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3924a18c-87bc-4727-b7cd-598d3e5ade2a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0de9240d2fd5ea701f701e34698b645b272b904b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978963"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="ab92a-102">Guest の設定の EDIFACT トランザクション セット制御番号が、許容される上限に到達しました</span><span class="sxs-lookup"><span data-stu-id="ab92a-102">Max limit of acceptable Edifact transaction set control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="ab92a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ab92a-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ab92a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ab92a-104">Product Name</span></span>   |                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
| <span data-ttu-id="ab92a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ab92a-105">Product Version</span></span> |                                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                             |
|    <span data-ttu-id="ab92a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ab92a-106">Event ID</span></span>     |                                                                                                         -                                                                                                          |
|  <span data-ttu-id="ab92a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ab92a-107">Event Source</span></span>   |                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ab92a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ab92a-108"> EDI</span></span>                                                               |
|    <span data-ttu-id="ab92a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ab92a-109">Component</span></span>    |                                                                                                     <span data-ttu-id="ab92a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ab92a-110">EDI Engine</span></span>                                                                                                     |
|  <span data-ttu-id="ab92a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ab92a-111">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="ab92a-112">GlobalEdifactUnhNumberError</span><span class="sxs-lookup"><span data-stu-id="ab92a-112">GlobalEdifactUnhNumberError</span></span>                                                                                             |
|  <span data-ttu-id="ab92a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ab92a-113">Message Text</span></span>   | <span data-ttu-id="ab92a-114">Guest の設定の EDIFACT トランザクション セット制御番号が、許容される上限に到達しました。</span><span class="sxs-lookup"><span data-stu-id="ab92a-114">Max limit of acceptable Edifact transaction set control number has reached for Guest settings.</span></span> <span data-ttu-id="ab92a-115">パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [UNH 1] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="ab92a-115">Reset counter by  navigating to Global configuration receiver role screen, field UNH 1 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ab92a-116">説明</span><span class="sxs-lookup"><span data-stu-id="ab92a-116">Explanation</span></span>  
 <span data-ttu-id="ab92a-117">このエラー/警告/情報イベントは、グローバル設定で指定された UNH1 フィールドのトランザクション セット制御番号 (具体的には、UNH1.2 フィールドの参照番号) が許容される最大値よりも大きかったため、送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ab92a-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the transaction set control number in the UNH1 field specified in the global settings, specifically the reference number in field UNH1.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="ab92a-118">グループ制御番号の許容される上限値は、UNH1 の 3 つのフィールドの値によって決定します。</span><span class="sxs-lookup"><span data-stu-id="ab92a-118">The maximum allowable value for the group control number depends upon the values of the three fields in UNH1.</span></span> <span data-ttu-id="ab92a-119">最大文字数が、フィールド UNH1.2、unh1.1 のプレフィックスと、UNH1.3 のサフィックスの 13 および 14 を組み合わせた 3 つのフィールドの参照番号が 14 文字です。</span><span class="sxs-lookup"><span data-stu-id="ab92a-119">The maximum number of characters is 14 for the reference number in field UNH1.2, 13 for the prefix in UNH1.1 and 13 for the suffix in UNH1.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab92a-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ab92a-120">User Action</span></span>  
 <span data-ttu-id="ab92a-121">このエラーを解決するには、次のように、トランザクション セット制御番号の参照番号フィールド (UNH1.2) をリセットします。</span><span class="sxs-lookup"><span data-stu-id="ab92a-121">To resolve this error, reset the reference number field (UNH1.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="ab92a-122">[EDI グローバル プロパティ] ダイアログ ボックスで、[UNH セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="ab92a-122">In the EDI Global Properties dialog box, open the UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="ab92a-123">UNH1 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab92a-123">Click the Edit field associated with the UNH1 field.</span></span>  
  
3.  <span data-ttu-id="ab92a-124">グループ制御番号 (UNH1.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="ab92a-124">Set the middle field of the group control number (the reference number in UNH1.2) to a new value such that the field has an acceptable number of digits.</span></span>