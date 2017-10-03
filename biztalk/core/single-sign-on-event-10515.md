---
title: "シングル サインオン: イベント 10515 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41edc008-b6d3-401d-97af-80b36ab0ba55
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e2b884ae52af96ceaae83f8b092ed15b6b12e3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10515"></a><span data-ttu-id="f33e4-102">シングル サインオン: イベント 10515</span><span class="sxs-lookup"><span data-stu-id="f33e4-102">Single Sign-On: Event 10515</span></span>
## <a name="details"></a><span data-ttu-id="f33e4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f33e4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f33e4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f33e4-104">Product Name</span></span>|<span data-ttu-id="f33e4-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f33e4-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f33e4-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f33e4-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f33e4-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f33e4-107">Event ID</span></span>|<span data-ttu-id="f33e4-108">10515</span><span class="sxs-lookup"><span data-stu-id="f33e4-108">10515</span></span>|  
|<span data-ttu-id="f33e4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f33e4-109">Event Source</span></span>|<span data-ttu-id="f33e4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f33e4-110">ENTSSO</span></span>|  
|<span data-ttu-id="f33e4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f33e4-111">Component</span></span>|<span data-ttu-id="f33e4-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f33e4-112">N\A</span></span>|  
|<span data-ttu-id="f33e4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f33e4-113">Symbolic Name</span></span>|<span data-ttu-id="f33e4-114">SSO_ERROR_POLL_DATABASE</span><span class="sxs-lookup"><span data-stu-id="f33e4-114">SSO_ERROR_POLL_DATABASE</span></span>|  
|<span data-ttu-id="f33e4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f33e4-115">Message Text</span></span>|<span data-ttu-id="f33e4-116">SSO データベースとの接続が切断されました。</span><span class="sxs-lookup"><span data-stu-id="f33e4-116">Lost contact with the SSO database.</span></span> <span data-ttu-id="f33e4-117">SSO データベースが使用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f33e4-117">Check that the SSO database is available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f33e4-118">説明</span><span class="sxs-lookup"><span data-stu-id="f33e4-118">Explanation</span></span>  
 <span data-ttu-id="f33e4-119">このエラー イベントは、SSO サービスと SSO データベースとの接続が切断されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="f33e4-119">This Error event indicates that the SSO Service has lost contact with the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f33e4-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f33e4-120">User Action</span></span>  
 <span data-ttu-id="f33e4-121">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f33e4-121">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="f33e4-122">SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f33e4-122">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
-   <span data-ttu-id="f33e4-123">SQL Server がリモート サーバー上で実行されている場合は、ネットワーク接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="f33e4-123">Verify network connectivity to SQL Server if on a remote server.</span></span>  
  
 <span data-ttu-id="f33e4-124">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="f33e4-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="f33e4-125">エンタープライズ シングル サインオンを実装します。</span><span class="sxs-lookup"><span data-stu-id="f33e4-125">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="f33e4-126">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="f33e4-126">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
-   [<span data-ttu-id="f33e4-127">SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="f33e4-127">Configuring SSO</span></span>](../core/configuring-sso.md)  
  
 <span data-ttu-id="f33e4-128">SQL Server オンライン ブックも参照してください。</span><span class="sxs-lookup"><span data-stu-id="f33e4-128">See also SQL Server Books Online</span></span>