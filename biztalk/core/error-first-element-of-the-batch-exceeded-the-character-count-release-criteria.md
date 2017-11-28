---
title: "バッチの最初の要素を文字数のリリース条件セットを超えています |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4b06f8f-247d-4e93-8c4e-5e86e4ad70c9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 746fbfabb2fe411310735f66c6d8a8398a94a5dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-first-element-of-the-batch-exceeded-the-character-count-release-criteria-set"></a><span data-ttu-id="f5548-102">バッチの最初の要素が、文字数のリリース条件セットで指定されている文字数を超えました</span><span class="sxs-lookup"><span data-stu-id="f5548-102">The first element of the batch exceeded the character count release criteria set</span></span>
## <a name="details"></a><span data-ttu-id="f5548-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f5548-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5548-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f5548-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f5548-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f5548-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f5548-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f5548-106">Event ID</span></span>|-|  
|<span data-ttu-id="f5548-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f5548-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f5548-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f5548-108"> EDI</span></span>|  
|<span data-ttu-id="f5548-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f5548-109">Component</span></span>|<span data-ttu-id="f5548-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="f5548-110">Batching Engine</span></span>|  
|<span data-ttu-id="f5548-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f5548-111">Symbolic Name</span></span>|<span data-ttu-id="f5548-112">FirstElementExceededCharCount</span><span class="sxs-lookup"><span data-stu-id="f5548-112">FirstElementExceededCharCount</span></span>|  
|<span data-ttu-id="f5548-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f5548-113">Message Text</span></span>|<span data-ttu-id="f5548-114">バッチの最初の要素が、文字数のリリース条件セットで指定されている文字数を超えました。</span><span class="sxs-lookup"><span data-stu-id="f5548-114">The first element of the batch exceeded the character count release criteria set.</span></span> <span data-ttu-id="f5548-115">このメッセージを処理できるように、文字数のリリース条件を変更してください。</span><span class="sxs-lookup"><span data-stu-id="f5548-115">Please change the character count release criteria to be able to process this message.</span></span> <span data-ttu-id="f5548-116">設定の変更後、バッチ処理システムにメッセージを再送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5548-116">The message will need to be resent to the batching system after the settings are modified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f5548-117">説明</span><span class="sxs-lookup"><span data-stu-id="f5548-117">Explanation</span></span>  
 <span data-ttu-id="f5548-118">このエラー/警告/情報イベントは、バッチ処理オーケストレーションによって取得された最初のバッチ要素の文字数が、バッチのリリース条件の "インターチェンジ内の最大文字数" プロパティで指定された文字数を超えていたため、バッチ処理オーケストレーションが、バッチ化されたインターチェンジを生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f5548-118">This Error/Warning/Information event indicates that the batching orchestration could not generate the batched interchange because the number of characters in the first batch element picked up by the batching orchestration exceeded the number of characters specified by the "Maximum number of characters in an interchange" property of the batch release criteria.</span></span> <span data-ttu-id="f5548-119">最大値と比較する文字数には、エンベロープ内の文字数は含まれません。</span><span class="sxs-lookup"><span data-stu-id="f5548-119">Note that the number of characters compared to the maximum does not include the number of characters in the envelope.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f5548-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f5548-120">User Action</span></span>  
 <span data-ttu-id="f5548-121">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f5548-121">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="f5548-122">インターチェンジの受信者となるパーティに対して、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジのバッチ作成用の設定] ページで "インターチェンジ内の最大文字数" プロパティを大きくします。</span><span class="sxs-lookup"><span data-stu-id="f5548-122">Increase the "Maximum number of characters in an interchange" property in the Interchange Batch Creation Settings Page of the EDI Properties dialog box for the party as interchange receiver.</span></span> <span data-ttu-id="f5548-123">これを行うには、オーケストレーション インスタンスを停止し、プロパティの最大文字数を大きくしてから、オーケストレーション インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5548-123">To do so, you must stop the orchestration instance, increase the maximum number of characters in the property, and then restart the orchestration instance.</span></span> <span data-ttu-id="f5548-124">送信者にメッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="f5548-124">Have the sender resend the message.</span></span>  
  
2.  <span data-ttu-id="f5548-125">送信者が最大文字数よりも文字数の少ないトランザクション セットを送信するようにします。</span><span class="sxs-lookup"><span data-stu-id="f5548-125">Have the sender send transaction sets that have fewer characters than the maximum number of characters.</span></span>