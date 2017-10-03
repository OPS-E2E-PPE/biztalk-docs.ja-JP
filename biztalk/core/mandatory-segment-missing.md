---
title: "必須セグメントがない |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e459a22-8de5-426a-a46a-1d0ab72b532d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1250499f127aaa09e21269b894ed7bd51bd6a6ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mandatory-segment-missing"></a><span data-ttu-id="29a7a-102">必須のセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="29a7a-102">Mandatory Segment Missing</span></span>
## <a name="details"></a><span data-ttu-id="29a7a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="29a7a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29a7a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="29a7a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="29a7a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="29a7a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="29a7a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="29a7a-106">Event ID</span></span>|-|  
|<span data-ttu-id="29a7a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="29a7a-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="29a7a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="29a7a-108"> EDI</span></span>|  
|<span data-ttu-id="29a7a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="29a7a-109">Component</span></span>|<span data-ttu-id="29a7a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="29a7a-110">EDI Engine</span></span>|  
|<span data-ttu-id="29a7a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="29a7a-111">Symbolic Name</span></span>|<span data-ttu-id="29a7a-112">X12MandatorySegmentMissingDescription</span><span class="sxs-lookup"><span data-stu-id="29a7a-112">X12MandatorySegmentMissingDescription</span></span>|  
|<span data-ttu-id="29a7a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="29a7a-113">Message Text</span></span>|<span data-ttu-id="29a7a-114">必須のセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="29a7a-114">Mandatory Segment Missing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="29a7a-115">説明</span><span class="sxs-lookup"><span data-stu-id="29a7a-115">Explanation</span></span>  
 <span data-ttu-id="29a7a-116">このエラー/警告/情報イベントは、メッセージ スキーマで要求されている (minOccurs が 0 より大きい) セグメントがインターチェンジに含まれていなかったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="29a7a-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a segment that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29a7a-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="29a7a-117">User Action</span></span>  
 <span data-ttu-id="29a7a-118">このエラーを解決するには、メッセージ スキーマで要求されているすべてのセグメントがインターチェンジに含まれていることを確認し、メッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="29a7a-118">To resolve this error, make sure that the interchange contains all segments required by the message schema, and then have the message resent.</span></span>