---
title: シングル サインオン:イベント 10668 |Microsoft Docs
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
ms.openlocfilehash: 6f9930c9c9f07c95ddc39ae1806fc6ba41e50a2d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397525"
---
# <a name="single-sign-on-event-10668"></a><span data-ttu-id="5725f-102">シングル サインオン:イベント 10668</span><span class="sxs-lookup"><span data-stu-id="5725f-102">Single Sign-On: Event 10668</span></span>
## <a name="details"></a><span data-ttu-id="5725f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5725f-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5725f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5725f-104">Product Name</span></span>   |                                                                                                                                                   <span data-ttu-id="5725f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5725f-105">Enterprise Single Sign-On</span></span>                                                                                                                                                   |
| <span data-ttu-id="5725f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5725f-106">Product Version</span></span> |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    <span data-ttu-id="5725f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5725f-107">Event ID</span></span>     |                                                                                                                                                             <span data-ttu-id="5725f-108">10668</span><span class="sxs-lookup"><span data-stu-id="5725f-108">10668</span></span>                                                                                                                                                             |
|  <span data-ttu-id="5725f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5725f-109">Event Source</span></span>   |                                                                                                                                                            <span data-ttu-id="5725f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5725f-110">ENTSSO</span></span>                                                                                                                                                             |
|    <span data-ttu-id="5725f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5725f-111">Component</span></span>    |                                                                                                                                                              <span data-ttu-id="5725f-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="5725f-112">N\A</span></span>                                                                                                                                                              |
|  <span data-ttu-id="5725f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5725f-113">Symbolic Name</span></span>  |                                                                                                                                               <span data-ttu-id="5725f-114">SSO_WARN_NO_OLD_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="5725f-114">SSO_WARN_NO_OLD_WINDOWS_PASSWORD</span></span>                                                                                                                                                |
|  <span data-ttu-id="5725f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5725f-115">Message Text</span></span>   | <span data-ttu-id="5725f-116">このアカウントの古い Windows パスワードが SSO database.%r で利用できないため、Windows パスワードを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5725f-116">Cannot change the Windows password because the old Windows password for this account is not available in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="5725f-117">SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。%r</span><span class="sxs-lookup"><span data-stu-id="5725f-117">Use the SSO administration tools to set the external credentials for this Windows account.%r</span></span><br /><br /> <span data-ttu-id="5725f-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5725f-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="5725f-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="5725f-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="5725f-120">Windows アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="5725f-120">Windows Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="5725f-121">説明</span><span class="sxs-lookup"><span data-stu-id="5725f-121">Explanation</span></span>  
 <span data-ttu-id="5725f-122">この警告イベントは、このアカウントの古い Windows パスワードが SSO データベースで利用できないために、パスワード同期が Windows パスワードを変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="5725f-122">This Warning event indicates that Password Sync cannot change the Windows password because the old Windows password for this account is not available in the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5725f-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5725f-123">User Action</span></span>  
 <span data-ttu-id="5725f-124">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5725f-124">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="5725f-125">このアダプター (イベント ログ メッセージ名) に割り当てられているどのアプリケーションを特定し、この Windows アカウントの外部資格情報を設定する SSO 管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="5725f-125">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this Windows account.</span></span> <span data-ttu-id="5725f-126">それらのアプリケーションのすべてでは、(特定の Windows アカウント) の外部パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5725f-126">You must set the external password (for the given Windows Account) in all of those Applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="5725f-127">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5725f-127">More info</span></span>

- [<span data-ttu-id="5725f-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="5725f-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="5725f-129">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="5725f-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
