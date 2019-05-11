---
title: シングル サインオン:イベント 10539 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a67f5719-da7c-4ae0-a6fe-ff7b653a184d
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbae36ca6e261fab1b7ae4e691f64da2bf9ba718
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392915"
---
# <a name="single-sign-on-event-10539"></a><span data-ttu-id="c2010-102">シングル サインオン:イベント 10539</span><span class="sxs-lookup"><span data-stu-id="c2010-102">Single Sign-On: Event 10539</span></span>
## <a name="details"></a><span data-ttu-id="c2010-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c2010-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="c2010-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c2010-104">Product Name</span></span>   |                 <span data-ttu-id="c2010-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c2010-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="c2010-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c2010-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="c2010-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c2010-107">Event ID</span></span>     |                           <span data-ttu-id="c2010-108">10539</span><span class="sxs-lookup"><span data-stu-id="c2010-108">10539</span></span>                            |
|  <span data-ttu-id="c2010-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c2010-109">Event Source</span></span>   |                           <span data-ttu-id="c2010-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c2010-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="c2010-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c2010-111">Component</span></span>    |                             <span data-ttu-id="c2010-112">CO</span><span class="sxs-lookup"><span data-stu-id="c2010-112">CO</span></span>                             |
|  <span data-ttu-id="c2010-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c2010-113">Symbolic Name</span></span>  |              <span data-ttu-id="c2010-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="c2010-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span></span>              |
|  <span data-ttu-id="c2010-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c2010-115">Message Text</span></span>   |        <span data-ttu-id="c2010-116">SSO システムに対しては、チケットが有効にできません。</span><span class="sxs-lookup"><span data-stu-id="c2010-116">Tickets are not enabled for the SSO system.</span></span>         |

## <a name="explanation"></a><span data-ttu-id="c2010-117">説明</span><span class="sxs-lookup"><span data-stu-id="c2010-117">Explanation</span></span>  
 <span data-ttu-id="c2010-118">この警告イベントは、SSO チケットの使用が有効でないことを示します。</span><span class="sxs-lookup"><span data-stu-id="c2010-118">This Warning event indicates that the use of SSO tickets is not enabled.</span></span> <span data-ttu-id="c2010-119">SSO の使用を許可するチケットは、SSO システムの省略可能な機能です。</span><span class="sxs-lookup"><span data-stu-id="c2010-119">Allowing the use of SSO tickets is an optional feature of the SSO system.</span></span> <span data-ttu-id="c2010-120">この機能は、SSO システムで有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="c2010-120">This feature has not been enabled on your SSO system.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c2010-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c2010-121">User Action</span></span>  
 <span data-ttu-id="c2010-122">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c2010-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="c2010-123">SSO システムに対してチケットを有効にする、SSO 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c2010-123">Contact your SSO Administrator to enable tickets for the SSO system.</span></span> <span data-ttu-id="c2010-124">これ行う SSO 管理ツール (GUI またはコマンドライン) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2010-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="c2010-125">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="c2010-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="c2010-126">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c2010-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  

- [<span data-ttu-id="c2010-127">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="c2010-127">Using SSO</span></span>](../core/using-sso.md)
