---
title: AS2 が含まれていない AS2 メッセージを受信-ヘッダー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 343a9b41-fcd9-4508-ac65-9b6e05ec6496
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8bee1ee759a8aefb83aa3045808b6ce22689a6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359244"
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-to-header"></a><span data-ttu-id="1e794-102">AS2-To ヘッダーが含まれていない AS2 メッセージを受信しました</span><span class="sxs-lookup"><span data-stu-id="1e794-102">An AS2 message was received that did not contain the AS2-To header</span></span>
## <a name="details"></a><span data-ttu-id="1e794-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1e794-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="1e794-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1e794-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="1e794-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1e794-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="1e794-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1e794-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="1e794-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1e794-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1e794-108">EDI</span><span class="sxs-lookup"><span data-stu-id="1e794-108">EDI</span></span> |
|    <span data-ttu-id="1e794-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1e794-109">Component</span></span>    |                                       <span data-ttu-id="1e794-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="1e794-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="1e794-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1e794-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="1e794-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1e794-112">Message Text</span></span>   |           <span data-ttu-id="1e794-113">AS2-To ヘッダーが含まれていない AS2 メッセージを受信しました</span><span class="sxs-lookup"><span data-stu-id="1e794-113">An AS2 message was received that did not contain the AS2-To header</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="1e794-114">説明</span><span class="sxs-lookup"><span data-stu-id="1e794-114">Explanation</span></span>  
 <span data-ttu-id="1e794-115">このエラー/警告/情報イベントは、メッセージにメッセージの送信元を示す AS2-To ヘッダーが含まれていなかったため、BizTalk Server が受信 AS2 メッセージを処理できなかったことを表します。</span><span class="sxs-lookup"><span data-stu-id="1e794-115">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message did not contain an AS2-To header indicating the source of the message.</span></span> <span data-ttu-id="1e794-116">AS2 メッセージには AS2-To ヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="1e794-116">An AS2 message must have an AS2-To header.</span></span> <span data-ttu-id="1e794-117">メッセージに AS2-To ヘッダーがない場合、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="1e794-117">The message will be suspended if it does not have an AS2-To header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1e794-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1e794-118">User Action</span></span>  
 <span data-ttu-id="1e794-119">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1e794-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="1e794-120">送信元パーティが AS2 メッセージを送信する前に、AS2 メッセージの HTTP、AS2、MIME の各ヘッダーに AS2-To ヘッダーを追加するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1e794-120">Ensure the sending party adds an AS2-To header to the HTTP, AS2, and MIME header of the AS2 message before sending it.</span></span>