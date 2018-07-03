---
title: 'シングル サインオン: イベント 10668 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eb3dd4d-04b5-4713-93c1-76af012d6920
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a7a3efa9ba3e9ccae3cdc39c4549a4625e5d872
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974003"
---
# <a name="single-sign-on-event-10668"></a><span data-ttu-id="544d3-102">シングル サインオン: イベント 10668</span><span class="sxs-lookup"><span data-stu-id="544d3-102">Single Sign-On: Event 10668</span></span>
## <a name="details"></a><span data-ttu-id="544d3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="544d3-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="544d3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="544d3-104">Product Name</span></span>   |                                                                                                                                                   <span data-ttu-id="544d3-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="544d3-105">Enterprise Single Sign-On</span></span>                                                                                                                                                   |
| <span data-ttu-id="544d3-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="544d3-106">Product Version</span></span> |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    <span data-ttu-id="544d3-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="544d3-107">Event ID</span></span>     |                                                                                                                                                             <span data-ttu-id="544d3-108">10668</span><span class="sxs-lookup"><span data-stu-id="544d3-108">10668</span></span>                                                                                                                                                             |
|  <span data-ttu-id="544d3-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="544d3-109">Event Source</span></span>   |                                                                                                                                                            <span data-ttu-id="544d3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="544d3-110">ENTSSO</span></span>                                                                                                                                                             |
|    <span data-ttu-id="544d3-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="544d3-111">Component</span></span>    |                                                                                                                                                              <span data-ttu-id="544d3-112">N\A</span><span class="sxs-lookup"><span data-stu-id="544d3-112">N\A</span></span>                                                                                                                                                              |
|  <span data-ttu-id="544d3-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="544d3-113">Symbolic Name</span></span>  |                                                                                                                                               <span data-ttu-id="544d3-114">SSO_WARN_NO_OLD_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="544d3-114">SSO_WARN_NO_OLD_WINDOWS_PASSWORD</span></span>                                                                                                                                                |
|  <span data-ttu-id="544d3-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="544d3-115">Message Text</span></span>   | <span data-ttu-id="544d3-116">SSO データベースでこのアカウントの古い Windows パスワードを使用できないので、Windows パスワードを変更できません。%r</span><span class="sxs-lookup"><span data-stu-id="544d3-116">Cannot change the Windows password because the old Windows password for this account is not available in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="544d3-117">SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。%r</span><span class="sxs-lookup"><span data-stu-id="544d3-117">Use the SSO administration tools to set the external credentials for this Windows account.%r</span></span><br /><br /> <span data-ttu-id="544d3-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="544d3-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="544d3-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="544d3-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="544d3-120">Windows アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="544d3-120">Windows Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="544d3-121">説明</span><span class="sxs-lookup"><span data-stu-id="544d3-121">Explanation</span></span>  
 <span data-ttu-id="544d3-122">この警告イベントは、SSO データベースでこのアカウントの古い Windows パスワードが使用できないので、パスワード同期で Windows パスワードを変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="544d3-122">This Warning event indicates that Password Sync cannot change the Windows password because the old Windows password for this account is not available in the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="544d3-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="544d3-123">User Action</span></span>  
 <span data-ttu-id="544d3-124">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="544d3-124">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="544d3-125">このアダプターに割り当てられているアプリケーション (イベント ログ メッセージ内の名前) を特定し、SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="544d3-125">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this Windows account.</span></span> <span data-ttu-id="544d3-126">このようなアプリケーションのすべてにおいて、(特定の Windows アカウントの) 外部パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="544d3-126">You must set the external password (for the given Windows Account) in all of those Applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="544d3-127">詳細</span><span class="sxs-lookup"><span data-stu-id="544d3-127">More info</span></span>

- [<span data-ttu-id="544d3-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="544d3-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="544d3-129">**パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="544d3-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
