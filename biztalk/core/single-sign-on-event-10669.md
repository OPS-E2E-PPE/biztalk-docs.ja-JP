---
title: 'シングル サインオン: イベント 10669 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e88a583d-7385-42dd-841e-aa2d2215dd69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 334180225d47cb9a86577cab75490ea0b6f2225a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271626"
---
# <a name="single-sign-on-event-10669"></a><span data-ttu-id="36745-102">シングル サインオン: イベント 10669</span><span class="sxs-lookup"><span data-stu-id="36745-102">Single Sign-On: Event 10669</span></span>
## <a name="details"></a><span data-ttu-id="36745-103">詳細</span><span class="sxs-lookup"><span data-stu-id="36745-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="36745-104">製品名</span><span class="sxs-lookup"><span data-stu-id="36745-104">Product Name</span></span>|<span data-ttu-id="36745-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="36745-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="36745-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="36745-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="36745-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36745-107">Event ID</span></span>|<span data-ttu-id="36745-108">10669</span><span class="sxs-lookup"><span data-stu-id="36745-108">10669</span></span>|  
|<span data-ttu-id="36745-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="36745-109">Event Source</span></span>|<span data-ttu-id="36745-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="36745-110">ENTSSO</span></span>|  
|<span data-ttu-id="36745-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="36745-111">Component</span></span>|<span data-ttu-id="36745-112">N\A</span><span class="sxs-lookup"><span data-stu-id="36745-112">N\A</span></span>|  
|<span data-ttu-id="36745-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="36745-113">Symbolic Name</span></span>|<span data-ttu-id="36745-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="36745-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span></span>|  
|<span data-ttu-id="36745-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="36745-115">Message Text</span></span>|<span data-ttu-id="36745-116">Windows パスワードを変更できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="36745-116">Failed to change the Windows password.%r</span></span><br /><br /> <span data-ttu-id="36745-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="36745-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="36745-118">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="36745-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="36745-119">Windows アカウント: %3 %r</span><span class="sxs-lookup"><span data-stu-id="36745-119">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="36745-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="36745-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="36745-121">説明</span><span class="sxs-lookup"><span data-stu-id="36745-121">Explanation</span></span>  
 <span data-ttu-id="36745-122">この警告イベントは、SSO が Windows のパスワードを変更できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="36745-122">This Warning event indicates that SSO failed to change a Windows password.</span></span> <span data-ttu-id="36745-123">SSO は、Win32 の関数 NetUserChangePassword を呼び出して、マッピングと関連付けられた Windows のパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="36745-123">SSO calls the Win32 function NetUserChangePassword function to change the Windows password associated with the mapping.</span></span> <span data-ttu-id="36745-124">この関数が失敗すると、このエラー メッセージが発生します。</span><span class="sxs-lookup"><span data-stu-id="36745-124">If this function fails this error message is issued.</span></span> <span data-ttu-id="36745-125">エラー コードは、NetUserChangePassword から返されたものです。</span><span class="sxs-lookup"><span data-stu-id="36745-125">The error code will be the one returned from NetUserChangePassword.</span></span> <span data-ttu-id="36745-126">詳細については、MSDN でこの関数のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36745-126">See the documentation for this function in MSDN for details.</span></span> <span data-ttu-id="36745-127">原因として最も可能性が高いのは、古いパスワードが正しくなかったか、または新しいパスワードが必要な Windows パスワード ポリシーを満たしていない場合です。</span><span class="sxs-lookup"><span data-stu-id="36745-127">Most likely causes of failure are that the old password was incorrect, or that the new password does not meet the required Windows password policy.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="36745-128">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="36745-128">User Action</span></span>  
 <span data-ttu-id="36745-129">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="36745-129">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="36745-130">古いパスワードを確認します。</span><span class="sxs-lookup"><span data-stu-id="36745-130">Verify the old password.</span></span> <span data-ttu-id="36745-131">古いパスワードが正しくない場合は、コマンド ライン ツールまたは管理 MMC を使用して、SSO データベースを手動で設定できます。</span><span class="sxs-lookup"><span data-stu-id="36745-131">If the old password is incorrect then it can be set manually in the SSO database using the command line tools or Admin MMC.</span></span>  
  
-   <span data-ttu-id="36745-132">新しいパスワードが必要な Windows パスワード ポリシーを満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36745-132">Verify the new password meets the required Windows password policy.</span></span> <span data-ttu-id="36745-133">パスワードが Windows パスワード ポリシーを満たしていない場合は、パスワード フィルターの使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="36745-133">If the password does not meet the Windows password policy then consider using password filters.</span></span>  
  
 <span data-ttu-id="36745-134">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="36745-134">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="36745-135">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="36745-135">Password Synchronization</span></span>](../core/password-synchronization2.md)