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
ms.openlocfilehash: 0ebd39a1711f4e1af15735f5a6d2e9523c490036
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330474"
---
# <a name="invalid-segment-terminator"></a><span data-ttu-id="a9b96-102">セグメント終端記号が無効です</span><span class="sxs-lookup"><span data-stu-id="a9b96-102">Invalid Segment Terminator</span></span>
## <a name="details"></a><span data-ttu-id="a9b96-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a9b96-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a9b96-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a9b96-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a9b96-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a9b96-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a9b96-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a9b96-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a9b96-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a9b96-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a9b96-108">EDI</span><span class="sxs-lookup"><span data-stu-id="a9b96-108">EDI</span></span> |
|    <span data-ttu-id="a9b96-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a9b96-109">Component</span></span>    |                                       <span data-ttu-id="a9b96-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="a9b96-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="a9b96-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a9b96-111">Symbolic Name</span></span>  |                       <span data-ttu-id="a9b96-112">X12Ta1InvalidSegmentTerminatorDescription</span><span class="sxs-lookup"><span data-stu-id="a9b96-112">X12Ta1InvalidSegmentTerminatorDescription</span></span>                        |
|  <span data-ttu-id="a9b96-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a9b96-113">Message Text</span></span>   |                               <span data-ttu-id="a9b96-114">セグメント終端記号が無効です</span><span class="sxs-lookup"><span data-stu-id="a9b96-114">Invalid Segment Terminator</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="a9b96-115">説明</span><span class="sxs-lookup"><span data-stu-id="a9b96-115">Explanation</span></span>  
 <span data-ttu-id="a9b96-116">このエラー/警告/情報イベントは、インターチェンジ内のセグメント終端記号の値が ASCII 文字セット内の文字に制限されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a9b96-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the segment terminator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="a9b96-117">X12 では、セグメント終端記号は ISA セグメントの最後の文字として定義されます。</span><span class="sxs-lookup"><span data-stu-id="a9b96-117">In X12, the segment terminator is defined as the last character in the ISA segment.</span></span> <span data-ttu-id="a9b96-118">EDIFACT では、セグメント終端記号は UNA6 フィールドです。</span><span class="sxs-lookup"><span data-stu-id="a9b96-118">In EDIFACT, the segment terminator is the UNA6 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9b96-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a9b96-119">User Action</span></span>  
 <span data-ttu-id="a9b96-120">このエラーを解決するには、セグメント終端記号 (X12 インターチェンジでは ISA セグメントの最後の文字、または EDIFACT インターチェンジの UNA6 フィールド) が、ASCII 文字セットの文字に制限されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9b96-120">To resolve this error, make sure that the segment terminator (the last character of the ISA segment in an X12 interchange or the UNA6 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="a9b96-121">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="a9b96-121">Have the interchange resent.</span></span>