---
title: 'シングル サインオン: イベント 10671 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c5564f-6412-4e83-9bec-03264e992ebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f321a971f89c535da26604c3e03a2b62ebf060e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000075"
---
# <a name="single-sign-on-event-10671"></a><span data-ttu-id="da7a1-102">シングル サインオン: イベント 10671</span><span class="sxs-lookup"><span data-stu-id="da7a1-102">Single Sign-On: Event 10671</span></span>
## <a name="details"></a><span data-ttu-id="da7a1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="da7a1-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="da7a1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="da7a1-104">Product Name</span></span>   |                                                                                                                                                                                  <span data-ttu-id="da7a1-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="da7a1-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="da7a1-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="da7a1-106">Product Version</span></span> |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    <span data-ttu-id="da7a1-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="da7a1-107">Event ID</span></span>     |                                                                                                                                                                                            <span data-ttu-id="da7a1-108">10671</span><span class="sxs-lookup"><span data-stu-id="da7a1-108">10671</span></span>                                                                                                                                                                                            |
|  <span data-ttu-id="da7a1-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="da7a1-109">Event Source</span></span>   |                                                                                                                                                                                           <span data-ttu-id="da7a1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="da7a1-110">ENTSSO</span></span>                                                                                                                                                                                            |
|    <span data-ttu-id="da7a1-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="da7a1-111">Component</span></span>    |                                                                                                                                                                                             <span data-ttu-id="da7a1-112">N\A</span><span class="sxs-lookup"><span data-stu-id="da7a1-112">N\A</span></span>                                                                                                                                                                                             |
|  <span data-ttu-id="da7a1-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="da7a1-113">Symbolic Name</span></span>  |                                                                                                                                                                         <span data-ttu-id="da7a1-114">SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="da7a1-114">SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="da7a1-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="da7a1-115">Message Text</span></span>   | <span data-ttu-id="da7a1-116">Windows パスワードを変更すると、同じ外部システムの複数のアカウントも変更されます。%r</span><span class="sxs-lookup"><span data-stu-id="da7a1-116">A Windows password change will cause changes to more than one account on the same external system.%r</span></span><br /><br /> <span data-ttu-id="da7a1-117">この外部システムのアダプターは、マッピングの競合を許可するように構成されているため、これは許可されます。%r</span><span class="sxs-lookup"><span data-stu-id="da7a1-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="da7a1-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="da7a1-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="da7a1-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="da7a1-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="da7a1-120">Windows アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="da7a1-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="da7a1-121">外部アカウント 1: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="da7a1-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="da7a1-122">外部アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="da7a1-122">External Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="da7a1-123">説明</span><span class="sxs-lookup"><span data-stu-id="da7a1-123">Explanation</span></span>  
 <span data-ttu-id="da7a1-124">この情報イベントは、Windows パスワードを変更すると、同じ外部システムの複数のアカウントも変更されることを示します。</span><span class="sxs-lookup"><span data-stu-id="da7a1-124">This Information event indicates that a Windows password change will cause changes to more than one account on the same external system.</span></span>  

## <a name="user-action"></a><span data-ttu-id="da7a1-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="da7a1-125">User Action</span></span>  

-   <span data-ttu-id="da7a1-126">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="da7a1-126">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="da7a1-127">詳細</span><span class="sxs-lookup"><span data-stu-id="da7a1-127">More info</span></span>

- <span data-ttu-id="da7a1-128">**パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="da7a1-128">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="da7a1-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="da7a1-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
