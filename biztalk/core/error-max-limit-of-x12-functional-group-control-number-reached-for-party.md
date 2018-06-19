---
title: パーティの機能グループ制御番号に達した許容される X12 上限 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a920a66c-1e38-4f4a-8113-cbad01940839
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91d9fd8cba9ca86627c1381917a107e3ade754e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241514"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-party"></a><span data-ttu-id="e6d68-102">パーティの X12 機能グループ制御番号が、許容される上限に到達しました</span><span class="sxs-lookup"><span data-stu-id="e6d68-102">Max limit of acceptable X12 functional group control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="e6d68-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e6d68-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6d68-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e6d68-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e6d68-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e6d68-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e6d68-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e6d68-106">Event ID</span></span>|-|  
|<span data-ttu-id="e6d68-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e6d68-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e6d68-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e6d68-108"> EDI</span></span>|  
|<span data-ttu-id="e6d68-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e6d68-109">Component</span></span>|<span data-ttu-id="e6d68-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e6d68-110">EDI Engine</span></span>|  
|<span data-ttu-id="e6d68-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e6d68-111">Symbolic Name</span></span>|<span data-ttu-id="e6d68-112">PartyX12GsNumberError</span><span class="sxs-lookup"><span data-stu-id="e6d68-112">PartyX12GsNumberError</span></span>|  
|<span data-ttu-id="e6d68-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e6d68-113">Message Text</span></span>|<span data-ttu-id="e6d68-114">パーティ {0} の X12 機能グループ制御番号が、許容される上限に到達しました。</span><span class="sxs-lookup"><span data-stu-id="e6d68-114">Max limit of acceptable X12 functional group control number has reached for party {0}.</span></span> <span data-ttu-id="e6d68-115">パートナー アグリーメント マネージャーで、[Party in receiver role] の [GS 6] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="e6d68-115">Reset counter by navigating to Party in receiver role screen, field GS 6 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e6d68-116">説明</span><span class="sxs-lookup"><span data-stu-id="e6d68-116">Explanation</span></span>  
 <span data-ttu-id="e6d68-117">このエラー/警告/情報イベントは、パーティ設定で指定された GS06 フィールドのグループ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e6d68-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the group control number in the GS06 field specified in the party settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="e6d68-118">グループ制御番号の最大文字数は 9 文字です。</span><span class="sxs-lookup"><span data-stu-id="e6d68-118">The maximum number of characters for the group control number is 9.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e6d68-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e6d68-119">User Action</span></span>  
 <span data-ttu-id="e6d68-120">このエラーを解決するには、グループ制御番号を次のようにリセットします。</span><span class="sxs-lookup"><span data-stu-id="e6d68-120">To resolve this error, reset the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="e6d68-121">インターチェンジに解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、インターチェンジの受信者のパーティに対する [GS および ST セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="e6d68-121">In the EDI Properties dialog box for the party resolved for the interchange, open the GS and ST Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="e6d68-122">GS06 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6d68-122">Click the Edit field associated with the GS06 field.</span></span>  
  
3.  <span data-ttu-id="e6d68-123">フィールドの桁数が 9 以下になるように、グループ制御番号に新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="e6d68-123">Set the group control number to a new value such that the field has nine or fewer digits.</span></span>