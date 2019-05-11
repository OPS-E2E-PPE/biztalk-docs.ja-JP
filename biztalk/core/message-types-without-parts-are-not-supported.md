---
title: メッセージの種類の部分はサポートされていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0bfb042-feda-4282-a7fa-c13be4ff6254
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef2ef118aab93f10d766aeaf34af74a23908822
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394535"
---
# <a name="message-types-without-parts-are-not-supported"></a><span data-ttu-id="afbf8-102">メッセージの種類の部分はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="afbf8-102">Message types without parts are not supported</span></span>
## <a name="details"></a><span data-ttu-id="afbf8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="afbf8-103">Details</span></span>  
  
|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="afbf8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="afbf8-104">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="afbf8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="afbf8-105">Product Version</span></span> |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    <span data-ttu-id="afbf8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="afbf8-106">Event ID</span></span>     |                                                             <span data-ttu-id="afbf8-107">0</span><span class="sxs-lookup"><span data-stu-id="afbf8-107">0</span></span>                                                             |
|  <span data-ttu-id="afbf8-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="afbf8-108">Event Source</span></span>   |                                                             <span data-ttu-id="afbf8-109">0</span><span class="sxs-lookup"><span data-stu-id="afbf8-109">0</span></span>                                                             |
|    <span data-ttu-id="afbf8-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="afbf8-110">Component</span></span>    |                                                             <span data-ttu-id="afbf8-111">0</span><span class="sxs-lookup"><span data-stu-id="afbf8-111">0</span></span>                                                             |
|  <span data-ttu-id="afbf8-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="afbf8-112">Symbolic Name</span></span>  |                                                             <span data-ttu-id="afbf8-113">0</span><span class="sxs-lookup"><span data-stu-id="afbf8-113">0</span></span>                                                             |
|  <span data-ttu-id="afbf8-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="afbf8-114">Message Text</span></span>   | <span data-ttu-id="afbf8-115">メッセージの種類の部分は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="afbf8-115">Message types without parts are not supported.</span></span> <span data-ttu-id="afbf8-116">サービスの説明を修正"{0}「メッセージの種類」{1}"、ウィザードを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="afbf8-116">Correct service description "{0}" message type "{1}" and rerun the wizard.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="afbf8-117">説明</span><span class="sxs-lookup"><span data-stu-id="afbf8-117">Explanation</span></span>  
 <span data-ttu-id="afbf8-118">このエラーは、使用しようとするサービスに定義されているメッセージ型がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="afbf8-118">This error indicates the service that is trying to be consumed does not have a message type defined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="afbf8-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="afbf8-119">User Action</span></span>  
 <span data-ttu-id="afbf8-120">適切なメッセージの種類、サービスを修正して、(使用しようとしている WCF サービスを所有) 場合に使用する再試行してください。</span><span class="sxs-lookup"><span data-stu-id="afbf8-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="afbf8-121">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="afbf8-121">Otherwise, contact the serviced provider.</span></span>  <span data-ttu-id="afbf8-122">メッセージの詳細についてで、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="afbf8-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Help:</span></span>  
  
-   [<span data-ttu-id="afbf8-123">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="afbf8-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)