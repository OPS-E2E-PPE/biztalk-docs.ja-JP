---
title: 区切り記号が一意で、フィールドではないと、コンポーネントの区切り記号が同じ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cba15b30-b07d-4caa-8c43-6b4d8c4ca81c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd6439bd307ec922b9dbdd5761f61e9e3ad557f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979419"
---
# <a name="delimiters-are-not-unique-field-and-component-separator-are-the-same"></a><span data-ttu-id="7b9d1-102">区切り記号が一意ではなく、フィールドとコンポーネントの区切り記号が同じです</span><span class="sxs-lookup"><span data-stu-id="7b9d1-102">Delimiters are not unique, field and component separator are the same</span></span>
## <a name="details"></a><span data-ttu-id="7b9d1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7b9d1-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7b9d1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7b9d1-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7b9d1-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7b9d1-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7b9d1-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7b9d1-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7b9d1-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7b9d1-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7b9d1-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7b9d1-108"> EDI</span></span> |
|    <span data-ttu-id="7b9d1-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7b9d1-109">Component</span></span>    |                                       <span data-ttu-id="7b9d1-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="7b9d1-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="7b9d1-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7b9d1-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="7b9d1-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7b9d1-112">Message Text</span></span>   |         <span data-ttu-id="7b9d1-113">区切り記号が一意ではなく、フィールドとコンポーネントの区切り記号が同じです</span><span class="sxs-lookup"><span data-stu-id="7b9d1-113">Delimiters are not unique, field and component separator are the same</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="7b9d1-114">説明</span><span class="sxs-lookup"><span data-stu-id="7b9d1-114">Explanation</span></span>  
 <span data-ttu-id="7b9d1-115">このエラー/警告/情報イベントは、データ要素とコンポーネントの区切り記号の値が同じだったため、EDI 送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="7b9d1-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because the data element and component separators were the same value.</span></span> <span data-ttu-id="7b9d1-116">X12 インターチェンジでは、データ要素の区切り記号は ISA セグメントの 4 番目の文字の位置にある文字であり、コンポーネントの区切り記号は ISA16 フィールドの文字です。</span><span class="sxs-lookup"><span data-stu-id="7b9d1-116">In an X12 interchange, the data element separator is the character in the fourth character position of the ISA segment and the component separator is the character in the ISA16 field.</span></span> <span data-ttu-id="7b9d1-117">EDIFACT インターチェンジでは、データ要素の区切り記号は UNA2 フィールドの文字であり、コンポーネントの区切り記号は UNA1 フィールドの文字です。</span><span class="sxs-lookup"><span data-stu-id="7b9d1-117">In an EDIFACT interchange, the data element separator is the character in the UNA2 field and the component separator is the character in the UNA1 field.</span></span> <span data-ttu-id="7b9d1-118">保存されたバッチ シナリオでは、同じ値を持つ 2 つの区切り記号が存在する (ただし、エラー状態を引き起こす) 可能性があります。つまり、インターチェンジがパススルー送信を経由して受信され、次にメッセージ ボックス内の XML ファイルとして送信ポートによって取得される場合です。</span><span class="sxs-lookup"><span data-stu-id="7b9d1-118">Two separators with the same value can occur (but will cause an error condition) in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b9d1-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7b9d1-119">User Action</span></span>  
 <span data-ttu-id="7b9d1-120">このエラーを解決するには、データ要素、またはコンポーネントの区切り記号のどちらかの値を変更し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="7b9d1-120">To resolve this error, change the value of either the data element or component separators, and then resubmit the interchange.</span></span>