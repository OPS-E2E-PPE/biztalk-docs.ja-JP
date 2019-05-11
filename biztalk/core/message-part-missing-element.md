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
ms.openlocfilehash: c2dfa36a5814b270da64eb95dc8e082a91674003
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325023"
---
# <a name="message-part-missing-element"></a><span data-ttu-id="b0eef-102">メッセージ部分の要素が見つかりません</span><span class="sxs-lookup"><span data-stu-id="b0eef-102">Message part missing element</span></span>
## <a name="details"></a><span data-ttu-id="b0eef-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b0eef-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b0eef-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b0eef-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="b0eef-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b0eef-105">Product Version</span></span> |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    <span data-ttu-id="b0eef-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b0eef-106">Event ID</span></span>     |                                                         <span data-ttu-id="b0eef-107">0</span><span class="sxs-lookup"><span data-stu-id="b0eef-107">0</span></span>                                                          |
|  <span data-ttu-id="b0eef-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b0eef-108">Event Source</span></span>   |                                                         <span data-ttu-id="b0eef-109">0</span><span class="sxs-lookup"><span data-stu-id="b0eef-109">0</span></span>                                                          |
|    <span data-ttu-id="b0eef-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b0eef-110">Component</span></span>    |                                                         <span data-ttu-id="b0eef-111">0</span><span class="sxs-lookup"><span data-stu-id="b0eef-111">0</span></span>                                                          |
|  <span data-ttu-id="b0eef-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b0eef-112">Symbolic Name</span></span>  |                                                         <span data-ttu-id="b0eef-113">0</span><span class="sxs-lookup"><span data-stu-id="b0eef-113">0</span></span>                                                          |
|  <span data-ttu-id="b0eef-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b0eef-114">Message Text</span></span>   | <span data-ttu-id="b0eef-115">メッセージ部分に不足している要素。</span><span class="sxs-lookup"><span data-stu-id="b0eef-115">Message part missing element.</span></span> <span data-ttu-id="b0eef-116">サービスの説明を修正"{0}「メッセージの種類」{1}「パーツ」{2}"し、ウィザードを再実行</span><span class="sxs-lookup"><span data-stu-id="b0eef-116">Correct service description "{0}" message type "{1}" part "{2}" and rerun the wizard</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b0eef-117">説明</span><span class="sxs-lookup"><span data-stu-id="b0eef-117">Explanation</span></span>  
 <span data-ttu-id="b0eef-118">このエラーは、使用しようとするサービスがメッセージの種類を識別する要素タグを持たないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b0eef-118">This error indicates the service that is trying to be consumed does not have the element tag identifying the type of message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b0eef-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b0eef-119">User Action</span></span>  
 <span data-ttu-id="b0eef-120">適切なメッセージの種類、サービスを修正して、(使用しようとしている WCF サービスを所有) 場合に使用する再試行してください。</span><span class="sxs-lookup"><span data-stu-id="b0eef-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="b0eef-121">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="b0eef-121">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="b0eef-122">メッセージの詳細についてで、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="b0eef-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="b0eef-123">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="b0eef-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)