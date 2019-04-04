---
title: 'シングル サインオン: イベント 10550 |Microsoft Docs'
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
ms.openlocfilehash: 987e01d741ef49245c931f828f6cebeb3bf52cd2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021960"
---
# <a name="single-sign-on-event-10550"></a><span data-ttu-id="f9dea-102">シングル サインオン: イベント 10550</span><span class="sxs-lookup"><span data-stu-id="f9dea-102">Single Sign-On: Event 10550</span></span>
## <a name="details"></a><span data-ttu-id="f9dea-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f9dea-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f9dea-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f9dea-104">Product Name</span></span>   |                                                                                           <span data-ttu-id="f9dea-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f9dea-105">Enterprise Single Sign-On</span></span>                                                                                           |
| <span data-ttu-id="f9dea-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f9dea-106">Product Version</span></span> |                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                           |
|    <span data-ttu-id="f9dea-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f9dea-107">Event ID</span></span>     |                                                                                                     <span data-ttu-id="f9dea-108">10550</span><span class="sxs-lookup"><span data-stu-id="f9dea-108">10550</span></span>                                                                                                     |
|  <span data-ttu-id="f9dea-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f9dea-109">Event Source</span></span>   |                                                                                                    <span data-ttu-id="f9dea-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f9dea-110">ENTSSO</span></span>                                                                                                     |
|    <span data-ttu-id="f9dea-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f9dea-111">Component</span></span>    |                                                                                                      <span data-ttu-id="f9dea-112">なし</span><span class="sxs-lookup"><span data-stu-id="f9dea-112">N/A</span></span>                                                                                                      |
|  <span data-ttu-id="f9dea-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f9dea-113">Symbolic Name</span></span>  |                                                                                        <span data-ttu-id="f9dea-114">SSO_ERROR_SERVICE_NOT_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="f9dea-114">SSO_ERROR_SERVICE_NOT_SSO_ADMIN</span></span>                                                                                        |
|  <span data-ttu-id="f9dea-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f9dea-115">Message Text</span></span>   | <span data-ttu-id="f9dea-116">SSO サービスを実行するサービス アカウントが SSO 管理者アカウントのメンバーではないため、SSO サービスを開始できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="f9dea-116">The SSO service could not start because the service account it is running under is not a member of the SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="f9dea-117">SSO 管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="f9dea-117">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="f9dea-118">SSO サービス アカウント: %2</span><span class="sxs-lookup"><span data-stu-id="f9dea-118">SSO Service Account: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f9dea-119">説明</span><span class="sxs-lookup"><span data-stu-id="f9dea-119">Explanation</span></span>  
 <span data-ttu-id="f9dea-120">SSO サービスは、SSO 管理者アカウントのメンバーであるサービス アカウントで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9dea-120">The SSO service must be running under a service account that is a member of the SSO Administrators account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f9dea-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f9dea-121">User Action</span></span>  
 <span data-ttu-id="f9dea-122">詳細については、[SSO 管理者の指定および関連管理者アカウントを表示する方法](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9dea-122">For more information, see [How to Specify SSO Administrators and Affiliate Administrators Accounts](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md).</span></span>