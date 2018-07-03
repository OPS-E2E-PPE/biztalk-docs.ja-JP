---
title: 見つかったデータ要素が少なすぎる |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6eca6c1-73ee-4b9a-be84-461051eda963
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89d82a5015d2285437363f178f88c165e3ba6333
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984779"
---
# <a name="too-few-data-elements-found"></a><span data-ttu-id="10159-102">見つかったデータ要素が少なすぎます</span><span class="sxs-lookup"><span data-stu-id="10159-102">Too few data elements found</span></span>
## <a name="details"></a><span data-ttu-id="10159-103">詳細</span><span class="sxs-lookup"><span data-stu-id="10159-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="10159-104">製品名</span><span class="sxs-lookup"><span data-stu-id="10159-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="10159-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="10159-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="10159-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="10159-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="10159-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="10159-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="10159-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="10159-108"> EDI</span></span> |
|    <span data-ttu-id="10159-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="10159-109">Component</span></span>    |                                       <span data-ttu-id="10159-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="10159-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="10159-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="10159-111">Symbolic Name</span></span>  |                        <span data-ttu-id="10159-112">X12FeTooFewDataElementsFoundDescription</span><span class="sxs-lookup"><span data-stu-id="10159-112">X12FeTooFewDataElementsFoundDescription</span></span>                         |
|  <span data-ttu-id="10159-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="10159-113">Message Text</span></span>   |                              <span data-ttu-id="10159-114">見つかったデータ要素が少なすぎます</span><span class="sxs-lookup"><span data-stu-id="10159-114">Too few data elements found</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="10159-115">説明</span><span class="sxs-lookup"><span data-stu-id="10159-115">Explanation</span></span>  
 <span data-ttu-id="10159-116">このエラー/警告/情報イベントは、インターチェンジのセグメントに含まれていたデータ要素の数が、ドキュメント スキーマまたはサービス スキーマで要求されている数を下回っていたため、受信パイプラインで受信インターチェンジを処理できなかったか、または送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="10159-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a segment in the interchange contained fewer data elements than required by the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10159-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="10159-117">User Action</span></span>  
 <span data-ttu-id="10159-118">このエラーを解決するには、インターチェンジの送信者に対して、セグメントに必要な数のデータ要素を含めるよう依頼し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="10159-118">To resolve this error, have the sender of the interchange ensure that segments include the required number of data elements, and then resend the interchange.</span></span>