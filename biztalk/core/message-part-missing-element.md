---
title: メッセージ部分の要素がありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b519315f-d51d-4ca3-a0e6-d08bb920c6c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 412b25d2f7ea027de53818b032b50562faab9865
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009443"
---
# <a name="message-part-missing-element"></a><span data-ttu-id="256cf-102">メッセージ部分に要素が見つかりません</span><span class="sxs-lookup"><span data-stu-id="256cf-102">Message part missing element</span></span>
## <a name="details"></a><span data-ttu-id="256cf-103">詳細</span><span class="sxs-lookup"><span data-stu-id="256cf-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="256cf-104">製品名</span><span class="sxs-lookup"><span data-stu-id="256cf-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="256cf-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="256cf-105">Product Version</span></span> |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    <span data-ttu-id="256cf-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="256cf-106">Event ID</span></span>     |                                                         <span data-ttu-id="256cf-107">0</span><span class="sxs-lookup"><span data-stu-id="256cf-107">0</span></span>                                                          |
|  <span data-ttu-id="256cf-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="256cf-108">Event Source</span></span>   |                                                         <span data-ttu-id="256cf-109">0</span><span class="sxs-lookup"><span data-stu-id="256cf-109">0</span></span>                                                          |
|    <span data-ttu-id="256cf-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="256cf-110">Component</span></span>    |                                                         <span data-ttu-id="256cf-111">0</span><span class="sxs-lookup"><span data-stu-id="256cf-111">0</span></span>                                                          |
|  <span data-ttu-id="256cf-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="256cf-112">Symbolic Name</span></span>  |                                                         <span data-ttu-id="256cf-113">0</span><span class="sxs-lookup"><span data-stu-id="256cf-113">0</span></span>                                                          |
|  <span data-ttu-id="256cf-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="256cf-114">Message Text</span></span>   | <span data-ttu-id="256cf-115">メッセージ部分に要素が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="256cf-115">Message part missing element.</span></span> <span data-ttu-id="256cf-116">サービスの説明を修正"{0}「メッセージの種類」{1}「パーツ」{2}"し、ウィザードを再実行</span><span class="sxs-lookup"><span data-stu-id="256cf-116">Correct service description "{0}" message type "{1}" part "{2}" and rerun the wizard</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="256cf-117">説明</span><span class="sxs-lookup"><span data-stu-id="256cf-117">Explanation</span></span>  
 <span data-ttu-id="256cf-118">このエラーは、使用するサービスに、メッセージの種類を識別する要素タグがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="256cf-118">This error indicates the service that is trying to be consumed does not have the element tag identifying the type of message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="256cf-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="256cf-119">User Action</span></span>  
 <span data-ttu-id="256cf-120">サービスを適切なメッセージの種類に修正し、使用します (使用しようとしている WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="256cf-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="256cf-121">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="256cf-121">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="256cf-122">メッセージの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="256cf-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="256cf-123">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="256cf-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)