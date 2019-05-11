---
title: グループの受信者設定がバッチのアグリーメント構成されていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57b205e9-aaab-43d1-b373-17d206957814
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa5b6e201ffc3321920e23129adf9073589c25f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394126"
---
# <a name="the-group-receiver-settings-are-not-configured-for-agreement-of-batch"></a><span data-ttu-id="46729-102">グループの受信者設定がバッチのアグリーメント構成されていません</span><span class="sxs-lookup"><span data-stu-id="46729-102">The group receiver settings are not configured for agreement of batch</span></span>
## <a name="details"></a><span data-ttu-id="46729-103">詳細</span><span class="sxs-lookup"><span data-stu-id="46729-103">Details</span></span>  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="46729-104">製品名</span><span class="sxs-lookup"><span data-stu-id="46729-104">Product Name</span></span>   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="46729-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="46729-105">Product Version</span></span> |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    <span data-ttu-id="46729-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="46729-106">Event ID</span></span>     |                                                                  -                                                                  |
|  <span data-ttu-id="46729-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="46729-107">Event Source</span></span>   |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="46729-108">EDI</span><span class="sxs-lookup"><span data-stu-id="46729-108">EDI</span></span>                        |
|    <span data-ttu-id="46729-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="46729-109">Component</span></span>    |                                                           <span data-ttu-id="46729-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="46729-110">Batching Engine</span></span>                                                           |
|  <span data-ttu-id="46729-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="46729-111">Symbolic Name</span></span>  |                                                      <span data-ttu-id="46729-112">GroupReceiverNotSelected</span><span class="sxs-lookup"><span data-stu-id="46729-112">GroupReceiverNotSelected</span></span>                                                       |
|  <span data-ttu-id="46729-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="46729-113">Message Text</span></span>   | <span data-ttu-id="46729-114">グループの受信者設定がバッチのアグリーメント構成されていない{0}します。</span><span class="sxs-lookup"><span data-stu-id="46729-114">The group receiver settings are not configured for agreement of batch {0}.</span></span> <span data-ttu-id="46729-115">これは、バッチ処理を続行する前に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46729-115">This needs to be configured before batching can proceed.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="46729-116">説明</span><span class="sxs-lookup"><span data-stu-id="46729-116">Explanation</span></span>  
 <span data-ttu-id="46729-117">このエラー/警告/情報イベントは、2 つの条件のいずれかが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="46729-117">This Error/Warning/Information event indicates that one of two conditions has occurred:</span></span>  
  
-   <span data-ttu-id="46729-118">バッチ処理オーケストレーションは、エンコードの構文を含む UNB1.1 フィールド (EDIFACT でエンコードされたインターチェンジ) に対してが設定されていないため、受信したバッチ要素を検証できませんでした。</span><span class="sxs-lookup"><span data-stu-id="46729-118">The batching orchestration could not validate a batch element that it has received because the UNB1.1 field (for an EDIFACT-encoded interchange) that contains the encoding syntax was not set.</span></span>  
  
-   <span data-ttu-id="46729-119">ヘッダーのプロパティが完了しなかったために、バッチ処理オーケストレーションは、バッチ要素のエンベロープ設定を作成できませんでした (x12 ISA、GS、および ST プロパティ インターチェンジまたは EDIFACT インターチェンジの UNA、UNB、UNG、および UNH プロパティ)。</span><span class="sxs-lookup"><span data-stu-id="46729-119">The batching orchestration could not create the envelope settings for the batch element because the header properties were not complete (ISA, GS, and ST properties for an X12 interchange or UNA, UNB, UNG, and UNH properties for an EDIFACT interchange).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46729-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="46729-120">User Action</span></span>  
 <span data-ttu-id="46729-121">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="46729-121">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="46729-122">バッチ処理オーケストレーションは、エンコードの構文が設定されていないため、受信したバッチ要素を検証できませんだった場合、は、EDI のプロパティ ダイアログ ボックスの UNB セグメントの定義 ページで、UNB1.1 フィールドのエンコードの構文を設定します。</span><span class="sxs-lookup"><span data-stu-id="46729-122">If the batching orchestration could not validate a batch element that it has received because the encoding syntax was not set, set the encoding syntax for the UNB1.1 field in the UNB Segment Definition page of the EDI Properties dialog box.</span></span>  
  
-   <span data-ttu-id="46729-123">場合は、バッチ処理オーケストレーションは、ヘッダーのプロパティが完了しなかったために、バッチ要素のエンベロープ設定を作成できませんでした、確認のインターチェンジが x12 ISA、GS、および ST プロパティ セットまたは UNA、UNB、UNG、および UNH プロパティをEDIFACT インターチェンジが設定されます。</span><span class="sxs-lookup"><span data-stu-id="46729-123">If the batching orchestration could not create the envelope settings for the batch element because the header properties were not complete, ensure that the ISA, GS, and ST properties for an X12 interchange are set or that the UNA, UNB, UNG, and UNH properties for an EDIFACT interchange are set.</span></span>