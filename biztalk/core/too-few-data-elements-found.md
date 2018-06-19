---
title: 見つかったデータ要素数が少なすぎます |Microsoft ドキュメント
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
ms.openlocfilehash: 8244f927cb7aff9cd0cb517dd132b986d53d67f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278962"
---
# <a name="too-few-data-elements-found"></a><span data-ttu-id="8edb8-102">見つかったデータ要素が少なすぎます</span><span class="sxs-lookup"><span data-stu-id="8edb8-102">Too few data elements found</span></span>
## <a name="details"></a><span data-ttu-id="8edb8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8edb8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8edb8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8edb8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8edb8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8edb8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="8edb8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8edb8-106">Event ID</span></span>|-|  
|<span data-ttu-id="8edb8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8edb8-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8edb8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="8edb8-108"> EDI</span></span>|  
|<span data-ttu-id="8edb8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8edb8-109">Component</span></span>|<span data-ttu-id="8edb8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8edb8-110">EDI Engine</span></span>|  
|<span data-ttu-id="8edb8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8edb8-111">Symbolic Name</span></span>|<span data-ttu-id="8edb8-112">X12FeTooFewDataElementsFoundDescription</span><span class="sxs-lookup"><span data-stu-id="8edb8-112">X12FeTooFewDataElementsFoundDescription</span></span>|  
|<span data-ttu-id="8edb8-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8edb8-113">Message Text</span></span>|<span data-ttu-id="8edb8-114">見つかったデータ要素が少なすぎます</span><span class="sxs-lookup"><span data-stu-id="8edb8-114">Too few data elements found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8edb8-115">説明</span><span class="sxs-lookup"><span data-stu-id="8edb8-115">Explanation</span></span>  
 <span data-ttu-id="8edb8-116">このエラー/警告/情報イベントは、インターチェンジのセグメントに含まれていたデータ要素の数が、ドキュメント スキーマまたはサービス スキーマで要求されている数を下回っていたため、受信パイプラインで受信インターチェンジを処理できなかったか、または送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8edb8-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a segment in the interchange contained fewer data elements than required by the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8edb8-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8edb8-117">User Action</span></span>  
 <span data-ttu-id="8edb8-118">このエラーを解決するには、インターチェンジの送信者に対して、セグメントに必要な数のデータ要素を含めるよう依頼し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="8edb8-118">To resolve this error, have the sender of the interchange ensure that segments include the required number of data elements, and then resend the interchange.</span></span>