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
ms.openlocfilehash: 0656cf14e1c2a16d6d53966e316550020c8cd0af
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="biztalk-message-body-element-not-specified"></a><span data-ttu-id="7ed77-102">BizTalk メッセージ本文要素が指定されていません</span><span class="sxs-lookup"><span data-stu-id="7ed77-102">BizTalk message body element not specified</span></span>
## <a name="details"></a><span data-ttu-id="7ed77-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7ed77-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ed77-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7ed77-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7ed77-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7ed77-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="7ed77-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7ed77-106">Event ID</span></span>|<span data-ttu-id="7ed77-107">0</span><span class="sxs-lookup"><span data-stu-id="7ed77-107">0</span></span>|  
|<span data-ttu-id="7ed77-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7ed77-108">Event Source</span></span>|<span data-ttu-id="7ed77-109">0</span><span class="sxs-lookup"><span data-stu-id="7ed77-109">0</span></span>|  
|<span data-ttu-id="7ed77-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7ed77-110">Component</span></span>|<span data-ttu-id="7ed77-111">0</span><span class="sxs-lookup"><span data-stu-id="7ed77-111">0</span></span>|  
|<span data-ttu-id="7ed77-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7ed77-112">Symbolic Name</span></span>|<span data-ttu-id="7ed77-113">0</span><span class="sxs-lookup"><span data-stu-id="7ed77-113">0</span></span>|  
|<span data-ttu-id="7ed77-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7ed77-114">Message Text</span></span>|<span data-ttu-id="7ed77-115">BizTalk メッセージ本文要素が指定されていません</span><span class="sxs-lookup"><span data-stu-id="7ed77-115">BizTalk message body element not specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7ed77-116">説明</span><span class="sxs-lookup"><span data-stu-id="7ed77-116">Explanation</span></span>  
 <span data-ttu-id="7ed77-117">このエラーは、送信 WCF メッセージにテンプレート オプションが使用されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="7ed77-117">This error indicates the use of the template option for the outbound WCF message.</span></span> <span data-ttu-id="7ed77-118">一方で、テンプレート式には BizTalk メッセージ本文要素が含まれません。</span><span class="sxs-lookup"><span data-stu-id="7ed77-118">However, the template expression doesn’t contain the BizTalk message body element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ed77-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7ed77-119">User Action</span></span>  
 <span data-ttu-id="7ed77-120">テンプレート式に次の要素が含まれていることを確認します\< **bts メッセージ本文の xmlns ="http://www.microsoft.com/schemas/bts2007"encoding ="[xml &#124; base64 &#124; 16 進数 &#124; 文字列]"/**\>。</span><span class="sxs-lookup"><span data-stu-id="7ed77-120">Ensure that the template expression contains the following element: \<**bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>.</span></span>