---
title: サポートされていないバインドの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5556a7d7-f092-4f69-9561-88f51ac46cc9
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6714c1acdf2f802037b8cd9509468194fee9d360
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399458"
---
# <a name="unsupported-binding-type"></a><span data-ttu-id="46438-102">バインドの種類はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="46438-102">Unsupported binding type</span></span>
## <a name="details"></a><span data-ttu-id="46438-103">詳細</span><span class="sxs-lookup"><span data-stu-id="46438-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="46438-104">製品名</span><span class="sxs-lookup"><span data-stu-id="46438-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="46438-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="46438-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="46438-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="46438-106">Event ID</span></span>     |                                         <span data-ttu-id="46438-107">0</span><span class="sxs-lookup"><span data-stu-id="46438-107">0</span></span>                                          |
|  <span data-ttu-id="46438-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="46438-108">Event Source</span></span>   |                                         <span data-ttu-id="46438-109">0</span><span class="sxs-lookup"><span data-stu-id="46438-109">0</span></span>                                          |
|    <span data-ttu-id="46438-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="46438-110">Component</span></span>    |                                         <span data-ttu-id="46438-111">0</span><span class="sxs-lookup"><span data-stu-id="46438-111">0</span></span>                                          |
|  <span data-ttu-id="46438-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="46438-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="46438-113">0</span><span class="sxs-lookup"><span data-stu-id="46438-113">0</span></span>                                          |
|  <span data-ttu-id="46438-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="46438-114">Message Text</span></span>   |                              <span data-ttu-id="46438-115">バインドの種類はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="46438-115">Unsupported binding type</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="46438-116">説明</span><span class="sxs-lookup"><span data-stu-id="46438-116">Explanation</span></span>  
 <span data-ttu-id="46438-117">MsmqIntegration バインディングが選択されましたが、WCF アダプターでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="46438-117">The MsmqIntegration binding was chosen, but is not supported by the WCF adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46438-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="46438-118">User Action</span></span>  
 <span data-ttu-id="46438-119">WCF-NetMsmq アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="46438-119">Use the WCF-NetMsmq adapter.</span></span> <span data-ttu-id="46438-120">ネイティブの MSMQ メッセージを交換する必要がある場合、BizTalk MSMQ アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="46438-120">If native MSMQ messages need to be exchanged, use the BizTalk MSMQ adapter.</span></span>  
  
 <span data-ttu-id="46438-121">アダプターの構成の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46438-121">For further information on configuring adapters, see the following resource:</span></span>  
  
-   [<span data-ttu-id="46438-122">WCF-NetMsmq アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="46438-122">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)