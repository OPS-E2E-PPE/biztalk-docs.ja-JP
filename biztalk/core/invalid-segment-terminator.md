---
title: 無効なセグメント終端記号 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 508dac21-4731-439d-bf4a-a50858f1ffa0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47d5a79af0616baed6d401b4df7b68f5f596ef07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257250"
---
# <a name="invalid-segment-terminator"></a><span data-ttu-id="b9104-102">セグメント終端記号が無効です</span><span class="sxs-lookup"><span data-stu-id="b9104-102">Invalid Segment Terminator</span></span>
## <a name="details"></a><span data-ttu-id="b9104-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b9104-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b9104-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b9104-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b9104-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b9104-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b9104-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b9104-106">Event ID</span></span>|-|  
|<span data-ttu-id="b9104-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b9104-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b9104-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="b9104-108"> EDI</span></span>|  
|<span data-ttu-id="b9104-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b9104-109">Component</span></span>|<span data-ttu-id="b9104-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="b9104-110">EDI Engine</span></span>|  
|<span data-ttu-id="b9104-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b9104-111">Symbolic Name</span></span>|<span data-ttu-id="b9104-112">X12Ta1InvalidSegmentTerminatorDescription</span><span class="sxs-lookup"><span data-stu-id="b9104-112">X12Ta1InvalidSegmentTerminatorDescription</span></span>|  
|<span data-ttu-id="b9104-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b9104-113">Message Text</span></span>|<span data-ttu-id="b9104-114">セグメント終端記号が無効です</span><span class="sxs-lookup"><span data-stu-id="b9104-114">Invalid Segment Terminator</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b9104-115">説明</span><span class="sxs-lookup"><span data-stu-id="b9104-115">Explanation</span></span>  
 <span data-ttu-id="b9104-116">このエラー/警告/情報イベントは、インターチェンジ内のセグメント終端記号の値が ASCII 文字セット内の文字に制限されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b9104-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the segment terminator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="b9104-117">X12 では、セグメント終端記号は ISA セグメントの最後の文字として定義されます。</span><span class="sxs-lookup"><span data-stu-id="b9104-117">In X12, the segment terminator is defined as the last character in the ISA segment.</span></span> <span data-ttu-id="b9104-118">EDIFACT では、セグメント終端記号は UNA6 フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b9104-118">In EDIFACT, the segment terminator is the UNA6 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b9104-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b9104-119">User Action</span></span>  
 <span data-ttu-id="b9104-120">このエラーを解決するには、セグメント終端記号 (X12 インターチェンジでは ISA セグメントの最後の文字、または EDIFACT インターチェンジの UNA6 フィールド) が、ASCII 文字セットの文字に制限されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9104-120">To resolve this error, make sure that the segment terminator (the last character of the ISA segment in an X12 interchange or the UNA6 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="b9104-121">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="b9104-121">Have the interchange resent.</span></span>