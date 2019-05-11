---
title: バッチ要素が構成されている文字の最大回数を超過しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ad12733-295a-43ba-8147-34c8716c2d37
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c4f784d8edb5542992a7df4d7de14e018d861a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298842"
---
# <a name="the-batch-element-exceeded-the-maximum-configured-character-count"></a><span data-ttu-id="a69d3-102">バッチ要素の文字数が、構成されている最大文字数を超えました</span><span class="sxs-lookup"><span data-stu-id="a69d3-102">The batch element exceeded the maximum configured character count</span></span>
## <a name="details"></a><span data-ttu-id="a69d3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a69d3-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a69d3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a69d3-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a69d3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a69d3-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a69d3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a69d3-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a69d3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a69d3-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a69d3-108">EDI</span><span class="sxs-lookup"><span data-stu-id="a69d3-108">EDI</span></span> |
|    <span data-ttu-id="a69d3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a69d3-109">Component</span></span>    |                                    <span data-ttu-id="a69d3-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="a69d3-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="a69d3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a69d3-111">Symbolic Name</span></span>  |                             <span data-ttu-id="a69d3-112">MessageExceededCharacterCount</span><span class="sxs-lookup"><span data-stu-id="a69d3-112">MessageExceededCharacterCount</span></span>                              |
|  <span data-ttu-id="a69d3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a69d3-113">Message Text</span></span>   |           <span data-ttu-id="a69d3-114">バッチ要素の文字数が、構成されている最大文字数を超えました</span><span class="sxs-lookup"><span data-stu-id="a69d3-114">The batch element exceeded the maximum configured character count</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="a69d3-115">説明</span><span class="sxs-lookup"><span data-stu-id="a69d3-115">Explanation</span></span>  
 <span data-ttu-id="a69d3-116">このエラー/警告/情報イベントは、バッチ処理オーケストレーションによって取得されたバッチ要素の文字数が、バッチのリリース条件の "インターチェンジ内の最大文字数" プロパティで指定された文字数を超えているため、バッチ処理オーケストレーションが、バッチ化されたインターチェンジを生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a69d3-116">This Error/Warning/Information event indicates that the batching orchestration could not generate the batched interchange because the number of characters in a batch element picked up by the batching orchestration exceeds the number of characters specified by the "Maximum number of characters in an interchange" property of the batch release criteria.</span></span> <span data-ttu-id="a69d3-117">このエラー メッセージを生成するバッチ要素は、バッチ用に取得される最初のバッチ要素ではなく、最初の要素が既にバッチ化された後のバッチ要素です。</span><span class="sxs-lookup"><span data-stu-id="a69d3-117">The batch element that generates this error message will not be the first batch element picked up for a batch, but a batch element after the first element has already been batched.</span></span> <span data-ttu-id="a69d3-118">最大値と比較する文字数には、エンベロープ内の文字数は含まれません。</span><span class="sxs-lookup"><span data-stu-id="a69d3-118">Note that the number of characters compared to the maximum does not include the number of characters in the envelope.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a69d3-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a69d3-119">User Action</span></span>  
 <span data-ttu-id="a69d3-120">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a69d3-120">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="a69d3-121">インターチェンジの受信者となるパーティに対して、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジのバッチ作成用の設定] ページで "インターチェンジ内の最大文字数" プロパティを大きくします。</span><span class="sxs-lookup"><span data-stu-id="a69d3-121">Increase the "Maximum number of characters in an interchange" property in the Interchange Batch Creation Settings Page of the EDI Properties dialog box for the party as interchange receiver.</span></span> <span data-ttu-id="a69d3-122">これを行うには、オーケストレーション インスタンスを停止し、プロパティの最大文字数を大きくしてから、オーケストレーション インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a69d3-122">To do so, you must stop the orchestration instance, increase the maximum number of characters in the property, and then restart the orchestration instance.</span></span>  
  
2.  <span data-ttu-id="a69d3-123">送信者が最大文字数よりも文字数の少ないトランザクション セットを送信するようにします。</span><span class="sxs-lookup"><span data-stu-id="a69d3-123">Have the sender send transaction sets that have fewer characters than the maximum number of characters.</span></span>