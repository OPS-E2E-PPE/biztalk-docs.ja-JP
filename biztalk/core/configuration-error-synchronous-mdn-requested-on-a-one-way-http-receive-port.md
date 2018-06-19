---
title: 構成エラー。 受信ポートで一方向の HTTP 要求、同期 MDN |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f140c7a4-46bf-4557-9679-cdaf2fbe66f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa49120ecbdbd0a00de1bbd6cd552f56cb626ddd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232202"
---
# <a name="configuration-error-synchronous-mdn-requested-on-a-one-way-http-receive-port"></a><span data-ttu-id="f2864-103">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="f2864-103">Configuration error.</span></span> <span data-ttu-id="f2864-104">一方向の HTTP 受信ポートで同期 MDN が要求されました</span><span class="sxs-lookup"><span data-stu-id="f2864-104">Synchronous MDN requested on a one way HTTP receive Port</span></span>
## <a name="details"></a><span data-ttu-id="f2864-105">詳細</span><span class="sxs-lookup"><span data-stu-id="f2864-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2864-106">製品名</span><span class="sxs-lookup"><span data-stu-id="f2864-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f2864-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f2864-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f2864-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f2864-108">Event ID</span></span>|-|  
|<span data-ttu-id="f2864-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f2864-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f2864-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="f2864-110"> EDI</span></span>|  
|<span data-ttu-id="f2864-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f2864-111">Component</span></span>|<span data-ttu-id="f2864-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="f2864-112">EDI Engine</span></span>|  
|<span data-ttu-id="f2864-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f2864-113">Symbolic Name</span></span>|-|  
|<span data-ttu-id="f2864-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f2864-114">Message Text</span></span>|<span data-ttu-id="f2864-115">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="f2864-115">Configuration error.</span></span> <span data-ttu-id="f2864-116">一方向の HTTP 送信ポートで同期 MDN が要求されました。</span><span class="sxs-lookup"><span data-stu-id="f2864-116">Synchronous MDN requested on one way HTTP send port.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f2864-117">説明</span><span class="sxs-lookup"><span data-stu-id="f2864-117">Explanation</span></span>  
 <span data-ttu-id="f2864-118">このエラー/警告/情報イベントは、受信 AS2 メッセージを処理した HTTP 受信ポートが一方向ポートだったため、BizTalk Server が AS2 メッセージの受信後に同期 MDN を返すことができなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f2864-118">This Error/Warning/Information event indicates that BizTalk Server could not return a synchronous MDN after receiving an AS2 message because the HTTP receive port that processed the incoming AS2 message was a one-way port.</span></span> <span data-ttu-id="f2864-119">受信 AS2 メッセージに応答して同期 MDN を返すには、双方向の要求 - 応答受信ポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="f2864-119">A two-way request-response receive port is required to return a synchronous MDN in response to an incoming AS2 message.</span></span> <span data-ttu-id="f2864-120">この場合、AS2 メッセージに Disposition-Notification-To ヘッダーが含まれているか、または AS2 メッセージ送信者としてのパーティの構成で、[受信メッセージのプロパティを上書きする] プロパティがオン、[MDN の生成] プロパティがオン、[MDN を非同期に送信する] プロパティがオフになっているため、MDN は同期的に返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2864-120">In this case, the MDN must be returned synchronously because the AS2 message includes the Disposition-Notification-To header, or in the configuration for the party as an AS2 Message Sender, the Override inbound message properties property is checked, the Generate MDN property is checked, and the Transmit MDN asynchronously property is cleared.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f2864-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f2864-121">User Action</span></span>  
 <span data-ttu-id="f2864-122">このエラーを解決するには、AS2 メッセージを受信している受信ポートを、一方向の受信ポートとするのではなく、要求 - 応答の受信ポートに変更します。</span><span class="sxs-lookup"><span data-stu-id="f2864-122">To resolve this error, change the receive port that is receiving the AS2 message to be a request response receive port, rather than a one-way receive port.</span></span> <span data-ttu-id="f2864-123">要求 - 応答の受信場所の送信パイプラインを、EDI インターチェンジに対しては AS2EdiSend とし、非 EDI インターチェンジに対しては AS2Send に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2864-123">Set the send pipeline of the request response receive location to be AS2EdiSend for an EDI interchange or AS2Send for a non-EDI interchange.</span></span>