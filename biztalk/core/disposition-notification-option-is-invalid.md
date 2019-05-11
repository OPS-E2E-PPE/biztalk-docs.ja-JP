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
ms.openlocfilehash: 8956b6ef3dd583522bb142e646920d4731651391
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351004"
---
# <a name="disposition-notification-option-is-invalid"></a><span data-ttu-id="a1319-102">ディス ポジション-通知のオプションが無効です。</span><span class="sxs-lookup"><span data-stu-id="a1319-102">Disposition-Notification-Option is invalid</span></span>
## <a name="details"></a><span data-ttu-id="a1319-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a1319-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a1319-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a1319-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a1319-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a1319-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a1319-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a1319-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a1319-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a1319-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a1319-108">EDI</span><span class="sxs-lookup"><span data-stu-id="a1319-108">EDI</span></span> |
|    <span data-ttu-id="a1319-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a1319-109">Component</span></span>    |                                       <span data-ttu-id="a1319-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="a1319-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="a1319-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a1319-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="a1319-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a1319-112">Message Text</span></span>   |              <span data-ttu-id="a1319-113">ディス ポジション-通知-オプションの値:"{0}"が無効です。</span><span class="sxs-lookup"><span data-stu-id="a1319-113">Disposition-Notification-Option value: "{0}" is invalid.</span></span> <span data-ttu-id="a1319-114">{1}</span><span class="sxs-lookup"><span data-stu-id="a1319-114">{1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="a1319-115">説明</span><span class="sxs-lookup"><span data-stu-id="a1319-115">Explanation</span></span>  
 <span data-ttu-id="a1319-116">このエラー/警告/情報イベントは、AS2 の受信を示す通知オプションが廃棄 - ヘッダーが無効なために、パイプラインは MDN を生成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a1319-116">This Error/Warning/Information event indicates that the AS2 receive pipeline could not generate the MDN because the Disposition-Notification-Option header was invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a1319-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a1319-117">User Action</span></span>  
 <span data-ttu-id="a1319-118">このエラーを解決するには、AS2 メッセージのディス ポジション-通知オプション ヘッダーが RFC 4130 で説明する構文に準拠しているかどうかを確認"Mime-based Secure ピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2")。</span><span class="sxs-lookup"><span data-stu-id="a1319-118">To resolve this error, make sure that the Disposition-Notification-Option header in the AS2 message conforms to the syntax described in RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2").</span></span> <span data-ttu-id="a1319-119">署名済みの受信プロトコル ヘッダーを"optional"または「pcks7-署名」に設定されているの Signed-receipt-micalg ヘッダーが"optional"、"MD5"または"SHA1"に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1319-119">Ensure that the Signed-Receipt-Protocol header is set to "optional" or "pcks7-signature", and that the Signed-Receipt-MICAlg header is set to "optional", "MD5", or "SHA1".</span></span> <span data-ttu-id="a1319-120">(これらのヘッダーの両方に含まれる廃棄通知-オプション ヘッダー。)</span><span class="sxs-lookup"><span data-stu-id="a1319-120">(Both of these headers are included in the Disposition-Notification-Option header.)</span></span>