---
title: トランザクション セットのトレーラーがありません |Microsoft Docs
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
ms.openlocfilehash: b23ddf1905bc0067d5d35b625d4a66ec058028fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985131"
---
# <a name="transaction-set-trailer-missing"></a><span data-ttu-id="ff601-102">トランザクション セットのトレーラーがありません</span><span class="sxs-lookup"><span data-stu-id="ff601-102">Transaction Set Trailer Missing</span></span>
## <a name="details"></a><span data-ttu-id="ff601-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ff601-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ff601-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ff601-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ff601-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ff601-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ff601-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ff601-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ff601-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ff601-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ff601-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ff601-108"> EDI</span></span> |
|    <span data-ttu-id="ff601-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ff601-109">Component</span></span>    |                                       <span data-ttu-id="ff601-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ff601-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="ff601-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ff601-111">Symbolic Name</span></span>  |                             <span data-ttu-id="ff601-112">X12TsTrailerMissingDescription</span><span class="sxs-lookup"><span data-stu-id="ff601-112">X12TsTrailerMissingDescription</span></span>                             |
|  <span data-ttu-id="ff601-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ff601-113">Message Text</span></span>   |                            <span data-ttu-id="ff601-114">トランザクション セットのトレーラーがありません</span><span class="sxs-lookup"><span data-stu-id="ff601-114">Transaction Set Trailer Missing</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="ff601-115">説明</span><span class="sxs-lookup"><span data-stu-id="ff601-115">Explanation</span></span>  
 <span data-ttu-id="ff601-116">このエラー/警告/情報イベントは、トランザクション セットに SE トランザクション セット トレーラー (X12 トランザクション セットの場合) または UNT メッセージ トレーラー (EDIFACT トランザクション セットの場合) が含まれていなかったため、受信パイプラインで受信トランザクション セットを処理できなかったか、送信パイプラインで送信トランザクション セットを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ff601-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming transaction set or the send pipeline could not process the outgoing transaction set because the transaction set did not include the SE transaction set trailer (for X12 transaction sets) or the UNT message trailer (for EDIFACT transaction sets).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ff601-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ff601-117">User Action</span></span>  
 <span data-ttu-id="ff601-118">このエラーを解決するには、トランザクション セットに SE トランザクション セット トレーラー (X12 トランザクション セットの場合) または UNT メッセージ トレーラー (EDIFACT トランザクション セットの場合) を追加することをトランザクション セットの送信元に依頼します。</span><span class="sxs-lookup"><span data-stu-id="ff601-118">To resolve this error, have the sender of the transaction set add to the transaction set an SE transaction set trailer (for X12 transaction sets) or the UNT message trailer (for EDIFACT transaction sets), and then resend the transaction set.</span></span>