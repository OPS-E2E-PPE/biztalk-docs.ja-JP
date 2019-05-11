---
title: シングル サインオン:イベント 10550 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73d63bc5-1e60-426c-a0d6-55c51dbb8d76
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77e5cbfe7e06973dfd96a78ce37072a7dd49c35c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243526"
---
# <a name="single-sign-on-event-10550"></a><span data-ttu-id="d5a32-102">シングル サインオン:イベント 10550</span><span class="sxs-lookup"><span data-stu-id="d5a32-102">Single Sign-On: Event 10550</span></span>
## <a name="details"></a><span data-ttu-id="d5a32-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d5a32-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d5a32-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d5a32-104">Product Name</span></span>   |                                                                                           <span data-ttu-id="d5a32-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d5a32-105">Enterprise Single Sign-On</span></span>                                                                                           |
| <span data-ttu-id="d5a32-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d5a32-106">Product Version</span></span> |                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                           |
|    <span data-ttu-id="d5a32-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d5a32-107">Event ID</span></span>     |                                                                                                     <span data-ttu-id="d5a32-108">10550</span><span class="sxs-lookup"><span data-stu-id="d5a32-108">10550</span></span>                                                                                                     |
|  <span data-ttu-id="d5a32-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d5a32-109">Event Source</span></span>   |                                                                                                    <span data-ttu-id="d5a32-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d5a32-110">ENTSSO</span></span>                                                                                                     |
|    <span data-ttu-id="d5a32-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d5a32-111">Component</span></span>    |                                                                                                      <span data-ttu-id="d5a32-112">なし</span><span class="sxs-lookup"><span data-stu-id="d5a32-112">N/A</span></span>                                                                                                      |
|  <span data-ttu-id="d5a32-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d5a32-113">Symbolic Name</span></span>  |                                                                                        <span data-ttu-id="d5a32-114">SSO_ERROR_SERVICE_NOT_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="d5a32-114">SSO_ERROR_SERVICE_NOT_SSO_ADMIN</span></span>                                                                                        |
|  <span data-ttu-id="d5a32-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d5a32-115">Message Text</span></span>   | <span data-ttu-id="d5a32-116">SSO サービスを実行するサービス アカウントが SSO 管理者アカウントのメンバーではないため、SSO サービスを開始できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="d5a32-116">The SSO service could not start because the service account it is running under is not a member of the SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="d5a32-117">SSO 管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="d5a32-117">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="d5a32-118">SSO サービス アカウント: %2</span><span class="sxs-lookup"><span data-stu-id="d5a32-118">SSO Service Account: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d5a32-119">説明</span><span class="sxs-lookup"><span data-stu-id="d5a32-119">Explanation</span></span>  
 <span data-ttu-id="d5a32-120">SSO サービスは、SSO 管理者アカウントのメンバーであるサービス アカウントで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5a32-120">The SSO service must be running under a service account that is a member of the SSO Administrators account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5a32-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d5a32-121">User Action</span></span>  
 <span data-ttu-id="d5a32-122">詳細については、次を参照してください。 [SSO 管理者の指定および関連管理者アカウントを表示する方法](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md)します。</span><span class="sxs-lookup"><span data-stu-id="d5a32-122">For more information, see [How to Specify SSO Administrators and Affiliate Administrators Accounts](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md).</span></span>