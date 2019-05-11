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
ms.openlocfilehash: 2e79b28c69786bad3e261cc3269329bd6465a8ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388998"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a><span data-ttu-id="279d4-102">AS2 デコーダーは MDN の署名が、要求と一致しなかったため、処理が失敗しました</span><span class="sxs-lookup"><span data-stu-id="279d4-102">The AS2 Decoder failed processing because the MDN signing did not match our request</span></span>
## <a name="details"></a><span data-ttu-id="279d4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="279d4-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="279d4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="279d4-104">Product Name</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="279d4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="279d4-105">Product Version</span></span> |                                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    <span data-ttu-id="279d4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="279d4-106">Event ID</span></span>     |                                                                                                   -                                                                                                    |
|  <span data-ttu-id="279d4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="279d4-107">Event Source</span></span>   |                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="279d4-108">EDI</span><span class="sxs-lookup"><span data-stu-id="279d4-108">EDI</span></span>                                                         |
|    <span data-ttu-id="279d4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="279d4-109">Component</span></span>    |                                                                                               <span data-ttu-id="279d4-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="279d4-110">AS2 Engine</span></span>                                                                                               |
|  <span data-ttu-id="279d4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="279d4-111">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="279d4-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="279d4-112">AS2DecoderMdnSigningMismatchFailureDuringProcessing</span></span>                                                                           |
|  <span data-ttu-id="279d4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="279d4-113">Message Text</span></span>   | <span data-ttu-id="279d4-114">AS2 デコーダー処理は失敗しました、MDN の署名要求が一致しないためです。</span><span class="sxs-lookup"><span data-stu-id="279d4-114">The AS2 Decoder failure processing because the MDN signing did not match our request.</span></span>  <span data-ttu-id="279d4-115">MDN メッセージの詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"</span><span class="sxs-lookup"><span data-stu-id="279d4-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="279d4-116">説明</span><span class="sxs-lookup"><span data-stu-id="279d4-116">Explanation</span></span>  
 <span data-ttu-id="279d4-117">このエラー/警告/情報イベントは、受信パイプラインが、いずれか、MDN は署名されたが、署名されていないが、署名には、MDN では、または MDN に要求署名されなかったため、要求された MDN の受信 MDN を処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="279d4-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming MDN either because the MDN was signed, but signing wasn't requested for the MDN, or the MDN was unsigned, but signing was requested for the MDN.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="279d4-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="279d4-118">User Action</span></span>  
 <span data-ttu-id="279d4-119">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="279d4-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="279d4-120">要求と一致する MDN の署名要求を変更します。</span><span class="sxs-lookup"><span data-stu-id="279d4-120">Change the signature request for the MDN to match the request.</span></span> <span data-ttu-id="279d4-121">これを行うには、パーティ-AS2 メッセージの受信者 ページ"MDN を要求する"プロパティが選択されていると、AS2 のプロパティ ダイアログ ボックスのいずれかをオンまたはオフ、「要求署名付き MDN を」プロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="279d4-121">To do so, open the Party as AS2 Message Receiver page of the AS2 Properties dialog box, and with the "Request MDN" property selected, either select or clear the "Request signed MDN" property.</span></span>  
  
2.  <span data-ttu-id="279d4-122">Mdn を署名する必要があるかどうかを解決するのには、元の AS2 メッセージの受信者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="279d4-122">Contact the receiver of the original AS2 message to resolve whether MDNs should be signed or not.</span></span>