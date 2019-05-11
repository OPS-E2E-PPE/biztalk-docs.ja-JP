---
title: シングル サインオン:イベント 10709 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98e86890-88dd-49f0-bb2c-1234507e8be5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4f69e2226ab304e9d6b23ead1c9e2b84ffa9fb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397244"
---
# <a name="single-sign-on-event-10709"></a><span data-ttu-id="3fcbd-102">シングル サインオン:イベント 10709</span><span class="sxs-lookup"><span data-stu-id="3fcbd-102">Single Sign-On: Event 10709</span></span>
## <a name="details"></a><span data-ttu-id="3fcbd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3fcbd-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3fcbd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3fcbd-104">Product Name</span></span>   |                                                                                                                  <span data-ttu-id="3fcbd-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3fcbd-105">Enterprise Single Sign-On</span></span>                                                                                                                   |
| <span data-ttu-id="3fcbd-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3fcbd-106">Product Version</span></span> |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    <span data-ttu-id="3fcbd-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3fcbd-107">Event ID</span></span>     |                                                                                                                            <span data-ttu-id="3fcbd-108">10709</span><span class="sxs-lookup"><span data-stu-id="3fcbd-108">10709</span></span>                                                                                                                             |
|  <span data-ttu-id="3fcbd-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3fcbd-109">Event Source</span></span>   |                                                                                                                            <span data-ttu-id="3fcbd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3fcbd-110">ENTSSO</span></span>                                                                                                                            |
|    <span data-ttu-id="3fcbd-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3fcbd-111">Component</span></span>    |                                                                                                                             <span data-ttu-id="3fcbd-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="3fcbd-112">N\A</span></span>                                                                                                                              |
|  <span data-ttu-id="3fcbd-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3fcbd-113">Symbolic Name</span></span>  |                                                                                                                <span data-ttu-id="3fcbd-114">SSO_WARN_PS_PCNS_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="3fcbd-114">SSO_WARN_PS_PCNS_ACCESS_DENIED</span></span>                                                                                                                |
|  <span data-ttu-id="3fcbd-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3fcbd-115">Message Text</span></span>   | <span data-ttu-id="3fcbd-116">アクセス domain.%r 内に、PCNS から Windows パスワード変更がドメイン コント ローラーから受け入れのみ</span><span class="sxs-lookup"><span data-stu-id="3fcbd-116">Windows password changes from PCNS will only be accepted from Domain Controllers in the access domain.%r</span></span><br /><br /> <span data-ttu-id="3fcbd-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3fcbd-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3fcbd-118">クライアント ユーザー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="3fcbd-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="3fcbd-119">アクセス ドメイン: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="3fcbd-119">Access Domain: %3%r</span></span><br /><br /> <span data-ttu-id="3fcbd-120">アクセス Sid: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="3fcbd-120">Access Sid: %4%r</span></span><br /><br /> <span data-ttu-id="3fcbd-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="3fcbd-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="3fcbd-122">説明</span><span class="sxs-lookup"><span data-stu-id="3fcbd-122">Explanation</span></span>  
 <span data-ttu-id="3fcbd-123">この警告イベントでは、Windows パスワードの変更が、ENTSSO サーバーのドメインの外部のサーバーでパスワード変更通知サービス (PCNS) からを受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="3fcbd-123">This Warning event indicates that a Windows password change was received from Password Change Notification Services (PCNS) on a server outside the ENTSSO server's domain.</span></span> <span data-ttu-id="3fcbd-124">Windows パスワードの変更は、ENTSSO サーバーと同じドメインのドメイン コント ローラーからのみ受け付けられます。</span><span class="sxs-lookup"><span data-stu-id="3fcbd-124">Windows password changes will only be accepted from domain controllers in the same domain as the ENTSSO server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3fcbd-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3fcbd-125">User Action</span></span>  
 <span data-ttu-id="3fcbd-126">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3fcbd-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="3fcbd-127">PCNS と同じドメイン内には、ENTSSO サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3fcbd-127">Configure an ENTSSO server in the same domain as PCNS.</span></span>  

  <span data-ttu-id="3fcbd-128">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fcbd-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="3fcbd-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="3fcbd-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
