---
title: 種類名の競合により続行できません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ced6de4-0950-498e-a548-5c85419726d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a2423e0ba1ba537bde860b2539b77e59e67857a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357619"
---
# <a name="cannot-proceed-due-to-type-name-clash"></a><span data-ttu-id="32b3e-102">種類名の競合により続行できません</span><span class="sxs-lookup"><span data-stu-id="32b3e-102">Cannot proceed due to type name clash</span></span>
## <a name="details"></a><span data-ttu-id="32b3e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="32b3e-103">Details</span></span>  
  
|                 |                                                                                       |
|-----------------|---------------------------------------------------------------------------------------|
|  <span data-ttu-id="32b3e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="32b3e-104">Product Name</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="32b3e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="32b3e-105">Product Version</span></span> |              [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    <span data-ttu-id="32b3e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="32b3e-106">Event ID</span></span>     |                                           <span data-ttu-id="32b3e-107">0</span><span class="sxs-lookup"><span data-stu-id="32b3e-107">0</span></span>                                           |
|  <span data-ttu-id="32b3e-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="32b3e-108">Event Source</span></span>   |                                           <span data-ttu-id="32b3e-109">0</span><span class="sxs-lookup"><span data-stu-id="32b3e-109">0</span></span>                                           |
|    <span data-ttu-id="32b3e-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="32b3e-110">Component</span></span>    |                                           <span data-ttu-id="32b3e-111">0</span><span class="sxs-lookup"><span data-stu-id="32b3e-111">0</span></span>                                           |
|  <span data-ttu-id="32b3e-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="32b3e-112">Symbolic Name</span></span>  |                                           <span data-ttu-id="32b3e-113">0</span><span class="sxs-lookup"><span data-stu-id="32b3e-113">0</span></span>                                           |
|  <span data-ttu-id="32b3e-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="32b3e-114">Message Text</span></span>   | <span data-ttu-id="32b3e-115">種類名の競合により続行できません。</span><span class="sxs-lookup"><span data-stu-id="32b3e-115">Cannot proceed due to type name clash.</span></span> <span data-ttu-id="32b3e-116">名前"{0}"名前空間に既に存在します</span><span class="sxs-lookup"><span data-stu-id="32b3e-116">The name "{0}" already exists in the namespace</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="32b3e-117">説明</span><span class="sxs-lookup"><span data-stu-id="32b3e-117">Explanation</span></span>  
 <span data-ttu-id="32b3e-118">このエラーは、同じ定義済み名前空間の複数のアイテムが同じ名前であることを示します。</span><span class="sxs-lookup"><span data-stu-id="32b3e-118">This error indicates multiple artifacts in the same defined namespace have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="32b3e-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="32b3e-119">User Action</span></span>  
 <span data-ttu-id="32b3e-120">同じ名前空間のアイテム名を変更するか、別の名前空間に配置します。</span><span class="sxs-lookup"><span data-stu-id="32b3e-120">Rename the artifacts in the same namespace or put them in a different namespace.</span></span>