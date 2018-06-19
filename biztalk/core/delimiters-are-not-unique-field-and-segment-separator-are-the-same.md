---
title: 区切り記号が一意ではない、フィールドとセグメントの区切り記号は、同じ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1441434a-e969-4803-8e44-c7738d9b23ed
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 440ffb1213936fba4b08a8ee478f6c141eba38fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238730"
---
# <a name="delimiters-are-not-unique-field-and-segment-separator-are-the-same"></a><span data-ttu-id="5adc4-102">区切り記号が一意ではなく、フィールドとセグメントの区切り記号が同じです</span><span class="sxs-lookup"><span data-stu-id="5adc4-102">Delimiters are not unique, field and segment separator are the same</span></span>
## <a name="details"></a><span data-ttu-id="5adc4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5adc4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5adc4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5adc4-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5adc4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5adc4-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5adc4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5adc4-106">Event ID</span></span>|-|  
|<span data-ttu-id="5adc4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5adc4-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5adc4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5adc4-108"> EDI</span></span>|  
|<span data-ttu-id="5adc4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5adc4-109">Component</span></span>|<span data-ttu-id="5adc4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="5adc4-110">EDI Engine</span></span>|  
|<span data-ttu-id="5adc4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5adc4-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="5adc4-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5adc4-112">Message Text</span></span>|<span data-ttu-id="5adc4-113">区切り記号が一意ではなく、フィールドとセグメントの区切り記号が同じです</span><span class="sxs-lookup"><span data-stu-id="5adc4-113">Delimiters are not unique, field and segment separator are the same</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5adc4-114">説明</span><span class="sxs-lookup"><span data-stu-id="5adc4-114">Explanation</span></span>  
 <span data-ttu-id="5adc4-115">このエラー/警告/情報イベントは、データ要素区切り記号とセグメント区切り記号が同じ値であったため、EDI 送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5adc4-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because the data element and segment separators were the same value.</span></span> <span data-ttu-id="5adc4-116">X12 インターチェンジでは、データ要素の区切り記号は ISA セグメントの 4 番目の文字位置にある文字であり、セグメント区切り記号は ISA セグメントの最後の文字位置にある文字です。</span><span class="sxs-lookup"><span data-stu-id="5adc4-116">In an X12 interchange, the data element separator is the character in the fourth character position of the ISA segment and the segment terminator is the character in the last character position of the ISA segment.</span></span> <span data-ttu-id="5adc4-117">EDIFACT インターチェンジでは、データ要素の区切り記号は UNA2 フィールド内の文字であり、セグメント区切り記号は UNA6 フィールド内の文字です。</span><span class="sxs-lookup"><span data-stu-id="5adc4-117">In an EDIFACT interchange, the data element separator is the character in the UNA2 field and the segment terminator is the character in the UNA6 field.</span></span> <span data-ttu-id="5adc4-118">保存されたバッチ シナリオでは、同じ値を持つ 2 つの区切り記号が存在する (ただし、エラー状態を引き起こす) 可能性があります。つまり、インターチェンジがパススルー送信を経由して受信され、次にメッセージ ボックス内の XML ファイルとして送信ポートによって取得される場合です。</span><span class="sxs-lookup"><span data-stu-id="5adc4-118">Two separators with the same value can occur (but will cause an error condition) in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5adc4-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5adc4-119">User Action</span></span>  
 <span data-ttu-id="5adc4-120">このエラーを解決するには、インターチェンジのデータ要素の区切り記号またはセグメント区切り記号のいずれかの値を変更し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="5adc4-120">To resolve this error, change the value of either the data element or segment separator in the interchange, and then resubmit the interchange.</span></span>