---
title: パーティの機能グループ制御番号に達した許容される X12 上限 |Microsoft Docs
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
ms.openlocfilehash: b5ba87e528063e8c4ba4159d9a0fbb299d55c236
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347457"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-party"></a><span data-ttu-id="f3350-102">許容される X12 機能グループ制御番号に達してパーティの上限</span><span class="sxs-lookup"><span data-stu-id="f3350-102">Max limit of acceptable X12 functional group control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="f3350-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f3350-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f3350-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f3350-104">Product Name</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="f3350-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f3350-105">Product Version</span></span> |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="f3350-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f3350-106">Event ID</span></span>     |                                                                                              -                                                                                               |
|  <span data-ttu-id="f3350-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f3350-107">Event Source</span></span>   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f3350-108">EDI</span><span class="sxs-lookup"><span data-stu-id="f3350-108">EDI</span></span>                                                    |
|    <span data-ttu-id="f3350-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f3350-109">Component</span></span>    |                                                                                          <span data-ttu-id="f3350-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="f3350-110">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="f3350-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f3350-111">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="f3350-112">PartyX12GsNumberError</span><span class="sxs-lookup"><span data-stu-id="f3350-112">PartyX12GsNumberError</span></span>                                                                                     |
|  <span data-ttu-id="f3350-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f3350-113">Message Text</span></span>   | <span data-ttu-id="f3350-114">パーティの機能グループ制御番号に達した許容される X12 上限{0}します。</span><span class="sxs-lookup"><span data-stu-id="f3350-114">Max limit of acceptable X12 functional group control number has reached for party {0}.</span></span> <span data-ttu-id="f3350-115">パートナー アグリーメント マネージャーで、[Party in receiver role] の [GS 6] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="f3350-115">Reset counter by navigating to Party in receiver role screen, field GS 6 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f3350-116">説明</span><span class="sxs-lookup"><span data-stu-id="f3350-116">Explanation</span></span>  
 <span data-ttu-id="f3350-117">このエラー/警告/情報イベントは、パーティ設定で指定された GS06 フィールドのグループ制御番号が許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f3350-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the group control number in the GS06 field specified in the party settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="f3350-118">グループ制御番号の最大文字数は 9 文字です。</span><span class="sxs-lookup"><span data-stu-id="f3350-118">The maximum number of characters for the group control number is 9.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3350-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f3350-119">User Action</span></span>  
 <span data-ttu-id="f3350-120">このエラーを解決するには、グループ制御番号を次のようにリセットします。</span><span class="sxs-lookup"><span data-stu-id="f3350-120">To resolve this error, reset the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="f3350-121">インターチェンジに解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、インターチェンジの受信者のパーティに対する [GS および ST セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="f3350-121">In the EDI Properties dialog box for the party resolved for the interchange, open the GS and ST Segment Definition page for the party as interchange receiver.</span></span>  
  
2.  <span data-ttu-id="f3350-122">GS06 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3350-122">Click the Edit field associated with the GS06 field.</span></span>  
  
3.  <span data-ttu-id="f3350-123">フィールドの桁数が 9 以下になるように、グループ制御番号に新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f3350-123">Set the group control number to a new value such that the field has nine or fewer digits.</span></span>