---
title: シングル サインオン:イベント 10669 |Microsoft Docs
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
ms.openlocfilehash: 1d0a9ab77f528060be25616eb8d80072402957a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397534"
---
# <a name="single-sign-on-event-10669"></a><span data-ttu-id="24430-102">シングル サインオン:イベント 10669</span><span class="sxs-lookup"><span data-stu-id="24430-102">Single Sign-On: Event 10669</span></span>
## <a name="details"></a><span data-ttu-id="24430-103">詳細</span><span class="sxs-lookup"><span data-stu-id="24430-103">Details</span></span>  

|                 |                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="24430-104">製品名</span><span class="sxs-lookup"><span data-stu-id="24430-104">Product Name</span></span>   |                                                                   <span data-ttu-id="24430-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="24430-105">Enterprise Single Sign-On</span></span>                                                                   |
| <span data-ttu-id="24430-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="24430-106">Product Version</span></span> |                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    <span data-ttu-id="24430-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="24430-107">Event ID</span></span>     |                                                                             <span data-ttu-id="24430-108">10669</span><span class="sxs-lookup"><span data-stu-id="24430-108">10669</span></span>                                                                             |
|  <span data-ttu-id="24430-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="24430-109">Event Source</span></span>   |                                                                            <span data-ttu-id="24430-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="24430-110">ENTSSO</span></span>                                                                             |
|    <span data-ttu-id="24430-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="24430-111">Component</span></span>    |                                                                              <span data-ttu-id="24430-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="24430-112">N\A</span></span>                                                                              |
|  <span data-ttu-id="24430-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="24430-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="24430-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="24430-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span></span>                                                            |
|  <span data-ttu-id="24430-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="24430-115">Message Text</span></span>   | <span data-ttu-id="24430-116">Windows password.%r を変更できませんでした。</span><span class="sxs-lookup"><span data-stu-id="24430-116">Failed to change the Windows password.%r</span></span><br /><br /> <span data-ttu-id="24430-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="24430-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="24430-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="24430-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="24430-119">Windows アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="24430-119">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="24430-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="24430-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="24430-121">説明</span><span class="sxs-lookup"><span data-stu-id="24430-121">Explanation</span></span>  
 <span data-ttu-id="24430-122">この警告イベントは、Windows パスワードを変更する SSO が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="24430-122">This Warning event indicates that SSO failed to change a Windows password.</span></span> <span data-ttu-id="24430-123">SSO は、Win32 関数のマッピングに関連付けられている Windows のパスワードを変更する netuserchangepassword を呼び出して関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="24430-123">SSO calls the Win32 function NetUserChangePassword function to change the Windows password associated with the mapping.</span></span> <span data-ttu-id="24430-124">この関数が失敗するとこのエラー メッセージが発行されます。</span><span class="sxs-lookup"><span data-stu-id="24430-124">If this function fails this error message is issued.</span></span> <span data-ttu-id="24430-125">エラー コードは、NetUserChangePassword から返された 1 つになります。</span><span class="sxs-lookup"><span data-stu-id="24430-125">The error code will be the one returned from NetUserChangePassword.</span></span> <span data-ttu-id="24430-126">詳細については MSDN では、この関数のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24430-126">See the documentation for this function in MSDN for details.</span></span> <span data-ttu-id="24430-127">エラーの最も多い原因は、古いパスワードが間違ってまたは、新しいパスワードが必要な Windows パスワード ポリシーを満たしていないことです。</span><span class="sxs-lookup"><span data-stu-id="24430-127">Most likely causes of failure are that the old password was incorrect, or that the new password does not meet the required Windows password policy.</span></span>  

## <a name="user-action"></a><span data-ttu-id="24430-128">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="24430-128">User Action</span></span>  
 <span data-ttu-id="24430-129">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="24430-129">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="24430-130">古いパスワードを確認します。</span><span class="sxs-lookup"><span data-stu-id="24430-130">Verify the old password.</span></span> <span data-ttu-id="24430-131">古いパスワードが正しくない場合、コマンド ライン ツールまたは管理 MMC を使用して SSO データベースに手動で設定することができます。</span><span class="sxs-lookup"><span data-stu-id="24430-131">If the old password is incorrect then it can be set manually in the SSO database using the command line tools or Admin MMC.</span></span>  

- <span data-ttu-id="24430-132">新しいパスワードが必要な Windows パスワード ポリシーを満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24430-132">Verify the new password meets the required Windows password policy.</span></span> <span data-ttu-id="24430-133">パスワードが満たしていない場合し Windows パスワード ポリシーがパスワード フィルターの使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="24430-133">If the password does not meet the Windows password policy then consider using password filters.</span></span>  

  <span data-ttu-id="24430-134">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="24430-134">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="24430-135">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="24430-135">Password Synchronization</span></span>](../core/password-synchronization2.md)
