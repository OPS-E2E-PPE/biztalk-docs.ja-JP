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
ms.openlocfilehash: 742d537f2329c53cd974abbaac9a6b9f7f8f5126
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008483"
---
# <a name="cannot-proceed-due-to-type-name-clash"></a><span data-ttu-id="f7654-102">種類名の競合により続行できません</span><span class="sxs-lookup"><span data-stu-id="f7654-102">Cannot proceed due to type name clash</span></span>
## <a name="details"></a><span data-ttu-id="f7654-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f7654-103">Details</span></span>  
  
|                 |                                                                                       |
|-----------------|---------------------------------------------------------------------------------------|
|  <span data-ttu-id="f7654-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f7654-104">Product Name</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f7654-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f7654-105">Product Version</span></span> |              [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    <span data-ttu-id="f7654-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f7654-106">Event ID</span></span>     |                                           <span data-ttu-id="f7654-107">0</span><span class="sxs-lookup"><span data-stu-id="f7654-107">0</span></span>                                           |
|  <span data-ttu-id="f7654-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f7654-108">Event Source</span></span>   |                                           <span data-ttu-id="f7654-109">0</span><span class="sxs-lookup"><span data-stu-id="f7654-109">0</span></span>                                           |
|    <span data-ttu-id="f7654-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f7654-110">Component</span></span>    |                                           <span data-ttu-id="f7654-111">0</span><span class="sxs-lookup"><span data-stu-id="f7654-111">0</span></span>                                           |
|  <span data-ttu-id="f7654-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f7654-112">Symbolic Name</span></span>  |                                           <span data-ttu-id="f7654-113">0</span><span class="sxs-lookup"><span data-stu-id="f7654-113">0</span></span>                                           |
|  <span data-ttu-id="f7654-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f7654-114">Message Text</span></span>   | <span data-ttu-id="f7654-115">種類名の競合により続行できません。</span><span class="sxs-lookup"><span data-stu-id="f7654-115">Cannot proceed due to type name clash.</span></span> <span data-ttu-id="f7654-116">名前"{0}"名前空間に既に存在します</span><span class="sxs-lookup"><span data-stu-id="f7654-116">The name "{0}" already exists in the namespace</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f7654-117">説明</span><span class="sxs-lookup"><span data-stu-id="f7654-117">Explanation</span></span>  
 <span data-ttu-id="f7654-118">このエラーは、同じ定義済み名前空間の複数のアイテムが同じ名前であることを示します。</span><span class="sxs-lookup"><span data-stu-id="f7654-118">This error indicates multiple artifacts in the same defined namespace have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f7654-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f7654-119">User Action</span></span>  
 <span data-ttu-id="f7654-120">同じ名前空間のアイテム名を変更するか、別の名前空間に配置します。</span><span class="sxs-lookup"><span data-stu-id="f7654-120">Rename the artifacts in the same namespace or put them in a different namespace.</span></span>