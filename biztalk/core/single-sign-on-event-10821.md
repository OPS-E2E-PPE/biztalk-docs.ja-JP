---
title: 'シングル サインオン: イベント 10821 |Microsoft ドキュメント'
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
ms.openlocfilehash: 8f212a77f85330d256f1415ec13f3ec267e4be7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278266"
---
# <a name="single-sign-on-event-10821"></a><span data-ttu-id="bf771-102">シングル サインオン: イベント 10821</span><span class="sxs-lookup"><span data-stu-id="bf771-102">Single Sign-On: Event 10821</span></span>
## <a name="details"></a><span data-ttu-id="bf771-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bf771-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf771-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bf771-104">Product Name</span></span>|<span data-ttu-id="bf771-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bf771-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="bf771-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bf771-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="bf771-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bf771-107">Event ID</span></span>|<span data-ttu-id="bf771-108">10821</span><span class="sxs-lookup"><span data-stu-id="bf771-108">10821</span></span>|  
|<span data-ttu-id="bf771-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bf771-109">Event Source</span></span>|<span data-ttu-id="bf771-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bf771-110">ENTSSO</span></span>|  
|<span data-ttu-id="bf771-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bf771-111">Component</span></span>|<span data-ttu-id="bf771-112">なし</span><span class="sxs-lookup"><span data-stu-id="bf771-112">N/A</span></span>|  
|<span data-ttu-id="bf771-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bf771-113">Symbolic Name</span></span>|<span data-ttu-id="bf771-114">ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="bf771-114">ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER</span></span>|  
|<span data-ttu-id="bf771-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bf771-115">Message Text</span></span>|<span data-ttu-id="bf771-116">アダプターは現在グループ アダプターに割り当てられているため、削除できません。</span><span class="sxs-lookup"><span data-stu-id="bf771-116">The adapter cannot be deleted because it is currently assigned to a group adapter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bf771-117">説明</span><span class="sxs-lookup"><span data-stu-id="bf771-117">Explanation</span></span>  
 <span data-ttu-id="bf771-118">アダプターは現在グループ アダプターに割り当てられているため、削除できません。</span><span class="sxs-lookup"><span data-stu-id="bf771-118">The adapter cannot be deleted because it is currently assigned to a group adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf771-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bf771-119">User Action</span></span>  
 <span data-ttu-id="bf771-120">アダプターの割り当てを解除し、削除します。</span><span class="sxs-lookup"><span data-stu-id="bf771-120">Unassign the adapter and then delete it.</span></span>