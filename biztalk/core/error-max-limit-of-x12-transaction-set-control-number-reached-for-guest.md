---
title: "許容される X12 トランザクション セット制御番号が Guest の設定に達しました上限 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5a4aa5c-13a7-4234-916e-562b52644c51
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16ab48c7bc5615a17c4927d7bf971bdec87a9c2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-x12-transaction-set-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="7d02b-102">Guest の設定の X12 トランザクション セット制御番号が、許容される上限に到達しました</span><span class="sxs-lookup"><span data-stu-id="7d02b-102">Max limit of acceptable X12 transaction set control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="7d02b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7d02b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d02b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7d02b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7d02b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7d02b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7d02b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7d02b-106">Event ID</span></span>|-|  
|<span data-ttu-id="7d02b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7d02b-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7d02b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7d02b-108"> EDI</span></span>|  
|<span data-ttu-id="7d02b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7d02b-109">Component</span></span>|<span data-ttu-id="7d02b-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="7d02b-110">EDI Engine</span></span>|  
|<span data-ttu-id="7d02b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7d02b-111">Symbolic Name</span></span>|<span data-ttu-id="7d02b-112">GlobalX12TsNumberError</span><span class="sxs-lookup"><span data-stu-id="7d02b-112">GlobalX12TsNumberError</span></span>|  
|<span data-ttu-id="7d02b-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7d02b-113">Message Text</span></span>|<span data-ttu-id="7d02b-114">Guest の設定の X12 トランザクション セット制御番号が、許容される上限に到達しました。</span><span class="sxs-lookup"><span data-stu-id="7d02b-114">Max limit of acceptable X12 transaction set control number has reached for Guest settings.</span></span> <span data-ttu-id="7d02b-115">パートナー アグリーメント マネージャーで、[Global configuration sender role] の [ST 2] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="7d02b-115">Reset counter by navigating to Global configuration sender role screen, field ST 2 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7d02b-116">説明</span><span class="sxs-lookup"><span data-stu-id="7d02b-116">Explanation</span></span>  
 <span data-ttu-id="7d02b-117">このエラー/警告/情報イベントは、グローバル設定で指定された ST02 フィールドのトランザクション セット制御番号 (具体的には ST02.2 フィールドの参照番号) が、許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="7d02b-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the transaction set control number in the ST02 field specified in the global settings, specifically the reference number in field ST02.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="7d02b-118">トランザクション セット制御番号の最大許容値は ST02 の 3 つのフィールドの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="7d02b-118">The maximum allowable value for the transaction set control number depends upon the values of the three fields in ST02.</span></span> <span data-ttu-id="7d02b-119">最大文字数は、フィールド UNH1.2 の参照番号が 9 文字、UNH1.1 のプレフィックスが 8 文字、UNH1.3 のサフィックスが 8 文字、3 つすべてのフィールドの組み合わせで 9 文字です。</span><span class="sxs-lookup"><span data-stu-id="7d02b-119">The maximum number of characters is 9 for the reference number in field UNH1.2, 8 for the prefix in UNH1.1 and 8 for the suffix in UNH1.3, and 9 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d02b-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7d02b-120">User Action</span></span>  
 <span data-ttu-id="7d02b-121">このエラーを解決するには、次のようにして、トランザクション セット制御番号の参照番号フィールド (ST02.2) をリセットします。</span><span class="sxs-lookup"><span data-stu-id="7d02b-121">To resolve this error, reset the reference number field (ST02.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="7d02b-122">[EDI グローバル プロパティ] ダイアログ ボックスで、[GS および ST セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7d02b-122">In the EDI Global Properties dialog box, open the GS and ST Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="7d02b-123">ST02 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d02b-123">Click the Edit field associated with the ST02 field.</span></span>  
  
3.  <span data-ttu-id="7d02b-124">グループ制御番号 (ST02.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7d02b-124">Set the middle field of the group control number (the reference number in ST02.2) to a new value such that the field has an acceptable number of digits.</span></span>