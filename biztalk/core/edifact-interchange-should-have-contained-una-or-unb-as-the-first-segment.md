---
title: Edifact インターチェンジに UNA または UNB の最初のセグメントとして含まれていた必要があります |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43fd17-31d0-48df-93cd-524b40034764
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e673df728dea00852e9713aed12f8ced902a4fdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240034"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a><span data-ttu-id="4873a-102">EDIFACT インターチェンジには、最初のセグメントとして UNA または UNB が含まれている必要があります</span><span class="sxs-lookup"><span data-stu-id="4873a-102">Edifact interchange should have contained UNA or UNB as the first segment</span></span>
## <a name="details"></a><span data-ttu-id="4873a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4873a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4873a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4873a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="4873a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4873a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="4873a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4873a-106">Event ID</span></span>|-|  
|<span data-ttu-id="4873a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4873a-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4873a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="4873a-108"> EDI</span></span>|  
|<span data-ttu-id="4873a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4873a-109">Component</span></span>|<span data-ttu-id="4873a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="4873a-110">EDI Engine</span></span>|  
|<span data-ttu-id="4873a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4873a-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="4873a-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4873a-112">Message Text</span></span>|<span data-ttu-id="4873a-113">EDIFACT インターチェンジには、最初のセグメントとして UNA または UNB が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4873a-113">Edifact interchange should have contained UNA or UNB as the first segment.</span></span> <span data-ttu-id="4873a-114">代わりに、{0} が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4873a-114">Instead {0} was found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4873a-115">説明</span><span class="sxs-lookup"><span data-stu-id="4873a-115">Explanation</span></span>  
 <span data-ttu-id="4873a-116">このエラー/警告/情報イベントは、EDI 受信を示す最初のセグメントが UNA も UNB セグメントでもないために、パイプラインは受信 EDIFACT インターチェンジを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="4873a-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA nor a UNB segment.</span></span> <span data-ttu-id="4873a-117">UNA セグメントは省略可能ですが、UNB セグメントは必須です。</span><span class="sxs-lookup"><span data-stu-id="4873a-117">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4873a-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4873a-118">User Action</span></span>  
 <span data-ttu-id="4873a-119">このエラーを解決するには、インターチェンジの送信者に対して、インターチェンジの最初のセグメントとして UNA または UNB セグメントを含めるよう依頼し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="4873a-119">To resolve this error, ensure that the sender of the interchange includes the UNA or UNB segment as the first segment of the interchange, and then resends the interchange.</span></span>