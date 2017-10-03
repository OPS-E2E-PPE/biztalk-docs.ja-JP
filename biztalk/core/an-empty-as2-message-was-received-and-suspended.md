---
title: "空の AS2 メッセージが受信され、中断された |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 349f7134-d039-44ab-b2b3-d378d38dfd38
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90c8221c7e0bd5b297b33118b8672fbe55612244
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="an-empty-as2-message-was-received-and-suspended"></a><span data-ttu-id="802d6-102">空の AS2 メッセージが受信され、中断されました</span><span class="sxs-lookup"><span data-stu-id="802d6-102">An empty AS2 message was received and suspended</span></span>
## <a name="details"></a><span data-ttu-id="802d6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="802d6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="802d6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="802d6-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="802d6-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="802d6-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="802d6-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="802d6-106">Event ID</span></span>|-|  
|<span data-ttu-id="802d6-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="802d6-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="802d6-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="802d6-108"> EDI</span></span>|  
|<span data-ttu-id="802d6-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="802d6-109">Component</span></span>|<span data-ttu-id="802d6-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="802d6-110">AS2 Engine</span></span>|  
|<span data-ttu-id="802d6-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="802d6-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="802d6-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="802d6-112">Message Text</span></span>|<span data-ttu-id="802d6-113">空の AS2 メッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="802d6-113">An empty AS2 message was received.</span></span>  <span data-ttu-id="802d6-114">メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="802d6-114">The message will be suspended.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="802d6-115">説明</span><span class="sxs-lookup"><span data-stu-id="802d6-115">Explanation</span></span>  
 <span data-ttu-id="802d6-116">このエラー/警告/情報イベントは、メッセージに本文が含まれていないため、BizTalk Server が受信 AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="802d6-116">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message does not contain a body.</span></span> <span data-ttu-id="802d6-117">本文は 2 回の復帰/改行によってヘッダーと区切られている必要があります。</span><span class="sxs-lookup"><span data-stu-id="802d6-117">The body must be separated from the headers by two carriage return/line feeds.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="802d6-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="802d6-118">User Action</span></span>  
 <span data-ttu-id="802d6-119">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="802d6-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="802d6-120">AS2 メッセージの送信前に、送信元のパーティによってメッセージに必ず本文 (2 回の復帰/改行によってヘッダーと区切られている) が追加されるようにします。</span><span class="sxs-lookup"><span data-stu-id="802d6-120">Ensure the sending party adds a body (separated from the headers by two carriage return/line feeds) to the AS2 message before sending it.</span></span>