---
title: シングル サインオン:イベント 10673 |Microsoft Docs
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
ms.openlocfilehash: 7d6481684fdb53aed156703a52e472c3fe1f06d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397496"
---
# <a name="single-sign-on-event-10673"></a><span data-ttu-id="a3ad4-102">シングル サインオン:イベント 10673</span><span class="sxs-lookup"><span data-stu-id="a3ad4-102">Single Sign-On: Event 10673</span></span>
## <a name="details"></a><span data-ttu-id="a3ad4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a3ad4-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a3ad4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a3ad4-104">Product Name</span></span>   |                                                                                                                                                                        <span data-ttu-id="a3ad4-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a3ad4-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                         |
| <span data-ttu-id="a3ad4-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a3ad4-106">Product Version</span></span> |                                                                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                        |
|    <span data-ttu-id="a3ad4-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a3ad4-107">Event ID</span></span>     |                                                                                                                                                                                  <span data-ttu-id="a3ad4-108">10673</span><span class="sxs-lookup"><span data-stu-id="a3ad4-108">10673</span></span>                                                                                                                                                                                   |
|  <span data-ttu-id="a3ad4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a3ad4-109">Event Source</span></span>   |                                                                                                                                                                                  <span data-ttu-id="a3ad4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a3ad4-110">ENTSSO</span></span>                                                                                                                                                                                  |
|    <span data-ttu-id="a3ad4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a3ad4-111">Component</span></span>    |                                                                                                                                                                                   <span data-ttu-id="a3ad4-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="a3ad4-112">N\A</span></span>                                                                                                                                                                                    |
|  <span data-ttu-id="a3ad4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a3ad4-113">Symbolic Name</span></span>  |                                                                                                                                                                <span data-ttu-id="a3ad4-114">SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="a3ad4-114">SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span></span>                                                                                                                                                                 |
|  <span data-ttu-id="a3ad4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a3ad4-115">Message Text</span></span>   | <span data-ttu-id="a3ad4-116">外部パスワード変更が発生する 1 つ以上の Windows account.%r への変更</span><span class="sxs-lookup"><span data-stu-id="a3ad4-116">An external password change will cause changes to more than one Windows account.%r</span></span><br /><br /> <span data-ttu-id="a3ad4-117">この外部システムのアダプタで構成されているマッピング conflicts.%r を許可するため、これは許可します。</span><span class="sxs-lookup"><span data-stu-id="a3ad4-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="a3ad4-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a3ad4-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a3ad4-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="a3ad4-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="a3ad4-120">外部アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="a3ad4-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="a3ad4-121">Windows アカウント 1: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="a3ad4-121">Windows Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="a3ad4-122">Windows アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="a3ad4-122">Windows Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="a3ad4-123">説明</span><span class="sxs-lookup"><span data-stu-id="a3ad4-123">Explanation</span></span>  
 <span data-ttu-id="a3ad4-124">この情報イベントは、外部パスワード変更は 1 つ以上の Windows アカウントへの変更が発生することを示します。</span><span class="sxs-lookup"><span data-stu-id="a3ad4-124">This Information event indicates that an external password change will cause changes to more than one Windows account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a3ad4-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a3ad4-125">User Action</span></span>  

-   <span data-ttu-id="a3ad4-126">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a3ad4-126">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="a3ad4-127">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a3ad4-127">More info</span></span>

- [<span data-ttu-id="a3ad4-128">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="a3ad4-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="a3ad4-129">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a3ad4-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="a3ad4-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="a3ad4-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
