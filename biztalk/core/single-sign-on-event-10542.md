---
title: シングル サインオン:イベント 10542 |Microsoft Docs
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
ms.openlocfilehash: 493937fbcf9eb04ccfe59881c56f12e4b3851f11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243435"
---
# <a name="single-sign-on-event-10542"></a><span data-ttu-id="21a03-102">シングル サインオン:イベント 10542</span><span class="sxs-lookup"><span data-stu-id="21a03-102">Single Sign-On: Event 10542</span></span>
## <a name="details"></a><span data-ttu-id="21a03-103">詳細</span><span class="sxs-lookup"><span data-stu-id="21a03-103">Details</span></span>  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="21a03-104">製品名</span><span class="sxs-lookup"><span data-stu-id="21a03-104">Product Name</span></span>   |                                          <span data-ttu-id="21a03-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="21a03-105">Enterprise Single Sign-On</span></span>                                          |
| <span data-ttu-id="21a03-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="21a03-106">Product Version</span></span> |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    <span data-ttu-id="21a03-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="21a03-107">Event ID</span></span>     |                                                    <span data-ttu-id="21a03-108">10542</span><span class="sxs-lookup"><span data-stu-id="21a03-108">10542</span></span>                                                    |
|  <span data-ttu-id="21a03-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="21a03-109">Event Source</span></span>   |                                                   <span data-ttu-id="21a03-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="21a03-110">ENTSSO</span></span>                                                    |
|    <span data-ttu-id="21a03-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="21a03-111">Component</span></span>    |                                                     <span data-ttu-id="21a03-112">CO</span><span class="sxs-lookup"><span data-stu-id="21a03-112">CO</span></span>                                                      |
|  <span data-ttu-id="21a03-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="21a03-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="21a03-114">SSO_WARN_APP_TICKETS_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="21a03-114">SSO_WARN_APP_TICKETS_VALIDATED</span></span>                                        |
|  <span data-ttu-id="21a03-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="21a03-115">Message Text</span></span>   | <span data-ttu-id="21a03-116">Validated.%r せずにこのアプリケーションのチケットを引き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="21a03-116">Tickets cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="21a03-117">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="21a03-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="21a03-118">説明</span><span class="sxs-lookup"><span data-stu-id="21a03-118">Explanation</span></span>  
 <span data-ttu-id="21a03-119">この警告イベントは、検証されることがなくアプリケーション チケットを引き換えることができないことを示します。</span><span class="sxs-lookup"><span data-stu-id="21a03-119">This Warning event indicates that application tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="21a03-120">アプリケーションのチケットを引き換えるときに検証したりできます検証されません。</span><span class="sxs-lookup"><span data-stu-id="21a03-120">When application tickets are redeemed they can be validated or not validated.</span></span> <span data-ttu-id="21a03-121">検証では、BizTalk メッセージ内のユーザーの名前を持つ、チケットを発行したユーザーの名前を比較することによってセキュリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="21a03-121">Validation improves security by comparing the name of the user who issued the ticket with the name of the user in the BizTalk message.</span></span> <span data-ttu-id="21a03-122">名前が同じではない場合は、検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="21a03-122">If the names are not the same then validation fails.</span></span> <span data-ttu-id="21a03-123">BizTalk メッセージのフロー、信頼されていないホストを介して、ときに、信頼されていないホストに、BizTalk メッセージ内のユーザーの名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="21a03-123">When a BizTalk message flows through an un-trusted host, the name of the user in the BizTalk message is changed to that of the un-trusted host.</span></span> <span data-ttu-id="21a03-124">検証では、BizTalk メッセージが信頼されたホストでのみフローされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="21a03-124">Validation ensures that the BizTalk message has only flowed through trusted hosts.</span></span> <span data-ttu-id="21a03-125">このメッセージは意味 (SSO システム オプションの設定による)、アプリケーションのシステム レベルの検証が必要ですが、呼び出し元によって検証情報が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="21a03-125">This message means specifically that validation is required at the application system level (due to an SSO system option setting), but no validation information was provided by the caller.</span></span>  

## <a name="user-action"></a><span data-ttu-id="21a03-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="21a03-126">User Action</span></span>  
 <span data-ttu-id="21a03-127">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="21a03-127">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="21a03-128">BizTalk Server を使用している場合は、メッセージが 信頼されたホストのみを介して送信されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="21a03-128">If you are using BizTalk Server, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="21a03-129">これにより、メッセージのデータの改ざんのリスクが低減されます。</span><span class="sxs-lookup"><span data-stu-id="21a03-129">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="21a03-130">自分のシナリオにより、このアプリケーションの検証をオフにします。</span><span class="sxs-lookup"><span data-stu-id="21a03-130">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="21a03-131">検証は、管理オプションであり、システムまたはこの特定のアプリケーションに対してだけ、オフにすることです。</span><span class="sxs-lookup"><span data-stu-id="21a03-131">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="21a03-132">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="21a03-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="21a03-133">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="21a03-133">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="21a03-134">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="21a03-134">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="21a03-135">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="21a03-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
