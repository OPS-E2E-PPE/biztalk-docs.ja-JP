---
title: "AS2 デコーダーは MDN には、失敗したメッセージの AS2 処理が示されているために、処理が失敗しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bce620a-f336-435e-b7c3-3db060f2819d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20454f1c551b6b4828c42e09f0442b83275256ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-indicated-the-as2-message-failed-processing"></a><span data-ttu-id="efa31-102">AS2 メッセージを処理できなかったことが MDN によって示されたため、AS2 デコーダーの処理は失敗しました</span><span class="sxs-lookup"><span data-stu-id="efa31-102">The AS2 Decoder failed processing because the MDN indicated the AS2 message failed processing</span></span>
## <a name="details"></a><span data-ttu-id="efa31-103">詳細</span><span class="sxs-lookup"><span data-stu-id="efa31-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efa31-104">製品名</span><span class="sxs-lookup"><span data-stu-id="efa31-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="efa31-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="efa31-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="efa31-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="efa31-106">Event ID</span></span>|-|  
|<span data-ttu-id="efa31-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="efa31-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="efa31-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="efa31-108"> EDI</span></span>|  
|<span data-ttu-id="efa31-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="efa31-109">Component</span></span>|<span data-ttu-id="efa31-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="efa31-110">AS2 Engine</span></span>|  
|<span data-ttu-id="efa31-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="efa31-111">Symbolic Name</span></span>|<span data-ttu-id="efa31-112">AS2DecoderMdnProcessingFailureReturned</span><span class="sxs-lookup"><span data-stu-id="efa31-112">AS2DecoderMdnProcessingFailureReturned</span></span>|  
|<span data-ttu-id="efa31-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="efa31-113">Message Text</span></span>|<span data-ttu-id="efa31-114">AS2 メッセージを処理できなかったことが MDN によって示されたため、AS2 デコーダの処理は失敗しました。</span><span class="sxs-lookup"><span data-stu-id="efa31-114">The AS2 Decoder failure processing because the MDN indicated the AS2 message failed processing.</span></span>  <span data-ttu-id="efa31-115">MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:「\ 」MessageID:「\ {2 \}」OriginalMessageID:「\ {3\}」</span><span class="sxs-lookup"><span data-stu-id="efa31-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="efa31-116">説明</span><span class="sxs-lookup"><span data-stu-id="efa31-116">Explanation</span></span>  
 <span data-ttu-id="efa31-117">このエラー/警告/情報イベントは、AS2 メッセージの受信者が元の AS2 メッセージを処理できなかったことが MDN 応答に示されていることを表します。</span><span class="sxs-lookup"><span data-stu-id="efa31-117">This Error/Warning/Information event indicates that the MDN response shows that the receiver of the original AS2 message could not process the original AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="efa31-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="efa31-118">User Action</span></span>  
 <span data-ttu-id="efa31-119">このエラーを解決するには、AS2 メッセージの受信者に連絡し、受信側での処理が失敗した理由を確認して、元の AS2 メッセージを修正して再送信します。</span><span class="sxs-lookup"><span data-stu-id="efa31-119">To resolve this error, contact the receiver of the AS2 message, determine why processing failed at the receiver, fix the original AS2 message, and then resend.</span></span>