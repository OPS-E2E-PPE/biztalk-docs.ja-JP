---
title: シングル サインオン:イベント 11009 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5f06f8c-1614-4538-83e6-689657135776
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d53f665ae1f900506d1bfc71873a1c40311faea0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306627"
---
# <a name="single-sign-on-event-11009"></a><span data-ttu-id="4d311-102">シングル サインオン:イベント 11009</span><span class="sxs-lookup"><span data-stu-id="4d311-102">Single Sign-On: Event 11009</span></span>
## <a name="details"></a><span data-ttu-id="4d311-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4d311-103">Details</span></span>  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4d311-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4d311-104">Product Name</span></span>   |                                                                      <span data-ttu-id="4d311-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4d311-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="4d311-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4d311-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="4d311-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4d311-107">Event ID</span></span>     |                                                                                <span data-ttu-id="4d311-108">11009</span><span class="sxs-lookup"><span data-stu-id="4d311-108">11009</span></span>                                                                                |
|  <span data-ttu-id="4d311-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4d311-109">Event Source</span></span>   |                                                                               <span data-ttu-id="4d311-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4d311-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="4d311-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4d311-111">Component</span></span>    |                                                                                 <span data-ttu-id="4d311-112">なし</span><span class="sxs-lookup"><span data-stu-id="4d311-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="4d311-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4d311-113">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="4d311-114">SSO_WARN_NOT_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="4d311-114">SSO_WARN_NOT_SSO_ADMIN</span></span>                                                                        |
|  <span data-ttu-id="4d311-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4d311-115">Message Text</span></span>   | <span data-ttu-id="4d311-116">クライアント ユーザーは SSO 管理者 account.%r のメンバーではありません。</span><span class="sxs-lookup"><span data-stu-id="4d311-116">Client user is not a member of the SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="4d311-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4d311-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="4d311-118">クライアント ユーザー: %2\\% 3 %r</span><span class="sxs-lookup"><span data-stu-id="4d311-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="4d311-119">SSO 管理者: %4</span><span class="sxs-lookup"><span data-stu-id="4d311-119">SSO Administrators: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4d311-120">説明</span><span class="sxs-lookup"><span data-stu-id="4d311-120">Explanation</span></span>  
 <span data-ttu-id="4d311-121">クライアント ユーザーは SSO 管理者アカウントのメンバーではないです。</span><span class="sxs-lookup"><span data-stu-id="4d311-121">The client user is not a member of the SSO Administrators account.</span></span> <span data-ttu-id="4d311-122">この警告は、監査レベルが高に設定されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d311-122">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4d311-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4d311-123">User Action</span></span>  
 <span data-ttu-id="4d311-124">状況を解決するには、クライアントのユーザーに SSO 管理者アカウントのメンバーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d311-124">To remedy the situation, you must make the client user a member of the SSO Administrators account.</span></span> <span data-ttu-id="4d311-125">この警告を今後表示しないを停止するには、監査レベルを下げることです。</span><span class="sxs-lookup"><span data-stu-id="4d311-125">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>