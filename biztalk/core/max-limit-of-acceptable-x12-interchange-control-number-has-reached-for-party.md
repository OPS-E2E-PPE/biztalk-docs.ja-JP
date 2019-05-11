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
ms.openlocfilehash: fc1cbbeaac1eb401b8887c3fe56a047f0cac4345
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325573"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-party"></a><span data-ttu-id="2446a-102">パーティのインターチェンジ制御番号に到達する許容される X12 の上限</span><span class="sxs-lookup"><span data-stu-id="2446a-102">Max limit of acceptable X12 interchange control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="2446a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2446a-103">Details</span></span>  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2446a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2446a-104">Product Name</span></span>   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| <span data-ttu-id="2446a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2446a-105">Product Version</span></span> |                                                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    <span data-ttu-id="2446a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2446a-106">Event ID</span></span>     |                                                                                             -                                                                                             |
|  <span data-ttu-id="2446a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2446a-107">Event Source</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2446a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="2446a-108">EDI</span></span>                                                   |
|    <span data-ttu-id="2446a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2446a-109">Component</span></span>    |                                                                                        <span data-ttu-id="2446a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="2446a-110">EDI Engine</span></span>                                                                                         |
|  <span data-ttu-id="2446a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2446a-111">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="2446a-112">PartyX12IsaNumberError</span><span class="sxs-lookup"><span data-stu-id="2446a-112">PartyX12IsaNumberError</span></span>                                                                                   |
|  <span data-ttu-id="2446a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2446a-113">Message Text</span></span>   | <span data-ttu-id="2446a-114">パーティのインターチェンジ制御番号に到達する許容される X12 上限{0}します。</span><span class="sxs-lookup"><span data-stu-id="2446a-114">Max limit of acceptable X12 interchange control number has reached for party {0}.</span></span> <span data-ttu-id="2446a-115">パートナー アグリーメント マネージャーで、[Party in receiver role] の [ISA 13] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="2446a-115">Reset counter by navigating to Party in receiver role screen, field ISA 13 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2446a-116">説明</span><span class="sxs-lookup"><span data-stu-id="2446a-116">Explanation</span></span>  
 <span data-ttu-id="2446a-117">このエラー/警告/情報イベントは、パーティ設定で指定された ISA13 フィールドのインターチェンジ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="2446a-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the interchange control number in the ISA13 field specified in the party settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="2446a-118">インターチェンジ制御番号の最大文字数は 9 文字です。</span><span class="sxs-lookup"><span data-stu-id="2446a-118">The maximum number of characters for the interchange control number is nine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2446a-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2446a-119">User Action</span></span>  
 <span data-ttu-id="2446a-120">このエラーを解決するには、インターチェンジ制御番号を次のようにリセットします。</span><span class="sxs-lookup"><span data-stu-id="2446a-120">To resolve this error, reset the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="2446a-121">インターチェンジに対して解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、インターチェンジの受信者としてのパーティの [ISA セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="2446a-121">In the EDI Properties dialog box for the party resolved for the interchange, open the ISA Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="2446a-122">ISA13 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2446a-122">Click the Edit field associated with the ISA13 field.</span></span>  
  
3.  <span data-ttu-id="2446a-123">フィールドの桁数が許容値になるように、インターチェンジ制御番号に新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2446a-123">Set the interchange control number to a new value such that the field has an acceptable number of digits.</span></span>