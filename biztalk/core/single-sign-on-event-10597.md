---
title: シングル サインオン:イベント 10597 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c57db8f-f7e4-4745-89b6-3112a3b2e1be
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a65e16c4575b1eee29fd920ab55a3bf76bf87197
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397829"
---
# <a name="single-sign-on-event-10597"></a><span data-ttu-id="e9ad8-102">シングル サインオン:イベント 10597</span><span class="sxs-lookup"><span data-stu-id="e9ad8-102">Single Sign-On: Event 10597</span></span>
## <a name="details"></a><span data-ttu-id="e9ad8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e9ad8-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e9ad8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e9ad8-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="e9ad8-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="e9ad8-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="e9ad8-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e9ad8-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="e9ad8-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e9ad8-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="e9ad8-108">10597</span><span class="sxs-lookup"><span data-stu-id="e9ad8-108">10597</span></span>                                                                                             |
|  <span data-ttu-id="e9ad8-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e9ad8-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="e9ad8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e9ad8-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="e9ad8-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e9ad8-111">Component</span></span>    |                                                                                             <span data-ttu-id="e9ad8-112">なし</span><span class="sxs-lookup"><span data-stu-id="e9ad8-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="e9ad8-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e9ad8-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="e9ad8-114">SSO_WARN_CALLER_NOT_IN_NEW_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="e9ad8-114">SSO_WARN_CALLER_NOT_IN_NEW_SSO_ADMIN</span></span>                                                                             |
|  <span data-ttu-id="e9ad8-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e9ad8-115">Message Text</span></span>   | <span data-ttu-id="e9ad8-116">クライアント ユーザーは SSO 管理者アカウントの name.%r を変更するには、新しい SSO 管理者アカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9ad8-116">The client user must be a member of the new SSO Administrators account to change the SSO Administrators account name.%r</span></span><br /><br /> <span data-ttu-id="e9ad8-117">クライアント ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="e9ad8-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="e9ad8-118">新しい SSO 管理者: %2</span><span class="sxs-lookup"><span data-stu-id="e9ad8-118">New SSO Administrators: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e9ad8-119">説明</span><span class="sxs-lookup"><span data-stu-id="e9ad8-119">Explanation</span></span>  
 <span data-ttu-id="e9ad8-120">クライアント ユーザーは SSO 管理者アカウント名を変更するには、新しい SSO 管理者アカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9ad8-120">The client user must be a member of the new SSO Administrators account to change the SSO Administrators account name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9ad8-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e9ad8-121">User Action</span></span>  
 <span data-ttu-id="e9ad8-122">SSO 管理者アカウント名を変更するには、新しい SSO 管理者アカウントのメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="e9ad8-122">You must be a member of the new SSO Administrators account to change the SSO Administrators account name.</span></span>