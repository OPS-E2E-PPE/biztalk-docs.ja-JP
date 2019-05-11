---
title: 構成エラー。 送信ポートで一方向の HTTP 要求されている同期 MDN |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd38eb3-321f-4738-b35e-390f4f54673e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1e52f0d7107a09357af0b6ab35db15ad0a8514c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391526"
---
# <a name="configuration-error-synchronous-mdn-requested-on-one-way-http-send-port"></a><span data-ttu-id="e5d61-103">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="e5d61-103">Configuration error.</span></span> <span data-ttu-id="e5d61-104">送信ポートで一方向の HTTP 要求された MDN が同期</span><span class="sxs-lookup"><span data-stu-id="e5d61-104">Synchronous MDN requested on one way HTTP send port</span></span>
## <a name="details"></a><span data-ttu-id="e5d61-105">詳細</span><span class="sxs-lookup"><span data-stu-id="e5d61-105">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e5d61-106">製品名</span><span class="sxs-lookup"><span data-stu-id="e5d61-106">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e5d61-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e5d61-107">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e5d61-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e5d61-108">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e5d61-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e5d61-109">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e5d61-110">EDI</span><span class="sxs-lookup"><span data-stu-id="e5d61-110">EDI</span></span> |
|    <span data-ttu-id="e5d61-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e5d61-111">Component</span></span>    |                                       <span data-ttu-id="e5d61-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e5d61-112">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e5d61-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e5d61-113">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="e5d61-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e5d61-114">Message Text</span></span>   |       <span data-ttu-id="e5d61-115">構成エラー。</span><span class="sxs-lookup"><span data-stu-id="e5d61-115">Configuration error.</span></span> <span data-ttu-id="e5d61-116">一方向の HTTP 送信ポートで同期 MDN が要求されました。</span><span class="sxs-lookup"><span data-stu-id="e5d61-116">Synchronous MDN requested on one way HTTP send port.</span></span>        |
  
## <a name="explanation"></a><span data-ttu-id="e5d61-117">説明</span><span class="sxs-lookup"><span data-stu-id="e5d61-117">Explanation</span></span>  
 <span data-ttu-id="e5d61-118">このエラー/警告/情報イベントは、AS2 メッセージを送信した HTTP 送信ポートが一方向ポートであったため、BizTalk Server が AS2 メッセージ送信後の同期 MDN を受信できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e5d61-118">This Error/Warning/Information event indicates that BizTalk Server could not receive a synchronous MDN after sending an AS2 message because the HTTP send port that sent the AS2 message was a one-way port.</span></span> <span data-ttu-id="e5d61-119">ポートから送信された AS2 メッセージへの応答として返される同期 MDN を処理するには、双方向の送信請求 - 応答の送信ポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="e5d61-119">A two-way solicit-response send port is required to process a synchronous MDN returned in response to an AS2 message sent by the port.</span></span> <span data-ttu-id="e5d61-120">この場合、AS2 メッセージの受信者としてのパーティの構成で [MDN を要求する] プロパティがオンになっており、[非同期 MDN を要求する] プロパティがオフになっているため、MDN は同期的に返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5d61-120">In this case, the MDN must be returned synchronously because in the configuration for the party as an AS2 Message Receiver, the Request MDN property is checked, and the Request asynchronous MDN property is cleared.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e5d61-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e5d61-121">User Action</span></span>  
 <span data-ttu-id="e5d61-122">このエラーを解決するには、AS2 メッセージの送信元の送信ポートを、一方向の送信ポートではなく静的な送信請求 - 応答の送信ポートに変更します。</span><span class="sxs-lookup"><span data-stu-id="e5d61-122">To resolve this error, change the send port that is sending the AS2 message to be a static solicit-response send port, rather than a one-way send port.</span></span> <span data-ttu-id="e5d61-123">送信請求 - 応答の送信ポートの受信パイプラインを AS2EdiReceive (EDI インターチェンジ用) または AS2Receive (非 EDI インターチェンジ用) に設定します。</span><span class="sxs-lookup"><span data-stu-id="e5d61-123">Set the receive pipeline of the solicit-response send port to be AS2EdiReceive for an EDI interchange or AS2Receive for a non-EDI interchange.</span></span>