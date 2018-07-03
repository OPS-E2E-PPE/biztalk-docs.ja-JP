---
title: 'シングル サインオン: イベント 10541 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e206158-5652-453c-91ac-9a75ab02809a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46f3b34c5e57b4fe10a50f684143cc10476e4eaa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991019"
---
# <a name="single-sign-on-event-10541"></a><span data-ttu-id="5e9ed-102">シングル サインオン: イベント 10541</span><span class="sxs-lookup"><span data-stu-id="5e9ed-102">Single Sign-On: Event 10541</span></span>
## <a name="details"></a><span data-ttu-id="5e9ed-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5e9ed-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="5e9ed-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5e9ed-104">Product Name</span></span>   |                 <span data-ttu-id="5e9ed-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5e9ed-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="5e9ed-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5e9ed-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="5e9ed-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5e9ed-107">Event ID</span></span>     |                           <span data-ttu-id="5e9ed-108">10541</span><span class="sxs-lookup"><span data-stu-id="5e9ed-108">10541</span></span>                            |
|  <span data-ttu-id="5e9ed-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5e9ed-109">Event Source</span></span>   |                           <span data-ttu-id="5e9ed-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5e9ed-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="5e9ed-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5e9ed-111">Component</span></span>    |                             <span data-ttu-id="5e9ed-112">CO</span><span class="sxs-lookup"><span data-stu-id="5e9ed-112">CO</span></span>                             |
|  <span data-ttu-id="5e9ed-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5e9ed-113">Symbolic Name</span></span>  |               <span data-ttu-id="5e9ed-114">SSO_WARN_SSO_TICKETS_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="5e9ed-114">SSO_WARN_SSO_TICKETS_VALIDATED</span></span>               |
|  <span data-ttu-id="5e9ed-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5e9ed-115">Message Text</span></span>   |    <span data-ttu-id="5e9ed-116">チケットを引き換えるには、検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-116">Tickets cannot be redeemed without being validated.</span></span>     |

## <a name="explanation"></a><span data-ttu-id="5e9ed-117">説明</span><span class="sxs-lookup"><span data-stu-id="5e9ed-117">Explanation</span></span>  
 <span data-ttu-id="5e9ed-118">この警告イベントは、SSO チケットを検証しないと引き換えできないことを示します。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-118">This Warning event indicates that SSO tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="5e9ed-119">SSO チケットを引き換えるときに、検証できる場合と、検証できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-119">When SSO tickets are redeemed they can be validated or not validated.</span></span> <span data-ttu-id="5e9ed-120">検証により、チケットを発行したユーザーの名前と BizTalk メッセージ内のユーザーの名前を比較することで、セキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-120">Validation improves security by comparing the name of the user who issued the ticket with the name of the user in the BizTalk message.</span></span> <span data-ttu-id="5e9ed-121">名前が一致しないと、検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-121">If the names are not the same then validation fails.</span></span> <span data-ttu-id="5e9ed-122">BizTalk メッセージが信頼されないホストを経由する場合、BizTalk メッセージ内のユーザーの名前は、信頼されないホストのユーザーに変更されます。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-122">When a BizTalk message flows through an un-trusted host, the name of the user in the BizTalk message is changed to that of the un-trusted host.</span></span> <span data-ttu-id="5e9ed-123">検証により、信頼されるホスト経由でのみ BizTalk メッセージが送信されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-123">Validation ensures that the BizTalk message has only flowed through trusted hosts.</span></span> <span data-ttu-id="5e9ed-124">このメッセージは、SSO システム レベルで検証が必要であるが (SSO システム オプションの設定による)、呼び出し元によって検証情報が提供されていなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-124">This message means specifically that validation is required at the SSO system level (due to an SSO system option setting), but no validation information was provided by the caller.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5e9ed-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5e9ed-125">User Action</span></span>  
 <span data-ttu-id="5e9ed-126">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="5e9ed-126">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="5e9ed-127">BizTalk Server を使用している場合、メッセージは信頼されるホストのみを経由することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-127">If you are using BizTalk Server, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="5e9ed-128">メッセージのデータ改ざんのリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-128">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="5e9ed-129">シナリオで許可される場合は、このアプリケーションに対して検証をオフにしてください。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-129">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="5e9ed-130">検証は、システムまたは特定のアプリケーションのみに対してオフにできる管理オプションです。</span><span class="sxs-lookup"><span data-stu-id="5e9ed-130">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="5e9ed-131">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="5e9ed-131">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="5e9ed-132">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="5e9ed-132">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="5e9ed-133">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="5e9ed-133">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="5e9ed-134">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="5e9ed-134">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
