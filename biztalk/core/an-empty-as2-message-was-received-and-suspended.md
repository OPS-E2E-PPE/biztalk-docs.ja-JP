---
title: 空の AS2 メッセージが受信され、中断 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 349f7134-d039-44ab-b2b3-d378d38dfd38
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1c99776d350f556855b541290fac1f6a65f5921
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360256"
---
# <a name="an-empty-as2-message-was-received-and-suspended"></a><span data-ttu-id="fed5f-102">空の AS2 メッセージが受信され、中断</span><span class="sxs-lookup"><span data-stu-id="fed5f-102">An empty AS2 message was received and suspended</span></span>
## <a name="details"></a><span data-ttu-id="fed5f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fed5f-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="fed5f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fed5f-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="fed5f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fed5f-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="fed5f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fed5f-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="fed5f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fed5f-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="fed5f-108">EDI</span><span class="sxs-lookup"><span data-stu-id="fed5f-108">EDI</span></span> |
|    <span data-ttu-id="fed5f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fed5f-109">Component</span></span>    |                                       <span data-ttu-id="fed5f-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="fed5f-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="fed5f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fed5f-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="fed5f-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fed5f-112">Message Text</span></span>   |           <span data-ttu-id="fed5f-113">空の AS2 メッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="fed5f-113">An empty AS2 message was received.</span></span>  <span data-ttu-id="fed5f-114">メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="fed5f-114">The message will be suspended.</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="fed5f-115">説明</span><span class="sxs-lookup"><span data-stu-id="fed5f-115">Explanation</span></span>  
 <span data-ttu-id="fed5f-116">このエラー/警告/情報イベントは、メッセージに本文が含まれていないため、BizTalk Server が受信 AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="fed5f-116">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message does not contain a body.</span></span> <span data-ttu-id="fed5f-117">本文は 2 回の復帰/改行によってヘッダーと区切られている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fed5f-117">The body must be separated from the headers by two carriage return/line feeds.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fed5f-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fed5f-118">User Action</span></span>  
 <span data-ttu-id="fed5f-119">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fed5f-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="fed5f-120">AS2 メッセージの送信前に、送信元のパーティによってメッセージに必ず本文 (2 回の復帰/改行によってヘッダーと区切られている) が追加されるようにします。</span><span class="sxs-lookup"><span data-stu-id="fed5f-120">Ensure the sending party adds a body (separated from the headers by two carriage return/line feeds) to the AS2 message before sending it.</span></span>