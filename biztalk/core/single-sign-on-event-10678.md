---
title: シングル サインオン:イベント 10678 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af92ce1-fdac-432f-be6b-cf8958aee776
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c8acb17f22b9b7fbf3faeaa918aa2fc0a7fd68e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397462"
---
# <a name="single-sign-on-event-10678"></a><span data-ttu-id="f5765-102">シングル サインオン:イベント 10678</span><span class="sxs-lookup"><span data-stu-id="f5765-102">Single Sign-On: Event 10678</span></span>
## <a name="details"></a><span data-ttu-id="f5765-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f5765-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f5765-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f5765-104">Product Name</span></span>   |                                                                                                                    <span data-ttu-id="f5765-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f5765-105">Enterprise Single Sign-On</span></span>                                                                                                                    |
| <span data-ttu-id="f5765-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f5765-106">Product Version</span></span> |                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    <span data-ttu-id="f5765-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f5765-107">Event ID</span></span>     |                                                                                                                              <span data-ttu-id="f5765-108">10678</span><span class="sxs-lookup"><span data-stu-id="f5765-108">10678</span></span>                                                                                                                              |
|  <span data-ttu-id="f5765-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f5765-109">Event Source</span></span>   |                                                                                                                             <span data-ttu-id="f5765-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f5765-110">ENTSSO</span></span>                                                                                                                              |
|    <span data-ttu-id="f5765-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f5765-111">Component</span></span>    |                                                                                                                               <span data-ttu-id="f5765-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="f5765-112">N\A</span></span>                                                                                                                               |
|  <span data-ttu-id="f5765-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f5765-113">Symbolic Name</span></span>  |                                                                                                                   <span data-ttu-id="f5765-114">SSO_WARN_PASSWORD_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="f5765-114">SSO_WARN_PASSWORD_MISMATCH</span></span>                                                                                                                    |
|  <span data-ttu-id="f5765-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f5765-115">Message Text</span></span>   | <span data-ttu-id="f5765-116">外部パスワード変更。</span><span class="sxs-lookup"><span data-stu-id="f5765-116">External password change.</span></span> <span data-ttu-id="f5765-117">アダプターによって指定された古いパスワードが外部 account.%r の既存のパスワードと一致しません</span><span class="sxs-lookup"><span data-stu-id="f5765-117">The old password supplied by the adapter does not match the existing password for the external account.%r</span></span><br /><br /> <span data-ttu-id="f5765-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f5765-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="f5765-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="f5765-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="f5765-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="f5765-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="f5765-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="f5765-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="f5765-122">説明</span><span class="sxs-lookup"><span data-stu-id="f5765-122">Explanation</span></span>  
 <span data-ttu-id="f5765-123">この警告イベントは、アダプターによって指定された古いパスワードでは、外部アカウントの既存のパスワードが一致しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f5765-123">This Warning event indicates that the old password supplied by the adapter does not match the existing password for the external account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f5765-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f5765-124">User Action</span></span>  
 <span data-ttu-id="f5765-125">この警告は、次を解決するには。</span><span class="sxs-lookup"><span data-stu-id="f5765-125">To resolve this warning do the following:</span></span>  

-   <span data-ttu-id="f5765-126">アダプター (イベント ログ メッセージ名) に割り当てられているどのアプリケーションを決定し、SSO 管理ツールを使用して、この外部アカウントの外部資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="f5765-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="f5765-127">それらのアプリケーションのすべてでは、(特定のアカウント) の外部パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5765-127">You must set the external password (for the given account) in all of those Applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="f5765-128">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f5765-128">More info</span></span>

- [<span data-ttu-id="f5765-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="f5765-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="f5765-130">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="f5765-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
