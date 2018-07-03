---
title: 'シングル サインオン: イベント 10678 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af92ce1-fdac-432f-be6b-cf8958aee776
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fa3cde1cb26023ab4115f5538b8a3081eaaf1bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977435"
---
# <a name="single-sign-on-event-10678"></a><span data-ttu-id="8ad77-102">シングル サインオン: イベント 10678</span><span class="sxs-lookup"><span data-stu-id="8ad77-102">Single Sign-On: Event 10678</span></span>
## <a name="details"></a><span data-ttu-id="8ad77-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8ad77-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8ad77-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8ad77-104">Product Name</span></span>   |                                                                                                                    <span data-ttu-id="8ad77-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8ad77-105">Enterprise Single Sign-On</span></span>                                                                                                                    |
| <span data-ttu-id="8ad77-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8ad77-106">Product Version</span></span> |                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    <span data-ttu-id="8ad77-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8ad77-107">Event ID</span></span>     |                                                                                                                              <span data-ttu-id="8ad77-108">10678</span><span class="sxs-lookup"><span data-stu-id="8ad77-108">10678</span></span>                                                                                                                              |
|  <span data-ttu-id="8ad77-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8ad77-109">Event Source</span></span>   |                                                                                                                             <span data-ttu-id="8ad77-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8ad77-110">ENTSSO</span></span>                                                                                                                              |
|    <span data-ttu-id="8ad77-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8ad77-111">Component</span></span>    |                                                                                                                               <span data-ttu-id="8ad77-112">N\A</span><span class="sxs-lookup"><span data-stu-id="8ad77-112">N\A</span></span>                                                                                                                               |
|  <span data-ttu-id="8ad77-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8ad77-113">Symbolic Name</span></span>  |                                                                                                                   <span data-ttu-id="8ad77-114">SSO_WARN_PASSWORD_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="8ad77-114">SSO_WARN_PASSWORD_MISMATCH</span></span>                                                                                                                    |
|  <span data-ttu-id="8ad77-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8ad77-115">Message Text</span></span>   | <span data-ttu-id="8ad77-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="8ad77-116">External password change.</span></span> <span data-ttu-id="8ad77-117">アダプターによって指定された古いパスワードは、外部アカウントの既存のパスワードと一致しません。%r</span><span class="sxs-lookup"><span data-stu-id="8ad77-117">The old password supplied by the adapter does not match the existing password for the external account.%r</span></span><br /><br /> <span data-ttu-id="8ad77-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8ad77-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="8ad77-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="8ad77-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="8ad77-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="8ad77-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="8ad77-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="8ad77-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="8ad77-122">説明</span><span class="sxs-lookup"><span data-stu-id="8ad77-122">Explanation</span></span>  
 <span data-ttu-id="8ad77-123">この警告イベントは、アダプターによって指定された古いパスワードが、外部アカウントの既存のパスワードと一致しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8ad77-123">This Warning event indicates that the old password supplied by the adapter does not match the existing password for the external account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8ad77-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8ad77-124">User Action</span></span>  
 <span data-ttu-id="8ad77-125">この警告を解消するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ad77-125">To resolve this warning do the following:</span></span>  

-   <span data-ttu-id="8ad77-126">このアダプターにどのアプリケーションが割り当てられていたかを確認し (イベント ログ メッセージに名前があります)、SSO 管理ツールを使用してこの外部アカウントの外部資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="8ad77-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="8ad77-127">それらのアプリケーションのすべてに対して (指定されたアカウントに) 外部パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ad77-127">You must set the external password (for the given account) in all of those Applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="8ad77-128">詳細</span><span class="sxs-lookup"><span data-stu-id="8ad77-128">More info</span></span>

- [<span data-ttu-id="8ad77-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="8ad77-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="8ad77-130">**パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="8ad77-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
