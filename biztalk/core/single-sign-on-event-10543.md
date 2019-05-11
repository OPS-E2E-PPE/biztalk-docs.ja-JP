---
title: シングル サインオン:イベント 10543 |Microsoft Docs
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
ms.openlocfilehash: 4f8a3b284910ea5555085a5617a2d2922d0231f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243387"
---
# <a name="single-sign-on-event-10543"></a><span data-ttu-id="4126d-102">シングル サインオン:イベント 10543</span><span class="sxs-lookup"><span data-stu-id="4126d-102">Single Sign-On: Event 10543</span></span>
## <a name="details"></a><span data-ttu-id="4126d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4126d-103">Details</span></span>  

|                 |                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4126d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4126d-104">Product Name</span></span>   |                                                               <span data-ttu-id="4126d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4126d-105">Enterprise Single Sign-On</span></span>                                                                |
| <span data-ttu-id="4126d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4126d-106">Product Version</span></span> |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                               |
|    <span data-ttu-id="4126d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4126d-107">Event ID</span></span>     |                                                                         <span data-ttu-id="4126d-108">10543</span><span class="sxs-lookup"><span data-stu-id="4126d-108">10543</span></span>                                                                          |
|  <span data-ttu-id="4126d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4126d-109">Event Source</span></span>   |                                                                         <span data-ttu-id="4126d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4126d-110">ENTSSO</span></span>                                                                         |
|    <span data-ttu-id="4126d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4126d-111">Component</span></span>    |                                                                           <span data-ttu-id="4126d-112">CO</span><span class="sxs-lookup"><span data-stu-id="4126d-112">CO</span></span>                                                                           |
|  <span data-ttu-id="4126d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4126d-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="4126d-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="4126d-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span></span>                                                           |
|  <span data-ttu-id="4126d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4126d-115">Message Text</span></span>   | <span data-ttu-id="4126d-116">検証が必要なチケットが発行されました。</span><span class="sxs-lookup"><span data-stu-id="4126d-116">The ticket was issued with validation required.</span></span> <span data-ttu-id="4126d-117">このアプリケーションの validated.%r せず引き換えることができません。</span><span class="sxs-lookup"><span data-stu-id="4126d-117">It cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="4126d-118">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="4126d-118">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="4126d-119">説明</span><span class="sxs-lookup"><span data-stu-id="4126d-119">Explanation</span></span>  
 <span data-ttu-id="4126d-120">この警告イベントは、検証が必要なアプリケーション チケットが発行されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="4126d-120">This Warning event indicates that an application ticket was issued with validation required.</span></span> <span data-ttu-id="4126d-121">検証を行わず、チケットを引き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="4126d-121">Tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="4126d-122">チケットの検証は、関連アプリケーションごと。</span><span class="sxs-lookup"><span data-stu-id="4126d-122">Validation of the ticket is on a per affiliate application basis.</span></span>  

## <a name="user-action"></a><span data-ttu-id="4126d-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4126d-123">User Action</span></span>  
 <span data-ttu-id="4126d-124">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4126d-124">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="4126d-125">エンタープライズ シングル サインオンを使用する場合は、メッセージが 信頼されたホストのみを介して送信されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4126d-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="4126d-126">これにより、メッセージのデータの改ざんのリスクが低減されます。</span><span class="sxs-lookup"><span data-stu-id="4126d-126">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="4126d-127">自分のシナリオにより、このアプリケーションの検証をオフにします。</span><span class="sxs-lookup"><span data-stu-id="4126d-127">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="4126d-128">検証は、管理オプションであり、システムまたはこの特定のアプリケーションに対してだけ、オフにすることです。</span><span class="sxs-lookup"><span data-stu-id="4126d-128">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="4126d-129">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="4126d-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="4126d-130">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="4126d-130">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="4126d-131">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="4126d-131">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="4126d-132">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="4126d-132">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
