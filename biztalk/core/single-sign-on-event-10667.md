---
title: シングル サインオン:イベント 10667 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74bbe7e6-af21-434c-9a62-3c3b13ca3307
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5115d7d521a0e19d1b48f5c1bf1f9f1f5937e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397542"
---
# <a name="single-sign-on-event-10667"></a><span data-ttu-id="cfb64-102">シングル サインオン:イベント 10667</span><span class="sxs-lookup"><span data-stu-id="cfb64-102">Single Sign-On: Event 10667</span></span>
## <a name="details"></a><span data-ttu-id="cfb64-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cfb64-103">Details</span></span>  

|                 |                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cfb64-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cfb64-104">Product Name</span></span>   |                                                        <span data-ttu-id="cfb64-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="cfb64-105">Enterprise Single Sign-On</span></span>                                                        |
| <span data-ttu-id="cfb64-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cfb64-106">Product Version</span></span> |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    <span data-ttu-id="cfb64-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cfb64-107">Event ID</span></span>     |                                                                  <span data-ttu-id="cfb64-108">10667</span><span class="sxs-lookup"><span data-stu-id="cfb64-108">10667</span></span>                                                                  |
|  <span data-ttu-id="cfb64-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cfb64-109">Event Source</span></span>   |                                                                 <span data-ttu-id="cfb64-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cfb64-110">ENTSSO</span></span>                                                                  |
|    <span data-ttu-id="cfb64-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cfb64-111">Component</span></span>    |                                                                   <span data-ttu-id="cfb64-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="cfb64-112">N\A</span></span>                                                                   |
|  <span data-ttu-id="cfb64-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cfb64-113">Symbolic Name</span></span>  |                                          <span data-ttu-id="cfb64-114">SSO_INFO_SUPPRESSED_DUPLICATE_WINDOWS_PASSWORD_CHANGE</span><span class="sxs-lookup"><span data-stu-id="cfb64-114">SSO_INFO_SUPPRESSED_DUPLICATE_WINDOWS_PASSWORD_CHANGE</span></span>                                          |
|  <span data-ttu-id="cfb64-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cfb64-115">Message Text</span></span>   | <span data-ttu-id="cfb64-116">重複する Windows パスワード change.%r の抑制</span><span class="sxs-lookup"><span data-stu-id="cfb64-116">Suppressed duplicate Windows password change.%r</span></span><br /><br /> <span data-ttu-id="cfb64-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cfb64-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="cfb64-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="cfb64-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="cfb64-119">Windows アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="cfb64-119">Windows Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="cfb64-120">説明</span><span class="sxs-lookup"><span data-stu-id="cfb64-120">Explanation</span></span>  
 <span data-ttu-id="cfb64-121">この情報イベントは、SSO が重複している Windows パスワード変更を抑制することを示します。</span><span class="sxs-lookup"><span data-stu-id="cfb64-121">This Information event indicates that SSO has suppressed a duplicate Windows password change.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cfb64-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cfb64-122">User Action</span></span>  

-   <span data-ttu-id="cfb64-123">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cfb64-123">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="cfb64-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="cfb64-124">More info</span></span>

- [<span data-ttu-id="cfb64-125">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="cfb64-125">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="cfb64-126">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="cfb64-126">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
