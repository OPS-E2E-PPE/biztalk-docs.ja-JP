---
title: 'シングル サインオン: イベント 10673 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1d572a-1e9f-496e-a219-852e7d9228d5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fb923d1e137a00eed4ba87e65df71b226287aa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975139"
---
# <a name="single-sign-on-event-10673"></a><span data-ttu-id="ed8ef-102">シングル サインオン: イベント 10673</span><span class="sxs-lookup"><span data-stu-id="ed8ef-102">Single Sign-On: Event 10673</span></span>
## <a name="details"></a><span data-ttu-id="ed8ef-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ed8ef-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ed8ef-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ed8ef-104">Product Name</span></span>   |                                                                                                                                                                        <span data-ttu-id="ed8ef-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ed8ef-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                         |
| <span data-ttu-id="ed8ef-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ed8ef-106">Product Version</span></span> |                                                                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                        |
|    <span data-ttu-id="ed8ef-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ed8ef-107">Event ID</span></span>     |                                                                                                                                                                                  <span data-ttu-id="ed8ef-108">10673</span><span class="sxs-lookup"><span data-stu-id="ed8ef-108">10673</span></span>                                                                                                                                                                                   |
|  <span data-ttu-id="ed8ef-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ed8ef-109">Event Source</span></span>   |                                                                                                                                                                                  <span data-ttu-id="ed8ef-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ed8ef-110">ENTSSO</span></span>                                                                                                                                                                                  |
|    <span data-ttu-id="ed8ef-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ed8ef-111">Component</span></span>    |                                                                                                                                                                                   <span data-ttu-id="ed8ef-112">N\A</span><span class="sxs-lookup"><span data-stu-id="ed8ef-112">N\A</span></span>                                                                                                                                                                                    |
|  <span data-ttu-id="ed8ef-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ed8ef-113">Symbolic Name</span></span>  |                                                                                                                                                                <span data-ttu-id="ed8ef-114">SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="ed8ef-114">SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span></span>                                                                                                                                                                 |
|  <span data-ttu-id="ed8ef-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ed8ef-115">Message Text</span></span>   | <span data-ttu-id="ed8ef-116">外部パスワード変更により、複数の Windows アカウントが変更されます。%r</span><span class="sxs-lookup"><span data-stu-id="ed8ef-116">An external password change will cause changes to more than one Windows account.%r</span></span><br /><br /> <span data-ttu-id="ed8ef-117">この外部システムのアダプターは、マッピングの競合を許可するように構成されているため、これは許可されます。%r</span><span class="sxs-lookup"><span data-stu-id="ed8ef-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="ed8ef-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ed8ef-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="ed8ef-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="ed8ef-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="ed8ef-120">外部アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="ed8ef-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="ed8ef-121">Windows アカウント 1: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="ed8ef-121">Windows Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="ed8ef-122">Windows アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="ed8ef-122">Windows Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="ed8ef-123">説明</span><span class="sxs-lookup"><span data-stu-id="ed8ef-123">Explanation</span></span>  
 <span data-ttu-id="ed8ef-124">この情報イベントは、外部パスワード変更により複数の Windows アカウントが変更されることを示します。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-124">This Information event indicates that an external password change will cause changes to more than one Windows account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ed8ef-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ed8ef-125">User Action</span></span>  

-   <span data-ttu-id="ed8ef-126">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-126">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="ed8ef-127">詳細</span><span class="sxs-lookup"><span data-stu-id="ed8ef-127">More info</span></span>

- [<span data-ttu-id="ed8ef-128">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="ed8ef-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="ed8ef-129">**パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="ed8ef-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="ed8ef-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="ed8ef-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
