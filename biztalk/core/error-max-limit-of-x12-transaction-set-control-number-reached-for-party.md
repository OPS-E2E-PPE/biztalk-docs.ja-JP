---
title: パーティのトランザクション セット制御番号に達した許容される X12 上限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a402f6d0-4399-47c9-a39a-56d7fa1efa86
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bafbafdd799330b9c34179cfd1949629eee4ca3b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001819"
---
# <a name="max-limit-of-acceptable-x12-transaction-set-control-number-has-reached-for-party"></a><span data-ttu-id="75752-102">パーティの X12 トランザクション セット制御番号が、許容される上限に到達しました</span><span class="sxs-lookup"><span data-stu-id="75752-102">Max limit of acceptable X12 transaction set control number has reached for party</span></span>
## <a name="details"></a><span data-ttu-id="75752-103">詳細</span><span class="sxs-lookup"><span data-stu-id="75752-103">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="75752-104">製品名</span><span class="sxs-lookup"><span data-stu-id="75752-104">Product Name</span></span>   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="75752-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="75752-105">Product Version</span></span> |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="75752-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="75752-106">Event ID</span></span>     |                                                                                              -                                                                                              |
|  <span data-ttu-id="75752-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="75752-107">Event Source</span></span>   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="75752-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="75752-108"> EDI</span></span>                                                    |
|    <span data-ttu-id="75752-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="75752-109">Component</span></span>    |                                                                                         <span data-ttu-id="75752-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="75752-110">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="75752-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="75752-111">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="75752-112">PartyX12TsNumberError</span><span class="sxs-lookup"><span data-stu-id="75752-112">PartyX12TsNumberError</span></span>                                                                                    |
|  <span data-ttu-id="75752-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="75752-113">Message Text</span></span>   | <span data-ttu-id="75752-114">パーティのトランザクション セット制御番号に達した許容される X12 上限{0}します。</span><span class="sxs-lookup"><span data-stu-id="75752-114">Max limit of acceptable X12 transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="75752-115">パートナー アグリーメント マネージャーで、[Party in receiver role] の [ST 2] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="75752-115">Reset counter by navigating to Party in receiver role screen, field ST 2 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="75752-116">説明</span><span class="sxs-lookup"><span data-stu-id="75752-116">Explanation</span></span>  
 <span data-ttu-id="75752-117">このエラー/警告/情報イベントは、パーティ設定で指定された ST02 フィールドのトランザクション セット制御番号 (具体的には ST02.2 フィールドの参照番号) が、許容される最大値よりも大きかったため、送信パイプラインで送信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="75752-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the transaction set control number in the ST02 field specified in the party settings, specifically the reference number in field ST02.2, was greater than the maximum allowable value.</span></span> <span data-ttu-id="75752-118">トランザクション セット制御番号の最大許容値は ST02 の 3 つのフィールドの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="75752-118">The maximum allowable value for the transaction set control number depends upon the values of the three fields in ST02.</span></span> <span data-ttu-id="75752-119">最大文字数は、ST02.2 フィールドの参照番号が 9 文字、ST02.1 のプレフィックスが 8 文字、ST02.3 のサフィックスが 8 文字、3 つすべてのフィールドの組み合わせで 9 文字です。</span><span class="sxs-lookup"><span data-stu-id="75752-119">The maximum number of characters is 9 for the reference number in field ST02.2, 8 for the prefix in ST02.1 and 8 for the suffix in ST02.3, and 9 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="75752-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="75752-120">User Action</span></span>  
 <span data-ttu-id="75752-121">このエラーを解決するには、次のように、トランザクション セット制御番号の参照番号フィールド (UNH1.2) をリセットします。</span><span class="sxs-lookup"><span data-stu-id="75752-121">To resolve this error, reset the reference number field (UNH1.2) of the transaction set control number, as follows:</span></span>  
  
1.  <span data-ttu-id="75752-122">インターチェンジに対して解決されるパーティの [EDI のプロパティ] ダイアログ ボックスで、[UNG および UNH セグメントの定義] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="75752-122">In the EDI Properties dialog box for the party resolved for the interchange, open the UNG and UNH Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="75752-123">UNH1 フィールドに関連付けられている [編集] フィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="75752-123">Click the Edit field associated with the UNH1 field.</span></span>  
  
3.  <span data-ttu-id="75752-124">トランザクション セット制御番号 (UNH1.2 の参照番号) の中央のフィールドの桁数が許容値になるように、このフィールドに新しい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="75752-124">Set the middle field of the transaction set control number (the reference number in UNH1.2) to a new value such that the field has an acceptable number of digits.</span></span>