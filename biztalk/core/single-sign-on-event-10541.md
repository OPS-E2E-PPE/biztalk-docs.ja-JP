---
title: シングル サインオン:イベント 10541 |Microsoft Docs
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
ms.openlocfilehash: b7a30d3c2221632d4dd9d050067f8fc9094d37d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250287"
---
# <a name="single-sign-on-event-10541"></a><span data-ttu-id="6cf05-102">シングル サインオン:イベント 10541</span><span class="sxs-lookup"><span data-stu-id="6cf05-102">Single Sign-On: Event 10541</span></span>
## <a name="details"></a><span data-ttu-id="6cf05-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6cf05-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="6cf05-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6cf05-104">Product Name</span></span>   |                 <span data-ttu-id="6cf05-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6cf05-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="6cf05-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6cf05-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="6cf05-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6cf05-107">Event ID</span></span>     |                           <span data-ttu-id="6cf05-108">10541</span><span class="sxs-lookup"><span data-stu-id="6cf05-108">10541</span></span>                            |
|  <span data-ttu-id="6cf05-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6cf05-109">Event Source</span></span>   |                           <span data-ttu-id="6cf05-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6cf05-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="6cf05-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6cf05-111">Component</span></span>    |                             <span data-ttu-id="6cf05-112">CO</span><span class="sxs-lookup"><span data-stu-id="6cf05-112">CO</span></span>                             |
|  <span data-ttu-id="6cf05-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6cf05-113">Symbolic Name</span></span>  |               <span data-ttu-id="6cf05-114">SSO_WARN_SSO_TICKETS_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="6cf05-114">SSO_WARN_SSO_TICKETS_VALIDATED</span></span>               |
|  <span data-ttu-id="6cf05-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6cf05-115">Message Text</span></span>   |    <span data-ttu-id="6cf05-116">検証を行わず、チケットを引き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="6cf05-116">Tickets cannot be redeemed without being validated.</span></span>     |

## <a name="explanation"></a><span data-ttu-id="6cf05-117">説明</span><span class="sxs-lookup"><span data-stu-id="6cf05-117">Explanation</span></span>  
 <span data-ttu-id="6cf05-118">この警告イベントは、検証を行わず SSO チケットを引き換えることができないことを示します。</span><span class="sxs-lookup"><span data-stu-id="6cf05-118">This Warning event indicates that SSO tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="6cf05-119">SSO チケットを引き換えるときに検証したりできます検証されません。</span><span class="sxs-lookup"><span data-stu-id="6cf05-119">When SSO tickets are redeemed they can be validated or not validated.</span></span> <span data-ttu-id="6cf05-120">検証では、BizTalk メッセージ内のユーザーの名前を持つ、チケットを発行したユーザーの名前を比較することによってセキュリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="6cf05-120">Validation improves security by comparing the name of the user who issued the ticket with the name of the user in the BizTalk message.</span></span> <span data-ttu-id="6cf05-121">名前が同じではない場合は、検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="6cf05-121">If the names are not the same then validation fails.</span></span> <span data-ttu-id="6cf05-122">BizTalk メッセージのフロー、信頼されていないホストを介して、ときに、信頼されていないホストに、BizTalk メッセージ内のユーザーの名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="6cf05-122">When a BizTalk message flows through an un-trusted host, the name of the user in the BizTalk message is changed to that of the un-trusted host.</span></span> <span data-ttu-id="6cf05-123">検証では、BizTalk メッセージが信頼されたホストでのみフローされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6cf05-123">Validation ensures that the BizTalk message has only flowed through trusted hosts.</span></span> <span data-ttu-id="6cf05-124">このメッセージは意味 (SSO システム オプションの設定による)、SSO システム レベルで検証が必要ですが、呼び出し元によって検証情報が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="6cf05-124">This message means specifically that validation is required at the SSO system level (due to an SSO system option setting), but no validation information was provided by the caller.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6cf05-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6cf05-125">User Action</span></span>  
 <span data-ttu-id="6cf05-126">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6cf05-126">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="6cf05-127">BizTalk Server を使用している場合は、メッセージが 信頼されたホストのみを介して送信されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6cf05-127">If you are using BizTalk Server, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="6cf05-128">これにより、メッセージのデータの改ざんのリスクが低減されます。</span><span class="sxs-lookup"><span data-stu-id="6cf05-128">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="6cf05-129">自分のシナリオにより、このアプリケーションの検証をオフにします。</span><span class="sxs-lookup"><span data-stu-id="6cf05-129">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="6cf05-130">検証は、管理オプションであり、システムまたはこの特定のアプリケーションに対してだけ、オフにすることです。</span><span class="sxs-lookup"><span data-stu-id="6cf05-130">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="6cf05-131">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="6cf05-131">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="6cf05-132">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="6cf05-132">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="6cf05-133">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="6cf05-133">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="6cf05-134">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="6cf05-134">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
