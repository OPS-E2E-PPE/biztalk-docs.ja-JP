---
title: ポートの構成エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92eae0d8-a0c4-4f8c-b91a-fd98b9f6931a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 773741699d040a909ef56bf2034a3b52fddee79f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394893"
---
# <a name="port-configuration-errors"></a><span data-ttu-id="b9c91-102">ポート構成エラー</span><span class="sxs-lookup"><span data-stu-id="b9c91-102">Port Configuration Errors</span></span>
<span data-ttu-id="b9c91-103">診断および WCF のポート構成エラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="b9c91-103">Information for diagnosing and resolving WCF Port Configuration errors.</span></span>  

## <a name="cannot-merge-operation-due-to-communication-pattern-conflict"></a><span data-ttu-id="b9c91-104">通信方式が競合しているため、操作を結合できません</span><span class="sxs-lookup"><span data-stu-id="b9c91-104">Cannot merge operation due to communication pattern conflict</span></span>
  
|                 |                                                         <span data-ttu-id="b9c91-105">詳細</span><span class="sxs-lookup"><span data-stu-id="b9c91-105">Details</span></span>                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b9c91-106">製品名</span><span class="sxs-lookup"><span data-stu-id="b9c91-106">Product Name</span></span>   |                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| <span data-ttu-id="b9c91-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b9c91-107">Product Version</span></span> |                               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                |
|    <span data-ttu-id="b9c91-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b9c91-108">Event ID</span></span>     |                                                            <span data-ttu-id="b9c91-109">0</span><span class="sxs-lookup"><span data-stu-id="b9c91-109">0</span></span>                                                            |
|  <span data-ttu-id="b9c91-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b9c91-110">Event Source</span></span>   |                                                            <span data-ttu-id="b9c91-111">0</span><span class="sxs-lookup"><span data-stu-id="b9c91-111">0</span></span>                                                            |
|    <span data-ttu-id="b9c91-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b9c91-112">Component</span></span>    |                                                            <span data-ttu-id="b9c91-113">0</span><span class="sxs-lookup"><span data-stu-id="b9c91-113">0</span></span>                                                            |
|  <span data-ttu-id="b9c91-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b9c91-114">Symbolic Name</span></span>  |                                                            <span data-ttu-id="b9c91-115">0</span><span class="sxs-lookup"><span data-stu-id="b9c91-115">0</span></span>                                                            |
|  <span data-ttu-id="b9c91-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b9c91-116">Message Text</span></span>   | <span data-ttu-id="b9c91-117">操作を結合できません"{0}"通信方式が競合が原因です。</span><span class="sxs-lookup"><span data-stu-id="b9c91-117">Cannot merge operation "{0}" due to communication pattern conflict.</span></span>  <span data-ttu-id="b9c91-118">すべての操作は一方向または要求 - 応答方式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9c91-118">All operations must be one-way or request-response</span></span> |
  
### <a name="explanation"></a><span data-ttu-id="b9c91-119">説明</span><span class="sxs-lookup"><span data-stu-id="b9c91-119">Explanation</span></span>  
 <span data-ttu-id="b9c91-120">このエラーは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、通信方式が異なるポートの種類と結合しようとすると表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9c91-120">This error indicates [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is attempting to merge ports with port types that have different communication patterns.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="b9c91-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b9c91-121">User Action</span></span>  
 <span data-ttu-id="b9c91-122">ポート構成ウィザードを使用すると、結合されるすべてのポートは、同じ通信方式 (一方向または要求 - 応答) になります。</span><span class="sxs-lookup"><span data-stu-id="b9c91-122">Using the Port Configuration Wizard, ensure that all the ports that are being merged have the same communication direction, either one-way or request-response.</span></span>  
  
 <span data-ttu-id="b9c91-123">ポートの構成の詳細については、次を参照してください。[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)します。</span><span class="sxs-lookup"><span data-stu-id="b9c91-123">For additional information on port configuration, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>
 
## <a name="port-types-that-have-a-combination-of-one-way-and-request-response-operations-are-not-allowed"></a><span data-ttu-id="b9c91-124">一方向の操作および要求 - 応答の操作の組み合わせを保持するポートの種類は許可されていません</span><span class="sxs-lookup"><span data-stu-id="b9c91-124">Port types that have a combination of one-way and request-response operations are not allowed</span></span> 
  
|                 |                                                                                <span data-ttu-id="b9c91-125">詳細</span><span class="sxs-lookup"><span data-stu-id="b9c91-125">Details</span></span>                                                                                |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b9c91-126">製品名</span><span class="sxs-lookup"><span data-stu-id="b9c91-126">Product Name</span></span>   |                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
| <span data-ttu-id="b9c91-127">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b9c91-127">Product Version</span></span> |                                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                       |
|    <span data-ttu-id="b9c91-128">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b9c91-128">Event ID</span></span>     |                                                                                   <span data-ttu-id="b9c91-129">0</span><span class="sxs-lookup"><span data-stu-id="b9c91-129">0</span></span>                                                                                   |
|  <span data-ttu-id="b9c91-130">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b9c91-130">Event Source</span></span>   |                                                                                   <span data-ttu-id="b9c91-131">0</span><span class="sxs-lookup"><span data-stu-id="b9c91-131">0</span></span>                                                                                   |
|    <span data-ttu-id="b9c91-132">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b9c91-132">Component</span></span>    |                                                                                   <span data-ttu-id="b9c91-133">0</span><span class="sxs-lookup"><span data-stu-id="b9c91-133">0</span></span>                                                                                   |
|  <span data-ttu-id="b9c91-134">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b9c91-134">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="b9c91-135">0</span><span class="sxs-lookup"><span data-stu-id="b9c91-135">0</span></span>                                                                                   |
|  <span data-ttu-id="b9c91-136">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b9c91-136">Message Text</span></span>   | <span data-ttu-id="b9c91-137">一方向の操作および要求 - 応答の操作の組み合わせを保持するポートの種類は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="b9c91-137">Port types that have a combination of one-way and request-response operations are not allowed.</span></span> <span data-ttu-id="b9c91-138">サービスの説明を修正"{0}「ポートの種類」{1}"し、ウィザードを再実行</span><span class="sxs-lookup"><span data-stu-id="b9c91-138">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span> |
  
### <a name="explanation"></a><span data-ttu-id="b9c91-139">説明</span><span class="sxs-lookup"><span data-stu-id="b9c91-139">Explanation</span></span>  
 <span data-ttu-id="b9c91-140">このエラーは、使用するサービスに、一方向と双方向 (つまり要求-応答) の両方があることを示します。</span><span class="sxs-lookup"><span data-stu-id="b9c91-140">This error indicates the service trying to be consumed has operations that are both one-way and two-way (or request-response).</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="b9c91-141">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b9c91-141">User Action</span></span>  
 <span data-ttu-id="b9c91-142">適切な操作 (両方ではなく、一方向または要求-応答) でサービスを修正して使用します (使用する WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="b9c91-142">Correct the service with the appropriate operations (either one-way or request-response but not both) and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="b9c91-143">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="b9c91-143">Otherwise, contact the service provider.</span></span>
