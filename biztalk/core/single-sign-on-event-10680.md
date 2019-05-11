---
title: シングル サインオン:イベント 10680 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88ea12ff-d181-423f-9054-b0c656cc4558
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a8b734006a8ec0181a3307386a32d8d249eaa25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397433"
---
# <a name="single-sign-on-event-10680"></a><span data-ttu-id="0cd02-102">シングル サインオン:イベント 10680</span><span class="sxs-lookup"><span data-stu-id="0cd02-102">Single Sign-On: Event 10680</span></span>
## <a name="details"></a><span data-ttu-id="0cd02-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0cd02-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0cd02-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0cd02-104">Product Name</span></span>   |                                                                                                                                        <span data-ttu-id="0cd02-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0cd02-105">Enterprise Single Sign-On</span></span>                                                                                                                                        |
| <span data-ttu-id="0cd02-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0cd02-106">Product Version</span></span> |                                                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                        |
|    <span data-ttu-id="0cd02-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0cd02-107">Event ID</span></span>     |                                                                                                                                                  <span data-ttu-id="0cd02-108">10680</span><span class="sxs-lookup"><span data-stu-id="0cd02-108">10680</span></span>                                                                                                                                                  |
|  <span data-ttu-id="0cd02-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0cd02-109">Event Source</span></span>   |                                                                                                                                                 <span data-ttu-id="0cd02-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0cd02-110">ENTSSO</span></span>                                                                                                                                                  |
|    <span data-ttu-id="0cd02-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0cd02-111">Component</span></span>    |                                                                                                                                                   <span data-ttu-id="0cd02-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="0cd02-112">N\A</span></span>                                                                                                                                                   |
|  <span data-ttu-id="0cd02-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0cd02-113">Symbolic Name</span></span>  |                                                                                                                                      <span data-ttu-id="0cd02-114">SSO_WARN_PS_GET_CREDS_FAILED</span><span class="sxs-lookup"><span data-stu-id="0cd02-114">SSO_WARN_PS_GET_CREDS_FAILED</span></span>                                                                                                                                       |
|  <span data-ttu-id="0cd02-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0cd02-115">Message Text</span></span>   | <span data-ttu-id="0cd02-116">既存の外部資格情報を SSO database.%r から取得できませんでした。 ので、外部アカウントのパスワードが変更されませんでした。</span><span class="sxs-lookup"><span data-stu-id="0cd02-116">The password was not changed for the external account because the existing external credentials could not be obtained from the SSO database.%r</span></span><br /><br /> <span data-ttu-id="0cd02-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0cd02-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0cd02-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="0cd02-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="0cd02-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="0cd02-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="0cd02-120">外部アカウント: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="0cd02-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="0cd02-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="0cd02-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="0cd02-122">説明</span><span class="sxs-lookup"><span data-stu-id="0cd02-122">Explanation</span></span>  
 <span data-ttu-id="0cd02-123">この警告イベントは、パスワードが変更されていないこと、外部アカウントの既存の外部資格情報を SSO データベースから取得できませんでしたのでを示します。</span><span class="sxs-lookup"><span data-stu-id="0cd02-123">This Warning event indicates that the password was not changed for the external account because the existing external credentials could not be obtained from the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="0cd02-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0cd02-124">User Action</span></span>  
 <span data-ttu-id="0cd02-125">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0cd02-125">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="0cd02-126">外部資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="0cd02-126">Verify external credentials.</span></span>  

-   <span data-ttu-id="0cd02-127">外部資格情報が有効でない、SSO 管理ツールを使用して、この外部アカウントの外部資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="0cd02-127">The external credentials are not valid, use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="0cd02-128">関連付けられているすべてのアプリケーションでは、(特定のアカウント) の外部パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cd02-128">You must set the external password (for the given account) in all associated applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="0cd02-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0cd02-129">More info</span></span>

- [<span data-ttu-id="0cd02-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="0cd02-130">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="0cd02-131">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0cd02-131">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
