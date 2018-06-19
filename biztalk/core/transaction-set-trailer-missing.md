---
title: トランザクション セットのトレーラーがありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07753300-fe47-47a6-a947-6abec10c1c90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7f1c153aa0bb62b6c62f4eeebf9d1fb9bea004b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279290"
---
# <a name="transaction-set-trailer-missing"></a><span data-ttu-id="c3317-102">トランザクション セットのトレーラーがありません</span><span class="sxs-lookup"><span data-stu-id="c3317-102">Transaction Set Trailer Missing</span></span>
## <a name="details"></a><span data-ttu-id="c3317-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c3317-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3317-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c3317-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c3317-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c3317-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c3317-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c3317-106">Event ID</span></span>|-|  
|<span data-ttu-id="c3317-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c3317-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c3317-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c3317-108"> EDI</span></span>|  
|<span data-ttu-id="c3317-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c3317-109">Component</span></span>|<span data-ttu-id="c3317-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c3317-110">EDI Engine</span></span>|  
|<span data-ttu-id="c3317-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c3317-111">Symbolic Name</span></span>|<span data-ttu-id="c3317-112">X12TsTrailerMissingDescription</span><span class="sxs-lookup"><span data-stu-id="c3317-112">X12TsTrailerMissingDescription</span></span>|  
|<span data-ttu-id="c3317-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c3317-113">Message Text</span></span>|<span data-ttu-id="c3317-114">トランザクション セットのトレーラーがありません</span><span class="sxs-lookup"><span data-stu-id="c3317-114">Transaction Set Trailer Missing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c3317-115">説明</span><span class="sxs-lookup"><span data-stu-id="c3317-115">Explanation</span></span>  
 <span data-ttu-id="c3317-116">このエラー/警告/情報イベントは、トランザクション セットに SE トランザクション セット トレーラー (X12 トランザクション セットの場合) または UNT メッセージ トレーラー (EDIFACT トランザクション セットの場合) が含まれていなかったため、受信パイプラインで受信トランザクション セットを処理できなかったか、送信パイプラインで送信トランザクション セットを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c3317-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming transaction set or the send pipeline could not process the outgoing transaction set because the transaction set did not include the SE transaction set trailer (for X12 transaction sets) or the UNT message trailer (for EDIFACT transaction sets).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c3317-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c3317-117">User Action</span></span>  
 <span data-ttu-id="c3317-118">このエラーを解決するには、トランザクション セットに SE トランザクション セット トレーラー (X12 トランザクション セットの場合) または UNT メッセージ トレーラー (EDIFACT トランザクション セットの場合) を追加することをトランザクション セットの送信元に依頼します。</span><span class="sxs-lookup"><span data-stu-id="c3317-118">To resolve this error, have the sender of the transaction set add to the transaction set an SE transaction set trailer (for X12 transaction sets) or the UNT message trailer (for EDIFACT transaction sets), and then resend the transaction set.</span></span>