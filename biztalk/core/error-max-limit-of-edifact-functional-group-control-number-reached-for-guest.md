---
title: Guest の設定の Edifact 機能グループ制御番号を許容される上限に達して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93ea1bd6-8c39-4d11-81a5-75d4a861e041
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736b191628807bf7ed0af647e83fb3665d4f2d65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241794"
---
# <a name="max-limit-of-acceptable-edifact-functional-group-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="989ba-102">Guest の設定の EDIFACT 機能グループ制御番号が、許容される上限に到達しました</span><span class="sxs-lookup"><span data-stu-id="989ba-102">Max limit of acceptable Edifact functional group control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="989ba-103">詳細</span><span class="sxs-lookup"><span data-stu-id="989ba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="989ba-104">製品名</span><span class="sxs-lookup"><span data-stu-id="989ba-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="989ba-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="989ba-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="989ba-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="989ba-106">Event ID</span></span>|-|  
|<span data-ttu-id="989ba-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="989ba-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="989ba-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="989ba-108"> EDI</span></span>|  
|<span data-ttu-id="989ba-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="989ba-109">Component</span></span>|<span data-ttu-id="989ba-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="989ba-110">EDI Engine</span></span>|  
|<span data-ttu-id="989ba-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="989ba-111">Symbolic Name</span></span>|<span data-ttu-id="989ba-112">GlobalEdifactUngNumberError</span><span class="sxs-lookup"><span data-stu-id="989ba-112">GlobalEdifactUngNumberError</span></span>|  
|<span data-ttu-id="989ba-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="989ba-113">Message Text</span></span>|<span data-ttu-id="989ba-114">Guest の設定の EDIFACT 機能グループ制御番号が、許容される上限に到達しました。</span><span class="sxs-lookup"><span data-stu-id="989ba-114">Max limit of acceptable Edifact functional group control number has reached for Guest settings.</span></span> <span data-ttu-id="989ba-115">パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [UNG 5] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="989ba-115">Reset counter by navigating to Global configuration receiver role screen, field UNG 5 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="989ba-116">説明</span><span class="sxs-lookup"><span data-stu-id="989ba-116">Explanation</span></span>  
 <span data-ttu-id="989ba-117">このエラー/警告/情報イベントは、グローバル設定に指定されている UNG5 フィールド内のグループ制御番号 (具体的には UNG5.2 フィールド内の参照番号) が許容される最大値より大きかったため、送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="989ba-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the group control number in the UNG5 field specified in the global settings, specifically the reference number in field UNG5.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="989ba-118">グループ制御番号の最大許容値は UNG5 の 3 つのフィールドの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="989ba-118">The maximum allowable value for the group control number depends upon the values of the three fields in UNG5.</span></span> <span data-ttu-id="989ba-119">最大文字数は、フィールド UNG5.2 の参照番号が 14 文字、UNG5.1 のプレフィックスと UNG5.3 のサフィックスでは 13 文字、これらすべてのフィールドの組み合わせで 14 文字です。</span><span class="sxs-lookup"><span data-stu-id="989ba-119">The maximum number of characters is 14 for the reference number in field UNG5.2, 13 for the prefix in UNG5.1 and 13 for the suffix in UNG5.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="989ba-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="989ba-120">User Action</span></span>  
 <span data-ttu-id="989ba-121">このエラーを解決するには、次のように、グループ制御番号の参照番号フィールド (UNG5.2) をリセットします。</span><span class="sxs-lookup"><span data-stu-id="989ba-121">To resolve this error, reset the reference number field (UNG5.2) of the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="989ba-122">[EDI グローバル プロパティ] ダイアログ ボックスで、[UNG および UNH セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="989ba-122">In the EDI Global Properties dialog box, open the UNG and UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="989ba-123">UNG5 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="989ba-123">Click the Edit field associated with the UNG5 field.</span></span>  
  
3.  <span data-ttu-id="989ba-124">グループ制御番号 (UNG5.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="989ba-124">Set the middle field of the group control number (the reference number in UNG5.2) to a new value such that the field has an acceptable number of digits.</span></span>