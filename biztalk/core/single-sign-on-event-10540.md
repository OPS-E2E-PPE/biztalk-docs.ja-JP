---
title: 'シングル サインオン: イベント 10540 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1bcd7cc64a79634aa7868791d7e74e92cd1c4a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990947"
---
# <a name="single-sign-on-event-10540"></a><span data-ttu-id="15082-102">シングル サインオン: イベント 10540</span><span class="sxs-lookup"><span data-stu-id="15082-102">Single Sign-On: Event 10540</span></span>
## <a name="details"></a><span data-ttu-id="15082-103">詳細</span><span class="sxs-lookup"><span data-stu-id="15082-103">Details</span></span>  

|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  <span data-ttu-id="15082-104">製品名</span><span class="sxs-lookup"><span data-stu-id="15082-104">Product Name</span></span>   |                            <span data-ttu-id="15082-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="15082-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="15082-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="15082-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="15082-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="15082-107">Event ID</span></span>     |                                      <span data-ttu-id="15082-108">10540</span><span class="sxs-lookup"><span data-stu-id="15082-108">10540</span></span>                                       |
|  <span data-ttu-id="15082-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="15082-109">Event Source</span></span>   |                                      <span data-ttu-id="15082-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="15082-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="15082-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="15082-111">Component</span></span>    |                                        <span data-ttu-id="15082-112">CO</span><span class="sxs-lookup"><span data-stu-id="15082-112">CO</span></span>                                        |
|  <span data-ttu-id="15082-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="15082-113">Symbolic Name</span></span>  |                         <span data-ttu-id="15082-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="15082-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span></span>                         |
|  <span data-ttu-id="15082-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="15082-115">Message Text</span></span>   | <span data-ttu-id="15082-116">チケットはこのアプリケーションに対して有効になっていません。%r</span><span class="sxs-lookup"><span data-stu-id="15082-116">Tickets are not enabled for this application.%r</span></span><br /><br /> <span data-ttu-id="15082-117">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="15082-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="15082-118">説明</span><span class="sxs-lookup"><span data-stu-id="15082-118">Explanation</span></span>  
 <span data-ttu-id="15082-119">この警告イベントは、チケット機能がこのアプリケーションで有効になっていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="15082-119">This Warning event indicates that the tickets feature has not been enabled for this application.</span></span> <span data-ttu-id="15082-120">SSO チケットの使用は、SSO アプリケーションごとのオプション機能です。</span><span class="sxs-lookup"><span data-stu-id="15082-120">The use of SSO tickets is an optional feature for each SSO application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="15082-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="15082-121">User Action</span></span>  
 <span data-ttu-id="15082-122">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="15082-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="15082-123">アプリケーション管理者に連絡し、この SSO アプリケーションのチケットを有効にしてもらいます。</span><span class="sxs-lookup"><span data-stu-id="15082-123">Contact your Application Administrator to enable tickets for this SSO application.</span></span> <span data-ttu-id="15082-124">SSO 管理ツール (GUI またはコマンド ライン) を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="15082-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="15082-125">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="15082-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="15082-126">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="15082-126">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="15082-127">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="15082-127">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="15082-128">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="15082-128">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
