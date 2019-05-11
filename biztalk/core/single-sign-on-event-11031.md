---
title: シングル サインオン:イベント 11031 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ecd24c2-e251-4eb9-b3ca-ec0f095bb23a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b0a8f424cc0b26e26b1006d6b1aca8be0339f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379862"
---
# <a name="single-sign-on-event-11031"></a><span data-ttu-id="10cf7-102">シングル サインオン:イベント 11031</span><span class="sxs-lookup"><span data-stu-id="10cf7-102">Single Sign-On: Event 11031</span></span>
## <a name="details"></a><span data-ttu-id="10cf7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="10cf7-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="10cf7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="10cf7-104">Product Name</span></span>   |                                                                                                                                <span data-ttu-id="10cf7-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="10cf7-105">Enterprise Single Sign-On</span></span>                                                                                                                                |
| <span data-ttu-id="10cf7-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="10cf7-106">Product Version</span></span> |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    <span data-ttu-id="10cf7-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="10cf7-107">Event ID</span></span>     |                                                                                                                                          <span data-ttu-id="10cf7-108">11031</span><span class="sxs-lookup"><span data-stu-id="10cf7-108">11031</span></span>                                                                                                                                          |
|  <span data-ttu-id="10cf7-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="10cf7-109">Event Source</span></span>   |                                                                                                                                         <span data-ttu-id="10cf7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="10cf7-110">ENTSSO</span></span>                                                                                                                                          |
|    <span data-ttu-id="10cf7-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="10cf7-111">Component</span></span>    |                                                                                                                                           <span data-ttu-id="10cf7-112">なし</span><span class="sxs-lookup"><span data-stu-id="10cf7-112">N/A</span></span>                                                                                                                                           |
|  <span data-ttu-id="10cf7-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="10cf7-113">Symbolic Name</span></span>  |                                                                                                                         <span data-ttu-id="10cf7-114">SSO_INFO_PS_WIN_CHANGE_INVALID_MAPPING</span><span class="sxs-lookup"><span data-stu-id="10cf7-114">SSO_INFO_PS_WIN_CHANGE_INVALID_MAPPING</span></span>                                                                                                                          |
|  <span data-ttu-id="10cf7-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="10cf7-115">Message Text</span></span>   | <span data-ttu-id="10cf7-116">Windows パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="10cf7-116">Windows password change.</span></span> <span data-ttu-id="10cf7-117">この Windows アカウントのマッピングが検出されましたが、valid.%r ではないために無視されます。</span><span class="sxs-lookup"><span data-stu-id="10cf7-117">A mapping for this Windows account has been detected but ignored because it is no longer valid.%r</span></span><br /><br /> <span data-ttu-id="10cf7-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="10cf7-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="10cf7-119">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="10cf7-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="10cf7-120">アプリケーションの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="10cf7-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="10cf7-121">外部アカウント: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="10cf7-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="10cf7-122">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="10cf7-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="10cf7-123">説明</span><span class="sxs-lookup"><span data-stu-id="10cf7-123">Explanation</span></span>  
 <span data-ttu-id="10cf7-124">Windows アカウントが存在して有効ですが、アプリケーション ユーザー アカウントにない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="10cf7-124">It may be that the Windows account exists and is valid, but is not in the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10cf7-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="10cf7-125">User Action</span></span>  
 <span data-ttu-id="10cf7-126">マッピングを削除し、再作成しようとしてください。</span><span class="sxs-lookup"><span data-stu-id="10cf7-126">Delete the mapping and try to recreate it.</span></span>