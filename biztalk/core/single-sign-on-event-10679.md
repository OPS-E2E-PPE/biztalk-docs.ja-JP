---
title: シングル サインオン:イベント 10679 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645f2b74-2cbe-4c6a-b0f5-7e31f93f88c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f3b551d0c5eecab6ad84b54303bd2c25bbf46eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397438"
---
# <a name="single-sign-on-event-10679"></a><span data-ttu-id="a9f28-102">シングル サインオン:イベント 10679</span><span class="sxs-lookup"><span data-stu-id="a9f28-102">Single Sign-On: Event 10679</span></span>
## <a name="details"></a><span data-ttu-id="a9f28-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a9f28-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a9f28-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a9f28-104">Product Name</span></span>   |                                                                                                           <span data-ttu-id="a9f28-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a9f28-105">Enterprise Single Sign-On</span></span>                                                                                                            |
| <span data-ttu-id="a9f28-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a9f28-106">Product Version</span></span> |                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                           |
|    <span data-ttu-id="a9f28-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a9f28-107">Event ID</span></span>     |                                                                                                                     <span data-ttu-id="a9f28-108">10679</span><span class="sxs-lookup"><span data-stu-id="a9f28-108">10679</span></span>                                                                                                                      |
|  <span data-ttu-id="a9f28-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a9f28-109">Event Source</span></span>   |                                                                                                                     <span data-ttu-id="a9f28-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a9f28-110">ENTSSO</span></span>                                                                                                                     |
|    <span data-ttu-id="a9f28-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a9f28-111">Component</span></span>    |                                                                                                                      <span data-ttu-id="a9f28-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="a9f28-112">N\A</span></span>                                                                                                                       |
|  <span data-ttu-id="a9f28-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a9f28-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="a9f28-114">SSO_WARN_PS_MAPPING_DISABLED</span><span class="sxs-lookup"><span data-stu-id="a9f28-114">SSO_WARN_PS_MAPPING_DISABLED</span></span>                                                                                                          |
|  <span data-ttu-id="a9f28-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a9f28-115">Message Text</span></span>   | <span data-ttu-id="a9f28-116">外部パスワード変更。</span><span class="sxs-lookup"><span data-stu-id="a9f28-116">External password change.</span></span> <span data-ttu-id="a9f28-117">マッピングは disabled.%r のため、外部アカウントのパスワードが変更されませんでした。</span><span class="sxs-lookup"><span data-stu-id="a9f28-117">The password was not changed for the external account because the mapping is disabled.%r</span></span><br /><br /> <span data-ttu-id="a9f28-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a9f28-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a9f28-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="a9f28-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="a9f28-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="a9f28-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="a9f28-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="a9f28-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="a9f28-122">説明</span><span class="sxs-lookup"><span data-stu-id="a9f28-122">Explanation</span></span>  
 <span data-ttu-id="a9f28-123">この警告イベントは、パスワードが変更されていないこと、外部アカウントのマッピングが無効になっているため、ことを示します。</span><span class="sxs-lookup"><span data-stu-id="a9f28-123">This Warning event indicates that the password was not changed for the external account because the mapping is disabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a9f28-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a9f28-124">User Action</span></span>  
 <span data-ttu-id="a9f28-125">この警告は、次を解決するには。</span><span class="sxs-lookup"><span data-stu-id="a9f28-125">To resolve this warning do the following:</span></span>  

-   <span data-ttu-id="a9f28-126">このアダプターのマッピングを有効にするのにには、SSO 管理ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9f28-126">Use the SSO administration tools to enable mapping for this adapter.</span></span>  

## <a name="more-info"></a><span data-ttu-id="a9f28-127">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a9f28-127">More info</span></span>

- [<span data-ttu-id="a9f28-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="a9f28-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="a9f28-129">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a9f28-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
