---
title: 適切なシーケンスではなくセグメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f0c0fdc-10d9-4b77-a80d-b2b8571e7665
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2e90f42fdc3226827dae670daecb0e856eba156
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980363"
---
# <a name="segment-not-in-proper-sequence"></a><span data-ttu-id="35c9b-102">適切なシーケンスにセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="35c9b-102">Segment Not In Proper Sequence</span></span>
## <a name="details"></a><span data-ttu-id="35c9b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="35c9b-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="35c9b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="35c9b-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="35c9b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="35c9b-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="35c9b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="35c9b-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="35c9b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="35c9b-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="35c9b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="35c9b-108"> EDI</span></span> |
|    <span data-ttu-id="35c9b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="35c9b-109">Component</span></span>    |                                       <span data-ttu-id="35c9b-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="35c9b-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="35c9b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="35c9b-111">Symbolic Name</span></span>  |                        <span data-ttu-id="35c9b-112">X12SegmentNotInProperSequenceDescription</span><span class="sxs-lookup"><span data-stu-id="35c9b-112">X12SegmentNotInProperSequenceDescription</span></span>                        |
|  <span data-ttu-id="35c9b-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="35c9b-113">Message Text</span></span>   |                             <span data-ttu-id="35c9b-114">適切なシーケンスにセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="35c9b-114">Segment Not In Proper Sequence</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="35c9b-115">説明</span><span class="sxs-lookup"><span data-stu-id="35c9b-115">Explanation</span></span>  
 <span data-ttu-id="35c9b-116">このエラー/警告/情報イベントは、インターチェンジのセグメントが、ドキュメント スキーマで指定されたシーケンスの範囲外であるため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="35c9b-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a segment in the interchange is out of the sequence specified by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35c9b-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="35c9b-117">User Action</span></span>  
 <span data-ttu-id="35c9b-118">このエラーを解決するには、インターチェンジの送信者に対して、インターチェンジのセグメントを並べ替え、ドキュメント スキーマで指定されている順序になるようにして、インターチェンジを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="35c9b-118">To resolve this error, have the sender of the interchange rearrange the segments in the interchange so they are in the order specified by the document schema, and then resend the interchange.</span></span>