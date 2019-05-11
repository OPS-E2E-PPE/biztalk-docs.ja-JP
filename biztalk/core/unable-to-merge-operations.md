---
title: 操作を結合できません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2741790-2c27-4dc5-9299-680e170f0366
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a40f6ce64351136f13288655fb5c51952896ee85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292724"
---
# <a name="unable-to-merge-operations"></a><span data-ttu-id="3e70d-102">操作を結合できません</span><span class="sxs-lookup"><span data-stu-id="3e70d-102">Unable to merge operations</span></span>
## <a name="details"></a><span data-ttu-id="3e70d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3e70d-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="3e70d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3e70d-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="3e70d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3e70d-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="3e70d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3e70d-106">Event ID</span></span>     |                                         <span data-ttu-id="3e70d-107">0</span><span class="sxs-lookup"><span data-stu-id="3e70d-107">0</span></span>                                          |
|  <span data-ttu-id="3e70d-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3e70d-108">Event Source</span></span>   |                                         <span data-ttu-id="3e70d-109">0</span><span class="sxs-lookup"><span data-stu-id="3e70d-109">0</span></span>                                          |
|    <span data-ttu-id="3e70d-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3e70d-110">Component</span></span>    |                                         <span data-ttu-id="3e70d-111">0</span><span class="sxs-lookup"><span data-stu-id="3e70d-111">0</span></span>                                          |
|  <span data-ttu-id="3e70d-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3e70d-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="3e70d-113">0</span><span class="sxs-lookup"><span data-stu-id="3e70d-113">0</span></span>                                          |
|  <span data-ttu-id="3e70d-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3e70d-114">Message Text</span></span>   |                             <span data-ttu-id="3e70d-115">操作を結合できません</span><span class="sxs-lookup"><span data-stu-id="3e70d-115">Unable to merge operations</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="3e70d-116">説明</span><span class="sxs-lookup"><span data-stu-id="3e70d-116">Explanation</span></span>  
 <span data-ttu-id="3e70d-117">このエラーは、名前の競合、または異なる通信方向のために、操作を統合できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="3e70d-117">This error indicates the operations cannot be merged due to name collision or due to different communication directions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3e70d-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3e70d-118">User Action</span></span>  
 <span data-ttu-id="3e70d-119">名前の競合や同じ通信方式がないオーケストレーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="3e70d-119">Try to publish the orchestration without name collision and the same communication pattern.</span></span>