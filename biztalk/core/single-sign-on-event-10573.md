---
title: シングル サインオン:イベント 10573 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de1ea4e3-5d5f-4d50-8f9a-eff270ac0edb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37199e0b619f6d9f9d5a37ef1a6b4eb53c6f5712
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398729"
---
# <a name="single-sign-on-event-10573"></a><span data-ttu-id="2d0a2-102">シングル サインオン:イベント 10573</span><span class="sxs-lookup"><span data-stu-id="2d0a2-102">Single Sign-On: Event 10573</span></span>
## <a name="details"></a><span data-ttu-id="2d0a2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2d0a2-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2d0a2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2d0a2-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="2d0a2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="2d0a2-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="2d0a2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2d0a2-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="2d0a2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d0a2-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="2d0a2-108">10573</span><span class="sxs-lookup"><span data-stu-id="2d0a2-108">10573</span></span>                                                                                             |
|  <span data-ttu-id="2d0a2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2d0a2-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="2d0a2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2d0a2-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="2d0a2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2d0a2-111">Component</span></span>    |                                                                                             <span data-ttu-id="2d0a2-112">なし</span><span class="sxs-lookup"><span data-stu-id="2d0a2-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="2d0a2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2d0a2-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="2d0a2-114">SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="2d0a2-114">SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP</span></span>                                                                             |
|  <span data-ttu-id="2d0a2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2d0a2-115">Message Text</span></span>   | <span data-ttu-id="2d0a2-116">SSO 関連管理者アカウントがグローバル情報 update.%r のため無効です。</span><span class="sxs-lookup"><span data-stu-id="2d0a2-116">The SSO Affiliate Administrators account is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="2d0a2-117">SSO 関連管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="2d0a2-117">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="2d0a2-118">無効なアカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="2d0a2-118">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="2d0a2-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="2d0a2-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2d0a2-120">説明</span><span class="sxs-lookup"><span data-stu-id="2d0a2-120">Explanation</span></span>  
 <span data-ttu-id="2d0a2-121">SSO 関連管理者アカウントがグローバル情報アダプターに対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="2d0a2-121">The SSO Affiliate Administrators account is not valid for global info update.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2d0a2-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2d0a2-122">User Action</span></span>  
 <span data-ttu-id="2d0a2-123">警告メッセージには、SSO 関連管理者アカウントおよび無効なアカウントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d0a2-123">The warning message contains information regarding the SSO Affiliate Administrators account and the invalid accounts.</span></span> <span data-ttu-id="2d0a2-124">この情報を確認、必要な修正、および更新プログラムをもう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="2d0a2-124">Review this information, make any necessary corrections, and try the update again.</span></span>