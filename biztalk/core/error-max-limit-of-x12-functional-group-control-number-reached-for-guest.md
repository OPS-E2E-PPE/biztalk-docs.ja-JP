---
title: 許容される X12 機能グループ制御番号が Guest の設定に達しました上限 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05cba774-fa35-4694-aa34-d7151f8cd75c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3210fb773b7093c2e28f98e0cf1aa223e1a63936
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241634"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="1add1-102">Guest の設定の X12 機能グループ制御番号が、許容される上限に到達しました</span><span class="sxs-lookup"><span data-stu-id="1add1-102">Max limit of acceptable X12 functional group control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="1add1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1add1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1add1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1add1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1add1-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1add1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1add1-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1add1-106">Event ID</span></span>|-|  
|<span data-ttu-id="1add1-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1add1-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1add1-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1add1-108"> EDI</span></span>|  
|<span data-ttu-id="1add1-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1add1-109">Component</span></span>|<span data-ttu-id="1add1-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="1add1-110">EDI Engine</span></span>|  
|<span data-ttu-id="1add1-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1add1-111">Symbolic Name</span></span>|<span data-ttu-id="1add1-112">GlobalEdifactUnhNumberError</span><span class="sxs-lookup"><span data-stu-id="1add1-112">GlobalEdifactUnhNumberError</span></span>|  
|<span data-ttu-id="1add1-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1add1-113">Message Text</span></span>|<span data-ttu-id="1add1-114">Guest の設定の X12 機能グループ制御番号が、許容される上限に到達しました。</span><span class="sxs-lookup"><span data-stu-id="1add1-114">Max limit of acceptable X12 functional group control number has reached for Guest settings.</span></span> <span data-ttu-id="1add1-115">パートナー アグリーメント マネージャーで、[Global configuration receiver role] の [GS 6] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="1add1-115">Reset counter by navigating to Global configuration receiver role screen, field GS 6 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1add1-116">説明</span><span class="sxs-lookup"><span data-stu-id="1add1-116">Explanation</span></span>  
 <span data-ttu-id="1add1-117">このエラー/警告/情報イベントは、グローバル設定で指定された GS06 フィールドのグループ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="1add1-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the group control number in the GS06 field specified in the global settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="1add1-118">グループ制御番号の最大文字数は 9 文字です。</span><span class="sxs-lookup"><span data-stu-id="1add1-118">The maximum number of characters for the group control number is 9.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1add1-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1add1-119">User Action</span></span>  
 <span data-ttu-id="1add1-120">このエラーを解決するには、グループ制御番号を次のようにリセットします。</span><span class="sxs-lookup"><span data-stu-id="1add1-120">To resolve this error, reset the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="1add1-121">[EDI グローバル プロパティ] ダイアログ ボックスで、[GS および ST セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="1add1-121">In the EDI Global Properties dialog box, open the GS and ST Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="1add1-122">GS06 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1add1-122">Click the Edit field associated with the GS06 field.</span></span>  
  
3.  <span data-ttu-id="1add1-123">フィールドの桁数が 9 以下になるように、グループ制御番号に新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="1add1-123">Set the group control number to a new value such that the field has nine or fewer digits.</span></span>