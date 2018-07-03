---
title: 無効なセグメント終端記号 |Microsoft Docs
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
ms.openlocfilehash: 0249c16bf495f9103759ec4eba9a9c6776b87ca2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001827"
---
# <a name="invalid-segment-terminator"></a><span data-ttu-id="1e08b-102">セグメント終端記号が無効です</span><span class="sxs-lookup"><span data-stu-id="1e08b-102">Invalid Segment Terminator</span></span>
## <a name="details"></a><span data-ttu-id="1e08b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1e08b-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="1e08b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1e08b-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="1e08b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1e08b-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="1e08b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1e08b-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="1e08b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1e08b-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1e08b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1e08b-108"> EDI</span></span> |
|    <span data-ttu-id="1e08b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1e08b-109">Component</span></span>    |                                       <span data-ttu-id="1e08b-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="1e08b-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="1e08b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1e08b-111">Symbolic Name</span></span>  |                       <span data-ttu-id="1e08b-112">X12Ta1InvalidSegmentTerminatorDescription</span><span class="sxs-lookup"><span data-stu-id="1e08b-112">X12Ta1InvalidSegmentTerminatorDescription</span></span>                        |
|  <span data-ttu-id="1e08b-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1e08b-113">Message Text</span></span>   |                               <span data-ttu-id="1e08b-114">セグメント終端記号が無効です</span><span class="sxs-lookup"><span data-stu-id="1e08b-114">Invalid Segment Terminator</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="1e08b-115">説明</span><span class="sxs-lookup"><span data-stu-id="1e08b-115">Explanation</span></span>  
 <span data-ttu-id="1e08b-116">このエラー/警告/情報イベントは、インターチェンジ内のセグメント終端記号の値が ASCII 文字セット内の文字に制限されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="1e08b-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the segment terminator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="1e08b-117">X12 では、セグメント終端記号は ISA セグメントの最後の文字として定義されます。</span><span class="sxs-lookup"><span data-stu-id="1e08b-117">In X12, the segment terminator is defined as the last character in the ISA segment.</span></span> <span data-ttu-id="1e08b-118">EDIFACT では、セグメント終端記号は UNA6 フィールドです。</span><span class="sxs-lookup"><span data-stu-id="1e08b-118">In EDIFACT, the segment terminator is the UNA6 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1e08b-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1e08b-119">User Action</span></span>  
 <span data-ttu-id="1e08b-120">このエラーを解決するには、セグメント終端記号 (X12 インターチェンジでは ISA セグメントの最後の文字、または EDIFACT インターチェンジの UNA6 フィールド) が、ASCII 文字セットの文字に制限されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e08b-120">To resolve this error, make sure that the segment terminator (the last character of the ISA segment in an X12 interchange or the UNA6 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="1e08b-121">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="1e08b-121">Have the interchange resent.</span></span>