---
title: "シングル サインオン: イベント 10680 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88ea12ff-d181-423f-9054-b0c656cc4558
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd7b1804578e1b0880eaa564f68a24f0841280fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10680"></a><span data-ttu-id="f4a90-102">シングル サインオン: イベント 10680</span><span class="sxs-lookup"><span data-stu-id="f4a90-102">Single Sign-On: Event 10680</span></span>
## <a name="details"></a><span data-ttu-id="f4a90-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f4a90-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4a90-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f4a90-104">Product Name</span></span>|<span data-ttu-id="f4a90-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f4a90-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f4a90-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f4a90-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f4a90-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f4a90-107">Event ID</span></span>|<span data-ttu-id="f4a90-108">10680</span><span class="sxs-lookup"><span data-stu-id="f4a90-108">10680</span></span>|  
|<span data-ttu-id="f4a90-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f4a90-109">Event Source</span></span>|<span data-ttu-id="f4a90-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f4a90-110">ENTSSO</span></span>|  
|<span data-ttu-id="f4a90-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f4a90-111">Component</span></span>|<span data-ttu-id="f4a90-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f4a90-112">N\A</span></span>|  
|<span data-ttu-id="f4a90-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f4a90-113">Symbolic Name</span></span>|<span data-ttu-id="f4a90-114">SSO_WARN_PS_GET_CREDS_FAILED</span><span class="sxs-lookup"><span data-stu-id="f4a90-114">SSO_WARN_PS_GET_CREDS_FAILED</span></span>|  
|<span data-ttu-id="f4a90-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f4a90-115">Message Text</span></span>|<span data-ttu-id="f4a90-116">既存の外部資格情報を SSO データベースから取得できなかったため、外部アカウントのパスワードを変更できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="f4a90-116">The password was not changed for the external account because the existing external credentials could not be obtained from the SSO database.%r</span></span><br /><br /> <span data-ttu-id="f4a90-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f4a90-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="f4a90-118">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f4a90-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="f4a90-119">アプリケーション名: %3 %r</span><span class="sxs-lookup"><span data-stu-id="f4a90-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="f4a90-120">外部アカウント: %4 %r</span><span class="sxs-lookup"><span data-stu-id="f4a90-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="f4a90-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="f4a90-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f4a90-122">説明</span><span class="sxs-lookup"><span data-stu-id="f4a90-122">Explanation</span></span>  
 <span data-ttu-id="f4a90-123">この警告イベントは、既存の外部資格情報を SSO データベースから取得できなかったため、外部アカウントのパスワードを変更できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f4a90-123">This Warning event indicates that the password was not changed for the external account because the existing external credentials could not be obtained from the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f4a90-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f4a90-124">User Action</span></span>  
 <span data-ttu-id="f4a90-125">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="f4a90-125">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="f4a90-126">外部資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="f4a90-126">Verify external credentials.</span></span>  
  
-   <span data-ttu-id="f4a90-127">外部資格情報が有効ではない場合は、SSO 管理ツールを使用して、この外部アカウントの外部資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="f4a90-127">The external credentials are not valid, use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="f4a90-128">関連付けられたすべてのアプリケーションにおいて、(特定のアカウントの) 外部パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4a90-128">You must set the external password (for the given account) in all associated applications.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="f4a90-129">詳細</span><span class="sxs-lookup"><span data-stu-id="f4a90-129">More info</span></span>
  
-   [<span data-ttu-id="f4a90-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="f4a90-130">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="f4a90-131">**パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="f4a90-131">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>