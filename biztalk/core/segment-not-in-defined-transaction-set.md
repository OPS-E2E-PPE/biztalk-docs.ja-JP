---
title: "定義されているトランザクションではないセットをセグメント化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 914e333f-96e4-4094-880d-51a5f25915c3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2f0b330110ef08196681e54e543173c3f2bd0f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="segment-not-in-defined-transaction-set"></a><span data-ttu-id="3a6e4-102">定義されたトランザクション セットにセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="3a6e4-102">Segment Not In Defined Transaction set</span></span>
## <a name="details"></a><span data-ttu-id="3a6e4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3a6e4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a6e4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3a6e4-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3a6e4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3a6e4-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3a6e4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3a6e4-106">Event ID</span></span>|-|  
|<span data-ttu-id="3a6e4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3a6e4-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3a6e4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3a6e4-108"> EDI</span></span>|  
|<span data-ttu-id="3a6e4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3a6e4-109">Component</span></span>|<span data-ttu-id="3a6e4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="3a6e4-110">EDI Engine</span></span>|  
|<span data-ttu-id="3a6e4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3a6e4-111">Symbolic Name</span></span>|<span data-ttu-id="3a6e4-112">X12SegmentNotInDefinedTSDescription</span><span class="sxs-lookup"><span data-stu-id="3a6e4-112">X12SegmentNotInDefinedTSDescription</span></span>|  
|<span data-ttu-id="3a6e4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3a6e4-113">Message Text</span></span>|<span data-ttu-id="3a6e4-114">定義されたトランザクション セットにセグメントがありません</span><span class="sxs-lookup"><span data-stu-id="3a6e4-114">Segment Not In Defined Transaction set</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3a6e4-115">説明</span><span class="sxs-lookup"><span data-stu-id="3a6e4-115">Explanation</span></span>  
 <span data-ttu-id="3a6e4-116">このエラー/警告/情報イベントは、インターチェンジのトランザクション セットに、ドキュメント スキーマで必要なセグメントが含まれていないため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3a6e4-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a transaction set in that interchange does not contain a segment required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3a6e4-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3a6e4-117">User Action</span></span>  
 <span data-ttu-id="3a6e4-118">このエラーを解決するには、インターチェンジの送信者が必要なセグメントをインターチェンジのトランザクション セットに追加した上で、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="3a6e4-118">To resolve this error, have the sender of the interchange add the required segment to the transaction set in the interchange, and then resend the interchange.</span></span>