---
title: 'シングル サインオン: イベント 10542 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e12444-b47c-4919-85b6-85c8e33b8342
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ebcf97a9de014d0651c9f239c1ae6e846925f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271178"
---
# <a name="single-sign-on-event-10542"></a><span data-ttu-id="44896-102">シングル サインオン: イベント 10542</span><span class="sxs-lookup"><span data-stu-id="44896-102">Single Sign-On: Event 10542</span></span>
## <a name="details"></a><span data-ttu-id="44896-103">詳細</span><span class="sxs-lookup"><span data-stu-id="44896-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44896-104">製品名</span><span class="sxs-lookup"><span data-stu-id="44896-104">Product Name</span></span>|<span data-ttu-id="44896-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="44896-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="44896-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="44896-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="44896-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="44896-107">Event ID</span></span>|<span data-ttu-id="44896-108">10542</span><span class="sxs-lookup"><span data-stu-id="44896-108">10542</span></span>|  
|<span data-ttu-id="44896-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="44896-109">Event Source</span></span>|<span data-ttu-id="44896-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="44896-110">ENTSSO</span></span>|  
|<span data-ttu-id="44896-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="44896-111">Component</span></span>|<span data-ttu-id="44896-112">CO</span><span class="sxs-lookup"><span data-stu-id="44896-112">CO</span></span>|  
|<span data-ttu-id="44896-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="44896-113">Symbolic Name</span></span>|<span data-ttu-id="44896-114">SSO_WARN_APP_TICKETS_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="44896-114">SSO_WARN_APP_TICKETS_VALIDATED</span></span>|  
|<span data-ttu-id="44896-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="44896-115">Message Text</span></span>|<span data-ttu-id="44896-116">チケットの検証を行わない場合、このアプリケーションと引き換えることはできません。%r</span><span class="sxs-lookup"><span data-stu-id="44896-116">Tickets cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="44896-117">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="44896-117">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="44896-118">説明</span><span class="sxs-lookup"><span data-stu-id="44896-118">Explanation</span></span>  
 <span data-ttu-id="44896-119">この警告イベントは、アプリケーション チケットを検証しないと引き換えできないことを示します。</span><span class="sxs-lookup"><span data-stu-id="44896-119">This Warning event indicates that application tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="44896-120">アプリケーション チケットを引き換えるときは、検証を受けることも、受けないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="44896-120">When application tickets are redeemed they can be validated or not validated.</span></span> <span data-ttu-id="44896-121">検証により、チケットを発行したユーザーの名前と BizTalk メッセージ内のユーザーの名前を比較することで、セキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="44896-121">Validation improves security by comparing the name of the user who issued the ticket with the name of the user in the BizTalk message.</span></span> <span data-ttu-id="44896-122">名前が一致しないと、検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="44896-122">If the names are not the same then validation fails.</span></span> <span data-ttu-id="44896-123">BizTalk メッセージが信頼されないホストを経由する場合、BizTalk メッセージ内のユーザーの名前は、信頼されないホストのユーザーに変更されます。</span><span class="sxs-lookup"><span data-stu-id="44896-123">When a BizTalk message flows through an un-trusted host, the name of the user in the BizTalk message is changed to that of the un-trusted host.</span></span> <span data-ttu-id="44896-124">検証により、信頼されるホスト経由でのみ BizTalk メッセージが送信されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="44896-124">Validation ensures that the BizTalk message has only flowed through trusted hosts.</span></span> <span data-ttu-id="44896-125">このメッセージは、アプリケーション システム レベルで検証が必要であるが (SSO システム オプションの設定による)、呼び出し元によって検証情報が提供されていなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="44896-125">This message means specifically that validation is required at the application system level (due to an SSO system option setting), but no validation information was provided by the caller.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44896-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="44896-126">User Action</span></span>  
 <span data-ttu-id="44896-127">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="44896-127">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="44896-128">BizTalk Server を使用している場合、メッセージは信頼されるホストのみを経由することを確認します。</span><span class="sxs-lookup"><span data-stu-id="44896-128">If you are using BizTalk Server, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="44896-129">メッセージのデータ改ざんのリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="44896-129">This will reduce the risk of tampering with the data in the message.</span></span>  
  
-   <span data-ttu-id="44896-130">シナリオで許可される場合は、このアプリケーションに対して検証をオフにしてください。</span><span class="sxs-lookup"><span data-stu-id="44896-130">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="44896-131">検証は、システムまたは特定のアプリケーションのみに対してオフにできる管理オプションです。</span><span class="sxs-lookup"><span data-stu-id="44896-131">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  
  
 <span data-ttu-id="44896-132">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="44896-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="44896-133">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="44896-133">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="44896-134">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="44896-134">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [<span data-ttu-id="44896-135">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="44896-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)