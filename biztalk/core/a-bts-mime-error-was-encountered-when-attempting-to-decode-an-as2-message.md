---
title: "AS2 メッセージをデコードしようとするときに BTS MIME エラーが発生しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 660a9e3a6ca5834448dd64815b031e00a0b2942a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a><span data-ttu-id="07da5-102">AS2 メッセージをデコードしようとしたときに BTS MIME エラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="07da5-102">A BTS MIME error was encountered when attempting to decode an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="07da5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="07da5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07da5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="07da5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="07da5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="07da5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="07da5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="07da5-106">Event ID</span></span>|-|  
|<span data-ttu-id="07da5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="07da5-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="07da5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="07da5-108"> EDI</span></span>|  
|<span data-ttu-id="07da5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="07da5-109">Component</span></span>|<span data-ttu-id="07da5-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="07da5-110">AS2 Engine</span></span>|  
|<span data-ttu-id="07da5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="07da5-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="07da5-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="07da5-112">Message Text</span></span>|<span data-ttu-id="07da5-113">AS2 メッセージをデコードしようとしたときに BTS MIME エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="07da5-113">A BTS MIME error was encountered when attempting to decode an AS2 message.</span></span>  <span data-ttu-id="07da5-114">AS2-から: {0}、AS2-を: {1}、MessageId: {2}、エラー: {3}</span><span class="sxs-lookup"><span data-stu-id="07da5-114">AS2-From: {0}, AS2-To: {1}, MessageId: {2}, Error: {3}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="07da5-115">説明</span><span class="sxs-lookup"><span data-stu-id="07da5-115">Explanation</span></span>  
 <span data-ttu-id="07da5-116">このエラーが発生するのは、BizTalk MIME コンポーネントを使用して MIME 処理の一部を実行するときです。</span><span class="sxs-lookup"><span data-stu-id="07da5-116">This error is encountered when using the BizTalk MIME component to handle part of the MIME processing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07da5-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="07da5-117">User Action</span></span>  
 <span data-ttu-id="07da5-118">完全なエラー メッセージは、MIME コンポーネントで発生した問題に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="07da5-118">The full error message provides the information about the problem encountered by the MIME component.</span></span> <span data-ttu-id="07da5-119">(これは、AS2 コンポーネントは MIME 処理の一部の BizTalk MIME コンポーネントを使用するため)、問題の診断に BTS MIME エラー情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07da5-119">Refer to the BTS MIME error information for diagnosis of the problem (this is because the AS2 components use the BizTalk MIME components for part of the MIME processing).</span></span>