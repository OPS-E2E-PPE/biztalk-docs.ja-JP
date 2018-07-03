---
title: ディス ポジション-通知のオプションが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b807a8-eec9-45a5-83cc-075c91b4bc9e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50831c03bc7dc0412cdb6fcd40ca981e87cf43f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023192"
---
# <a name="disposition-notification-option-is-invalid"></a><span data-ttu-id="73913-102">Disposition-Notification-Option が無効です</span><span class="sxs-lookup"><span data-stu-id="73913-102">Disposition-Notification-Option is invalid</span></span>
## <a name="details"></a><span data-ttu-id="73913-103">詳細</span><span class="sxs-lookup"><span data-stu-id="73913-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="73913-104">製品名</span><span class="sxs-lookup"><span data-stu-id="73913-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="73913-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="73913-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="73913-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="73913-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="73913-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="73913-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="73913-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="73913-108"> EDI</span></span> |
|    <span data-ttu-id="73913-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="73913-109">Component</span></span>    |                                       <span data-ttu-id="73913-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="73913-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="73913-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="73913-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="73913-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="73913-112">Message Text</span></span>   |              <span data-ttu-id="73913-113">ディス ポジション-通知-オプションの値:"{0}"が無効です。</span><span class="sxs-lookup"><span data-stu-id="73913-113">Disposition-Notification-Option value: "{0}" is invalid.</span></span> <span data-ttu-id="73913-114">{1}</span><span class="sxs-lookup"><span data-stu-id="73913-114">{1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="73913-115">説明</span><span class="sxs-lookup"><span data-stu-id="73913-115">Explanation</span></span>  
 <span data-ttu-id="73913-116">このエラー/警告/情報イベントは、Disposition-Notification-Option ヘッダーが無効だったため、AS2 受信パイプラインが MDN を生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="73913-116">This Error/Warning/Information event indicates that the AS2 receive pipeline could not generate the MDN because the Disposition-Notification-Option header was invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="73913-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="73913-117">User Action</span></span>  
 <span data-ttu-id="73913-118">このエラーを解決するには、AS2 メッセージの Disposition-Notification-Option ヘッダーが RFC 4130「MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)」に記載されている構文に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="73913-118">To resolve this error, make sure that the Disposition-Notification-Option header in the AS2 message conforms to the syntax described in RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2").</span></span> <span data-ttu-id="73913-119">Signed-Receipt-Protocol ヘッダーが "optional" または "pcks7-signature" に設定され、Signed-Receipt-MICAlg ヘッダーが "optional"、"MD5"、または "SHA1" に設定されていることを確認します </span><span class="sxs-lookup"><span data-stu-id="73913-119">Ensure that the Signed-Receipt-Protocol header is set to "optional" or "pcks7-signature", and that the Signed-Receipt-MICAlg header is set to "optional", "MD5", or "SHA1".</span></span> <span data-ttu-id="73913-120">(これらのヘッダーは、どちらも Disposition-Notification-Option ヘッダーに含まれています)。</span><span class="sxs-lookup"><span data-stu-id="73913-120">(Both of these headers are included in the Disposition-Notification-Option header.)</span></span>