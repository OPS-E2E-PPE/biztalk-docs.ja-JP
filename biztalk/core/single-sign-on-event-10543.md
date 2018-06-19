---
title: 'シングル サインオン: イベント 10543 |Microsoft ドキュメント'
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
ms.openlocfilehash: e9bf30640bf61f9c88de3fedbb5727be7a715aa8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270002"
---
# <a name="single-sign-on-event-10543"></a><span data-ttu-id="dad39-102">シングル サインオン: イベント 10543</span><span class="sxs-lookup"><span data-stu-id="dad39-102">Single Sign-On: Event 10543</span></span>
## <a name="details"></a><span data-ttu-id="dad39-103">詳細</span><span class="sxs-lookup"><span data-stu-id="dad39-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dad39-104">製品名</span><span class="sxs-lookup"><span data-stu-id="dad39-104">Product Name</span></span>|<span data-ttu-id="dad39-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="dad39-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="dad39-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="dad39-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="dad39-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="dad39-107">Event ID</span></span>|<span data-ttu-id="dad39-108">10543</span><span class="sxs-lookup"><span data-stu-id="dad39-108">10543</span></span>|  
|<span data-ttu-id="dad39-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="dad39-109">Event Source</span></span>|<span data-ttu-id="dad39-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="dad39-110">ENTSSO</span></span>|  
|<span data-ttu-id="dad39-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dad39-111">Component</span></span>|<span data-ttu-id="dad39-112">CO</span><span class="sxs-lookup"><span data-stu-id="dad39-112">CO</span></span>|  
|<span data-ttu-id="dad39-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="dad39-113">Symbolic Name</span></span>|<span data-ttu-id="dad39-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="dad39-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span></span>|  
|<span data-ttu-id="dad39-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="dad39-115">Message Text</span></span>|<span data-ttu-id="dad39-116">チケットは検証が必要な状態で発行されました。</span><span class="sxs-lookup"><span data-stu-id="dad39-116">The ticket was issued with validation required.</span></span> <span data-ttu-id="dad39-117">検証を行わない場合、このアプリケーションと引き換えることはできません。%r</span><span class="sxs-lookup"><span data-stu-id="dad39-117">It cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="dad39-118">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="dad39-118">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dad39-119">説明</span><span class="sxs-lookup"><span data-stu-id="dad39-119">Explanation</span></span>  
 <span data-ttu-id="dad39-120">この警告イベントは、アプリケーション チケットが検証が必要な状態で発行されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="dad39-120">This Warning event indicates that an application ticket was issued with validation required.</span></span> <span data-ttu-id="dad39-121">チケットを引き換えるには、検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad39-121">Tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="dad39-122">チケットの検証は、関連アプリケーションごとに行われます。</span><span class="sxs-lookup"><span data-stu-id="dad39-122">Validation of the ticket is on a per affiliate application basis.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dad39-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="dad39-123">User Action</span></span>  
 <span data-ttu-id="dad39-124">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="dad39-124">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="dad39-125">エンタープライズ シングル サインオンを使用している場合は、メッセージが信頼されているホストのみを介して送信されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dad39-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="dad39-126">メッセージのデータ改ざんのリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="dad39-126">This will reduce the risk of tampering with the data in the message.</span></span>  
  
-   <span data-ttu-id="dad39-127">シナリオで許可される場合は、このアプリケーションに対して検証をオフにしてください。</span><span class="sxs-lookup"><span data-stu-id="dad39-127">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="dad39-128">検証は、システムまたは特定のアプリケーションのみに対してオフにできる管理オプションです。</span><span class="sxs-lookup"><span data-stu-id="dad39-128">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  
  
 <span data-ttu-id="dad39-129">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="dad39-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="dad39-130">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="dad39-130">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="dad39-131">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="dad39-131">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [<span data-ttu-id="dad39-132">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="dad39-132">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)