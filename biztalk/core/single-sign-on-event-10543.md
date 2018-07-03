---
title: 'シングル サインオン: イベント 10543 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46b1ffda-a6c1-408c-acb4-074183d697bc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf5c026384bf463f6ee0a33045dd1e7b1fca4188
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998449"
---
# <a name="single-sign-on-event-10543"></a><span data-ttu-id="ffb09-102">シングル サインオン: イベント 10543</span><span class="sxs-lookup"><span data-stu-id="ffb09-102">Single Sign-On: Event 10543</span></span>
## <a name="details"></a><span data-ttu-id="ffb09-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ffb09-103">Details</span></span>  

|                 |                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ffb09-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ffb09-104">Product Name</span></span>   |                                                               <span data-ttu-id="ffb09-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ffb09-105">Enterprise Single Sign-On</span></span>                                                                |
| <span data-ttu-id="ffb09-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ffb09-106">Product Version</span></span> |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                               |
|    <span data-ttu-id="ffb09-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ffb09-107">Event ID</span></span>     |                                                                         <span data-ttu-id="ffb09-108">10543</span><span class="sxs-lookup"><span data-stu-id="ffb09-108">10543</span></span>                                                                          |
|  <span data-ttu-id="ffb09-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ffb09-109">Event Source</span></span>   |                                                                         <span data-ttu-id="ffb09-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ffb09-110">ENTSSO</span></span>                                                                         |
|    <span data-ttu-id="ffb09-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ffb09-111">Component</span></span>    |                                                                           <span data-ttu-id="ffb09-112">CO</span><span class="sxs-lookup"><span data-stu-id="ffb09-112">CO</span></span>                                                                           |
|  <span data-ttu-id="ffb09-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ffb09-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="ffb09-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="ffb09-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span></span>                                                           |
|  <span data-ttu-id="ffb09-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ffb09-115">Message Text</span></span>   | <span data-ttu-id="ffb09-116">チケットは検証が必要な状態で発行されました。</span><span class="sxs-lookup"><span data-stu-id="ffb09-116">The ticket was issued with validation required.</span></span> <span data-ttu-id="ffb09-117">検証を行わない場合、このアプリケーションと引き換えることはできません。%r</span><span class="sxs-lookup"><span data-stu-id="ffb09-117">It cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="ffb09-118">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="ffb09-118">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="ffb09-119">説明</span><span class="sxs-lookup"><span data-stu-id="ffb09-119">Explanation</span></span>  
 <span data-ttu-id="ffb09-120">この警告イベントは、アプリケーション チケットが検証が必要な状態で発行されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ffb09-120">This Warning event indicates that an application ticket was issued with validation required.</span></span> <span data-ttu-id="ffb09-121">チケットを引き換えるには、検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffb09-121">Tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="ffb09-122">チケットの検証は、関連アプリケーションごとに行われます。</span><span class="sxs-lookup"><span data-stu-id="ffb09-122">Validation of the ticket is on a per affiliate application basis.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ffb09-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ffb09-123">User Action</span></span>  
 <span data-ttu-id="ffb09-124">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="ffb09-124">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="ffb09-125">エンタープライズ シングル サインオンを使用している場合は、メッセージが信頼されているホストのみを介して送信されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffb09-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="ffb09-126">メッセージのデータ改ざんのリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="ffb09-126">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="ffb09-127">シナリオで許可される場合は、このアプリケーションに対して検証をオフにしてください。</span><span class="sxs-lookup"><span data-stu-id="ffb09-127">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="ffb09-128">検証は、システムまたは特定のアプリケーションのみに対してオフにできる管理オプションです。</span><span class="sxs-lookup"><span data-stu-id="ffb09-128">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="ffb09-129">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="ffb09-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="ffb09-130">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="ffb09-130">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="ffb09-131">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="ffb09-131">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="ffb09-132">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="ffb09-132">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
