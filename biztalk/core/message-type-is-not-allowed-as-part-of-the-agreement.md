---
title: "メッセージの種類が、アグリーメントの一部として許可されていません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979aa43d23d2fca95c244e10cb9d4768d76cf3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a><span data-ttu-id="2dcf8-102">メッセージの種類はアグリーメントの一部として使用できません</span><span class="sxs-lookup"><span data-stu-id="2dcf8-102">Message Type is not allowed as part of the Agreement</span></span>
## <a name="details"></a><span data-ttu-id="2dcf8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2dcf8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2dcf8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2dcf8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2dcf8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2dcf8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2dcf8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2dcf8-106">Event ID</span></span>|-|  
|<span data-ttu-id="2dcf8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2dcf8-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2dcf8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="2dcf8-108"> EDI</span></span>|  
|<span data-ttu-id="2dcf8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2dcf8-109">Component</span></span>|<span data-ttu-id="2dcf8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="2dcf8-110">EDI Engine</span></span>|  
|<span data-ttu-id="2dcf8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2dcf8-111">Symbolic Name</span></span>|<span data-ttu-id="2dcf8-112">TransactionSetNotAllowedDescription</span><span class="sxs-lookup"><span data-stu-id="2dcf8-112">TransactionSetNotAllowedDescription</span></span>|  
|<span data-ttu-id="2dcf8-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2dcf8-113">Message Text</span></span>|<span data-ttu-id="2dcf8-114">アグリーメントの一部としては、メッセージの種類 {0} することはできません。</span><span class="sxs-lookup"><span data-stu-id="2dcf8-114">Message Type {0} is not allowed as part of the Agreement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2dcf8-115">説明</span><span class="sxs-lookup"><span data-stu-id="2dcf8-115">Explanation</span></span>  
 <span data-ttu-id="2dcf8-116">このエラー/警告/情報イベントは、ドキュメントのメッセージの種類がアグリーメントの一部として許可されていないため、BizTalk Server がドキュメントを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="2dcf8-116">This Error/Warning/Information event indicates BizTalk Server was able to process the document because the message type of the document is not allowed as part of the agreement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2dcf8-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2dcf8-117">User Action</span></span>  
 <span data-ttu-id="2dcf8-118">このエラーを解決するには、アグリーメントの一部として許可されているメッセージの種類と、許可されていないメッセージの種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="2dcf8-118">To resolve this error, please look at the message types that are allowed and not allowed as part of the agreement.</span></span>