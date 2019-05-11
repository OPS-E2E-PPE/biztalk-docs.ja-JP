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
ms.openlocfilehash: 3c2507c1eafa258335302f4670f612db1b213e82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389016"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-indicated-the-as2-message-failed-processing"></a><span data-ttu-id="dee3f-102">AS2 デコーダーは MDN に失敗したメッセージの AS2 処理が示されるため、処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="dee3f-102">The AS2 Decoder failed processing because the MDN indicated the AS2 message failed processing</span></span>
## <a name="details"></a><span data-ttu-id="dee3f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="dee3f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dee3f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="dee3f-104">Product Name</span></span>   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                |
| <span data-ttu-id="dee3f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="dee3f-105">Product Version</span></span> |                                                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                            |
|    <span data-ttu-id="dee3f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="dee3f-106">Event ID</span></span>     |                                                                                                        -                                                                                                         |
|  <span data-ttu-id="dee3f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="dee3f-107">Event Source</span></span>   |                                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="dee3f-108">EDI</span><span class="sxs-lookup"><span data-stu-id="dee3f-108">EDI</span></span>                                                              |
|    <span data-ttu-id="dee3f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dee3f-109">Component</span></span>    |                                                                                                    <span data-ttu-id="dee3f-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="dee3f-110">AS2 Engine</span></span>                                                                                                    |
|  <span data-ttu-id="dee3f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="dee3f-111">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="dee3f-112">AS2DecoderMdnProcessingFailureReturned</span><span class="sxs-lookup"><span data-stu-id="dee3f-112">AS2DecoderMdnProcessingFailureReturned</span></span>                                                                                      |
|  <span data-ttu-id="dee3f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="dee3f-113">Message Text</span></span>   | <span data-ttu-id="dee3f-114">AS2 デコーダー、MDN が AS2 メッセージを示すため、処理されているエラー処理に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="dee3f-114">The AS2 Decoder failure processing because the MDN indicated the AS2 message failed processing.</span></span>  <span data-ttu-id="dee3f-115">MDN メッセージの詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"</span><span class="sxs-lookup"><span data-stu-id="dee3f-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dee3f-116">説明</span><span class="sxs-lookup"><span data-stu-id="dee3f-116">Explanation</span></span>  
 <span data-ttu-id="dee3f-117">このエラー/警告/情報イベントでは、元の AS2 メッセージの受信者が元の AS2 メッセージを処理できなかったことを MDN 応答が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="dee3f-117">This Error/Warning/Information event indicates that the MDN response shows that the receiver of the original AS2 message could not process the original AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dee3f-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="dee3f-118">User Action</span></span>  
 <span data-ttu-id="dee3f-119">このエラーを解決する、AS2 メッセージの受信者にお問い合わせください、受信側では、処理が失敗した理由を判断し、元の AS2 メッセージを修正し再送信します。</span><span class="sxs-lookup"><span data-stu-id="dee3f-119">To resolve this error, contact the receiver of the AS2 message, determine why processing failed at the receiver, fix the original AS2 message, and then resend.</span></span>