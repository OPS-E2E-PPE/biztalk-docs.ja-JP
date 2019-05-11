---
title: シングル サインオン:イベント 10540 |Microsoft Docs
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
ms.openlocfilehash: dd18184dbf06934600231a6bbb75abdc1709f5ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243408"
---
# <a name="single-sign-on-event-10540"></a><span data-ttu-id="17ba5-102">シングル サインオン:イベント 10540</span><span class="sxs-lookup"><span data-stu-id="17ba5-102">Single Sign-On: Event 10540</span></span>
## <a name="details"></a><span data-ttu-id="17ba5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="17ba5-103">Details</span></span>  

|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  <span data-ttu-id="17ba5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="17ba5-104">Product Name</span></span>   |                            <span data-ttu-id="17ba5-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="17ba5-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="17ba5-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="17ba5-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="17ba5-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="17ba5-107">Event ID</span></span>     |                                      <span data-ttu-id="17ba5-108">10540</span><span class="sxs-lookup"><span data-stu-id="17ba5-108">10540</span></span>                                       |
|  <span data-ttu-id="17ba5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="17ba5-109">Event Source</span></span>   |                                      <span data-ttu-id="17ba5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="17ba5-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="17ba5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="17ba5-111">Component</span></span>    |                                        <span data-ttu-id="17ba5-112">CO</span><span class="sxs-lookup"><span data-stu-id="17ba5-112">CO</span></span>                                        |
|  <span data-ttu-id="17ba5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="17ba5-113">Symbolic Name</span></span>  |                         <span data-ttu-id="17ba5-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="17ba5-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span></span>                         |
|  <span data-ttu-id="17ba5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="17ba5-115">Message Text</span></span>   | <span data-ttu-id="17ba5-116">この application.%r チケットが有効でないです。</span><span class="sxs-lookup"><span data-stu-id="17ba5-116">Tickets are not enabled for this application.%r</span></span><br /><br /> <span data-ttu-id="17ba5-117">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="17ba5-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="17ba5-118">説明</span><span class="sxs-lookup"><span data-stu-id="17ba5-118">Explanation</span></span>  
 <span data-ttu-id="17ba5-119">この警告イベントは、チケット機能が有効になっていないこのアプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="17ba5-119">This Warning event indicates that the tickets feature has not been enabled for this application.</span></span> <span data-ttu-id="17ba5-120">SSO チケットの使用は、SSO アプリケーションごとの省略可能な機能です。</span><span class="sxs-lookup"><span data-stu-id="17ba5-120">The use of SSO tickets is an optional feature for each SSO application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="17ba5-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="17ba5-121">User Action</span></span>  
 <span data-ttu-id="17ba5-122">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="17ba5-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="17ba5-123">この SSO アプリケーションのチケットを有効にする、アプリケーション管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="17ba5-123">Contact your Application Administrator to enable tickets for this SSO application.</span></span> <span data-ttu-id="17ba5-124">これ行う SSO 管理ツール (GUI またはコマンドライン) を使用します。</span><span class="sxs-lookup"><span data-stu-id="17ba5-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="17ba5-125">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="17ba5-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="17ba5-126">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="17ba5-126">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="17ba5-127">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="17ba5-127">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="17ba5-128">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="17ba5-128">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
