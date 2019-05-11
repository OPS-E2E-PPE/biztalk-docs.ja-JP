---
title: 必須のセグメントがありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e459a22-8de5-426a-a46a-1d0ab72b532d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05a2c3a1ed86e57a307c5b7e335febff87ce53cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380134"
---
# <a name="mandatory-segment-missing"></a><span data-ttu-id="b2fb8-102">必須のセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="b2fb8-102">Mandatory Segment Missing</span></span>
## <a name="details"></a><span data-ttu-id="b2fb8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b2fb8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="b2fb8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b2fb8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="b2fb8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b2fb8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="b2fb8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b2fb8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="b2fb8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b2fb8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b2fb8-108">EDI</span><span class="sxs-lookup"><span data-stu-id="b2fb8-108">EDI</span></span> |
|    <span data-ttu-id="b2fb8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b2fb8-109">Component</span></span>    |                                       <span data-ttu-id="b2fb8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="b2fb8-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="b2fb8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b2fb8-111">Symbolic Name</span></span>  |                         <span data-ttu-id="b2fb8-112">X12MandatorySegmentMissingDescription</span><span class="sxs-lookup"><span data-stu-id="b2fb8-112">X12MandatorySegmentMissingDescription</span></span>                          |
|  <span data-ttu-id="b2fb8-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b2fb8-113">Message Text</span></span>   |                               <span data-ttu-id="b2fb8-114">必須のセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="b2fb8-114">Mandatory Segment Missing</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="b2fb8-115">説明</span><span class="sxs-lookup"><span data-stu-id="b2fb8-115">Explanation</span></span>  
 <span data-ttu-id="b2fb8-116">このエラー/警告/情報イベントは、メッセージ スキーマで要求されている (minOccurs が 0 より大きい) セグメントがインターチェンジに含まれていなかったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b2fb8-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a segment that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2fb8-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b2fb8-117">User Action</span></span>  
 <span data-ttu-id="b2fb8-118">このエラーを解決するには、メッセージ スキーマで要求されているすべてのセグメントがインターチェンジに含まれていることを確認し、メッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="b2fb8-118">To resolve this error, make sure that the interchange contains all segments required by the message schema, and then have the message resent.</span></span>