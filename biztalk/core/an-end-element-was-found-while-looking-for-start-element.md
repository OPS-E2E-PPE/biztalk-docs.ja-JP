---
title: "開始要素を検索中に、終了要素が見つかりました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7690744-a795-47cc-bc66-a0314a4cc320
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dacaa096b15a6f2969ed56b5bac2138876a6095
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a><span data-ttu-id="cd2f8-102">StartElement の検索中に EndElement が見つかりました</span><span class="sxs-lookup"><span data-stu-id="cd2f8-102">An End Element was found while looking for Start Element</span></span>
## <a name="details"></a><span data-ttu-id="cd2f8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cd2f8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd2f8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cd2f8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="cd2f8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cd2f8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="cd2f8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cd2f8-106">Event ID</span></span>|-|  
|<span data-ttu-id="cd2f8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cd2f8-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cd2f8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="cd2f8-108"> EDI</span></span>|  
|<span data-ttu-id="cd2f8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cd2f8-109">Component</span></span>|<span data-ttu-id="cd2f8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="cd2f8-110">EDI Engine</span></span>|  
|<span data-ttu-id="cd2f8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cd2f8-111">Symbolic Name</span></span>|<span data-ttu-id="cd2f8-112">EndElementFoundWhenLookingForStartElement</span><span class="sxs-lookup"><span data-stu-id="cd2f8-112">EndElementFoundWhenLookingForStartElement</span></span>|  
|<span data-ttu-id="cd2f8-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cd2f8-113">Message Text</span></span>|<span data-ttu-id="cd2f8-114">{0} という名前の EndElement が見つかりましたが、StartElement 名前 {1}、深さ {2} での検索中には</span><span class="sxs-lookup"><span data-stu-id="cd2f8-114">An EndElement with name {0} was found, while looking for StartElement with name {1}, at depth {2}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cd2f8-115">説明</span><span class="sxs-lookup"><span data-stu-id="cd2f8-115">Explanation</span></span>  
 <span data-ttu-id="cd2f8-116">このエラー/警告/情報イベントは、XML メッセージが検証に失敗したため、BizTalk Server が受信 XML メッセージ (解析後) または送信 XML メッセージ (シリアル化前) を処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="cd2f8-116">This Error/Warning/Information event indicates that BizTalk Server could not process an incoming XML message (after parsing) or an outgoing XML message (before serialization) because the XML message failed validation.</span></span> <span data-ttu-id="cd2f8-117">XML メッセージに、ヘッダーまたはデータ要素の終了タグが含まれていませんでした。</span><span class="sxs-lookup"><span data-stu-id="cd2f8-117">The XML message did not contain an end tag for a header or data element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cd2f8-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cd2f8-118">User Action</span></span>  
 <span data-ttu-id="cd2f8-119">このエラーを解決するには、XML メッセージに適切な終了タグまたはトレーラーを追加し、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="cd2f8-119">To resolve this error, add the appropriate end tag or trailer to the XML message, and then resend the message.</span></span>