---
title: 'シングル サインオン: イベント 10735 |Microsoft Docs'
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
ms.openlocfilehash: ede774a4a212d71aa65165f7da1f6de5bb04103c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979227"
---
# <a name="single-sign-on-event-10735"></a><span data-ttu-id="b2a09-102">シングル サインオン: イベント 10735</span><span class="sxs-lookup"><span data-stu-id="b2a09-102">Single Sign-On: Event 10735</span></span>
## <a name="details"></a><span data-ttu-id="b2a09-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b2a09-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b2a09-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b2a09-104">Product Name</span></span>   |                                                                                                             <span data-ttu-id="b2a09-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="b2a09-105">Enterprise Single Sign-On</span></span>                                                                                                              |
| <span data-ttu-id="b2a09-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b2a09-106">Product Version</span></span> |                                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    <span data-ttu-id="b2a09-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b2a09-107">Event ID</span></span>     |                                                                                                                       <span data-ttu-id="b2a09-108">10735</span><span class="sxs-lookup"><span data-stu-id="b2a09-108">10735</span></span>                                                                                                                        |
|  <span data-ttu-id="b2a09-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b2a09-109">Event Source</span></span>   |                                                                                                                       <span data-ttu-id="b2a09-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b2a09-110">ENTSSO</span></span>                                                                                                                       |
|    <span data-ttu-id="b2a09-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b2a09-111">Component</span></span>    |                                                                                                                        <span data-ttu-id="b2a09-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b2a09-112">N\A</span></span>                                                                                                                         |
|  <span data-ttu-id="b2a09-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b2a09-113">Symbolic Name</span></span>  |                                                                                                              <span data-ttu-id="b2a09-114">SSO_WARN_PS_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="b2a09-114">SSO_WARN_PS_APP_DISABLED</span></span>                                                                                                              |
|  <span data-ttu-id="b2a09-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b2a09-115">Message Text</span></span>   | <span data-ttu-id="b2a09-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="b2a09-116">External password change.</span></span> <span data-ttu-id="b2a09-117">アプリケーションが無効になっているため、外部アカウントのパスワードは変更されませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="b2a09-117">The password was not changed for the external account because the application is disabled.%r</span></span><br /><br /> <span data-ttu-id="b2a09-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b2a09-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="b2a09-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="b2a09-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="b2a09-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="b2a09-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="b2a09-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="b2a09-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="b2a09-122">説明</span><span class="sxs-lookup"><span data-stu-id="b2a09-122">Explanation</span></span>  
 <span data-ttu-id="b2a09-123">この警告イベントは、アプリケーションが無効になっているため、外部アカウントのパスワードが変更されなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b2a09-123">This Warning event indicates that a password was not changed for the external account because the application is disabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="b2a09-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b2a09-124">User Action</span></span>  
 <span data-ttu-id="b2a09-125">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="b2a09-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="b2a09-126">関連アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b2a09-126">Enable the affiliate application</span></span>  

  <span data-ttu-id="b2a09-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2a09-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="b2a09-128">関連アプリケーションを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="b2a09-128">How to Enable an Affiliate Application</span></span>](../core/how-to-enable-an-affiliate-application.md)  

- [<span data-ttu-id="b2a09-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="b2a09-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
