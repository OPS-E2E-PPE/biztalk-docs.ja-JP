---
title: 'シングル サインオン: イベント 10566 |Microsoft Docs'
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
ms.openlocfilehash: 4748670e128b5b3a9717e2e430acb976da7bb4d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015091"
---
# <a name="single-sign-on-event-10566"></a><span data-ttu-id="d8126-102">シングル サインオン: イベント 10566</span><span class="sxs-lookup"><span data-stu-id="d8126-102">Single Sign-On: Event 10566</span></span>
## <a name="details"></a><span data-ttu-id="d8126-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d8126-103">Details</span></span>  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d8126-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d8126-104">Product Name</span></span>   |                                                                     <span data-ttu-id="d8126-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d8126-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="d8126-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d8126-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="d8126-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d8126-107">Event ID</span></span>     |                                                                               <span data-ttu-id="d8126-108">10566</span><span class="sxs-lookup"><span data-stu-id="d8126-108">10566</span></span>                                                                                |
|  <span data-ttu-id="d8126-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d8126-109">Event Source</span></span>   |                                                                               <span data-ttu-id="d8126-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d8126-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="d8126-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d8126-111">Component</span></span>    |                                                                                <span data-ttu-id="d8126-112">なし</span><span class="sxs-lookup"><span data-stu-id="d8126-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="d8126-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d8126-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="d8126-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d8126-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span></span>                                                                  |
|  <span data-ttu-id="d8126-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d8126-115">Message Text</span></span>   | <span data-ttu-id="d8126-116">このアプリケーションの指定されたフラグの一部を更新できません。</span><span class="sxs-lookup"><span data-stu-id="d8126-116">You cannot update some of the specified flags for this application.</span></span> <span data-ttu-id="d8126-117">これらは無視されます。%r</span><span class="sxs-lookup"><span data-stu-id="d8126-117">They will be ignored.%r</span></span><br /><br /> <span data-ttu-id="d8126-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d8126-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="d8126-119">指定フラグ マスク: %2</span><span class="sxs-lookup"><span data-stu-id="d8126-119">Specified Flag Mask: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d8126-120">説明</span><span class="sxs-lookup"><span data-stu-id="d8126-120">Explanation</span></span>  
 <span data-ttu-id="d8126-121">アプリケーションの特定のフラグを変更できません。</span><span class="sxs-lookup"><span data-stu-id="d8126-121">Certain flags in an application cannot be changed.</span></span> <span data-ttu-id="d8126-122">たとえば、アプリケーションの種類を単独からグループに変更することができません。このようなアプリケーションのフラグは、警告のテキストに示されます。</span><span class="sxs-lookup"><span data-stu-id="d8126-122">(For example, it is not allowed to change an application type from Individual to Group.) The flags for this application are specified in the warning text.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8126-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d8126-123">User Action</span></span>  
 <span data-ttu-id="d8126-124">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="d8126-124">No user action is required.</span></span>