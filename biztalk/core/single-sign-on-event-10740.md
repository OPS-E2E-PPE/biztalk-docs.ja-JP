---
title: シングル サインオン:イベント 10740 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e8521e7-32af-4a58-8b1a-66ea1d13f1e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db19b81cb024ff6dfee2196cdefc33f8f977dea9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291756"
---
# <a name="single-sign-on-event-10740"></a><span data-ttu-id="e7149-102">シングル サインオン:イベント 10740</span><span class="sxs-lookup"><span data-stu-id="e7149-102">Single Sign-On: Event 10740</span></span>
## <a name="details"></a><span data-ttu-id="e7149-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e7149-103">Details</span></span>  

|                 |                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e7149-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e7149-104">Product Name</span></span>   |                                                                 <span data-ttu-id="e7149-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="e7149-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="e7149-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e7149-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    <span data-ttu-id="e7149-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7149-107">Event ID</span></span>     |                                                                           <span data-ttu-id="e7149-108">10740</span><span class="sxs-lookup"><span data-stu-id="e7149-108">10740</span></span>                                                                            |
|  <span data-ttu-id="e7149-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e7149-109">Event Source</span></span>   |                                                                           <span data-ttu-id="e7149-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e7149-110">ENTSSO</span></span>                                                                           |
|    <span data-ttu-id="e7149-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7149-111">Component</span></span>    |                                                                            <span data-ttu-id="e7149-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="e7149-112">N\A</span></span>                                                                             |
|  <span data-ttu-id="e7149-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e7149-113">Symbolic Name</span></span>  |                                                               <span data-ttu-id="e7149-114">SSO_WARN_INVALID_WINDOWS_USER</span><span class="sxs-lookup"><span data-stu-id="e7149-114">SSO_WARN_INVALID_WINDOWS_USER</span></span>                                                                |
|  <span data-ttu-id="e7149-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e7149-115">Message Text</span></span>   | <span data-ttu-id="e7149-116">Windows アカウントがアプリケーション update.%r のため無効です。</span><span class="sxs-lookup"><span data-stu-id="e7149-116">The Windows Account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="e7149-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e7149-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="e7149-118">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="e7149-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="e7149-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="e7149-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="e7149-120">説明</span><span class="sxs-lookup"><span data-stu-id="e7149-120">Explanation</span></span>  
 <span data-ttu-id="e7149-121">この警告イベントは、(イベント メッセージで指定された) Windows アカウントがアプリケーションの更新プログラムに対して有効ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e7149-121">This Warning event indicates that the Windows Account (specified in the event message) is not valid for application update.</span></span> <span data-ttu-id="e7149-122">これは、ホスト グループ アプリケーションの Windows アカウントを変更するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e7149-122">This can occur when changing the Windows account for a Host Group application.</span></span> <span data-ttu-id="e7149-123">ホスト グループ アプリケーションは、シングル サインオンの外部システムから Windows システムに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7149-123">Host Group applications are used for single sign-on from external systems to Windows systems.</span></span> <span data-ttu-id="e7149-124">1 つの Windows アカウントに、一連の外部ユーザーをマップできます。</span><span class="sxs-lookup"><span data-stu-id="e7149-124">They can map a set of external users to a single Windows account.</span></span> <span data-ttu-id="e7149-125">Windows アカウントにマップされますが、アプリケーションのアプリケーション ユーザー フィールドで定義されます。</span><span class="sxs-lookup"><span data-stu-id="e7149-125">The Windows account they are mapped to is defined in the Application Users field of the application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e7149-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e7149-126">User Action</span></span>  
 <span data-ttu-id="e7149-127">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7149-127">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="e7149-128">Windows アカウントの中であることを確認が有効でを使用します。</span><span class="sxs-lookup"><span data-stu-id="e7149-128">Check that the Windows account your are using is valid.</span></span>  

- <span data-ttu-id="e7149-129">Windows アカウントに適切なプロパティを持つ Windows アカウントを再作成します。</span><span class="sxs-lookup"><span data-stu-id="e7149-129">Recreate the Windows account with the correct Windows account properties.</span></span>  

  <span data-ttu-id="e7149-130">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7149-130">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="e7149-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="e7149-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
