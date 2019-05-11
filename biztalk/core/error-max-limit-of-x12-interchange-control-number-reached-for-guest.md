---
title: 許容の X12 インターチェンジ制御番号が Guest の設定に達する上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9737053d-6065-4c88-8dfa-5f69b48e0e82
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89de1672ab7813c3e8eab7f6f9d188b51b799f6c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388688"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="91f5f-102">許容される X12 インターチェンジ制御番号に達した Guest の設定の上限</span><span class="sxs-lookup"><span data-stu-id="91f5f-102">Max limit of acceptable X12 interchange control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="91f5f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="91f5f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="91f5f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="91f5f-104">Product Name</span></span>   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| <span data-ttu-id="91f5f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="91f5f-105">Product Version</span></span> |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    <span data-ttu-id="91f5f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="91f5f-106">Event ID</span></span>     |                                                                                                     -                                                                                                      |
|  <span data-ttu-id="91f5f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="91f5f-107">Event Source</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="91f5f-108">EDI</span><span class="sxs-lookup"><span data-stu-id="91f5f-108">EDI</span></span>                                                           |
|    <span data-ttu-id="91f5f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="91f5f-109">Component</span></span>    |                                                                                                 <span data-ttu-id="91f5f-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="91f5f-110">EDI Engine</span></span>                                                                                                 |
|  <span data-ttu-id="91f5f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="91f5f-111">Symbolic Name</span></span>  |                                                                                          <span data-ttu-id="91f5f-112">GlobalX12IsaNumberError</span><span class="sxs-lookup"><span data-stu-id="91f5f-112">GlobalX12IsaNumberError</span></span>                                                                                           |
|  <span data-ttu-id="91f5f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="91f5f-113">Message Text</span></span>   | <span data-ttu-id="91f5f-114">Guest の設定の X12 インターチェンジ制御番号が、許容される上限に到達しました。</span><span class="sxs-lookup"><span data-stu-id="91f5f-114">Max limit of acceptable X12 interchange control number has reached for Guest settings.</span></span> <span data-ttu-id="91f5f-115">パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [ISA 13] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="91f5f-115">Reset counter by navigating to Global configuration receiver role screen, field ISA 13 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="91f5f-116">説明</span><span class="sxs-lookup"><span data-stu-id="91f5f-116">Explanation</span></span>  
 <span data-ttu-id="91f5f-117">このエラー/警告/情報イベントは、グローバル設定で指定された ISA13 フィールドのインターチェンジ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="91f5f-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the interchange control number in the ISA13 field specified in the global settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="91f5f-118">インターチェンジ制御番号の最大文字数は 9 文字です。</span><span class="sxs-lookup"><span data-stu-id="91f5f-118">The maximum number of characters for the interchange control number is nine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="91f5f-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="91f5f-119">User Action</span></span>  
 <span data-ttu-id="91f5f-120">このエラーを解決するには、インターチェンジ制御番号を次のようにリセットします。</span><span class="sxs-lookup"><span data-stu-id="91f5f-120">To resolve this error, reset the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="91f5f-121">[EDI グローバル プロパティ] ダイアログ ボックスで、[ISA セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="91f5f-121">In the EDI Global Properties dialog box, open the ISA Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="91f5f-122">ISA13 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="91f5f-122">Click the Edit field associated with the ISA13 field.</span></span>  
  
3.  <span data-ttu-id="91f5f-123">フィールドの桁数が許容値になるように、インターチェンジ制御番号に新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="91f5f-123">Set the interchange control number to a new value such that the field has an acceptable number of digits.</span></span>