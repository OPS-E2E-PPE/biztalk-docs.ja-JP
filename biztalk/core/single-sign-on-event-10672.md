---
title: シングル サインオン:イベント 10672 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2422c7d-51bc-4f12-8830-193d71d2bce9
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 443c0bce458775f73c397cb0f1b1038665f328ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397504"
---
# <a name="single-sign-on-event-10672"></a><span data-ttu-id="85797-102">シングル サインオン:イベント 10672</span><span class="sxs-lookup"><span data-stu-id="85797-102">Single Sign-On: Event 10672</span></span>
## <a name="details"></a><span data-ttu-id="85797-103">詳細</span><span class="sxs-lookup"><span data-stu-id="85797-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="85797-104">製品名</span><span class="sxs-lookup"><span data-stu-id="85797-104">Product Name</span></span>   |                                                                                                                                                                                           <span data-ttu-id="85797-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="85797-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                            |
| <span data-ttu-id="85797-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="85797-106">Product Version</span></span> |                                                                                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                           |
|    <span data-ttu-id="85797-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="85797-107">Event ID</span></span>     |                                                                                                                                                                                                     <span data-ttu-id="85797-108">10672</span><span class="sxs-lookup"><span data-stu-id="85797-108">10672</span></span>                                                                                                                                                                                                      |
|  <span data-ttu-id="85797-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="85797-109">Event Source</span></span>   |                                                                                                                                                                                                     <span data-ttu-id="85797-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="85797-110">ENTSSO</span></span>                                                                                                                                                                                                     |
|    <span data-ttu-id="85797-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="85797-111">Component</span></span>    |                                                                                                                                                                                                      <span data-ttu-id="85797-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="85797-112">N\A</span></span>                                                                                                                                                                                                       |
|  <span data-ttu-id="85797-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="85797-113">Symbolic Name</span></span>  |                                                                                                                                                                                 <span data-ttu-id="85797-114">SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="85797-114">SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span></span>                                                                                                                                                                                 |
|  <span data-ttu-id="85797-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="85797-115">Message Text</span></span>   | <span data-ttu-id="85797-116">Windows パスワード変更原因となる 1 つ以上のアカウントへの変更に同じ外部 system.%r</span><span class="sxs-lookup"><span data-stu-id="85797-116">A Windows password change would have caused changes to more than one account on the same external system.%r</span></span><br /><br /> <span data-ttu-id="85797-117">この外部システムのアダプタがマッピング conflicts.%r を許可しないように構成されているため、これは、許可されていません</span><span class="sxs-lookup"><span data-stu-id="85797-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="85797-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="85797-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="85797-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="85797-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="85797-120">Windows アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="85797-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="85797-121">外部アカウント 1: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="85797-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="85797-122">外部アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="85797-122">External Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="85797-123">説明</span><span class="sxs-lookup"><span data-stu-id="85797-123">Explanation</span></span>  
 <span data-ttu-id="85797-124">この警告イベントは、こと、Windows パスワード変更原因となる 1 つ以上のアカウントへの変更、同じ外部システムのことを示します。</span><span class="sxs-lookup"><span data-stu-id="85797-124">This Warning event indicates that a Windows password change would have caused changes to more than one account on the same external system.</span></span> <span data-ttu-id="85797-125">アダプターの構成で許可されないため、この変更を実行できません。</span><span class="sxs-lookup"><span data-stu-id="85797-125">This change was prevented because the adapter configuration would not allow it.</span></span>  

## <a name="user-action"></a><span data-ttu-id="85797-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="85797-126">User Action</span></span>  

-   <span data-ttu-id="85797-127">SSO 管理ツールを使用して、構成、**マッピングの競合を許可する**パスワード同期アダプターのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="85797-127">Use the SSO Admin tools to configure the **Allow Mapping Conflicts** property for the Password Sync Adapter.</span></span>  

## <a name="more-info"></a><span data-ttu-id="85797-128">詳細情報</span><span class="sxs-lookup"><span data-stu-id="85797-128">More info</span></span>

- <span data-ttu-id="85797-129">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="85797-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="85797-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="85797-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
