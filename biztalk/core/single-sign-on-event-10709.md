---
title: "シングル サインオン: イベント 10709 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98e86890-88dd-49f0-bb2c-1234507e8be5
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a28807d9307ba1217e5b48e24facfe36711536f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10709"></a><span data-ttu-id="49042-102">シングル サインオン: イベント 10709</span><span class="sxs-lookup"><span data-stu-id="49042-102">Single Sign-On: Event 10709</span></span>
## <a name="details"></a><span data-ttu-id="49042-103">詳細</span><span class="sxs-lookup"><span data-stu-id="49042-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49042-104">製品名</span><span class="sxs-lookup"><span data-stu-id="49042-104">Product Name</span></span>|<span data-ttu-id="49042-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="49042-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="49042-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="49042-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="49042-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="49042-107">Event ID</span></span>|<span data-ttu-id="49042-108">10709</span><span class="sxs-lookup"><span data-stu-id="49042-108">10709</span></span>|  
|<span data-ttu-id="49042-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="49042-109">Event Source</span></span>|<span data-ttu-id="49042-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="49042-110">ENTSSO</span></span>|  
|<span data-ttu-id="49042-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="49042-111">Component</span></span>|<span data-ttu-id="49042-112">N\A</span><span class="sxs-lookup"><span data-stu-id="49042-112">N\A</span></span>|  
|<span data-ttu-id="49042-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="49042-113">Symbolic Name</span></span>|<span data-ttu-id="49042-114">SSO_WARN_PS_PCNS_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="49042-114">SSO_WARN_PS_PCNS_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="49042-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="49042-115">Message Text</span></span>|<span data-ttu-id="49042-116">PCNS からの Windows パスワード変更は、アクセス ドメイン内のドメイン コントローラーからのみ受け付けられます。%r</span><span class="sxs-lookup"><span data-stu-id="49042-116">Windows password changes from PCNS will only be accepted from Domain Controllers in the access domain.%r</span></span><br /><br /> <span data-ttu-id="49042-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="49042-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="49042-118">クライアント ユーザー: %2 %r</span><span class="sxs-lookup"><span data-stu-id="49042-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="49042-119">アクセス ドメイン: %3 %r</span><span class="sxs-lookup"><span data-stu-id="49042-119">Access Domain: %3%r</span></span><br /><br /> <span data-ttu-id="49042-120">アクセス Sid: %4 %r</span><span class="sxs-lookup"><span data-stu-id="49042-120">Access Sid: %4%r</span></span><br /><br /> <span data-ttu-id="49042-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="49042-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="49042-122">説明</span><span class="sxs-lookup"><span data-stu-id="49042-122">Explanation</span></span>  
 <span data-ttu-id="49042-123">この警告イベントは、Windows パスワード変更が、ENTSSO サーバーのドメイン以外のサーバー上のパスワード変更通知サービス (PCNS) から受信されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="49042-123">This Warning event indicates that a Windows password change was received from Password Change Notification Services (PCNS) on a server outside the ENTSSO server's domain.</span></span> <span data-ttu-id="49042-124">Windows パスワード変更は、ENTSSO サーバーと同じドメイン内のドメイン コントローラーからのみ受け付けられます。</span><span class="sxs-lookup"><span data-stu-id="49042-124">Windows password changes will only be accepted from domain controllers in the same domain as the ENTSSO server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="49042-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="49042-125">User Action</span></span>  
 <span data-ttu-id="49042-126">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="49042-126">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="49042-127">PCNS と同じドメイン内で ENTSSO サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="49042-127">Configure an ENTSSO server in the same domain as PCNS.</span></span>  
  
 <span data-ttu-id="49042-128">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49042-128">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="49042-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="49042-129">Password Synchronization</span></span>](../core/password-synchronization2.md)