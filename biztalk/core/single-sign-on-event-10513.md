---
title: "シングル サインオン: イベント 10513 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3306223-111f-4abf-ae65-be839b355216
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f1be7ae463dbb1ee9651f69f231614cc11db5f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10513"></a><span data-ttu-id="678cd-102">シングル サインオン: イベント 10513</span><span class="sxs-lookup"><span data-stu-id="678cd-102">Single Sign-On: Event 10513</span></span>
## <a name="details"></a><span data-ttu-id="678cd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="678cd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="678cd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="678cd-104">Product Name</span></span>|<span data-ttu-id="678cd-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="678cd-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="678cd-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="678cd-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="678cd-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="678cd-107">Event ID</span></span>|<span data-ttu-id="678cd-108">10513</span><span class="sxs-lookup"><span data-stu-id="678cd-108">10513</span></span>|  
|<span data-ttu-id="678cd-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="678cd-109">Event Source</span></span>|<span data-ttu-id="678cd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="678cd-110">ENTSSO</span></span>|  
|<span data-ttu-id="678cd-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="678cd-111">Component</span></span>|<span data-ttu-id="678cd-112">N\A</span><span class="sxs-lookup"><span data-stu-id="678cd-112">N\A</span></span>|  
|<span data-ttu-id="678cd-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="678cd-113">Symbolic Name</span></span>|<span data-ttu-id="678cd-114">SSO_ERROR_DB_FIRST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="678cd-114">SSO_ERROR_DB_FIRST_ACCESS</span></span>|  
|<span data-ttu-id="678cd-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="678cd-115">Message Text</span></span>|<span data-ttu-id="678cd-116">SSO データベースに接続に失敗しました: %1 %r</span><span class="sxs-lookup"><span data-stu-id="678cd-116">Failed to contact the SSO database: %1%r</span></span><br /><br /> <span data-ttu-id="678cd-117">%2%r</span><span class="sxs-lookup"><span data-stu-id="678cd-117">%2%r</span></span><br /><br /> <span data-ttu-id="678cd-118">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="678cd-118">Error code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="678cd-119">説明</span><span class="sxs-lookup"><span data-stu-id="678cd-119">Explanation</span></span>  
 <span data-ttu-id="678cd-120">このエラー イベントは、SSO サービスの開始時に SSO データベースに接続できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="678cd-120">This Error event indicates that the SSO Service cannot connect to the SSO database when it starts.</span></span> <span data-ttu-id="678cd-121">イベント メッセージには、指定された SQL Server 名とデータベース名を示すデータ ソース名 (DSN) 文字列、および SQL 接続ライブラリから返されたエラー メッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="678cd-121">The event message contains the Data Source Name (DSN) string indicating the specified SQL Server and database names as well as the error message that was returned from the SQL connection libraries.</span></span>  
  
 <span data-ttu-id="678cd-122">SSO サービスは、開始時に、レジストリで指定された SQL Server 名と SSO データベース名を使用して SSO データベースに接続しようとします。</span><span class="sxs-lookup"><span data-stu-id="678cd-122">When the SSO Service starts, it will attempt to connect to the SSO database using the SQL Server and SSO database names specified in the registry.</span></span> <span data-ttu-id="678cd-123">SSO サービスは、接続が失敗するたびに 5 秒間待機しながら 12 回、合計で 1 分間、接続を試行します。</span><span class="sxs-lookup"><span data-stu-id="678cd-123">The SSO Service will attempt to connect 12 times, waiting 5 seconds between each failed attempt, for a total of 1 minute.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="678cd-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="678cd-124">User Action</span></span>  
 <span data-ttu-id="678cd-125">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="678cd-125">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="678cd-126">SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="678cd-126">Verify the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
-   <span data-ttu-id="678cd-127">エラー メッセージに示されているデータ ソース名 (DSN) 文字列が正しく、適切な SQL Server 名とデータベース名が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="678cd-127">Verify the Data Source Name (DSN) string indicated in the error message is correct and contains the correct SQL Server and database names.</span></span>  
  
 <span data-ttu-id="678cd-128">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="678cd-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="678cd-129">エンタープライズ シングル サインオンを実装します。</span><span class="sxs-lookup"><span data-stu-id="678cd-129">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="678cd-130">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="678cd-130">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
-   [<span data-ttu-id="678cd-131">SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="678cd-131">Configuring SSO</span></span>](../core/configuring-sso.md)  
  
-   <span data-ttu-id="678cd-132">SQL Server オンライン ブック</span><span class="sxs-lookup"><span data-stu-id="678cd-132">SQL Server Books Online</span></span>