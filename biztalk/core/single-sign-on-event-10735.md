---
title: シングル サインオン:イベント 10735 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31c791c6-1901-4441-b329-ed75833cb83e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3e7752733a437f3526af7d5ac2790d2ffac64fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291779"
---
# <a name="single-sign-on-event-10735"></a><span data-ttu-id="d36e2-102">シングル サインオン:イベント 10735</span><span class="sxs-lookup"><span data-stu-id="d36e2-102">Single Sign-On: Event 10735</span></span>
## <a name="details"></a><span data-ttu-id="d36e2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d36e2-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d36e2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d36e2-104">Product Name</span></span>   |                                                                                                             <span data-ttu-id="d36e2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d36e2-105">Enterprise Single Sign-On</span></span>                                                                                                              |
| <span data-ttu-id="d36e2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d36e2-106">Product Version</span></span> |                                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    <span data-ttu-id="d36e2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d36e2-107">Event ID</span></span>     |                                                                                                                       <span data-ttu-id="d36e2-108">10735</span><span class="sxs-lookup"><span data-stu-id="d36e2-108">10735</span></span>                                                                                                                        |
|  <span data-ttu-id="d36e2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d36e2-109">Event Source</span></span>   |                                                                                                                       <span data-ttu-id="d36e2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d36e2-110">ENTSSO</span></span>                                                                                                                       |
|    <span data-ttu-id="d36e2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d36e2-111">Component</span></span>    |                                                                                                                        <span data-ttu-id="d36e2-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="d36e2-112">N\A</span></span>                                                                                                                         |
|  <span data-ttu-id="d36e2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d36e2-113">Symbolic Name</span></span>  |                                                                                                              <span data-ttu-id="d36e2-114">SSO_WARN_PS_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="d36e2-114">SSO_WARN_PS_APP_DISABLED</span></span>                                                                                                              |
|  <span data-ttu-id="d36e2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d36e2-115">Message Text</span></span>   | <span data-ttu-id="d36e2-116">外部パスワード変更。</span><span class="sxs-lookup"><span data-stu-id="d36e2-116">External password change.</span></span> <span data-ttu-id="d36e2-117">アプリケーションが disabled.%r であるため、外部アカウントのパスワードが変更されませんでした。</span><span class="sxs-lookup"><span data-stu-id="d36e2-117">The password was not changed for the external account because the application is disabled.%r</span></span><br /><br /> <span data-ttu-id="d36e2-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d36e2-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d36e2-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="d36e2-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="d36e2-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="d36e2-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="d36e2-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="d36e2-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="d36e2-122">説明</span><span class="sxs-lookup"><span data-stu-id="d36e2-122">Explanation</span></span>  
 <span data-ttu-id="d36e2-123">この警告イベントでは、パスワードが変更されていないこと、外部アカウントのため、アプリケーションが無効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d36e2-123">This Warning event indicates that a password was not changed for the external account because the application is disabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d36e2-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d36e2-124">User Action</span></span>  
 <span data-ttu-id="d36e2-125">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d36e2-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="d36e2-126">関連アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d36e2-126">Enable the affiliate application</span></span>  

  <span data-ttu-id="d36e2-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d36e2-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="d36e2-128">関連アプリケーションを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="d36e2-128">How to Enable an Affiliate Application</span></span>](../core/how-to-enable-an-affiliate-application.md)  

- [<span data-ttu-id="d36e2-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="d36e2-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
