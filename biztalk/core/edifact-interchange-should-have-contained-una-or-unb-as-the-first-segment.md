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
ms.openlocfilehash: 196b589ff886bed005e251c7172a3fd720d88868
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530741"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a><span data-ttu-id="05058-102">Edifact インターチェンジの必要がありますが含まれている UNA または UNB 最初のセグメントとして</span><span class="sxs-lookup"><span data-stu-id="05058-102">Edifact interchange should have contained UNA or UNB as the first segment</span></span>
## <a name="details"></a><span data-ttu-id="05058-103">詳細</span><span class="sxs-lookup"><span data-stu-id="05058-103">Details</span></span>  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="05058-104">製品名</span><span class="sxs-lookup"><span data-stu-id="05058-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| <span data-ttu-id="05058-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="05058-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    <span data-ttu-id="05058-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="05058-106">Event ID</span></span>     |                                                -                                                 |
|  <span data-ttu-id="05058-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="05058-107">Event Source</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="05058-108">EDI</span><span class="sxs-lookup"><span data-stu-id="05058-108">EDI</span></span>      |
|    <span data-ttu-id="05058-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="05058-109">Component</span></span>    |                                            <span data-ttu-id="05058-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="05058-110">EDI Engine</span></span>                                            |
|  <span data-ttu-id="05058-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="05058-111">Symbolic Name</span></span>  |                                                -                                                 |
|  <span data-ttu-id="05058-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="05058-112">Message Text</span></span>   | <span data-ttu-id="05058-113">Edifact インターチェンジは、最初のセグメントとして UNA または UNB 含まれていたする必要があります。</span><span class="sxs-lookup"><span data-stu-id="05058-113">Edifact interchange should have contained UNA or UNB as the first segment.</span></span> <span data-ttu-id="05058-114">代わりに{0}が見つかりました</span><span class="sxs-lookup"><span data-stu-id="05058-114">Instead {0} was found</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="05058-115">説明</span><span class="sxs-lookup"><span data-stu-id="05058-115">Explanation</span></span>  
 <span data-ttu-id="05058-116">このエラー/警告/情報イベントは、EDI が受信することを示します、最初のセグメントが UNA も UNB セグメントでもないために、パイプラインは受信 EDIFACT インターチェンジを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="05058-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA nor a UNB segment.</span></span> <span data-ttu-id="05058-117">UNA セグメントは省略可能ですが、UNB セグメントは必須です。</span><span class="sxs-lookup"><span data-stu-id="05058-117">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05058-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="05058-118">User Action</span></span>  
 <span data-ttu-id="05058-119">このエラーを解決するのには、インターチェンジの送信者がインターチェンジの最初のセグメントとして UNA または UNB セグメントが含まれていて、インターチェンジを再送信を確認します。</span><span class="sxs-lookup"><span data-stu-id="05058-119">To resolve this error, ensure that the sender of the interchange includes the UNA or UNB segment as the first segment of the interchange, and then resends the interchange.</span></span>