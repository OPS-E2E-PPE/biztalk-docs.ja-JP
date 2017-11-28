---
title: "シングル サインオン: イベント 10677 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2894792b-e1c9-4c24-875d-9193cbb5cd35
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 876048e9c86cf908be9eda121340ec60354803c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10677"></a><span data-ttu-id="77481-102">シングル サインオン: イベント 10677</span><span class="sxs-lookup"><span data-stu-id="77481-102">Single Sign-On: Event 10677</span></span>
## <a name="details"></a><span data-ttu-id="77481-103">詳細</span><span class="sxs-lookup"><span data-stu-id="77481-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77481-104">製品名</span><span class="sxs-lookup"><span data-stu-id="77481-104">Product Name</span></span>|<span data-ttu-id="77481-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="77481-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="77481-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="77481-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="77481-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77481-107">Event ID</span></span>|<span data-ttu-id="77481-108">10677</span><span class="sxs-lookup"><span data-stu-id="77481-108">10677</span></span>|  
|<span data-ttu-id="77481-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="77481-109">Event Source</span></span>|<span data-ttu-id="77481-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="77481-110">ENTSSO</span></span>|  
|<span data-ttu-id="77481-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="77481-111">Component</span></span>|<span data-ttu-id="77481-112">N\A</span><span class="sxs-lookup"><span data-stu-id="77481-112">N\A</span></span>|  
|<span data-ttu-id="77481-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="77481-113">Symbolic Name</span></span>|<span data-ttu-id="77481-114">SSO_WARN_NO_EXISTING_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="77481-114">SSO_WARN_NO_EXISTING_PASSWORD</span></span>|  
|<span data-ttu-id="77481-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="77481-115">Message Text</span></span>|<span data-ttu-id="77481-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="77481-116">External password change.</span></span> <span data-ttu-id="77481-117">この外部アカウントについて既存の資格情報が存在しないので、古いパスワードを検証できません。%r</span><span class="sxs-lookup"><span data-stu-id="77481-117">The old password cannot be verified because there are no existing credentials for this external account.%r</span></span><br /><br /> <span data-ttu-id="77481-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="77481-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="77481-119">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="77481-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="77481-120">アプリケーション名: %3 %r</span><span class="sxs-lookup"><span data-stu-id="77481-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="77481-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="77481-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77481-122">説明</span><span class="sxs-lookup"><span data-stu-id="77481-122">Explanation</span></span>  
 <span data-ttu-id="77481-123">この警告イベントは、古いパスワードに既存の資格情報がないため、既存のパスワードを変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="77481-123">This Warning event indicates that an external password change cannot occur because the old password does not have existing credentials.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77481-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="77481-124">User Action</span></span>  
 <span data-ttu-id="77481-125">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="77481-125">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="77481-126">このアダプターにどのアプリケーションが割り当てられていたかを確認し (イベント ログ メッセージに名前があります)、SSO 管理ツールを使用してこの外部アカウントの外部資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="77481-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="77481-127">それらのアプリケーションのすべてに対して (指定されたアカウントに) 外部パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77481-127">You must set the external password (for the given account) in all of those Applications.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="77481-128">詳細</span><span class="sxs-lookup"><span data-stu-id="77481-128">More info</span></span>
  
-   [<span data-ttu-id="77481-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="77481-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="77481-130">**パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="77481-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>