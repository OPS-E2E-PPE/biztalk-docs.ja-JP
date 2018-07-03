---
title: 'シングル サインオン: イベント 10715 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f63c98d2-988e-466f-be40-171b13a34732
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9bc461aa812c2c61844c11d54743335ac89321a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994859"
---
# <a name="single-sign-on-event-10715"></a><span data-ttu-id="0508b-102">シングル サインオン: イベント 10715</span><span class="sxs-lookup"><span data-stu-id="0508b-102">Single Sign-On: Event 10715</span></span>
## <a name="details"></a><span data-ttu-id="0508b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0508b-103">Details</span></span>  

|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0508b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0508b-104">Product Name</span></span>   |                                                                                            <span data-ttu-id="0508b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0508b-105">Enterprise Single Sign-On</span></span>                                                                                             |
| <span data-ttu-id="0508b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0508b-106">Product Version</span></span> |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                            |
|    <span data-ttu-id="0508b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0508b-107">Event ID</span></span>     |                                                                                                      <span data-ttu-id="0508b-108">10715</span><span class="sxs-lookup"><span data-stu-id="0508b-108">10715</span></span>                                                                                                       |
|  <span data-ttu-id="0508b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0508b-109">Event Source</span></span>   |                                                                                                      <span data-ttu-id="0508b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0508b-110">ENTSSO</span></span>                                                                                                      |
|    <span data-ttu-id="0508b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0508b-111">Component</span></span>    |                                                                                                       <span data-ttu-id="0508b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="0508b-112">N\A</span></span>                                                                                                        |
|  <span data-ttu-id="0508b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0508b-113">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="0508b-114">SSO_WARN_NO_CREATE_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="0508b-114">SSO_WARN_NO_CREATE_ADAPTER</span></span>                                                                                            |
|  <span data-ttu-id="0508b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0508b-115">Message Text</span></span>   | <span data-ttu-id="0508b-116">アダプターを作成するには、クライアント ユーザーは SSO 管理者アカウントのメンバーである必要があります。%r</span><span class="sxs-lookup"><span data-stu-id="0508b-116">The client user must be a member of the SSO Administrators account to create adapters.%r</span></span><br /><br /> <span data-ttu-id="0508b-117">クライアント ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="0508b-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="0508b-118">SSO 管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="0508b-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="0508b-119">アダプター: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="0508b-119">Adapter: %3%r</span></span><br /><br /> <span data-ttu-id="0508b-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="0508b-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="0508b-121">説明</span><span class="sxs-lookup"><span data-stu-id="0508b-121">Explanation</span></span>  
 <span data-ttu-id="0508b-122">この警告イベントは、アダプターを作成するにはクライアント ユーザーが SSO 管理者アカウントのメンバーである必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="0508b-122">This Warning event indicates that the client user must be a member of the SSO Administrators account to create adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="0508b-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0508b-123">User Action</span></span>  
 <span data-ttu-id="0508b-124">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="0508b-124">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="0508b-125">SSO 管理者グループに属しているアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="0508b-125">Logon with an account that belongs to the SSO Administrators group.</span></span>  

  <span data-ttu-id="0508b-126">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0508b-126">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="0508b-127">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="0508b-127">SSO User Groups</span></span>](../core/sso-user-groups.md)
