---
title: シングル サインオン:イベント 10514 |Microsoft Docs
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
ms.openlocfilehash: 8b3017f6a84910ecdfd0da07aeb0ae5c76485bc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243441"
---
# <a name="single-sign-on-event-10514"></a><span data-ttu-id="48a1c-102">シングル サインオン:イベント 10514</span><span class="sxs-lookup"><span data-stu-id="48a1c-102">Single Sign-On: Event 10514</span></span>
## <a name="details"></a><span data-ttu-id="48a1c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="48a1c-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="48a1c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="48a1c-104">Product Name</span></span>   |                                                                                    <span data-ttu-id="48a1c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="48a1c-105">Enterprise Single Sign-On</span></span>                                                                                     |
| <span data-ttu-id="48a1c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="48a1c-106">Product Version</span></span> |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    <span data-ttu-id="48a1c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48a1c-107">Event ID</span></span>     |                                                                                              <span data-ttu-id="48a1c-108">10514</span><span class="sxs-lookup"><span data-stu-id="48a1c-108">10514</span></span>                                                                                               |
|  <span data-ttu-id="48a1c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="48a1c-109">Event Source</span></span>   |                                                                                              <span data-ttu-id="48a1c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="48a1c-110">ENTSSO</span></span>                                                                                              |
|    <span data-ttu-id="48a1c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="48a1c-111">Component</span></span>    |                                                                                               <span data-ttu-id="48a1c-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="48a1c-112">N\A</span></span>                                                                                                |
|  <span data-ttu-id="48a1c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="48a1c-113">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="48a1c-114">SSO_ERROR_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="48a1c-114">SSO_ERROR_DB_ACCESS</span></span>                                                                                        |
|  <span data-ttu-id="48a1c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="48a1c-115">Message Text</span></span>   | <span data-ttu-id="48a1c-116">SSO database.%r へのアクセスを試みているときにエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="48a1c-116">An error occurred while attempting to access the SSO database.%r</span></span><br /><br /> <span data-ttu-id="48a1c-117">関数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="48a1c-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="48a1c-118">ファイル: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="48a1c-118">File: %2%r</span></span><br /><br /> <span data-ttu-id="48a1c-119">%3.%r</span><span class="sxs-lookup"><span data-stu-id="48a1c-119">%3.%r</span></span><br /><br /> <span data-ttu-id="48a1c-120">SQL エラー コード: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="48a1c-120">SQL Error code: %4%r</span></span><br /><br /> <span data-ttu-id="48a1c-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="48a1c-121">Error code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="48a1c-122">説明</span><span class="sxs-lookup"><span data-stu-id="48a1c-122">Explanation</span></span>  
 <span data-ttu-id="48a1c-123">このエラー イベントは、SSO データベースにアクセスする際にエラーが SQL Server から受信したことを示します。</span><span class="sxs-lookup"><span data-stu-id="48a1c-123">This Error event indicates that an error was received from SQL Server when attempting to access the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="48a1c-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="48a1c-124">User Action</span></span>  
 <span data-ttu-id="48a1c-125">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="48a1c-125">To resolve this error, do one or more of the following:</span></span>  
  
- <span data-ttu-id="48a1c-126">SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="48a1c-126">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
- <span data-ttu-id="48a1c-127">イベントとエラー メッセージ センターを使用して SQL Server エラー コードを確認して[ http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869)します。</span><span class="sxs-lookup"><span data-stu-id="48a1c-127">Check the SQL Server error code using the Events and Errors Message Center at [http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869).</span></span>  
  
  <span data-ttu-id="48a1c-128">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="48a1c-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
- [<span data-ttu-id="48a1c-129">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="48a1c-129">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
- [<span data-ttu-id="48a1c-130">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="48a1c-130">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
  <span data-ttu-id="48a1c-131">SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48a1c-131">See also SQL Server Books Online.</span></span>