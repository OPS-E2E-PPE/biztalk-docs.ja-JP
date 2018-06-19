---
title: 'シングル サインオン: イベント 10566 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd140b-5503-40f8-bf5d-604fa763989e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dec463e417ce7ab1a409f7660427d2f6882ea325
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270498"
---
# <a name="single-sign-on-event-10566"></a><span data-ttu-id="02c33-102">シングル サインオン: イベント 10566</span><span class="sxs-lookup"><span data-stu-id="02c33-102">Single Sign-On: Event 10566</span></span>
## <a name="details"></a><span data-ttu-id="02c33-103">詳細</span><span class="sxs-lookup"><span data-stu-id="02c33-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02c33-104">製品名</span><span class="sxs-lookup"><span data-stu-id="02c33-104">Product Name</span></span>|<span data-ttu-id="02c33-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="02c33-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="02c33-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="02c33-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="02c33-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="02c33-107">Event ID</span></span>|<span data-ttu-id="02c33-108">10566</span><span class="sxs-lookup"><span data-stu-id="02c33-108">10566</span></span>|  
|<span data-ttu-id="02c33-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="02c33-109">Event Source</span></span>|<span data-ttu-id="02c33-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="02c33-110">ENTSSO</span></span>|  
|<span data-ttu-id="02c33-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="02c33-111">Component</span></span>|<span data-ttu-id="02c33-112">なし</span><span class="sxs-lookup"><span data-stu-id="02c33-112">N/A</span></span>|  
|<span data-ttu-id="02c33-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="02c33-113">Symbolic Name</span></span>|<span data-ttu-id="02c33-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span><span class="sxs-lookup"><span data-stu-id="02c33-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span></span>|  
|<span data-ttu-id="02c33-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="02c33-115">Message Text</span></span>|<span data-ttu-id="02c33-116">このアプリケーションの指定されたフラグの一部を更新できません。</span><span class="sxs-lookup"><span data-stu-id="02c33-116">You cannot update some of the specified flags for this application.</span></span> <span data-ttu-id="02c33-117">これらは無視されます。%r</span><span class="sxs-lookup"><span data-stu-id="02c33-117">They will be ignored.%r</span></span><br /><br /> <span data-ttu-id="02c33-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="02c33-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="02c33-119">指定されたフラグ マスク: %2</span><span class="sxs-lookup"><span data-stu-id="02c33-119">Specified Flag Mask: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="02c33-120">説明</span><span class="sxs-lookup"><span data-stu-id="02c33-120">Explanation</span></span>  
 <span data-ttu-id="02c33-121">アプリケーションの特定のフラグを変更できません。</span><span class="sxs-lookup"><span data-stu-id="02c33-121">Certain flags in an application cannot be changed.</span></span> <span data-ttu-id="02c33-122">たとえば、アプリケーションの種類を単独からグループに変更することができません。このようなアプリケーションのフラグは、警告のテキストに示されます。</span><span class="sxs-lookup"><span data-stu-id="02c33-122">(For example, it is not allowed to change an application type from Individual to Group.) The flags for this application are specified in the warning text.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="02c33-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="02c33-123">User Action</span></span>  
 <span data-ttu-id="02c33-124">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="02c33-124">No user action is required.</span></span>