---
title: "アプリケーションまたはサービスが時間の経過と共に再送信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e50ea53-421a-4807-a178-a265431f9216
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92d03a631274e88f52cdaa777edb90e678d31ab1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="resubmissions-over-time-by-application-or-service"></a><span data-ttu-id="2295c-102">アプリケーションまたはサービスが時間の経過と共に再送信</span><span class="sxs-lookup"><span data-stu-id="2295c-102">Resubmissions over Time by Application or Service</span></span>
<span data-ttu-id="2295c-103">このオプションは、指定された一連のアプリケーションの指定した期間失敗したメッセージの再送信の数を表示します。</span><span class="sxs-lookup"><span data-stu-id="2295c-103">This option displays a count of failed message resubmissions over a specified period for a specified set of applications.</span></span> <span data-ttu-id="2295c-104">特定のサービスについて、アプリケーション内で時間の経過と共に再送信の数を示す傾向グラフを表示するアプリケーションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="2295c-104">You can select an application to display a trend chart showing the number of resubmissions over time for specific services within the application.</span></span> <span data-ttu-id="2295c-105">特定のサービスを選択するには、そのサービスの再送信を一覧表示するレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2295c-105">Selecting a specific service displays a report that lists the resubmissions for that service.</span></span> <span data-ttu-id="2295c-106">Microsoft Excel のスプレッドシートとしての再送信の一覧をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2295c-106">You can also export the list of resubmissions as a Microsoft Excel spreadsheet.</span></span>  
  
### <a name="to-view-charts-and-lists-of-resubmissions-over-time-by-application-or-service"></a><span data-ttu-id="2295c-107">アプリケーションまたはサービスによって、時間の経過と共にグラフとの再送信のリストを表示するには</span><span class="sxs-lookup"><span data-stu-id="2295c-107">To view charts and lists of resubmissions over time by application or service</span></span>  
  
1.  <span data-ttu-id="2295c-108">開く、[ポータル レポート ページ](../esb-toolkit/portal-reports-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="2295c-108">Open the [Portal Reports Page](../esb-toolkit/portal-reports-page.md).</span></span>  
  
2.  <span data-ttu-id="2295c-109">クリックして、**アプリケーションの選択**最初のグラフの上にリンクし、選択するか表示されるインストール済みの Microsoft BizTalk Server アプリケーションの一覧にあるチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="2295c-109">Click the **Select Applications** link above the first chart, and then select or clear the check boxes in the list of installed Microsoft BizTalk Server applications that appears.</span></span> <span data-ttu-id="2295c-110">また、またはすべてのアプリケーションの選択を表示するリンクを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2295c-110">You can also use the links that appear to select all or none of the applications.</span></span> <span data-ttu-id="2295c-111">をクリックして**保存**選択されたアプリケーションについての情報を表示またはをクリックする**キャンセル**変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="2295c-111">Click **Save** to show the information for the selected applications, or click **Cancel** to abandon your changes.</span></span>  
  
3.  <span data-ttu-id="2295c-112">グラフの情報を表示する期間を変更するには、次のように選択します。**時間、日、週、月、四半期、年、**または**すべて**最初のグラフ上のドロップダウン リストでします。</span><span class="sxs-lookup"><span data-stu-id="2295c-112">To change the period for which the charts display information, select **Hour, Day, Week, Month, Quarter, Year,** or **ALL** in the drop-down list above the first chart.</span></span>  
  
4.  <span data-ttu-id="2295c-113">そのアプリケーション内のサービスごとの再送信のトレンド グラフを表示するには、グラフのキー」セクションでアプリケーションの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2295c-113">Click the name of an application in the chart keys section to display a trend chart for resubmissions for each of the services within that application.</span></span>  
  
5.  <span data-ttu-id="2295c-114">選択したサービスに再送信をすべて一覧表示するテーブルを表示するには、このグラフでのサービスの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2295c-114">Click the name of a service in this chart to display a table listing all the resubmissions for the selected service.</span></span>  
  
6.  <span data-ttu-id="2295c-115">をクリックして**Excel にエクスポート**Microsoft Excel で表示できる形式で再送信の一覧をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2295c-115">Click **Export To Excel** to download the list of resubmissions in a format that you can view in Microsoft Excel.</span></span>