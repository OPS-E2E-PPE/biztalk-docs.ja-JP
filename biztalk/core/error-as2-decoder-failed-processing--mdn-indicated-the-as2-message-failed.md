---
title: AS2 デコーダーは、MDN が失敗したメッセージの AS2 処理によって示されたため失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bce620a-f336-435e-b7c3-3db060f2819d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 240c90d488d313bf43982c7c98db3e8a1ea05e75
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984499"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-indicated-the-as2-message-failed-processing"></a><span data-ttu-id="f0d4f-102">AS2 メッセージを処理できなかったことが MDN によって示されたため、AS2 デコーダーの処理は失敗しました</span><span class="sxs-lookup"><span data-stu-id="f0d4f-102">The AS2 Decoder failed processing because the MDN indicated the AS2 message failed processing</span></span>
## <a name="details"></a><span data-ttu-id="f0d4f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f0d4f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f0d4f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f0d4f-104">Product Name</span></span>   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                |
| <span data-ttu-id="f0d4f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f0d4f-105">Product Version</span></span> |                                                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                            |
|    <span data-ttu-id="f0d4f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f0d4f-106">Event ID</span></span>     |                                                                                                        -                                                                                                         |
|  <span data-ttu-id="f0d4f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f0d4f-107">Event Source</span></span>   |                                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f0d4f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f0d4f-108"> EDI</span></span>                                                              |
|    <span data-ttu-id="f0d4f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f0d4f-109">Component</span></span>    |                                                                                                    <span data-ttu-id="f0d4f-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="f0d4f-110">AS2 Engine</span></span>                                                                                                    |
|  <span data-ttu-id="f0d4f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f0d4f-111">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="f0d4f-112">AS2DecoderMdnProcessingFailureReturned</span><span class="sxs-lookup"><span data-stu-id="f0d4f-112">AS2DecoderMdnProcessingFailureReturned</span></span>                                                                                      |
|  <span data-ttu-id="f0d4f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f0d4f-113">Message Text</span></span>   | <span data-ttu-id="f0d4f-114">AS2 メッセージを処理できなかったことが MDN によって示されたため、AS2 デコーダの処理は失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-114">The AS2 Decoder failure processing because the MDN indicated the AS2 message failed processing.</span></span>  <span data-ttu-id="f0d4f-115">MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"</span><span class="sxs-lookup"><span data-stu-id="f0d4f-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f0d4f-116">説明</span><span class="sxs-lookup"><span data-stu-id="f0d4f-116">Explanation</span></span>  
 <span data-ttu-id="f0d4f-117">このエラー/警告/情報イベントは、AS2 メッセージの受信者が元の AS2 メッセージを処理できなかったことが MDN 応答に示されていることを表します。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-117">This Error/Warning/Information event indicates that the MDN response shows that the receiver of the original AS2 message could not process the original AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f0d4f-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f0d4f-118">User Action</span></span>  
 <span data-ttu-id="f0d4f-119">このエラーを解決するには、AS2 メッセージの受信者に連絡し、受信側での処理が失敗した理由を確認して、元の AS2 メッセージを修正して再送信します。</span><span class="sxs-lookup"><span data-stu-id="f0d4f-119">To resolve this error, contact the receiver of the AS2 message, determine why processing failed at the receiver, fix the original AS2 message, and then resend.</span></span>