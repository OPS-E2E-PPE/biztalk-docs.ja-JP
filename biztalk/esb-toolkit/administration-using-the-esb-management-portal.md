---
title: "ESB の管理ポータルを使用して管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 478d1dcc-e9b2-443b-be98-5b7545322401
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 351d06df4d6384607564778c4b86d8c509379488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="administration-using-the-esb-management-portal"></a><span data-ttu-id="69af0-102">ESB の管理ポータルを使用して管理</span><span class="sxs-lookup"><span data-stu-id="69af0-102">Administration Using the ESB Management Portal</span></span>
<span data-ttu-id="69af0-103">一部として含まれる、ESB 管理ポータル、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、BizTalk ESB Toolkit を拡張するためのメトリックと存在する可能性の使用方法を示すサンプル サイトです。</span><span class="sxs-lookup"><span data-stu-id="69af0-103">The ESB Management Portal, included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], is a sample site that demonstrates the use of metrics and the possibilities that exist for extending the BizTalk ESB Toolkit.</span></span> <span data-ttu-id="69af0-104">ポータルでは、カスタマイズした独自のポータルをビルドすることができます開始ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="69af0-104">The portal provides a starting point from which you can build your own customized portal.</span></span>  
  
 <span data-ttu-id="69af0-105">ESB 管理ポータルが使用して、ESB 例外管理システムの効率を最大化するのに役立つ高対応していて、役立つツールもできます。</span><span class="sxs-lookup"><span data-stu-id="69af0-105">The ESB Management Portal is also a highly capable and useful tool that can help to maximize the use and efficiency of the ESB exception management system.</span></span> <span data-ttu-id="69af0-106">さらに、ポータル ユーザー インターフェイスを提供 Universal Description, Discovery, and Integration (UDDI) レジストリの基になるサーバーおよび監査などの機能のグラフィカルな構成機能の履歴情報の表示を構成します。アラートと通知、およびユーザーを許可する ESB アプリケーションで発生するエラーを示すアラートにサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="69af0-106">In addition, the portal provides a user interface for an underlying Universal Description, Discovery, and Integration (UDDI) registry server and graphical configuration capabilities for features such as auditing, viewing history information, configuring alerts and notifications, and allowing users to subscribe to alerts that indicate faults occurring in ESB applications.</span></span>  
  
 <span data-ttu-id="69af0-107">このセクションでは、次を含む、ESB 管理ポータルを使用してを実行できる一般的なタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="69af0-107">This section describes the common tasks you can accomplish using the ESB Management Portal, including the following:</span></span>  
  
-   [<span data-ttu-id="69af0-108">例外とエラー メッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="69af0-108">Working with Exceptions and Fault Messages</span></span>](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [<span data-ttu-id="69af0-109">アラート、通知、およびサブスクリプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="69af0-109">Configuring Alerts, Notifications, and Subscriptions</span></span>](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [<span data-ttu-id="69af0-110">表示と管理の監査および履歴</span><span class="sxs-lookup"><span data-stu-id="69af0-110">Viewing and Managing Auditing and History</span></span>](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [<span data-ttu-id="69af0-111">グラフとレポートを使用してフォールト傾向の分析</span><span class="sxs-lookup"><span data-stu-id="69af0-111">Analyzing Fault Trends Using Charts and Reports</span></span>](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [<span data-ttu-id="69af0-112">表示して、UDDI の登録を公開</span><span class="sxs-lookup"><span data-stu-id="69af0-112">Viewing and Publishing UDDI Registrations</span></span>](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  <span data-ttu-id="69af0-113">ESB の管理ポータルの個々 の機能の詳細については、次を参照してください。 [ESB 管理ポータル機能リファレンス](../esb-toolkit/esb-management-portal-feature-reference.md)です。</span><span class="sxs-lookup"><span data-stu-id="69af0-113">For a detailed description of the individual features of the ESB Management Portal, see [ESB Management Portal Feature Reference](../esb-toolkit/esb-management-portal-feature-reference.md).</span></span>  
  
## <a name="esb-portal-technologies"></a><span data-ttu-id="69af0-114">ESB ポータル テクノロジ</span><span class="sxs-lookup"><span data-stu-id="69af0-114">ESB Portal Technologies</span></span>  
 <span data-ttu-id="69af0-115">ESB の管理ポータルでは、次のテクノロジを活用します。</span><span class="sxs-lookup"><span data-stu-id="69af0-115">The ESB Management Portal takes advantage of the following technologies:</span></span>  
  
-   [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
-   <span data-ttu-id="69af0-116">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="69af0-116">ASP.NET</span></span>
  
-   <span data-ttu-id="69af0-117">[エンタープライズ ライブラリ](http://go.microsoft.com/fwlink/?LinkId=188292)([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292))。</span><span class="sxs-lookup"><span data-stu-id="69af0-117">[Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292)).</span></span> <span data-ttu-id="69af0-118">ESB の管理ポータルでは、次のエンタープライズ ライブラリ アセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="69af0-118">The ESB Management Portal uses the following Enterprise Library assemblies:</span></span>  
  
    -   <span data-ttu-id="69af0-119">**Microsoft.Practices.EnterpriseLibrary.Caching**</span><span class="sxs-lookup"><span data-stu-id="69af0-119">**Microsoft.Practices.EnterpriseLibrary.Caching**</span></span>  
  
    -   <span data-ttu-id="69af0-120">**Microsoft.Practices.EnterpriseLibrary.Common**</span><span class="sxs-lookup"><span data-stu-id="69af0-120">**Microsoft.Practices.EnterpriseLibrary.Common**</span></span>  
  
    -   <span data-ttu-id="69af0-121">**Microsoft.Practices.EnterpriseLibrary.Data**</span><span class="sxs-lookup"><span data-stu-id="69af0-121">**Microsoft.Practices.EnterpriseLibrary.Data**</span></span>  
  
    -   <span data-ttu-id="69af0-122">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**</span><span class="sxs-lookup"><span data-stu-id="69af0-122">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**</span></span>  
  
    -   <span data-ttu-id="69af0-123">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**</span><span class="sxs-lookup"><span data-stu-id="69af0-123">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**</span></span>  
  
    -   <span data-ttu-id="69af0-124">**Microsoft.Practices.EnterpriseLibrary.Logging**</span><span class="sxs-lookup"><span data-stu-id="69af0-124">**Microsoft.Practices.EnterpriseLibrary.Logging**</span></span>  
  
    -   <span data-ttu-id="69af0-125">**Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**</span><span class="sxs-lookup"><span data-stu-id="69af0-125">**Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**</span></span>  
  
    -   <span data-ttu-id="69af0-126">**Microsoft.Practices.EnterpriseLibrary.Validation**</span><span class="sxs-lookup"><span data-stu-id="69af0-126">**Microsoft.Practices.EnterpriseLibrary.Validation**</span></span>  
  
    -   <span data-ttu-id="69af0-127">Microsoft.Practices.Unity</span><span class="sxs-lookup"><span data-stu-id="69af0-127">Microsoft.Practices.Unity</span></span>  
  
-   <span data-ttu-id="69af0-128">[Microsoft Chart コントロール](http://go.microsoft.com/fwlink/?LinkId=188293)(http://go.microsoft.com/fwlink/?LinkId=188293) の Microsoft .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="69af0-128">[Microsoft Chart Controls](http://go.microsoft.com/fwlink/?LinkId=188293) (http://go.microsoft.com/fwlink/?LinkId=188293) for Microsoft .NET Framework 4</span></span>  
  
<span data-ttu-id="69af0-129">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外管理システムの障害の追跡にのみメトリックの追跡を拡張します。</span><span class="sxs-lookup"><span data-stu-id="69af0-129">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] metric tracking extends only to fault tracking for the exception management system.</span></span>