---
title: "セグメントにあるデータ要素エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 469622e2-6500-4f55-ab53-f8d89ee0a978
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c8c9e43bfe0a733a3e95b7812195a0b7f3990c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="segment-has-data-element-errors"></a><span data-ttu-id="ecb34-102">セグメントは、データ要素エラーには</span><span class="sxs-lookup"><span data-stu-id="ecb34-102">Segment has data element errors</span></span>
## <a name="details"></a><span data-ttu-id="ecb34-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ecb34-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecb34-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ecb34-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ecb34-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ecb34-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ecb34-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ecb34-106">Event ID</span></span>|-|  
|<span data-ttu-id="ecb34-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ecb34-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ecb34-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ecb34-108"> EDI</span></span>|  
|<span data-ttu-id="ecb34-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ecb34-109">Component</span></span>|<span data-ttu-id="ecb34-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ecb34-110">EDI Engine</span></span>|  
|<span data-ttu-id="ecb34-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ecb34-111">Symbolic Name</span></span>|<span data-ttu-id="ecb34-112">X12SegmentHasDataElementErrorsDescription</span><span class="sxs-lookup"><span data-stu-id="ecb34-112">X12SegmentHasDataElementErrorsDescription</span></span>|  
|<span data-ttu-id="ecb34-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ecb34-113">Message Text</span></span>|<span data-ttu-id="ecb34-114">セグメントでデータ要素エラーが発生しています</span><span class="sxs-lookup"><span data-stu-id="ecb34-114">Segment Has Data Element Errors</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ecb34-115">説明</span><span class="sxs-lookup"><span data-stu-id="ecb34-115">Explanation</span></span>  
 <span data-ttu-id="ecb34-116">このエラー/警告/情報イベントは、ドキュメント スキーマに準拠していないデータ要素がインターチェンジ内のセグメントに含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ecb34-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained segments that included data elements that did not conform to the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ecb34-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ecb34-117">User Action</span></span>  
 <span data-ttu-id="ecb34-118">このエラーを解決するには、インターチェンジ内のデータ要素がドキュメント スキーマに準拠していることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="ecb34-118">To resolve this error, make sure that the data elements in the interchange conform to the document schema, and then resend the interchange.</span></span>