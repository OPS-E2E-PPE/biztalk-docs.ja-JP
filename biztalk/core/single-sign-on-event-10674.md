---
title: シングル サインオン:イベント 10674 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad0c0d9e-1e6d-4c3e-86e0-9e336a18f3d6
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f10f76d2d1be51271912b00110bb02f7009cfbc0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397486"
---
# <a name="single-sign-on-event-10674"></a><span data-ttu-id="ea124-102">シングル サインオン:イベント 10674</span><span class="sxs-lookup"><span data-stu-id="ea124-102">Single Sign-On: Event 10674</span></span>
## <a name="details"></a><span data-ttu-id="ea124-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ea124-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ea124-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ea124-104">Product Name</span></span>   |                                                                                                                                                                                  <span data-ttu-id="ea124-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ea124-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="ea124-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ea124-106">Product Version</span></span> |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    <span data-ttu-id="ea124-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ea124-107">Event ID</span></span>     |                                                                                                                                                                                            <span data-ttu-id="ea124-108">10674</span><span class="sxs-lookup"><span data-stu-id="ea124-108">10674</span></span>                                                                                                                                                                                            |
|  <span data-ttu-id="ea124-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ea124-109">Event Source</span></span>   |                                                                                                                                                                                           <span data-ttu-id="ea124-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ea124-110">ENTSSO</span></span>                                                                                                                                                                                            |
|    <span data-ttu-id="ea124-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ea124-111">Component</span></span>    |                                                                                                                                                                                             <span data-ttu-id="ea124-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="ea124-112">N\A</span></span>                                                                                                                                                                                             |
|  <span data-ttu-id="ea124-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ea124-113">Symbolic Name</span></span>  |                                                                                                                                                                        <span data-ttu-id="ea124-114">SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="ea124-114">SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED</span></span>                                                                                                                                                                        |
|  <span data-ttu-id="ea124-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ea124-115">Message Text</span></span>   | <span data-ttu-id="ea124-116">外部パスワードを変更する原因となる 1 つ以上の Windows account.%r への変更</span><span class="sxs-lookup"><span data-stu-id="ea124-116">An external password change would have caused changes to more than one Windows account.%r</span></span><br /><br /> <span data-ttu-id="ea124-117">この外部システムのアダプタがマッピング conflicts.%r を許可しないように構成されているため、これは、許可されていません</span><span class="sxs-lookup"><span data-stu-id="ea124-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="ea124-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ea124-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="ea124-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="ea124-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="ea124-120">外部アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="ea124-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="ea124-121">Windows アカウント 1: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="ea124-121">Windows Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="ea124-122">Windows アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="ea124-122">Windows Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="ea124-123">説明</span><span class="sxs-lookup"><span data-stu-id="ea124-123">Explanation</span></span>  
 <span data-ttu-id="ea124-124">この警告イベントは、1 つ以上の Windows アカウントに変更は、外部パスワード変更しようとしたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ea124-124">This Warning event indicates that an external password change would have caused changes to more than one Windows account.</span></span> <span data-ttu-id="ea124-125">アダプターの構成で許可されないため、この変更を実行できません。</span><span class="sxs-lookup"><span data-stu-id="ea124-125">This change was prevented because the adapter configuration would not allow it.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ea124-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ea124-126">User Action</span></span>  
 <span data-ttu-id="ea124-127">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ea124-127">To resolve this error, do the following:</span></span>  

-   <span data-ttu-id="ea124-128">マッピングの競合が予想され、許可される場合、は、SSO 管理ツールを使用して、構成する、**マッピングの競合を許可する**パスワード同期アダプターのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ea124-128">If mapping conflicts are expected and allowed, use the SSO Admin tools to configure the **Allow Mapping Conflicts** property for the Password Sync Adapter.</span></span>  

## <a name="more-info"></a><span data-ttu-id="ea124-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ea124-129">More info</span></span>

- <span data-ttu-id="ea124-130">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="ea124-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="ea124-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="ea124-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
