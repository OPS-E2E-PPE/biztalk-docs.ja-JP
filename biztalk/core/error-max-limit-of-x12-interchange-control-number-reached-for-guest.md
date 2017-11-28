---
title: "インターチェンジ制御番号が Guest の設定に達すると、許容される X12 上限 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9737053d-6065-4c88-8dfa-5f69b48e0e82
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c72fc565367477d9dbd09f3c0d4c4f9d6ab686a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="886e3-102">Guest の設定の X12 インターチェンジ制御番号が、許容される上限に到達しました</span><span class="sxs-lookup"><span data-stu-id="886e3-102">Max limit of acceptable X12 interchange control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="886e3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="886e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="886e3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="886e3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="886e3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="886e3-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="886e3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="886e3-106">Event ID</span></span>|-|  
|<span data-ttu-id="886e3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="886e3-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="886e3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="886e3-108"> EDI</span></span>|  
|<span data-ttu-id="886e3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="886e3-109">Component</span></span>|<span data-ttu-id="886e3-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="886e3-110">EDI Engine</span></span>|  
|<span data-ttu-id="886e3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="886e3-111">Symbolic Name</span></span>|<span data-ttu-id="886e3-112">GlobalX12IsaNumberError</span><span class="sxs-lookup"><span data-stu-id="886e3-112">GlobalX12IsaNumberError</span></span>|  
|<span data-ttu-id="886e3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="886e3-113">Message Text</span></span>|<span data-ttu-id="886e3-114">Guest の設定の X12 インターチェンジ制御番号が、許容される上限に到達しました。</span><span class="sxs-lookup"><span data-stu-id="886e3-114">Max limit of acceptable X12 interchange control number has reached for Guest settings.</span></span> <span data-ttu-id="886e3-115">パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [ISA 13] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="886e3-115">Reset counter by navigating to Global configuration receiver role screen, field ISA 13 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="886e3-116">説明</span><span class="sxs-lookup"><span data-stu-id="886e3-116">Explanation</span></span>  
 <span data-ttu-id="886e3-117">このエラー/警告/情報イベントは、グローバル設定で指定された ISA13 フィールドのインターチェンジ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="886e3-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the interchange control number in the ISA13 field specified in the global settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="886e3-118">インターチェンジ制御番号の最大文字数は 9 文字です。</span><span class="sxs-lookup"><span data-stu-id="886e3-118">The maximum number of characters for the interchange control number is nine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="886e3-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="886e3-119">User Action</span></span>  
 <span data-ttu-id="886e3-120">このエラーを解決するには、インターチェンジ制御番号を次のようにリセットします。</span><span class="sxs-lookup"><span data-stu-id="886e3-120">To resolve this error, reset the interchange control number, as follows:</span></span>  
  
1.  <span data-ttu-id="886e3-121">[EDI グローバル プロパティ] ダイアログ ボックスで、[ISA セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="886e3-121">In the EDI Global Properties dialog box, open the ISA Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="886e3-122">ISA13 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="886e3-122">Click the Edit field associated with the ISA13 field.</span></span>  
  
3.  <span data-ttu-id="886e3-123">フィールドの桁数が許容値になるように、インターチェンジ制御番号に新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="886e3-123">Set the interchange control number to a new value such that the field has an acceptable number of digits.</span></span>