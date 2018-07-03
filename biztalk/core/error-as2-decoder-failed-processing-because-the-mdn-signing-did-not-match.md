---
title: AS2 デコーダーは MDN の署名が、要求と一致しなかったため、処理が失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a42d344-fc28-4bc4-9328-46158f15a008
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a4d5cb5cd1825f5620ab39e4c770eb9818a5ade
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978876"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a><span data-ttu-id="c7844-102">MDN の署名が要求と一致しなかったため、AS2 デコーダーの処理は失敗しました</span><span class="sxs-lookup"><span data-stu-id="c7844-102">The AS2 Decoder failed processing because the MDN signing did not match our request</span></span>
## <a name="details"></a><span data-ttu-id="c7844-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c7844-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c7844-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c7844-104">Product Name</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="c7844-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c7844-105">Product Version</span></span> |                                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    <span data-ttu-id="c7844-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c7844-106">Event ID</span></span>     |                                                                                                   -                                                                                                    |
|  <span data-ttu-id="c7844-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c7844-107">Event Source</span></span>   |                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c7844-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c7844-108"> EDI</span></span>                                                         |
|    <span data-ttu-id="c7844-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c7844-109">Component</span></span>    |                                                                                               <span data-ttu-id="c7844-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="c7844-110">AS2 Engine</span></span>                                                                                               |
|  <span data-ttu-id="c7844-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c7844-111">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="c7844-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="c7844-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span></span>                                                                           |
|  <span data-ttu-id="c7844-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c7844-113">Message Text</span></span>   | <span data-ttu-id="c7844-114">MDN の署名が要求と一致しなかったため、AS2 デコーダの処理は失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c7844-114">The AS2 Decoder failure processing because the MDN signing did not match our request.</span></span>  <span data-ttu-id="c7844-115">MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"</span><span class="sxs-lookup"><span data-stu-id="c7844-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c7844-116">説明</span><span class="sxs-lookup"><span data-stu-id="c7844-116">Explanation</span></span>  
 <span data-ttu-id="c7844-117">このエラー/警告/情報イベントは、MDN は署名されていたが、署名が要求されていなかったか、または MDN は署名されていなかったが、署名が要求されていたため、受信パイプラインが受信 MDN を処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c7844-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming MDN either because the MDN was signed, but signing wasn't requested for the MDN, or the MDN was unsigned, but signing was requested for the MDN.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c7844-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c7844-118">User Action</span></span>  
 <span data-ttu-id="c7844-119">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c7844-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="c7844-120">MDN に対する署名要求を要求に合わせて変更します。</span><span class="sxs-lookup"><span data-stu-id="c7844-120">Change the signature request for the MDN to match the request.</span></span> <span data-ttu-id="c7844-121">そのためには、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページを開き、[MDN の要求] プロパティをオンにして、[署名付き MDN を要求する] プロパティをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="c7844-121">To do so, open the Party as AS2 Message Receiver page of the AS2 Properties dialog box, and with the "Request MDN" property selected, either select or clear the "Request signed MDN" property.</span></span>  
  
2.  <span data-ttu-id="c7844-122">元の AS2 メッセージの受信者に連絡し、MDN に署名が必要かどうかについて解決します。</span><span class="sxs-lookup"><span data-stu-id="c7844-122">Contact the receiver of the original AS2 message to resolve whether MDNs should be signed or not.</span></span>