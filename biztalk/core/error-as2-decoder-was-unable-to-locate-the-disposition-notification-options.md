---
title: AS2 デコーダーが廃棄通知-オプションの HTTP ヘッダーを見つけられませんでした |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6de4b9a6-17b2-4455-9dbd-a6bb69fac1d5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ef3f6f9e571f3469c2bd0de163f7ada90d0be7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388972"
---
# <a name="the-as2-decoder-was-unable-to-locate-the-disposition-notification-options-http-header"></a><span data-ttu-id="c9fe4-102">AS2 デコーダーが廃棄通知-オプションの HTTP ヘッダーを見つけられませんでした。</span><span class="sxs-lookup"><span data-stu-id="c9fe4-102">The AS2 Decoder was unable to locate the Disposition-Notification-Options HTTP header</span></span>
## <a name="details"></a><span data-ttu-id="c9fe4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c9fe4-103">Details</span></span>  
  
|                 |                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c9fe4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c9fe4-104">Product Name</span></span>   |                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                      |
| <span data-ttu-id="c9fe4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c9fe4-105">Product Version</span></span> |                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                  |
|    <span data-ttu-id="c9fe4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c9fe4-106">Event ID</span></span>     |                                                              -                                                              |
|  <span data-ttu-id="c9fe4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c9fe4-107">Event Source</span></span>   |                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c9fe4-108">EDI</span><span class="sxs-lookup"><span data-stu-id="c9fe4-108">EDI</span></span>                    |
|    <span data-ttu-id="c9fe4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c9fe4-109">Component</span></span>    |                                                         <span data-ttu-id="c9fe4-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="c9fe4-110">AS2 Engine</span></span>                                                          |
|  <span data-ttu-id="c9fe4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c9fe4-111">Symbolic Name</span></span>  |                               <span data-ttu-id="c9fe4-112">AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError</span><span class="sxs-lookup"><span data-stu-id="c9fe4-112">AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError</span></span>                                |
|  <span data-ttu-id="c9fe4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c9fe4-113">Message Text</span></span>   | <span data-ttu-id="c9fe4-114">AS2 デコーダは、MDN の生成に必要な Disposition-Notification-Options HTTP ヘッダーを見つけられませんでした。</span><span class="sxs-lookup"><span data-stu-id="c9fe4-114">The AS2 Decoder was unable to locate the Disposition-Notification-Options HTTP header which is required for MDN generation.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c9fe4-115">説明</span><span class="sxs-lookup"><span data-stu-id="c9fe4-115">Explanation</span></span>  
 <span data-ttu-id="c9fe4-116">このエラー/警告/情報イベントは、受信 AS2 メッセージに、MDN が署名されている必要があるかどうかと、使用する必要がある MIC アルゴリズムを示す Disposition-Notification-Options ヘッダーが含まれていなかったため、受信パイプラインで MDN を生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c9fe4-116">This Error/Warning/Information event indicates that the receive pipeline could not generate the MDN because the incoming AS2 message did not include the Disposition-Notification-Options header that indicates whether the MDN must be signed and which MIC algorithm must be used.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9fe4-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c9fe4-117">User Action</span></span>  
 <span data-ttu-id="c9fe4-118">このエラーを解決するには、AS2 メッセージの送信者に対して、メッセージに Disposition-Notification-Options ヘッダーを含め、メッセージを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="c9fe4-118">To resolve this error, have the sender of the AS2 message include the Disposition-Notification-Options header in the message and then resend the message.</span></span>