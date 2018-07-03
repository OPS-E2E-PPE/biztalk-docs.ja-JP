---
title: 'シングル サインオン: イベント 10679 |Microsoft Docs'
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
ms.openlocfilehash: dbeb91e58582fcd37fca4c791b35a9edfc558c96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000355"
---
# <a name="single-sign-on-event-10679"></a><span data-ttu-id="fffab-102">シングル サインオン: イベント 10679</span><span class="sxs-lookup"><span data-stu-id="fffab-102">Single Sign-On: Event 10679</span></span>
## <a name="details"></a><span data-ttu-id="fffab-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fffab-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fffab-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fffab-104">Product Name</span></span>   |                                                                                                           <span data-ttu-id="fffab-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="fffab-105">Enterprise Single Sign-On</span></span>                                                                                                            |
| <span data-ttu-id="fffab-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fffab-106">Product Version</span></span> |                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                           |
|    <span data-ttu-id="fffab-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fffab-107">Event ID</span></span>     |                                                                                                                     <span data-ttu-id="fffab-108">10679</span><span class="sxs-lookup"><span data-stu-id="fffab-108">10679</span></span>                                                                                                                      |
|  <span data-ttu-id="fffab-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fffab-109">Event Source</span></span>   |                                                                                                                     <span data-ttu-id="fffab-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fffab-110">ENTSSO</span></span>                                                                                                                     |
|    <span data-ttu-id="fffab-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fffab-111">Component</span></span>    |                                                                                                                      <span data-ttu-id="fffab-112">N\A</span><span class="sxs-lookup"><span data-stu-id="fffab-112">N\A</span></span>                                                                                                                       |
|  <span data-ttu-id="fffab-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fffab-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="fffab-114">SSO_WARN_PS_MAPPING_DISABLED</span><span class="sxs-lookup"><span data-stu-id="fffab-114">SSO_WARN_PS_MAPPING_DISABLED</span></span>                                                                                                          |
|  <span data-ttu-id="fffab-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fffab-115">Message Text</span></span>   | <span data-ttu-id="fffab-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="fffab-116">External password change.</span></span> <span data-ttu-id="fffab-117">マッピングが無効になっているため、外部アカウントのパスワードは変更されませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="fffab-117">The password was not changed for the external account because the mapping is disabled.%r</span></span><br /><br /> <span data-ttu-id="fffab-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fffab-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="fffab-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="fffab-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="fffab-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="fffab-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="fffab-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="fffab-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="fffab-122">説明</span><span class="sxs-lookup"><span data-stu-id="fffab-122">Explanation</span></span>  
 <span data-ttu-id="fffab-123">この警告イベントは、マッピングが無効になっているため、外部アカウントのパスワードが変更されなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="fffab-123">This Warning event indicates that the password was not changed for the external account because the mapping is disabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fffab-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fffab-124">User Action</span></span>  
 <span data-ttu-id="fffab-125">この警告を解消するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fffab-125">To resolve this warning do the following:</span></span>  

-   <span data-ttu-id="fffab-126">SSO 管理ツールを使用して、このアダプターのマッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fffab-126">Use the SSO administration tools to enable mapping for this adapter.</span></span>  

## <a name="more-info"></a><span data-ttu-id="fffab-127">詳細</span><span class="sxs-lookup"><span data-stu-id="fffab-127">More info</span></span>

- [<span data-ttu-id="fffab-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="fffab-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="fffab-129">**パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="fffab-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
