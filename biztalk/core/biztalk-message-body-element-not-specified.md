---
title: "BizTalk メッセージ本文の要素が指定されていない |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af5d63c0-af96-4e34-828f-d29638cdf46d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf79c8896169a06df66a8484377816c9897531e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-message-body-element-not-specified"></a><span data-ttu-id="45eb0-102">BizTalk メッセージ本文要素が指定されていません</span><span class="sxs-lookup"><span data-stu-id="45eb0-102">BizTalk message body element not specified</span></span>
## <a name="details"></a><span data-ttu-id="45eb0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="45eb0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45eb0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="45eb0-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="45eb0-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="45eb0-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="45eb0-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="45eb0-106">Event ID</span></span>|<span data-ttu-id="45eb0-107">0</span><span class="sxs-lookup"><span data-stu-id="45eb0-107">0</span></span>|  
|<span data-ttu-id="45eb0-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="45eb0-108">Event Source</span></span>|<span data-ttu-id="45eb0-109">0</span><span class="sxs-lookup"><span data-stu-id="45eb0-109">0</span></span>|  
|<span data-ttu-id="45eb0-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="45eb0-110">Component</span></span>|<span data-ttu-id="45eb0-111">0</span><span class="sxs-lookup"><span data-stu-id="45eb0-111">0</span></span>|  
|<span data-ttu-id="45eb0-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="45eb0-112">Symbolic Name</span></span>|<span data-ttu-id="45eb0-113">0</span><span class="sxs-lookup"><span data-stu-id="45eb0-113">0</span></span>|  
|<span data-ttu-id="45eb0-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="45eb0-114">Message Text</span></span>|<span data-ttu-id="45eb0-115">BizTalk メッセージ本文要素が指定されていません</span><span class="sxs-lookup"><span data-stu-id="45eb0-115">BizTalk message body element not specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="45eb0-116">説明</span><span class="sxs-lookup"><span data-stu-id="45eb0-116">Explanation</span></span>  
 <span data-ttu-id="45eb0-117">このエラーは、送信 WCF メッセージにテンプレート オプションが使用されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="45eb0-117">This error indicates the use of the template option for the outbound WCF message.</span></span> <span data-ttu-id="45eb0-118">一方で、テンプレート式には BizTalk メッセージ本文要素が含まれません。</span><span class="sxs-lookup"><span data-stu-id="45eb0-118">However, the template expression doesn’t contain the BizTalk message body element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="45eb0-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="45eb0-119">User Action</span></span>  
 <span data-ttu-id="45eb0-120">テンプレート式に次の要素が含まれていることを確認します\< **bts メッセージ本文の xmlns ="http://www.microsoft.com/schemas/bts2007"encoding ="[xml (&) #124; base64 &#124; 16 進数 (&) #124; 文字列]"/** 。>。</span><span class="sxs-lookup"><span data-stu-id="45eb0-120">Ensure that the template expression contains the following element: \<**bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="[xml&#124;base64&#124;hex&#124;string]"/**>.</span></span>