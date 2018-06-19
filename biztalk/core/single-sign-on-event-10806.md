---
title: 'シングル サインオン: イベント 10806 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd3f432a408cffcbd1ccd27508550fd0888c5213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277178"
---
# <a name="single-sign-on-event-10806"></a><span data-ttu-id="e766b-102">シングル サインオン: イベント 10806</span><span class="sxs-lookup"><span data-stu-id="e766b-102">Single Sign-On: Event 10806</span></span>
## <a name="details"></a><span data-ttu-id="e766b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e766b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e766b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e766b-104">Product Name</span></span>|<span data-ttu-id="e766b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="e766b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e766b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e766b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e766b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e766b-107">Event ID</span></span>|<span data-ttu-id="e766b-108">10806</span><span class="sxs-lookup"><span data-stu-id="e766b-108">10806</span></span>|  
|<span data-ttu-id="e766b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e766b-109">Event Source</span></span>|<span data-ttu-id="e766b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e766b-110">ENTSSO</span></span>|  
|<span data-ttu-id="e766b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e766b-111">Component</span></span>|<span data-ttu-id="e766b-112">なし</span><span class="sxs-lookup"><span data-stu-id="e766b-112">N/A</span></span>|  
|<span data-ttu-id="e766b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e766b-113">Symbolic Name</span></span>|<span data-ttu-id="e766b-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="e766b-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span></span>|  
|<span data-ttu-id="e766b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e766b-115">Message Text</span></span>|<span data-ttu-id="e766b-116">アプリケーションは、現在アダプターに割り当てられているため削除できません。</span><span class="sxs-lookup"><span data-stu-id="e766b-116">The application cannot be deleted because it is currently assigned to an adapter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e766b-117">説明</span><span class="sxs-lookup"><span data-stu-id="e766b-117">Explanation</span></span>  
 <span data-ttu-id="e766b-118">アプリケーションがアダプターに割り当てられている場合、アプリケーションを削除できません。</span><span class="sxs-lookup"><span data-stu-id="e766b-118">An application cannot be deleted when it is assigned to an adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e766b-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e766b-119">User Action</span></span>  
 <span data-ttu-id="e766b-120">アダプターからアプリケーションの割り当てを解除し、アプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="e766b-120">Unassign the application from the adapter, and then delete it.</span></span>