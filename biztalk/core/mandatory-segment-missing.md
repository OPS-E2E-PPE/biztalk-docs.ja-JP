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
ms.openlocfilehash: e2bc9775da2fcbef756774c576074b471e808484
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977091"
---
# <a name="mandatory-segment-missing"></a><span data-ttu-id="22005-102">必須のセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="22005-102">Mandatory Segment Missing</span></span>
## <a name="details"></a><span data-ttu-id="22005-103">詳細</span><span class="sxs-lookup"><span data-stu-id="22005-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="22005-104">製品名</span><span class="sxs-lookup"><span data-stu-id="22005-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="22005-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="22005-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="22005-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="22005-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="22005-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="22005-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="22005-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="22005-108"> EDI</span></span> |
|    <span data-ttu-id="22005-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="22005-109">Component</span></span>    |                                       <span data-ttu-id="22005-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="22005-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="22005-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="22005-111">Symbolic Name</span></span>  |                         <span data-ttu-id="22005-112">X12MandatorySegmentMissingDescription</span><span class="sxs-lookup"><span data-stu-id="22005-112">X12MandatorySegmentMissingDescription</span></span>                          |
|  <span data-ttu-id="22005-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="22005-113">Message Text</span></span>   |                               <span data-ttu-id="22005-114">必須のセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="22005-114">Mandatory Segment Missing</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="22005-115">説明</span><span class="sxs-lookup"><span data-stu-id="22005-115">Explanation</span></span>  
 <span data-ttu-id="22005-116">このエラー/警告/情報イベントは、メッセージ スキーマで要求されている (minOccurs が 0 より大きい) セグメントがインターチェンジに含まれていなかったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="22005-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a segment that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="22005-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="22005-117">User Action</span></span>  
 <span data-ttu-id="22005-118">このエラーを解決するには、メッセージ スキーマで要求されているすべてのセグメントがインターチェンジに含まれていることを確認し、メッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="22005-118">To resolve this error, make sure that the interchange contains all segments required by the message schema, and then have the message resent.</span></span>