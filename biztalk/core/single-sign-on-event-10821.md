---
title: 'シングル サインオン: イベント 10821 |Microsoft Docs'
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
ms.openlocfilehash: 6d1b9d5499ac11f29034f0110e0ff0fe6850f66a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988083"
---
# <a name="single-sign-on-event-10821"></a><span data-ttu-id="7211d-102">シングル サインオン: イベント 10821</span><span class="sxs-lookup"><span data-stu-id="7211d-102">Single Sign-On: Event 10821</span></span>
## <a name="details"></a><span data-ttu-id="7211d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7211d-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="7211d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7211d-104">Product Name</span></span>   |                             <span data-ttu-id="7211d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7211d-105">Enterprise Single Sign-On</span></span>                              |
| <span data-ttu-id="7211d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7211d-106">Product Version</span></span> |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    <span data-ttu-id="7211d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7211d-107">Event ID</span></span>     |                                       <span data-ttu-id="7211d-108">10821</span><span class="sxs-lookup"><span data-stu-id="7211d-108">10821</span></span>                                        |
|  <span data-ttu-id="7211d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7211d-109">Event Source</span></span>   |                                       <span data-ttu-id="7211d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7211d-110">ENTSSO</span></span>                                       |
|    <span data-ttu-id="7211d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7211d-111">Component</span></span>    |                                        <span data-ttu-id="7211d-112">なし</span><span class="sxs-lookup"><span data-stu-id="7211d-112">N/A</span></span>                                         |
|  <span data-ttu-id="7211d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7211d-113">Symbolic Name</span></span>  |                     <span data-ttu-id="7211d-114">ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="7211d-114">ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER</span></span>                     |
|  <span data-ttu-id="7211d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7211d-115">Message Text</span></span>   | <span data-ttu-id="7211d-116">アダプターは現在グループ アダプターに割り当てられているため、削除できません。</span><span class="sxs-lookup"><span data-stu-id="7211d-116">The adapter cannot be deleted because it is currently assigned to a group adapter.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7211d-117">説明</span><span class="sxs-lookup"><span data-stu-id="7211d-117">Explanation</span></span>  
 <span data-ttu-id="7211d-118">アダプターは現在グループ アダプターに割り当てられているため、削除できません。</span><span class="sxs-lookup"><span data-stu-id="7211d-118">The adapter cannot be deleted because it is currently assigned to a group adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7211d-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7211d-119">User Action</span></span>  
 <span data-ttu-id="7211d-120">アダプターの割り当てを解除し、削除します。</span><span class="sxs-lookup"><span data-stu-id="7211d-120">Unassign the adapter and then delete it.</span></span>