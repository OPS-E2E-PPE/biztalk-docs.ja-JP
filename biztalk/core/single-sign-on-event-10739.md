---
title: "シングル サインオン: イベント 10739 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1039c832-80ff-4cc2-97b4-2671672b6b12
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8a3dc964d830155a63a5ada8817e8b44aaa4c18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10739"></a><span data-ttu-id="a593c-102">シングル サインオン: イベント 10739</span><span class="sxs-lookup"><span data-stu-id="a593c-102">Single Sign-On: Event 10739</span></span>
## <a name="details"></a><span data-ttu-id="a593c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a593c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a593c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a593c-104">Product Name</span></span>|<span data-ttu-id="a593c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a593c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a593c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a593c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a593c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a593c-107">Event ID</span></span>|<span data-ttu-id="a593c-108">10739</span><span class="sxs-lookup"><span data-stu-id="a593c-108">10739</span></span>|  
|<span data-ttu-id="a593c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a593c-109">Event Source</span></span>|<span data-ttu-id="a593c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a593c-110">ENTSSO</span></span>|  
|<span data-ttu-id="a593c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a593c-111">Component</span></span>|<span data-ttu-id="a593c-112">N\A</span><span class="sxs-lookup"><span data-stu-id="a593c-112">N\A</span></span>|  
|<span data-ttu-id="a593c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a593c-113">Symbolic Name</span></span>|<span data-ttu-id="a593c-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="a593c-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span></span>|  
|<span data-ttu-id="a593c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a593c-115">Message Text</span></span>|<span data-ttu-id="a593c-116">SSO データベースの Windows パスワードを更新できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="a593c-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="a593c-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a593c-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a593c-118">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a593c-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="a593c-119">Windows アカウント: %3\\%4 %r</span><span class="sxs-lookup"><span data-stu-id="a593c-119">Windows Account: %3\\%4%r</span></span><br /><br /> <span data-ttu-id="a593c-120">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="a593c-120">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a593c-121">説明</span><span class="sxs-lookup"><span data-stu-id="a593c-121">Explanation</span></span>  
 <span data-ttu-id="a593c-122">この警告イベントは、SSO によって、SSO データベース内の Windows パスワードを更新できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a593c-122">This Warning event indicates that SSO failed to update the Windows password in the SSO database.</span></span> <span data-ttu-id="a593c-123">警告メッセージには、失敗の考えられるさまざまな原因が示されています。場合によっては、この警告で構成の問題が示されることがあります。また、パスワードの変更中にマッピングが削除された可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="a593c-123">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a593c-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a593c-124">User Action</span></span>  
 <span data-ttu-id="a593c-125">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="a593c-125">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="a593c-126">パスワードの変更を再試行します。</span><span class="sxs-lookup"><span data-stu-id="a593c-126">Retry the password change.</span></span>  
  
-   <span data-ttu-id="a593c-127">再試行も失敗する場合、UI またはコマンド ライン ツールを使用して手動でパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="a593c-127">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  
  
 <span data-ttu-id="a593c-128">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a593c-128">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="a593c-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="a593c-129">Password Synchronization</span></span>](../core/password-synchronization2.md)