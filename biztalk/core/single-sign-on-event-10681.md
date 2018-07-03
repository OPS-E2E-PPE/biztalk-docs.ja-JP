---
title: 'シングル サインオン: イベント 10681 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d2b400db062dc76b32d071032ee75c55ef48046
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011667"
---
# <a name="single-sign-on-event-10681"></a><span data-ttu-id="b8f7f-102">シングル サインオン: イベント 10681</span><span class="sxs-lookup"><span data-stu-id="b8f7f-102">Single Sign-On: Event 10681</span></span>
## <a name="details"></a><span data-ttu-id="b8f7f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b8f7f-103">Details</span></span>  

|                 |                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b8f7f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b8f7f-104">Product Name</span></span>   |                                                                                              <span data-ttu-id="b8f7f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="b8f7f-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="b8f7f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b8f7f-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    <span data-ttu-id="b8f7f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b8f7f-107">Event ID</span></span>     |                                                                                                        <span data-ttu-id="b8f7f-108">10681</span><span class="sxs-lookup"><span data-stu-id="b8f7f-108">10681</span></span>                                                                                                         |
|  <span data-ttu-id="b8f7f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b8f7f-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="b8f7f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b8f7f-110">ENTSSO</span></span>                                                                                                        |
|    <span data-ttu-id="b8f7f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b8f7f-111">Component</span></span>    |                                                                                                         <span data-ttu-id="b8f7f-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b8f7f-112">N\A</span></span>                                                                                                          |
|  <span data-ttu-id="b8f7f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b8f7f-113">Symbolic Name</span></span>  |                                                                                         <span data-ttu-id="b8f7f-114">SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE</span><span class="sxs-lookup"><span data-stu-id="b8f7f-114">SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE</span></span>                                                                                          |
|  <span data-ttu-id="b8f7f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b8f7f-115">Message Text</span></span>   | <span data-ttu-id="b8f7f-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="b8f7f-116">External password change.</span></span> <span data-ttu-id="b8f7f-117">1 つまたは複数の外部アカウント変更が失敗したため、Windows パスワードは変更されませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="b8f7f-117">The Windows password was not changed because one or more of the external account changes failed.%r</span></span><br /><br /> <span data-ttu-id="b8f7f-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b8f7f-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="b8f7f-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="b8f7f-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="b8f7f-120">Windows アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="b8f7f-120">Windows Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="b8f7f-121">説明</span><span class="sxs-lookup"><span data-stu-id="b8f7f-121">Explanation</span></span>  
 <span data-ttu-id="b8f7f-122">この警告イベントは、1 つまたは複数の外部アカウント変更が失敗したため、Windows パスワードが変更されなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b8f7f-122">This Warning event indicates that the Windows password was not changed because one or more of the external account changes failed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="b8f7f-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b8f7f-123">User Action</span></span>  
 <span data-ttu-id="b8f7f-124">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="b8f7f-124">To resolve this warning, do one or more of the following:</span></span>  

-   <span data-ttu-id="b8f7f-125">関連するイベントのシステムおよびアプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8f7f-125">Check the System and Application Event logs for associated events.</span></span>  

-   <span data-ttu-id="b8f7f-126">SSO 管理ツールを使用してアダプターの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="b8f7f-126">Verify adapter configuration using the SSO administration tools.</span></span>  

-   <span data-ttu-id="b8f7f-127">外部システムを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8f7f-127">Verify external systems.</span></span>  

## <a name="more-info"></a><span data-ttu-id="b8f7f-128">詳細</span><span class="sxs-lookup"><span data-stu-id="b8f7f-128">More info</span></span>

- [<span data-ttu-id="b8f7f-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="b8f7f-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="b8f7f-130">**パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="b8f7f-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
