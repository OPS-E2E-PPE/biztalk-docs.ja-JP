---
title: シングル サインオン:イベント 10821 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2200011e-3e4f-4fe4-b01f-f3b86cdc96db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 552f6677c1e52baab51e0725a4eca03a3d4335b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395461"
---
# <a name="single-sign-on-event-10821"></a><span data-ttu-id="eba0c-102">シングル サインオン:イベント 10821</span><span class="sxs-lookup"><span data-stu-id="eba0c-102">Single Sign-On: Event 10821</span></span>
## <a name="details"></a><span data-ttu-id="eba0c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="eba0c-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="eba0c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="eba0c-104">Product Name</span></span>   |                             <span data-ttu-id="eba0c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="eba0c-105">Enterprise Single Sign-On</span></span>                              |
| <span data-ttu-id="eba0c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="eba0c-106">Product Version</span></span> |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    <span data-ttu-id="eba0c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="eba0c-107">Event ID</span></span>     |                                       <span data-ttu-id="eba0c-108">10821</span><span class="sxs-lookup"><span data-stu-id="eba0c-108">10821</span></span>                                        |
|  <span data-ttu-id="eba0c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="eba0c-109">Event Source</span></span>   |                                       <span data-ttu-id="eba0c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="eba0c-110">ENTSSO</span></span>                                       |
|    <span data-ttu-id="eba0c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="eba0c-111">Component</span></span>    |                                        <span data-ttu-id="eba0c-112">なし</span><span class="sxs-lookup"><span data-stu-id="eba0c-112">N/A</span></span>                                         |
|  <span data-ttu-id="eba0c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="eba0c-113">Symbolic Name</span></span>  |                     <span data-ttu-id="eba0c-114">ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="eba0c-114">ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER</span></span>                     |
|  <span data-ttu-id="eba0c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="eba0c-115">Message Text</span></span>   | <span data-ttu-id="eba0c-116">アダプターは、現在グループ アダプタに割り当てられているために削除できません。</span><span class="sxs-lookup"><span data-stu-id="eba0c-116">The adapter cannot be deleted because it is currently assigned to a group adapter.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="eba0c-117">説明</span><span class="sxs-lookup"><span data-stu-id="eba0c-117">Explanation</span></span>  
 <span data-ttu-id="eba0c-118">アダプターは、現在グループ アダプタに割り当てられているために削除できません。</span><span class="sxs-lookup"><span data-stu-id="eba0c-118">The adapter cannot be deleted because it is currently assigned to a group adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eba0c-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="eba0c-119">User Action</span></span>  
 <span data-ttu-id="eba0c-120">アダプターの割り当てを解除してから削除します。</span><span class="sxs-lookup"><span data-stu-id="eba0c-120">Unassign the adapter and then delete it.</span></span>