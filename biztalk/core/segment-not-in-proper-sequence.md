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
ms.openlocfilehash: 0562c55f6b0b494058805febde18593da1b567f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279773"
---
# <a name="segment-not-in-proper-sequence"></a><span data-ttu-id="79de9-102">適切なシーケンスにセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="79de9-102">Segment Not In Proper Sequence</span></span>
## <a name="details"></a><span data-ttu-id="79de9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="79de9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="79de9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="79de9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="79de9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="79de9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="79de9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="79de9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="79de9-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="79de9-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="79de9-108">EDI</span><span class="sxs-lookup"><span data-stu-id="79de9-108">EDI</span></span> |
|    <span data-ttu-id="79de9-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="79de9-109">Component</span></span>    |                                       <span data-ttu-id="79de9-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="79de9-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="79de9-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="79de9-111">Symbolic Name</span></span>  |                        <span data-ttu-id="79de9-112">X12SegmentNotInProperSequenceDescription</span><span class="sxs-lookup"><span data-stu-id="79de9-112">X12SegmentNotInProperSequenceDescription</span></span>                        |
|  <span data-ttu-id="79de9-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="79de9-113">Message Text</span></span>   |                             <span data-ttu-id="79de9-114">適切なシーケンスにセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="79de9-114">Segment Not In Proper Sequence</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="79de9-115">説明</span><span class="sxs-lookup"><span data-stu-id="79de9-115">Explanation</span></span>  
 <span data-ttu-id="79de9-116">このエラー/警告/情報イベントは、インターチェンジのセグメントが、ドキュメント スキーマで指定されたシーケンスの範囲外であるため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="79de9-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a segment in the interchange is out of the sequence specified by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79de9-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="79de9-117">User Action</span></span>  
 <span data-ttu-id="79de9-118">このエラーを解決するには、インターチェンジの送信者に対して、インターチェンジのセグメントを並べ替え、ドキュメント スキーマで指定されている順序になるようにして、インターチェンジを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="79de9-118">To resolve this error, have the sender of the interchange rearrange the segments in the interchange so they are in the order specified by the document schema, and then resend the interchange.</span></span>