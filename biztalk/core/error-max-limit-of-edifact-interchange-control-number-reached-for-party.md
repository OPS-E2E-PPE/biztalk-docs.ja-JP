---
title: "パーティに対して許容される Edifact インターチェンジ制御番号の上限に達して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c00c357-4c7b-42ea-a031-15bad0195a75
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fdb92781d137f57a09ce8c45693c2928646af24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-edifact-interchange-control-number-has-reached-for-party"></a><span data-ttu-id="f93d3-102">パーティの EDIFACT インターチェンジ制御番号が、許容される上限に到達しました</span><span class="sxs-lookup"><span data-stu-id="f93d3-102">Max limit of acceptable Edifact interchange control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="f93d3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f93d3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f93d3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f93d3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f93d3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f93d3-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f93d3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f93d3-106">Event ID</span></span>|-|  
|<span data-ttu-id="f93d3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f93d3-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f93d3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f93d3-108"> EDI</span></span>|  
|<span data-ttu-id="f93d3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f93d3-109">Component</span></span>|<span data-ttu-id="f93d3-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="f93d3-110">EDI Engine</span></span>|  
|<span data-ttu-id="f93d3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f93d3-111">Symbolic Name</span></span>|<span data-ttu-id="f93d3-112">PartyEdifactUnbNumberError</span><span class="sxs-lookup"><span data-stu-id="f93d3-112">PartyEdifactUnbNumberError</span></span>|  
|<span data-ttu-id="f93d3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f93d3-113">Message Text</span></span>|<span data-ttu-id="f93d3-114">パーティ {0} の EDIFACT インターチェンジ制御番号が、許容される上限に到達しました。</span><span class="sxs-lookup"><span data-stu-id="f93d3-114">Max limit of acceptable Edifact interchange control number has reached for party {0}.</span></span> <span data-ttu-id="f93d3-115">パートナー アグリーメント マネージャーで、[Party in receiver role] の [UNB 5] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="f93d3-115">Reset counter by navigating to Party in receiver role screen, field UNB 5 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f93d3-116">説明</span><span class="sxs-lookup"><span data-stu-id="f93d3-116">Explanation</span></span>  
 <span data-ttu-id="f93d3-117">このエラー/警告/情報イベントは、パーティ設定で指定された UNB5 フィールドのインターチェンジ制御番号 (具体的には、UNB5.2 フィールドの参照番号) が許容される最大値よりも大きかったため、送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f93d3-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing interchange because the interchange control number in the UNB5 field specified in the party settings, specifically the reference number in field UNB5.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="f93d3-118">インターチェンジ制御番号の許容される上限値は、UNB5 の 3 つのフィールドの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="f93d3-118">The maximum allowable value for the interchange control number depends upon the values of the three fields in UNB5.</span></span> <span data-ttu-id="f93d3-119">最大文字数は、フィールド UNB5.2 の参照番号が 14 文字、UNB5.1 のプレフィックスが 13 文字、UNB5.3 のサフィックスが 13 文字、3 つすべてのフィールドの組み合わせで 14 文字です。</span><span class="sxs-lookup"><span data-stu-id="f93d3-119">The maximum number of characters is 14 for the reference number in field UNB5.2, 13 for the prefix in UNB5.1 and 13 for the suffix in UNB5.3, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f93d3-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f93d3-120">User Action</span></span>  
 <span data-ttu-id="f93d3-121">このエラーを解決するには、次のように、インターチェンジ制御番号の参照番号フィールド (UNB5.2) をリセットします。</span><span class="sxs-lookup"><span data-stu-id="f93d3-121">To resolve this error, reset the reference number field (UNB5.2) of the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="f93d3-122">インターチェンジに対して解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、インターチェンジの受信者としてのパーティの [UNB セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="f93d3-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNB Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="f93d3-123">UNB5 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f93d3-123">Click the Edit field associated with the UNB5 field.</span></span>  
  
3.  <span data-ttu-id="f93d3-124">インターチェンジ制御番号 (UNB5.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f93d3-124">Set the middle field of the interchange control number (the reference number in UNB5.2) to a new value such that the field has an acceptable number of digits.</span></span>