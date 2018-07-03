---
title: 無効なデータ要素区切り記号 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76c50a8b-274f-4f4a-9826-4f6f8123e9d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fbc355c6a89bd69364200dcd20ca257fc9dc54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972595"
---
# <a name="invalid-data-element-separator"></a><span data-ttu-id="bd67c-102">データ要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="bd67c-102">Invalid Data Element Separator</span></span>
## <a name="details"></a><span data-ttu-id="bd67c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bd67c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="bd67c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bd67c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="bd67c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bd67c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="bd67c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bd67c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="bd67c-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bd67c-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bd67c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="bd67c-108"> EDI</span></span> |
|    <span data-ttu-id="bd67c-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bd67c-109">Component</span></span>    |                                       <span data-ttu-id="bd67c-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="bd67c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="bd67c-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bd67c-111">Symbolic Name</span></span>  |                      <span data-ttu-id="bd67c-112">X12Ta1InvalidDataElementSeparatorDescription</span><span class="sxs-lookup"><span data-stu-id="bd67c-112">X12Ta1InvalidDataElementSeparatorDescription</span></span>                      |
|  <span data-ttu-id="bd67c-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bd67c-113">Message Text</span></span>   |                             <span data-ttu-id="bd67c-114">データ要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="bd67c-114">Invalid Data Element Separator</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="bd67c-115">説明</span><span class="sxs-lookup"><span data-stu-id="bd67c-115">Explanation</span></span>  
 <span data-ttu-id="bd67c-116">このエラー/警告/情報イベントは、インターチェンジ内のセグメント終端記号の値が ASCII 文字セット内の文字に制限されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="bd67c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the segment terminator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="bd67c-117">X12 で、セグメント終端記号は ISA セグメントの 4 番目の文字として定義されます。</span><span class="sxs-lookup"><span data-stu-id="bd67c-117">In X12, the segment terminator is defined as the fourth character in the ISA segment.</span></span> <span data-ttu-id="bd67c-118">EDIFACT では、セグメント終端記号は UNA2 フィールドです。</span><span class="sxs-lookup"><span data-stu-id="bd67c-118">In EDIFACT, the segment terminator is the UNA2 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd67c-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bd67c-119">User Action</span></span>  
 <span data-ttu-id="bd67c-120">このエラーを解決するには、セグメント終端記号 (X12 インターチェンジの ISA セグメントの 4 番目の文字、または EDIFACT インターチェンジの UNA2 フィールド) が、ASCII 文字セットの文字に制限されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd67c-120">To resolve this error, make sure that the segment terminator (the fourth character of the ISA segment in an X12 interchange or the UNA2 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="bd67c-121">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="bd67c-121">Have the interchange resent.</span></span>