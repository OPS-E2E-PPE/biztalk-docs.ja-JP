---
title: シングル サインオン:イベント 10545 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 268cb7be-b191-4335-a4cc-7c15d879507c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6695a46f2116045e5aec58514ac110c6a2948f66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243488"
---
# <a name="single-sign-on-event-10545"></a><span data-ttu-id="5d86e-102">シングル サインオン:イベント 10545</span><span class="sxs-lookup"><span data-stu-id="5d86e-102">Single Sign-On: Event 10545</span></span>
## <a name="details"></a><span data-ttu-id="5d86e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5d86e-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="5d86e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5d86e-104">Product Name</span></span>   |                 <span data-ttu-id="5d86e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5d86e-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="5d86e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5d86e-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="5d86e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5d86e-107">Event ID</span></span>     |                           <span data-ttu-id="5d86e-108">10545</span><span class="sxs-lookup"><span data-stu-id="5d86e-108">10545</span></span>                            |
|  <span data-ttu-id="5d86e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5d86e-109">Event Source</span></span>   |                           <span data-ttu-id="5d86e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5d86e-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="5d86e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5d86e-111">Component</span></span>    |                             <span data-ttu-id="5d86e-112">CO</span><span class="sxs-lookup"><span data-stu-id="5d86e-112">CO</span></span>                             |
|  <span data-ttu-id="5d86e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5d86e-113">Symbolic Name</span></span>  |             <span data-ttu-id="5d86e-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="5d86e-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span></span>             |
|  <span data-ttu-id="5d86e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5d86e-115">Message Text</span></span>   |        <span data-ttu-id="5d86e-116">SSO システムに対しては、チケットが有効にできません。</span><span class="sxs-lookup"><span data-stu-id="5d86e-116">Tickets are not enabled for the SSO system.</span></span>         |

## <a name="explanation"></a><span data-ttu-id="5d86e-117">説明</span><span class="sxs-lookup"><span data-stu-id="5d86e-117">Explanation</span></span>  
 <span data-ttu-id="5d86e-118">この警告イベントは、SSO システムに対してチケットが有効ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="5d86e-118">This Warning event indicates that tickets are not enabled for the SSO System.</span></span> <span data-ttu-id="5d86e-119">システム レベルでチケットが無効になっている場合は、チケット発行使用できません関連アプリケーション レベルか。</span><span class="sxs-lookup"><span data-stu-id="5d86e-119">If ticketing is disabled at the system level, ticketing cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="5d86e-120">システム レベルでチケットを有効にして、関連アプリケーション レベルで無効にすることになります。</span><span class="sxs-lookup"><span data-stu-id="5d86e-120">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5d86e-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5d86e-121">User Action</span></span>  
 <span data-ttu-id="5d86e-122">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5d86e-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="5d86e-123">SSO システム レベルでチケットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5d86e-123">Enable tickets at the SSO System level.</span></span>  

  <span data-ttu-id="5d86e-124">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="5d86e-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="5d86e-125">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="5d86e-125">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="5d86e-126">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="5d86e-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)
