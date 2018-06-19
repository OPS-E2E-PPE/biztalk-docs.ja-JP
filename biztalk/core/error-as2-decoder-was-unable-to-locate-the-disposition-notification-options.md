---
title: AS2 デコーダが廃棄通知オプションの HTTP ヘッダーを見つけられませんでした |Microsoft ドキュメント
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
ms.openlocfilehash: 966860c7f2b7b47187b861ed6b81fb14a4753872
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240018"
---
# <a name="the-as2-decoder-was-unable-to-locate-the-disposition-notification-options-http-header"></a><span data-ttu-id="fb063-102">AS2 デコーダーは、Disposition-Notification-Options HTTP ヘッダーを見つけられませんでした</span><span class="sxs-lookup"><span data-stu-id="fb063-102">The AS2 Decoder was unable to locate the Disposition-Notification-Options HTTP header</span></span>
## <a name="details"></a><span data-ttu-id="fb063-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fb063-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb063-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fb063-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="fb063-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fb063-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="fb063-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fb063-106">Event ID</span></span>|-|  
|<span data-ttu-id="fb063-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fb063-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fb063-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="fb063-108"> EDI</span></span>|  
|<span data-ttu-id="fb063-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fb063-109">Component</span></span>|<span data-ttu-id="fb063-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="fb063-110">AS2 Engine</span></span>|  
|<span data-ttu-id="fb063-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fb063-111">Symbolic Name</span></span>|<span data-ttu-id="fb063-112">AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError</span><span class="sxs-lookup"><span data-stu-id="fb063-112">AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError</span></span>|  
|<span data-ttu-id="fb063-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fb063-113">Message Text</span></span>|<span data-ttu-id="fb063-114">AS2 デコーダは、MDN の生成に必要な Disposition-Notification-Options HTTP ヘッダーを見つけられませんでした。</span><span class="sxs-lookup"><span data-stu-id="fb063-114">The AS2 Decoder was unable to locate the Disposition-Notification-Options HTTP header which is required for MDN generation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fb063-115">説明</span><span class="sxs-lookup"><span data-stu-id="fb063-115">Explanation</span></span>  
 <span data-ttu-id="fb063-116">このエラー/警告/情報イベントは、受信 AS2 メッセージに、MDN が署名されている必要があるかどうかと、使用する必要がある MIC アルゴリズムを示す Disposition-Notification-Options ヘッダーが含まれていなかったため、受信パイプラインで MDN を生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="fb063-116">This Error/Warning/Information event indicates that the receive pipeline could not generate the MDN because the incoming AS2 message did not include the Disposition-Notification-Options header that indicates whether the MDN must be signed and which MIC algorithm must be used.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fb063-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fb063-117">User Action</span></span>  
 <span data-ttu-id="fb063-118">このエラーを解決するには、AS2 メッセージの送信者に対して、メッセージに Disposition-Notification-Options ヘッダーを含め、メッセージを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="fb063-118">To resolve this error, have the sender of the AS2 message include the Disposition-Notification-Options header in the message and then resend the message.</span></span>