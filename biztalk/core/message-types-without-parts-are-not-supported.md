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
ms.openlocfilehash: 60bb78e2bbf06ff80315bd9bbc2b33346ed18d5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024168"
---
# <a name="message-types-without-parts-are-not-supported"></a><span data-ttu-id="d1af7-102">部分が空のメッセージの種類はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="d1af7-102">Message types without parts are not supported</span></span>
## <a name="details"></a><span data-ttu-id="d1af7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d1af7-103">Details</span></span>  
  
|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d1af7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d1af7-104">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="d1af7-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d1af7-105">Product Version</span></span> |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    <span data-ttu-id="d1af7-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d1af7-106">Event ID</span></span>     |                                                             <span data-ttu-id="d1af7-107">0</span><span class="sxs-lookup"><span data-stu-id="d1af7-107">0</span></span>                                                             |
|  <span data-ttu-id="d1af7-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d1af7-108">Event Source</span></span>   |                                                             <span data-ttu-id="d1af7-109">0</span><span class="sxs-lookup"><span data-stu-id="d1af7-109">0</span></span>                                                             |
|    <span data-ttu-id="d1af7-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d1af7-110">Component</span></span>    |                                                             <span data-ttu-id="d1af7-111">0</span><span class="sxs-lookup"><span data-stu-id="d1af7-111">0</span></span>                                                             |
|  <span data-ttu-id="d1af7-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d1af7-112">Symbolic Name</span></span>  |                                                             <span data-ttu-id="d1af7-113">0</span><span class="sxs-lookup"><span data-stu-id="d1af7-113">0</span></span>                                                             |
|  <span data-ttu-id="d1af7-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d1af7-114">Message Text</span></span>   | <span data-ttu-id="d1af7-115">部分が空のメッセージの種類はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d1af7-115">Message types without parts are not supported.</span></span> <span data-ttu-id="d1af7-116">サービスの説明を修正"{0}「メッセージの種類」{1}"、ウィザードを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="d1af7-116">Correct service description "{0}" message type "{1}" and rerun the wizard.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d1af7-117">説明</span><span class="sxs-lookup"><span data-stu-id="d1af7-117">Explanation</span></span>  
 <span data-ttu-id="d1af7-118">このエラーは、使用するサービスに、メッセージの種類が定義されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="d1af7-118">This error indicates the service that is trying to be consumed does not have a message type defined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1af7-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d1af7-119">User Action</span></span>  
 <span data-ttu-id="d1af7-120">サービスを適切なメッセージの種類に修正し、使用します (使用しようとしている WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="d1af7-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="d1af7-121">それ以外の場合は、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d1af7-121">Otherwise, contact the serviced provider.</span></span>  <span data-ttu-id="d1af7-122">メッセージの詳細についてで、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="d1af7-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Help:</span></span>  
  
-   [<span data-ttu-id="d1af7-123">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="d1af7-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)