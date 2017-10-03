---
title: "シングル サインオン: イベント 10750 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a0fdaf2-d429-40b9-adc3-eb134687fb1a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32b8c29159edc0cf6fa7281b5a717af509e3a63
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10750"></a><span data-ttu-id="4fb86-102">シングル サインオン: イベント 10750</span><span class="sxs-lookup"><span data-stu-id="4fb86-102">Single Sign-On: Event 10750</span></span>
## <a name="details"></a><span data-ttu-id="4fb86-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4fb86-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4fb86-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4fb86-104">Product Name</span></span>|<span data-ttu-id="4fb86-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4fb86-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4fb86-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4fb86-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4fb86-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4fb86-107">Event ID</span></span>|<span data-ttu-id="4fb86-108">10750</span><span class="sxs-lookup"><span data-stu-id="4fb86-108">10750</span></span>|  
|<span data-ttu-id="4fb86-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4fb86-109">Event Source</span></span>|<span data-ttu-id="4fb86-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4fb86-110">ENTSSO</span></span>|  
|<span data-ttu-id="4fb86-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4fb86-111">Component</span></span>|<span data-ttu-id="4fb86-112">N\A</span><span class="sxs-lookup"><span data-stu-id="4fb86-112">N\A</span></span>|  
|<span data-ttu-id="4fb86-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4fb86-113">Symbolic Name</span></span>|<span data-ttu-id="4fb86-114">SSO_ERROR_PS_WRONG_USER_NAME_TYPE</span><span class="sxs-lookup"><span data-stu-id="4fb86-114">SSO_ERROR_PS_WRONG_USER_NAME_TYPE</span></span>|  
|<span data-ttu-id="4fb86-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4fb86-115">Message Text</span></span>|<span data-ttu-id="4fb86-116">PasswordChangeNotify: 正しくないユーザー名の種類。</span><span class="sxs-lookup"><span data-stu-id="4fb86-116">PasswordChangeNotify: Incorrect User Name Type.</span></span> <span data-ttu-id="4fb86-117">指定できる値は USER_NAME_TYPE_NT4 のみです。</span><span class="sxs-lookup"><span data-stu-id="4fb86-117">The only accepted value is USER_NAME_TYPE_NT4.</span></span><br /><br /> <span data-ttu-id="4fb86-118">ターゲットが Active Directory で正しく構成されていません。%r</span><span class="sxs-lookup"><span data-stu-id="4fb86-118">The target is incorrectly configured in Active Directory.%r</span></span><br /><br /> <span data-ttu-id="4fb86-119">ユーザー名の種類: %r</span><span class="sxs-lookup"><span data-stu-id="4fb86-119">User Name Type: %1%r</span></span><br /><br /> <span data-ttu-id="4fb86-120">クライアント ユーザー: %2 %r</span><span class="sxs-lookup"><span data-stu-id="4fb86-120">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="4fb86-121">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="4fb86-121">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4fb86-122">説明</span><span class="sxs-lookup"><span data-stu-id="4fb86-122">Explanation</span></span>  
 <span data-ttu-id="4fb86-123">このエラー イベントは、パスワード同期が、パスワード変更通知サービス (PCNS) からパスワード変更を受け取ったが、パスワード変更の形式が正しくなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-123">This Error event indicates that Password Sync received a password change from the Password Change Notification Service (PCNS), but the password change was in the wrong format.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4fb86-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4fb86-124">User Action</span></span>  
 <span data-ttu-id="4fb86-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4fb86-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="4fb86-126">PCNS の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-126">Check the PCNS configuration.</span></span> <span data-ttu-id="4fb86-127">PCNS はドメイン コントローラーでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-127">PCNS can run only on a domain controller.</span></span>  
  
-   <span data-ttu-id="4fb86-128">Active Directory で、ユーザー名の種類を USER_NAME_TYPE_NT4 に構成します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-128">Configure User Name Type to USER_NAME_TYPE_NT4 in Active Directory.</span></span>  
  
 <span data-ttu-id="4fb86-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fb86-129">For more information, see the following resources:</span></span>  
  
-   <span data-ttu-id="4fb86-130">ユーザー名の種類を指定する方法については、Active Directory のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fb86-130">Refer to Active Directory documentation for information on how to specify User Name Type.</span></span>  
  
-   [<span data-ttu-id="4fb86-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="4fb86-131">Password Synchronization</span></span>](../core/password-synchronization2.md)