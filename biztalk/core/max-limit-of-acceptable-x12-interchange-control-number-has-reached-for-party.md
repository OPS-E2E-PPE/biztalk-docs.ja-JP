---
title: パーティのインターチェンジ制御番号に到達する許容される X12 上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc49089-3c7b-4ce2-9fbc-68e582c3a822
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de22f059a720fdec999f495f38a6b21009469158
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986307"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-party"></a><span data-ttu-id="863a4-102">パーティの X12 インターチェンジ制御番号が、許容される上限に到達しました</span><span class="sxs-lookup"><span data-stu-id="863a4-102">Max limit of acceptable X12 interchange control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="863a4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="863a4-103">Details</span></span>  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="863a4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="863a4-104">Product Name</span></span>   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| <span data-ttu-id="863a4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="863a4-105">Product Version</span></span> |                                                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    <span data-ttu-id="863a4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="863a4-106">Event ID</span></span>     |                                                                                             -                                                                                             |
|  <span data-ttu-id="863a4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="863a4-107">Event Source</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="863a4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="863a4-108"> EDI</span></span>                                                   |
|    <span data-ttu-id="863a4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="863a4-109">Component</span></span>    |                                                                                        <span data-ttu-id="863a4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="863a4-110">EDI Engine</span></span>                                                                                         |
|  <span data-ttu-id="863a4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="863a4-111">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="863a4-112">PartyX12IsaNumberError</span><span class="sxs-lookup"><span data-stu-id="863a4-112">PartyX12IsaNumberError</span></span>                                                                                   |
|  <span data-ttu-id="863a4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="863a4-113">Message Text</span></span>   | <span data-ttu-id="863a4-114">パーティのインターチェンジ制御番号に到達する許容される X12 上限{0}します。</span><span class="sxs-lookup"><span data-stu-id="863a4-114">Max limit of acceptable X12 interchange control number has reached for party {0}.</span></span> <span data-ttu-id="863a4-115">パートナー アグリーメント マネージャーで、[Party in receiver role] の [ISA 13] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="863a4-115">Reset counter by navigating to Party in receiver role screen, field ISA 13 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="863a4-116">説明</span><span class="sxs-lookup"><span data-stu-id="863a4-116">Explanation</span></span>  
 <span data-ttu-id="863a4-117">このエラー/警告/情報イベントは、パーティ設定で指定された ISA13 フィールドのインターチェンジ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="863a4-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the interchange control number in the ISA13 field specified in the party settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="863a4-118">インターチェンジ制御番号の最大文字数は 9 文字です。</span><span class="sxs-lookup"><span data-stu-id="863a4-118">The maximum number of characters for the interchange control number is nine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="863a4-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="863a4-119">User Action</span></span>  
 <span data-ttu-id="863a4-120">このエラーを解決するには、インターチェンジ制御番号を次のようにリセットします。</span><span class="sxs-lookup"><span data-stu-id="863a4-120">To resolve this error, reset the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="863a4-121">インターチェンジに対して解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、インターチェンジの受信者としてのパーティの [ISA セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="863a4-121">In the EDI Properties dialog box for the party resolved for the interchange, open the ISA Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="863a4-122">ISA13 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="863a4-122">Click the Edit field associated with the ISA13 field.</span></span>  
  
3.  <span data-ttu-id="863a4-123">フィールドの桁数が許容値になるように、インターチェンジ制御番号に新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="863a4-123">Set the interchange control number to a new value such that the field has an acceptable number of digits.</span></span>