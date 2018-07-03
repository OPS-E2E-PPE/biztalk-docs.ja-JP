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
ms.openlocfilehash: 689ba342affa3ed4f246e9aa963f8ea4e22704af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992419"
---
# <a name="the-batch-element-exceeded-the-maximum-configured-character-count"></a><span data-ttu-id="12f3a-102">バッチ要素の文字数が、構成されている最大文字数を超えました</span><span class="sxs-lookup"><span data-stu-id="12f3a-102">The batch element exceeded the maximum configured character count</span></span>
## <a name="details"></a><span data-ttu-id="12f3a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="12f3a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="12f3a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="12f3a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="12f3a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="12f3a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="12f3a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="12f3a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="12f3a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="12f3a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="12f3a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="12f3a-108"> EDI</span></span> |
|    <span data-ttu-id="12f3a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="12f3a-109">Component</span></span>    |                                    <span data-ttu-id="12f3a-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="12f3a-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="12f3a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="12f3a-111">Symbolic Name</span></span>  |                             <span data-ttu-id="12f3a-112">MessageExceededCharacterCount</span><span class="sxs-lookup"><span data-stu-id="12f3a-112">MessageExceededCharacterCount</span></span>                              |
|  <span data-ttu-id="12f3a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="12f3a-113">Message Text</span></span>   |           <span data-ttu-id="12f3a-114">バッチ要素の文字数が、構成されている最大文字数を超えました</span><span class="sxs-lookup"><span data-stu-id="12f3a-114">The batch element exceeded the maximum configured character count</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="12f3a-115">説明</span><span class="sxs-lookup"><span data-stu-id="12f3a-115">Explanation</span></span>  
 <span data-ttu-id="12f3a-116">このエラー/警告/情報イベントは、バッチ処理オーケストレーションによって取得されたバッチ要素の文字数が、バッチのリリース条件の "インターチェンジ内の最大文字数" プロパティで指定された文字数を超えているため、バッチ処理オーケストレーションが、バッチ化されたインターチェンジを生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="12f3a-116">This Error/Warning/Information event indicates that the batching orchestration could not generate the batched interchange because the number of characters in a batch element picked up by the batching orchestration exceeds the number of characters specified by the "Maximum number of characters in an interchange" property of the batch release criteria.</span></span> <span data-ttu-id="12f3a-117">このエラー メッセージを生成するバッチ要素は、バッチ用に取得される最初のバッチ要素ではなく、最初の要素が既にバッチ化された後のバッチ要素です。</span><span class="sxs-lookup"><span data-stu-id="12f3a-117">The batch element that generates this error message will not be the first batch element picked up for a batch, but a batch element after the first element has already been batched.</span></span> <span data-ttu-id="12f3a-118">最大値と比較する文字数には、エンベロープ内の文字数は含まれません。</span><span class="sxs-lookup"><span data-stu-id="12f3a-118">Note that the number of characters compared to the maximum does not include the number of characters in the envelope.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="12f3a-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="12f3a-119">User Action</span></span>  
 <span data-ttu-id="12f3a-120">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="12f3a-120">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="12f3a-121">インターチェンジの受信者となるパーティに対して、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジのバッチ作成用の設定] ページで "インターチェンジ内の最大文字数" プロパティを大きくします。</span><span class="sxs-lookup"><span data-stu-id="12f3a-121">Increase the "Maximum number of characters in an interchange" property in the Interchange Batch Creation Settings Page of the EDI Properties dialog box for the party as interchange receiver.</span></span> <span data-ttu-id="12f3a-122">これを行うには、オーケストレーション インスタンスを停止し、プロパティの最大文字数を大きくしてから、オーケストレーション インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12f3a-122">To do so, you must stop the orchestration instance, increase the maximum number of characters in the property, and then restart the orchestration instance.</span></span>  
  
2.  <span data-ttu-id="12f3a-123">送信者が最大文字数よりも文字数の少ないトランザクション セットを送信するようにします。</span><span class="sxs-lookup"><span data-stu-id="12f3a-123">Have the sender send transaction sets that have fewer characters than the maximum number of characters.</span></span>