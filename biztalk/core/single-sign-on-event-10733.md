---
title: シングル サインオン:イベント 10733 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01520ae4-f692-4697-82ce-53a8a63b5bd9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3f67e18a9388e5f055d760d6223e2034ad6ea0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291794"
---
# <a name="single-sign-on-event-10733"></a><span data-ttu-id="a04a8-102">シングル サインオン:イベント 10733</span><span class="sxs-lookup"><span data-stu-id="a04a8-102">Single Sign-On: Event 10733</span></span>
## <a name="details"></a><span data-ttu-id="a04a8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a04a8-103">Details</span></span>  

|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a04a8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a04a8-104">Product Name</span></span>   |                                                                  <span data-ttu-id="a04a8-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a04a8-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="a04a8-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a04a8-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    <span data-ttu-id="a04a8-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a04a8-107">Event ID</span></span>     |                                                                            <span data-ttu-id="a04a8-108">10733</span><span class="sxs-lookup"><span data-stu-id="a04a8-108">10733</span></span>                                                                            |
|  <span data-ttu-id="a04a8-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a04a8-109">Event Source</span></span>   |                                                                           <span data-ttu-id="a04a8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a04a8-110">ENTSSO</span></span>                                                                            |
|    <span data-ttu-id="a04a8-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a04a8-111">Component</span></span>    |                                                                             <span data-ttu-id="a04a8-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="a04a8-112">N\A</span></span>                                                                             |
|  <span data-ttu-id="a04a8-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a04a8-113">Symbolic Name</span></span>  |                                                              <span data-ttu-id="a04a8-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="a04a8-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span></span>                                                               |
|  <span data-ttu-id="a04a8-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a04a8-115">Message Text</span></span>   | <span data-ttu-id="a04a8-116">SSO database.%r 内の Windows パスワードを更新できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a04a8-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="a04a8-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a04a8-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a04a8-118">Windows アカウント: %2\\% 3 %r</span><span class="sxs-lookup"><span data-stu-id="a04a8-118">Windows Account: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="a04a8-119">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="a04a8-119">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="a04a8-120">説明</span><span class="sxs-lookup"><span data-stu-id="a04a8-120">Explanation</span></span>  
 <span data-ttu-id="a04a8-121">この警告イベントは、SSO データベース内の指定の Windows アカウントのパスワードを更新するパスワード同期が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="a04a8-121">This Warning event indicates that Password Sync failed to update the specified Windows account password in the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a04a8-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a04a8-122">User Action</span></span>  
 <span data-ttu-id="a04a8-123">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a04a8-123">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="a04a8-124">関連付けられているエラーのシステムおよびアプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="a04a8-124">Check the system and application event logs for associated errors.</span></span>  

- <span data-ttu-id="a04a8-125">指定されたアカウントのパスワードが有効な Windows パスワードであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a04a8-125">Verify the password for the specified account is a valid Windows password.</span></span>  

  <span data-ttu-id="a04a8-126">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a04a8-126">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="a04a8-127">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="a04a8-127">Password Synchronization</span></span>](../core/password-synchronization2.md)
