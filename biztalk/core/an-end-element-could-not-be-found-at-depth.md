---
title: 深いレベルで、終了要素が見つかりませんでした |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1edb60a-122a-4fe9-8d73-96521fe7326b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a90265b4348e4d35b66099f426b6f6177851ccc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229914"
---
# <a name="an-end-element-could-not-be-found-at-depth"></a><span data-ttu-id="91f98-102">深さの終了要素が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="91f98-102">An End Element could not be found at depth</span></span>
## <a name="details"></a><span data-ttu-id="91f98-103">詳細</span><span class="sxs-lookup"><span data-stu-id="91f98-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="91f98-104">製品名</span><span class="sxs-lookup"><span data-stu-id="91f98-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="91f98-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="91f98-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="91f98-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="91f98-106">Event ID</span></span>|-|  
|<span data-ttu-id="91f98-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="91f98-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="91f98-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="91f98-108"> EDI</span></span>|  
|<span data-ttu-id="91f98-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="91f98-109">Component</span></span>|<span data-ttu-id="91f98-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="91f98-110">EDI Engine</span></span>|  
|<span data-ttu-id="91f98-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="91f98-111">Symbolic Name</span></span>|<span data-ttu-id="91f98-112">EndElementNotFoundAtDepth</span><span class="sxs-lookup"><span data-stu-id="91f98-112">EndElementNotFoundAtDepth</span></span>|  
|<span data-ttu-id="91f98-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="91f98-113">Message Text</span></span>|<span data-ttu-id="91f98-114">深さ {0} の終了要素が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="91f98-114">An End Element at depth {0} could not be found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="91f98-115">説明</span><span class="sxs-lookup"><span data-stu-id="91f98-115">Explanation</span></span>  
 <span data-ttu-id="91f98-116">このエラー/警告/情報イベントは、XML メッセージの検証に失敗したため、BizTalk Server が送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="91f98-116">This Error/Warning/Information event indicates that BizTalk Server could not process the outgoing interchange because the XML message failed validation.</span></span> <span data-ttu-id="91f98-117">XML メッセージに、ヘッダーまたはデータ要素の終了タグが含まれていませんでした。</span><span class="sxs-lookup"><span data-stu-id="91f98-117">The XML message did not contain an end tag for a header or data element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="91f98-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="91f98-118">User Action</span></span>  
 <span data-ttu-id="91f98-119">このエラーを解決するには、XML メッセージに適切な終了タグまたはトレーラーを追加し、再送信します。</span><span class="sxs-lookup"><span data-stu-id="91f98-119">To resolve this error, add the appropriate end tag or trailer to the XML message, and then resend.</span></span>