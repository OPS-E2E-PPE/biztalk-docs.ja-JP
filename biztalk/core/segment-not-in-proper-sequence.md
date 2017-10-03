---
title: "適切な順序ではなくセグメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f0c0fdc-10d9-4b77-a80d-b2b8571e7665
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b6147ea32bed7adf10640a3291ea9c75f71b1e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="segment-not-in-proper-sequence"></a><span data-ttu-id="31058-102">適切なシーケンスにセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="31058-102">Segment Not In Proper Sequence</span></span>
## <a name="details"></a><span data-ttu-id="31058-103">詳細</span><span class="sxs-lookup"><span data-stu-id="31058-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31058-104">製品名</span><span class="sxs-lookup"><span data-stu-id="31058-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="31058-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="31058-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="31058-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="31058-106">Event ID</span></span>|-|  
|<span data-ttu-id="31058-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="31058-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="31058-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="31058-108"> EDI</span></span>|  
|<span data-ttu-id="31058-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="31058-109">Component</span></span>|<span data-ttu-id="31058-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="31058-110">EDI Engine</span></span>|  
|<span data-ttu-id="31058-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="31058-111">Symbolic Name</span></span>|<span data-ttu-id="31058-112">X12SegmentNotInProperSequenceDescription</span><span class="sxs-lookup"><span data-stu-id="31058-112">X12SegmentNotInProperSequenceDescription</span></span>|  
|<span data-ttu-id="31058-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="31058-113">Message Text</span></span>|<span data-ttu-id="31058-114">適切なシーケンスにセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="31058-114">Segment Not In Proper Sequence</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="31058-115">説明</span><span class="sxs-lookup"><span data-stu-id="31058-115">Explanation</span></span>  
 <span data-ttu-id="31058-116">このエラー/警告/情報イベントは、インターチェンジのセグメントが、ドキュメント スキーマで指定されたシーケンスの範囲外であるため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="31058-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a segment in the interchange is out of the sequence specified by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31058-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="31058-117">User Action</span></span>  
 <span data-ttu-id="31058-118">このエラーを解決するには、インターチェンジの送信者に対して、インターチェンジのセグメントを並べ替え、ドキュメント スキーマで指定されている順序になるようにして、インターチェンジを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="31058-118">To resolve this error, have the sender of the interchange rearrange the segments in the interchange so they are in the order specified by the document schema, and then resend the interchange.</span></span>