---
title: 'シングル サインオン: イベント 10672 |Microsoft Docs'
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
ms.openlocfilehash: 39a8dd5e65b513ceabf2c654dcb5cf083d6f1295
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000763"
---
# <a name="single-sign-on-event-10672"></a><span data-ttu-id="c8844-102">シングル サインオン: イベント 10672</span><span class="sxs-lookup"><span data-stu-id="c8844-102">Single Sign-On: Event 10672</span></span>
## <a name="details"></a><span data-ttu-id="c8844-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c8844-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c8844-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c8844-104">Product Name</span></span>   |                                                                                                                                                                                           <span data-ttu-id="c8844-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c8844-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                            |
| <span data-ttu-id="c8844-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c8844-106">Product Version</span></span> |                                                                                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                           |
|    <span data-ttu-id="c8844-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c8844-107">Event ID</span></span>     |                                                                                                                                                                                                     <span data-ttu-id="c8844-108">10672</span><span class="sxs-lookup"><span data-stu-id="c8844-108">10672</span></span>                                                                                                                                                                                                      |
|  <span data-ttu-id="c8844-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c8844-109">Event Source</span></span>   |                                                                                                                                                                                                     <span data-ttu-id="c8844-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c8844-110">ENTSSO</span></span>                                                                                                                                                                                                     |
|    <span data-ttu-id="c8844-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c8844-111">Component</span></span>    |                                                                                                                                                                                                      <span data-ttu-id="c8844-112">N\A</span><span class="sxs-lookup"><span data-stu-id="c8844-112">N\A</span></span>                                                                                                                                                                                                       |
|  <span data-ttu-id="c8844-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c8844-113">Symbolic Name</span></span>  |                                                                                                                                                                                 <span data-ttu-id="c8844-114">SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="c8844-114">SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span></span>                                                                                                                                                                                 |
|  <span data-ttu-id="c8844-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c8844-115">Message Text</span></span>   | <span data-ttu-id="c8844-116">同じ外部システムの複数のアカウントを変更するような Windows パスワードの変更が行われました。%r</span><span class="sxs-lookup"><span data-stu-id="c8844-116">A Windows password change would have caused changes to more than one account on the same external system.%r</span></span><br /><br /> <span data-ttu-id="c8844-117">この外部システムのアダプターは、マッピングの競合を許可しないよう構成されているため、実行できません。%r</span><span class="sxs-lookup"><span data-stu-id="c8844-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="c8844-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c8844-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c8844-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="c8844-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="c8844-120">Windows アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="c8844-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="c8844-121">外部アカウント 1: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="c8844-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="c8844-122">外部アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="c8844-122">External Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="c8844-123">説明</span><span class="sxs-lookup"><span data-stu-id="c8844-123">Explanation</span></span>  
 <span data-ttu-id="c8844-124">この警告イベントは、同じ外部システムの複数のアカウントを変更するような Windows パスワードの変更が行われたことを示します。%r</span><span class="sxs-lookup"><span data-stu-id="c8844-124">This Warning event indicates that a Windows password change would have caused changes to more than one account on the same external system.</span></span> <span data-ttu-id="c8844-125">アダプター構成で許可されないため、この変更を実行できません。</span><span class="sxs-lookup"><span data-stu-id="c8844-125">This change was prevented because the adapter configuration would not allow it.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c8844-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c8844-126">User Action</span></span>  

-   <span data-ttu-id="c8844-127">SSO 管理ツールを使用して、構成、**マッピングの競合を許可する**パスワード同期アダプターのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c8844-127">Use the SSO Admin tools to configure the **Allow Mapping Conflicts** property for the Password Sync Adapter.</span></span>  

## <a name="more-info"></a><span data-ttu-id="c8844-128">詳細</span><span class="sxs-lookup"><span data-stu-id="c8844-128">More info</span></span>

- <span data-ttu-id="c8844-129">**パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c8844-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="c8844-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="c8844-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
