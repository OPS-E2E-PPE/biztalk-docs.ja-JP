---
title: シングル サインオン:イベント 11023 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feeb4ede-6045-46bf-9f2b-65062c583faa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 525c2bd0759aa24c191991e075276bd75233d6d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266540"
---
# <a name="single-sign-on-event-11023"></a><span data-ttu-id="0a4a7-102">シングル サインオン:イベント 11023</span><span class="sxs-lookup"><span data-stu-id="0a4a7-102">Single Sign-On: Event 11023</span></span>
## <a name="details"></a><span data-ttu-id="0a4a7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0a4a7-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0a4a7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0a4a7-104">Product Name</span></span>   |                                                                                                                                 <span data-ttu-id="0a4a7-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0a4a7-105">Enterprise Single Sign-On</span></span>                                                                                                                                  |
| <span data-ttu-id="0a4a7-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0a4a7-106">Product Version</span></span> |                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                 |
|    <span data-ttu-id="0a4a7-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0a4a7-107">Event ID</span></span>     |                                                                                                                                           <span data-ttu-id="0a4a7-108">11023</span><span class="sxs-lookup"><span data-stu-id="0a4a7-108">11023</span></span>                                                                                                                                            |
|  <span data-ttu-id="0a4a7-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0a4a7-109">Event Source</span></span>   |                                                                                                                                           <span data-ttu-id="0a4a7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0a4a7-110">ENTSSO</span></span>                                                                                                                                           |
|    <span data-ttu-id="0a4a7-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a4a7-111">Component</span></span>    |                                                                                                                                            <span data-ttu-id="0a4a7-112">なし</span><span class="sxs-lookup"><span data-stu-id="0a4a7-112">N/A</span></span>                                                                                                                                             |
|  <span data-ttu-id="0a4a7-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0a4a7-113">Symbolic Name</span></span>  |                                                                                                                             <span data-ttu-id="0a4a7-114">SSO_WARN_WINDOWS_PASSWORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="0a4a7-114">SSO_WARN_WINDOWS_PASSWORD_DELETED</span></span>                                                                                                                              |
|  <span data-ttu-id="0a4a7-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0a4a7-115">Message Text</span></span>   | <span data-ttu-id="0a4a7-116">アカウントのロックアウトを防ぐために、SSO データベースの無効な Windows パスワードを削除しました。%r</span><span class="sxs-lookup"><span data-stu-id="0a4a7-116">An invalid Windows password in the SSO database was deleted to prevent account lockout.%r</span></span><br /><br /> <span data-ttu-id="0a4a7-117">SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。%r</span><span class="sxs-lookup"><span data-stu-id="0a4a7-117">Use the SSO administration tools to set the external credentials for this Windows account.%r</span></span><br /><br /> <span data-ttu-id="0a4a7-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0a4a7-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0a4a7-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="0a4a7-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="0a4a7-120">Windows アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="0a4a7-120">Windows Account: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0a4a7-121">説明</span><span class="sxs-lookup"><span data-stu-id="0a4a7-121">Explanation</span></span>  
 <span data-ttu-id="0a4a7-122">無効な Windows パスワードを削除しました。</span><span class="sxs-lookup"><span data-stu-id="0a4a7-122">An invalid Windows password has been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a4a7-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0a4a7-123">User Action</span></span>  
 <span data-ttu-id="0a4a7-124">SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="0a4a7-124">Use the SSO administration tools to set the external credentials for this Windows account.</span></span> <span data-ttu-id="0a4a7-125">詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)します。</span><span class="sxs-lookup"><span data-stu-id="0a4a7-125">For more information, see [Using SSO](../core/using-sso.md).</span></span>