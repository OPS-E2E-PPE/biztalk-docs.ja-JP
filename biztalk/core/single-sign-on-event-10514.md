---
title: 'シングル サインオン: イベント 10514 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b527841-a2e2-44c7-a9cb-6e9a8eea2fba
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fff4fbbb9b5c4d32968312b0f585ffbf2f5bb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995307"
---
# <a name="single-sign-on-event-10514"></a><span data-ttu-id="3071b-102">シングル サインオン: イベント 10514</span><span class="sxs-lookup"><span data-stu-id="3071b-102">Single Sign-On: Event 10514</span></span>
## <a name="details"></a><span data-ttu-id="3071b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3071b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3071b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3071b-104">Product Name</span></span>   |                                                                                    <span data-ttu-id="3071b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3071b-105">Enterprise Single Sign-On</span></span>                                                                                     |
| <span data-ttu-id="3071b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3071b-106">Product Version</span></span> |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    <span data-ttu-id="3071b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3071b-107">Event ID</span></span>     |                                                                                              <span data-ttu-id="3071b-108">10514</span><span class="sxs-lookup"><span data-stu-id="3071b-108">10514</span></span>                                                                                               |
|  <span data-ttu-id="3071b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3071b-109">Event Source</span></span>   |                                                                                              <span data-ttu-id="3071b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3071b-110">ENTSSO</span></span>                                                                                              |
|    <span data-ttu-id="3071b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3071b-111">Component</span></span>    |                                                                                               <span data-ttu-id="3071b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="3071b-112">N\A</span></span>                                                                                                |
|  <span data-ttu-id="3071b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3071b-113">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="3071b-114">SSO_ERROR_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="3071b-114">SSO_ERROR_DB_ACCESS</span></span>                                                                                        |
|  <span data-ttu-id="3071b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3071b-115">Message Text</span></span>   | <span data-ttu-id="3071b-116">SSO データベースへのアクセスを試みているときにエラーが発生しました。%r</span><span class="sxs-lookup"><span data-stu-id="3071b-116">An error occurred while attempting to access the SSO database.%r</span></span><br /><br /> <span data-ttu-id="3071b-117">関数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3071b-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="3071b-118">ファイル: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="3071b-118">File: %2%r</span></span><br /><br /> <span data-ttu-id="3071b-119">%3。%r</span><span class="sxs-lookup"><span data-stu-id="3071b-119">%3.%r</span></span><br /><br /> <span data-ttu-id="3071b-120">SQL エラー コード: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="3071b-120">SQL Error code: %4%r</span></span><br /><br /> <span data-ttu-id="3071b-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="3071b-121">Error code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3071b-122">説明</span><span class="sxs-lookup"><span data-stu-id="3071b-122">Explanation</span></span>  
 <span data-ttu-id="3071b-123">このエラー イベントは、SSO データベースにアクセスしようとしたときに、SQL Server からエラーを受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="3071b-123">This Error event indicates that an error was received from SQL Server when attempting to access the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3071b-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3071b-124">User Action</span></span>  
 <span data-ttu-id="3071b-125">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3071b-125">To resolve this error, do one or more of the following:</span></span>  
  
- <span data-ttu-id="3071b-126">SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3071b-126">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
- <span data-ttu-id="3071b-127">イベントとエラー メッセージ センターを使用して SQL Server エラー コードを確認して[ http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869)します。</span><span class="sxs-lookup"><span data-stu-id="3071b-127">Check the SQL Server error code using the Events and Errors Message Center at [http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869).</span></span>  
  
  <span data-ttu-id="3071b-128">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="3071b-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
- [<span data-ttu-id="3071b-129">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="3071b-129">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
- [<span data-ttu-id="3071b-130">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="3071b-130">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
  <span data-ttu-id="3071b-131">SQL Server Books Online も参照してください。</span><span class="sxs-lookup"><span data-stu-id="3071b-131">See also SQL Server Books Online.</span></span>