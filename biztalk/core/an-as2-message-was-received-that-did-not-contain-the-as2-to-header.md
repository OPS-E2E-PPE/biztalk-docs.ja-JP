---
title: AS2 メッセージを受信した AS2 が含まれていません-ヘッダー |。Microsoft ドキュメント
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
ms.openlocfilehash: 7176966bb22a38ba32ae5203f5ac142bdfd9df4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230138"
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-to-header"></a><span data-ttu-id="e4f54-102">AS2-To ヘッダーが含まれていない AS2 メッセージを受信しました</span><span class="sxs-lookup"><span data-stu-id="e4f54-102">An AS2 message was received that did not contain the AS2-To header</span></span>
## <a name="details"></a><span data-ttu-id="e4f54-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e4f54-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e4f54-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e4f54-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e4f54-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e4f54-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e4f54-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e4f54-106">Event ID</span></span>|-|  
|<span data-ttu-id="e4f54-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e4f54-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e4f54-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e4f54-108"> EDI</span></span>|  
|<span data-ttu-id="e4f54-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e4f54-109">Component</span></span>|<span data-ttu-id="e4f54-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="e4f54-110">AS2 Engine</span></span>|  
|<span data-ttu-id="e4f54-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e4f54-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="e4f54-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e4f54-112">Message Text</span></span>|<span data-ttu-id="e4f54-113">AS2-To ヘッダーが含まれていない AS2 メッセージを受信しました</span><span class="sxs-lookup"><span data-stu-id="e4f54-113">An AS2 message was received that did not contain the AS2-To header</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e4f54-114">説明</span><span class="sxs-lookup"><span data-stu-id="e4f54-114">Explanation</span></span>  
 <span data-ttu-id="e4f54-115">このエラー/警告/情報イベントは、メッセージにメッセージの送信元を示す AS2-To ヘッダーが含まれていなかったため、BizTalk Server が受信 AS2 メッセージを処理できなかったことを表します。</span><span class="sxs-lookup"><span data-stu-id="e4f54-115">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message did not contain an AS2-To header indicating the source of the message.</span></span> <span data-ttu-id="e4f54-116">AS2 メッセージには AS2-To ヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="e4f54-116">An AS2 message must have an AS2-To header.</span></span> <span data-ttu-id="e4f54-117">メッセージに AS2-To ヘッダーがない場合、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="e4f54-117">The message will be suspended if it does not have an AS2-To header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e4f54-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e4f54-118">User Action</span></span>  
 <span data-ttu-id="e4f54-119">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e4f54-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="e4f54-120">送信元パーティが AS2 メッセージを送信する前に、AS2 メッセージの HTTP、AS2、MIME の各ヘッダーに AS2-To ヘッダーを追加するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="e4f54-120">Ensure the sending party adds an AS2-To header to the HTTP, AS2, and MIME header of the AS2 message before sending it.</span></span>