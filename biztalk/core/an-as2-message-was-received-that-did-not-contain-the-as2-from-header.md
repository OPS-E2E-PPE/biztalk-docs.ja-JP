---
title: AS2 が含まれていない AS2 メッセージを受信-ヘッダーから |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 899f9b21-b321-49a3-84bd-a5410c883968
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8471dfe16338f71785062eca4484ca53185931d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005267"
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-from-header"></a><span data-ttu-id="9c9af-102">AS2-From ヘッダーが含まれていない AS2 メッセージを受信しました</span><span class="sxs-lookup"><span data-stu-id="9c9af-102">An AS2 message was received that did not contain the AS2-From header</span></span>
## <a name="details"></a><span data-ttu-id="9c9af-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9c9af-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9c9af-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9c9af-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9c9af-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9c9af-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9c9af-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9c9af-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9c9af-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9c9af-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9c9af-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9c9af-108"> EDI</span></span> |
|    <span data-ttu-id="9c9af-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9c9af-109">Component</span></span>    |                                       <span data-ttu-id="9c9af-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="9c9af-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="9c9af-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9c9af-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="9c9af-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9c9af-112">Message Text</span></span>   |          <span data-ttu-id="9c9af-113">AS2-From ヘッダーが含まれていない AS2 メッセージを受信しました</span><span class="sxs-lookup"><span data-stu-id="9c9af-113">An AS2 message was received that did not contain the AS2-From header</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="9c9af-114">説明</span><span class="sxs-lookup"><span data-stu-id="9c9af-114">Explanation</span></span>  
 <span data-ttu-id="9c9af-115">このエラー/警告/情報イベントは、メッセージにメッセージの送信元を示す AS2-From ヘッダーが含まれていなかったため、BizTalk Server が受信 AS2 メッセージを処理できなかったことを表します。</span><span class="sxs-lookup"><span data-stu-id="9c9af-115">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message did not contain an AS2-From header indicating the source of the message.</span></span> <span data-ttu-id="9c9af-116">AS2 メッセージには AS2-From ヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="9c9af-116">An AS2 message must have an AS2-From header.</span></span> <span data-ttu-id="9c9af-117">AS2-From ヘッダーがない場合、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="9c9af-117">The message will be suspended if it does not have an AS2-From header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9c9af-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9c9af-118">User Action</span></span>  
 <span data-ttu-id="9c9af-119">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c9af-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="9c9af-120">送信元パーティが AS2 メッセージを送信する前に、AS2 メッセージの HTTP、AS2、MIME の各ヘッダーに AS2-To ヘッダーを追加するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="9c9af-120">Ensure the sending party adds an AS2-To header to the HTTP, AS2, and MIME header of the AS2 message before sending it.</span></span>