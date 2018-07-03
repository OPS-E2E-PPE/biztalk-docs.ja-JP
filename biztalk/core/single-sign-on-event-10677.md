---
title: 'シングル サインオン: イベント 10677 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2894792b-e1c9-4c24-875d-9193cbb5cd35
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1fc5bfbb6df26f1b1125a0d5d8b06a75e441f15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022000"
---
# <a name="single-sign-on-event-10677"></a><span data-ttu-id="bc8da-102">シングル サインオン: イベント 10677</span><span class="sxs-lookup"><span data-stu-id="bc8da-102">Single Sign-On: Event 10677</span></span>
## <a name="details"></a><span data-ttu-id="bc8da-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bc8da-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bc8da-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bc8da-104">Product Name</span></span>   |                                                                                                                    <span data-ttu-id="bc8da-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bc8da-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="bc8da-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bc8da-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    <span data-ttu-id="bc8da-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bc8da-107">Event ID</span></span>     |                                                                                                                              <span data-ttu-id="bc8da-108">10677</span><span class="sxs-lookup"><span data-stu-id="bc8da-108">10677</span></span>                                                                                                                               |
|  <span data-ttu-id="bc8da-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bc8da-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="bc8da-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bc8da-110">ENTSSO</span></span>                                                                                                                              |
|    <span data-ttu-id="bc8da-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bc8da-111">Component</span></span>    |                                                                                                                               <span data-ttu-id="bc8da-112">N\A</span><span class="sxs-lookup"><span data-stu-id="bc8da-112">N\A</span></span>                                                                                                                                |
|  <span data-ttu-id="bc8da-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bc8da-113">Symbolic Name</span></span>  |                                                                                                                  <span data-ttu-id="bc8da-114">SSO_WARN_NO_EXISTING_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="bc8da-114">SSO_WARN_NO_EXISTING_PASSWORD</span></span>                                                                                                                   |
|  <span data-ttu-id="bc8da-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bc8da-115">Message Text</span></span>   | <span data-ttu-id="bc8da-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="bc8da-116">External password change.</span></span> <span data-ttu-id="bc8da-117">この外部アカウントについて既存の資格情報が存在しないので、古いパスワードを検証できません。%r</span><span class="sxs-lookup"><span data-stu-id="bc8da-117">The old password cannot be verified because there are no existing credentials for this external account.%r</span></span><br /><br /> <span data-ttu-id="bc8da-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bc8da-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="bc8da-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="bc8da-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="bc8da-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="bc8da-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="bc8da-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="bc8da-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="bc8da-122">説明</span><span class="sxs-lookup"><span data-stu-id="bc8da-122">Explanation</span></span>  
 <span data-ttu-id="bc8da-123">この警告イベントは、古いパスワードに既存の資格情報がないため、既存のパスワードを変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="bc8da-123">This Warning event indicates that an external password change cannot occur because the old password does not have existing credentials.</span></span>  

## <a name="user-action"></a><span data-ttu-id="bc8da-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bc8da-124">User Action</span></span>  
 <span data-ttu-id="bc8da-125">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="bc8da-125">To resolve this warning, do one or more of the following:</span></span>  

-   <span data-ttu-id="bc8da-126">このアダプターにどのアプリケーションが割り当てられていたかを確認し (イベント ログ メッセージに名前があります)、SSO 管理ツールを使用してこの外部アカウントの外部資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="bc8da-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="bc8da-127">それらのアプリケーションのすべてに対して (指定されたアカウントに) 外部パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc8da-127">You must set the external password (for the given account) in all of those Applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="bc8da-128">詳細</span><span class="sxs-lookup"><span data-stu-id="bc8da-128">More info</span></span>

- [<span data-ttu-id="bc8da-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="bc8da-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="bc8da-130">**パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="bc8da-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
