---
title: ESB 管理ポータルを使用して管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 478d1dcc-e9b2-443b-be98-5b7545322401
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24c44951b4284e0d17b2d8e69011cedfa213c219
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967763"
---
# <a name="administration-using-the-esb-management-portal"></a><span data-ttu-id="7b16f-102">ESB 管理ポータルを使用した管理</span><span class="sxs-lookup"><span data-stu-id="7b16f-102">Administration Using the ESB Management Portal</span></span>
<span data-ttu-id="7b16f-103">ESB 管理ポータルの一部として含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は、BizTalk ESB Toolkit を拡張するためのメトリックと存在する可能性の使用方法を示すサンプル サイトです。</span><span class="sxs-lookup"><span data-stu-id="7b16f-103">The ESB Management Portal, included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], is a sample site that demonstrates the use of metrics and the possibilities that exist for extending the BizTalk ESB Toolkit.</span></span> <span data-ttu-id="7b16f-104">ポータルでは、独自のカスタマイズされたポータルを作成、開始点を提供します。</span><span class="sxs-lookup"><span data-stu-id="7b16f-104">The portal provides a starting point from which you can build your own customized portal.</span></span>  
  
 <span data-ttu-id="7b16f-105">ESB 管理ポータルも非常に有用な対応のツールを使用し、ESB 例外管理システムの効率を最大限に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="7b16f-105">The ESB Management Portal is also a highly capable and useful tool that can help to maximize the use and efficiency of the ESB exception management system.</span></span> <span data-ttu-id="7b16f-106">さらに、ポータル ユーザー インターフェイスを提供 Universal Description, Discovery, and Integration (UDDI) レジストリの基になるサーバーと、監査などの機能をグラフィカルな構成機能の履歴情報の表示を構成します。アラートと通知、およびユーザーができるように ESB アプリケーションで発生している障害を示すアラートを購読します。</span><span class="sxs-lookup"><span data-stu-id="7b16f-106">In addition, the portal provides a user interface for an underlying Universal Description, Discovery, and Integration (UDDI) registry server and graphical configuration capabilities for features such as auditing, viewing history information, configuring alerts and notifications, and allowing users to subscribe to alerts that indicate faults occurring in ESB applications.</span></span>  
  
 <span data-ttu-id="7b16f-107">このセクションでは、次を含む、ESB 管理ポータルを使用してを実行できる一般的なタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7b16f-107">This section describes the common tasks you can accomplish using the ESB Management Portal, including the following:</span></span>  
  
-   [<span data-ttu-id="7b16f-108">例外とエラー メッセージの使用</span><span class="sxs-lookup"><span data-stu-id="7b16f-108">Working with Exceptions and Fault Messages</span></span>](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [<span data-ttu-id="7b16f-109">アラート、通知、サブスクリプションを構成する</span><span class="sxs-lookup"><span data-stu-id="7b16f-109">Configuring Alerts, Notifications, and Subscriptions</span></span>](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [<span data-ttu-id="7b16f-110">監査と履歴を表示し、管理する</span><span class="sxs-lookup"><span data-stu-id="7b16f-110">Viewing and Managing Auditing and History</span></span>](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [<span data-ttu-id="7b16f-111">グラフとレポートを利用してエラー傾向を分析する</span><span class="sxs-lookup"><span data-stu-id="7b16f-111">Analyzing Fault Trends Using Charts and Reports</span></span>](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [<span data-ttu-id="7b16f-112">UDDI 登録を表示し、発行する</span><span class="sxs-lookup"><span data-stu-id="7b16f-112">Viewing and Publishing UDDI Registrations</span></span>](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  <span data-ttu-id="7b16f-113">ESB 管理ポータルの個々 の機能の詳細については、次を参照してください。 [ESB 管理ポータル機能リファレンス](../esb-toolkit/esb-management-portal-feature-reference.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b16f-113">For a detailed description of the individual features of the ESB Management Portal, see [ESB Management Portal Feature Reference](../esb-toolkit/esb-management-portal-feature-reference.md).</span></span>  
  
## <a name="esb-portal-technologies"></a><span data-ttu-id="7b16f-114">ESB ポータル テクノロジ</span><span class="sxs-lookup"><span data-stu-id="7b16f-114">ESB Portal Technologies</span></span>  
 <span data-ttu-id="7b16f-115">ESB 管理ポータルでは、次のテクノロジを利用します。</span><span class="sxs-lookup"><span data-stu-id="7b16f-115">The ESB Management Portal takes advantage of the following technologies:</span></span>  
  
- [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
- <span data-ttu-id="7b16f-116">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7b16f-116">ASP.NET</span></span>
  
- <span data-ttu-id="7b16f-117">[Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292))。</span><span class="sxs-lookup"><span data-stu-id="7b16f-117">[Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292)).</span></span> <span data-ttu-id="7b16f-118">ESB 管理ポータルでは、次のエンタープライズ ライブラリ アセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b16f-118">The ESB Management Portal uses the following Enterprise Library assemblies:</span></span>  
  
  -   <span data-ttu-id="7b16f-119">**Microsoft.Practices.EnterpriseLibrary.Caching**</span><span class="sxs-lookup"><span data-stu-id="7b16f-119">**Microsoft.Practices.EnterpriseLibrary.Caching**</span></span>  
  
  -   <span data-ttu-id="7b16f-120">**Microsoft.Practices.EnterpriseLibrary.Common**</span><span class="sxs-lookup"><span data-stu-id="7b16f-120">**Microsoft.Practices.EnterpriseLibrary.Common**</span></span>  
  
  -   <span data-ttu-id="7b16f-121">**Microsoft.Practices.EnterpriseLibrary.Data**</span><span class="sxs-lookup"><span data-stu-id="7b16f-121">**Microsoft.Practices.EnterpriseLibrary.Data**</span></span>  
  
  -   <span data-ttu-id="7b16f-122">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**</span><span class="sxs-lookup"><span data-stu-id="7b16f-122">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**</span></span>  
  
  -   <span data-ttu-id="7b16f-123">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**</span><span class="sxs-lookup"><span data-stu-id="7b16f-123">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**</span></span>  
  
  -   <span data-ttu-id="7b16f-124">**Microsoft.Practices.EnterpriseLibrary.Logging**</span><span class="sxs-lookup"><span data-stu-id="7b16f-124">**Microsoft.Practices.EnterpriseLibrary.Logging**</span></span>  
  
  -   <span data-ttu-id="7b16f-125">**Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**</span><span class="sxs-lookup"><span data-stu-id="7b16f-125">**Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**</span></span>  
  
  -   <span data-ttu-id="7b16f-126">**Microsoft.Practices.EnterpriseLibrary.Validation**</span><span class="sxs-lookup"><span data-stu-id="7b16f-126">**Microsoft.Practices.EnterpriseLibrary.Validation**</span></span>  
  
  -   <span data-ttu-id="7b16f-127">Microsoft.Practices.Unity</span><span class="sxs-lookup"><span data-stu-id="7b16f-127">Microsoft.Practices.Unity</span></span>  
  
- <span data-ttu-id="7b16f-128">[Microsoft Chart Controls](http://go.microsoft.com/fwlink/?LinkId=188293) (http://go.microsoft.com/fwlink/?LinkId=188293) for Microsoft .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="7b16f-128">[Microsoft Chart Controls](http://go.microsoft.com/fwlink/?LinkId=188293) (http://go.microsoft.com/fwlink/?LinkId=188293) for Microsoft .NET Framework 4</span></span>  
  
<span data-ttu-id="7b16f-129">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外管理システムの障害の追跡のみにメトリックの追跡を拡張します。</span><span class="sxs-lookup"><span data-stu-id="7b16f-129">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] metric tracking extends only to fault tracking for the exception management system.</span></span>