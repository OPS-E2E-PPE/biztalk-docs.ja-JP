---
title: セグメントは、少なくとも 2 つの文字の名前を持つ必要があります |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f80bbc4a-151a-4094-8640-1944e8812730
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70d4b39aa9421e4b60fd9e0c4415c69862c00526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269146"
---
# <a name="segment-should-have-a-name-with-at-least-two-characters"></a><span data-ttu-id="acec2-102">セグメントには 2 文字以上の名前を指定する必要があります</span><span class="sxs-lookup"><span data-stu-id="acec2-102">Segment should have a name with at least two characters</span></span>
## <a name="details"></a><span data-ttu-id="acec2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="acec2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="acec2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="acec2-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="acec2-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="acec2-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="acec2-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="acec2-106">Event ID</span></span>|-|  
|<span data-ttu-id="acec2-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="acec2-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="acec2-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="acec2-108"> EDI</span></span>|  
|<span data-ttu-id="acec2-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="acec2-109">Component</span></span>|<span data-ttu-id="acec2-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="acec2-110">EDI Engine</span></span>|  
|<span data-ttu-id="acec2-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="acec2-111">Symbolic Name</span></span>|<span data-ttu-id="acec2-112">SchemaCode103EInvalidTagLength</span><span class="sxs-lookup"><span data-stu-id="acec2-112">SchemaCode103EInvalidTagLength</span></span>|  
|<span data-ttu-id="acec2-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="acec2-113">Message Text</span></span>|<span data-ttu-id="acec2-114">セグメントが少なくとも 2 つの文字を含む名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="acec2-114">Segment should have a name with at least 2 characters</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="acec2-115">説明</span><span class="sxs-lookup"><span data-stu-id="acec2-115">Explanation</span></span>  
 <span data-ttu-id="acec2-116">このエラー/警告/情報イベントは、インターチェンジのセグメントに 2 文字以上の名前が指定されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="acec2-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the name of a segment in the interchange does not have at least two characters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="acec2-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="acec2-117">User Action</span></span>  
 <span data-ttu-id="acec2-118">このエラーを解決するには、インターチェンジの送信者に対して、インターチェンジの各セグメントに少なくとも 2 文字以上の名前を指定し、インターチェンジを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="acec2-118">To resolve this error, have the sender of the interchange ensure that the name of each segment in the interchange has at least two characters, and then resend the interchange.</span></span>