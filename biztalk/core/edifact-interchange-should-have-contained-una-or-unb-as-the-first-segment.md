---
title: Edifact インターチェンジに UNA または UNB が最初のセグメントとして含まれていたする必要があります |Microsoft Docs
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
ms.openlocfilehash: 4ee9d5100c8378b5ee411673c4c185dcf5def365
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017836"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a><span data-ttu-id="ae843-102">EDIFACT インターチェンジには、最初のセグメントとして UNA または UNB が含まれている必要があります</span><span class="sxs-lookup"><span data-stu-id="ae843-102">Edifact interchange should have contained UNA or UNB as the first segment</span></span>
## <a name="details"></a><span data-ttu-id="ae843-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ae843-103">Details</span></span>  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ae843-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ae843-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| <span data-ttu-id="ae843-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ae843-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    <span data-ttu-id="ae843-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ae843-106">Event ID</span></span>     |                                                -                                                 |
|  <span data-ttu-id="ae843-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ae843-107">Event Source</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ae843-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ae843-108"> EDI</span></span>      |
|    <span data-ttu-id="ae843-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ae843-109">Component</span></span>    |                                            <span data-ttu-id="ae843-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ae843-110">EDI Engine</span></span>                                            |
|  <span data-ttu-id="ae843-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ae843-111">Symbolic Name</span></span>  |                                                -                                                 |
|  <span data-ttu-id="ae843-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ae843-112">Message Text</span></span>   | <span data-ttu-id="ae843-113">EDIFACT インターチェンジには、最初のセグメントとして UNA または UNB が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae843-113">Edifact interchange should have contained UNA or UNB as the first segment.</span></span> <span data-ttu-id="ae843-114">代わりに{0}が見つかりました</span><span class="sxs-lookup"><span data-stu-id="ae843-114">Instead {0} was found</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ae843-115">説明</span><span class="sxs-lookup"><span data-stu-id="ae843-115">Explanation</span></span>  
 <span data-ttu-id="ae843-116">このエラー/警告/情報イベントは、EDI が受信することを示します、最初のセグメントが UNA も UNB セグメントでもないために、パイプラインは受信 EDIFACT インターチェンジを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="ae843-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA nor a UNB segment.</span></span> <span data-ttu-id="ae843-117">UNA セグメントは省略可能ですが、UNB セグメントは必須です。</span><span class="sxs-lookup"><span data-stu-id="ae843-117">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae843-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ae843-118">User Action</span></span>  
 <span data-ttu-id="ae843-119">このエラーを解決するには、インターチェンジの送信者に対して、インターチェンジの最初のセグメントとして UNA または UNB セグメントを含めるよう依頼し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="ae843-119">To resolve this error, ensure that the sender of the interchange includes the UNA or UNB segment as the first segment of the interchange, and then resends the interchange.</span></span>