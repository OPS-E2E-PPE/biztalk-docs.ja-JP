---
title: シングル サインオン:イベント 10574 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f2a5aa-3a19-4d7c-9257-89f1567a3c2d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae5f0ecae1e9c3016817d1627ad0bfba75ef7ba4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398720"
---
# <a name="single-sign-on-event-10574"></a><span data-ttu-id="91cab-102">シングル サインオン:イベント 10574</span><span class="sxs-lookup"><span data-stu-id="91cab-102">Single Sign-On: Event 10574</span></span>
## <a name="details"></a><span data-ttu-id="91cab-103">詳細</span><span class="sxs-lookup"><span data-stu-id="91cab-103">Details</span></span>  
  
|                 |                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="91cab-104">製品名</span><span class="sxs-lookup"><span data-stu-id="91cab-104">Product Name</span></span>   |                                                                        <span data-ttu-id="91cab-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="91cab-105">Enterprise Single Sign-On</span></span>                                                                         |
| <span data-ttu-id="91cab-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="91cab-106">Product Version</span></span> |                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                        |
|    <span data-ttu-id="91cab-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="91cab-107">Event ID</span></span>     |                                                                                  <span data-ttu-id="91cab-108">10574</span><span class="sxs-lookup"><span data-stu-id="91cab-108">10574</span></span>                                                                                   |
|  <span data-ttu-id="91cab-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="91cab-109">Event Source</span></span>   |                                                                                  <span data-ttu-id="91cab-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="91cab-110">ENTSSO</span></span>                                                                                  |
|    <span data-ttu-id="91cab-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="91cab-111">Component</span></span>    |                                                                                   <span data-ttu-id="91cab-112">なし</span><span class="sxs-lookup"><span data-stu-id="91cab-112">N/A</span></span>                                                                                    |
|  <span data-ttu-id="91cab-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="91cab-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="91cab-114">SSO_WARN_INVALID_SSO_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="91cab-114">SSO_WARN_INVALID_SSO_ADMIN_GROUP</span></span>                                                                     |
|  <span data-ttu-id="91cab-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="91cab-115">Message Text</span></span>   | <span data-ttu-id="91cab-116">SSO 管理者アカウントがグローバル情報 update.%r のため無効です。</span><span class="sxs-lookup"><span data-stu-id="91cab-116">The SSO Administrators account is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="91cab-117">SSO 管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="91cab-117">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="91cab-118">無効なアカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="91cab-118">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="91cab-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="91cab-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="91cab-120">説明</span><span class="sxs-lookup"><span data-stu-id="91cab-120">Explanation</span></span>  
 <span data-ttu-id="91cab-121">グローバル情報アダプターに対して、SSO 管理者アカウントが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="91cab-121">The SSO Administrators account is not valid for global info update.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="91cab-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="91cab-122">User Action</span></span>  
 <span data-ttu-id="91cab-123">警告メッセージには、SSO 管理者アカウントおよび無効なアカウントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="91cab-123">The warning message contains information regarding the SSO Administrators account and the invalid accounts.</span></span> <span data-ttu-id="91cab-124">この情報を確認、必要な修正、および更新プログラムをもう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="91cab-124">Review this information, make any necessary corrections, and try the update again.</span></span>