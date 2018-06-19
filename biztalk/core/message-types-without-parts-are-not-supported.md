---
title: メッセージ部分はサポートされていないなしの種類 |Microsoft ドキュメント
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
ms.openlocfilehash: 7e3e6cc0f5d4a2ae18ff6bcb5fa0dc8ef605d730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263106"
---
# <a name="message-types-without-parts-are-not-supported"></a><span data-ttu-id="40e4b-102">部分が空のメッセージの種類はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="40e4b-102">Message types without parts are not supported</span></span>
## <a name="details"></a><span data-ttu-id="40e4b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="40e4b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="40e4b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="40e4b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="40e4b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="40e4b-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="40e4b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="40e4b-106">Event ID</span></span>|<span data-ttu-id="40e4b-107">0</span><span class="sxs-lookup"><span data-stu-id="40e4b-107">0</span></span>|  
|<span data-ttu-id="40e4b-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="40e4b-108">Event Source</span></span>|<span data-ttu-id="40e4b-109">0</span><span class="sxs-lookup"><span data-stu-id="40e4b-109">0</span></span>|  
|<span data-ttu-id="40e4b-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="40e4b-110">Component</span></span>|<span data-ttu-id="40e4b-111">0</span><span class="sxs-lookup"><span data-stu-id="40e4b-111">0</span></span>|  
|<span data-ttu-id="40e4b-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="40e4b-112">Symbolic Name</span></span>|<span data-ttu-id="40e4b-113">0</span><span class="sxs-lookup"><span data-stu-id="40e4b-113">0</span></span>|  
|<span data-ttu-id="40e4b-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="40e4b-114">Message Text</span></span>|<span data-ttu-id="40e4b-115">部分が空のメッセージの種類はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40e4b-115">Message types without parts are not supported.</span></span> <span data-ttu-id="40e4b-116">サービスの説明"0"} のメッセージの種類「{1}」を解決し、ウィザードを再実行します。</span><span class="sxs-lookup"><span data-stu-id="40e4b-116">Correct service description "{0}" message type "{1}" and rerun the wizard.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="40e4b-117">説明</span><span class="sxs-lookup"><span data-stu-id="40e4b-117">Explanation</span></span>  
 <span data-ttu-id="40e4b-118">このエラーは、使用するサービスに、メッセージの種類が定義されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="40e4b-118">This error indicates the service that is trying to be consumed does not have a message type defined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="40e4b-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="40e4b-119">User Action</span></span>  
 <span data-ttu-id="40e4b-120">サービスを適切なメッセージの種類に修正し、使用します (使用しようとしている WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="40e4b-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="40e4b-121">それ以外の場合は、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="40e4b-121">Otherwise, contact the serviced provider.</span></span>  <span data-ttu-id="40e4b-122">メッセージの詳細については、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="40e4b-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Help:</span></span>  
  
-   [<span data-ttu-id="40e4b-123">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="40e4b-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)