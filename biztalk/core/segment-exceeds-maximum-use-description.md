---
title: セグメントは、最大使用説明を超えています |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4e1704a-5d49-4549-af50-d1a89a1e70f0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f5e5a0ae590be850a4560324814c756d51e9fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269434"
---
# <a name="segment-exceeds-maximum-use-description"></a><span data-ttu-id="24b7a-102">セグメントが説明されている最大使用数を超えています</span><span class="sxs-lookup"><span data-stu-id="24b7a-102">Segment Exceeds Maximum Use Description</span></span>
## <a name="details"></a><span data-ttu-id="24b7a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="24b7a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24b7a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="24b7a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="24b7a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="24b7a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="24b7a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="24b7a-106">Event ID</span></span>|-|  
|<span data-ttu-id="24b7a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="24b7a-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="24b7a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="24b7a-108"> EDI</span></span>|  
|<span data-ttu-id="24b7a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="24b7a-109">Component</span></span>|<span data-ttu-id="24b7a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="24b7a-110">EDI Engine</span></span>|  
|<span data-ttu-id="24b7a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="24b7a-111">Symbolic Name</span></span>|<span data-ttu-id="24b7a-112">X12SegmentExceedsMaximumUseDescription</span><span class="sxs-lookup"><span data-stu-id="24b7a-112">X12SegmentExceedsMaximumUseDescription</span></span>|  
|<span data-ttu-id="24b7a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="24b7a-113">Message Text</span></span>|<span data-ttu-id="24b7a-114">セグメントが説明されている最大使用数を超えています</span><span class="sxs-lookup"><span data-stu-id="24b7a-114">Segment Exceeds Maximum Use Description</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="24b7a-115">説明</span><span class="sxs-lookup"><span data-stu-id="24b7a-115">Explanation</span></span>  
 <span data-ttu-id="24b7a-116">このエラー/警告/情報イベントは、スキーマで許可されているよりも多くの数のセグメントがインターチェンジに含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="24b7a-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained more instances of a segment than allowed by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="24b7a-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="24b7a-117">User Action</span></span>  
 <span data-ttu-id="24b7a-118">このエラーを解決するには、許可されている最大数を超える数のセグメントがインターチェンジに含まれていないことを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="24b7a-118">To resolve this error, make sure that the interchange does not have more than the maximum allowed number of segments, and then resend the interchange.</span></span>