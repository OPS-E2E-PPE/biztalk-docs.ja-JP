---
title: アプリケーションまたはサービス別の時間の経過と共にエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51fdbf8a-1e5f-4054-b8b1-e85b5de399c4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ead0c4da960081736d29412bf426b7f715bb3e31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295328"
---
# <a name="faults-over-time-by-application-or-service"></a><span data-ttu-id="e9a72-102">アプリケーションまたはサービス別の時間の経過と共にエラー</span><span class="sxs-lookup"><span data-stu-id="e9a72-102">Faults over Time by Application or Service</span></span>
<span data-ttu-id="e9a72-103">このオプションは、アプリケーションの指定されたセットの指定された期間に、エラーの数を表示します。</span><span class="sxs-lookup"><span data-stu-id="e9a72-103">This option displays a count of faults over a specified period for a specified set of applications.</span></span> <span data-ttu-id="e9a72-104">特定のサービス、アプリケーション内で時間の経過と共にエラーの数を示す傾向グラフを表示するアプリケーションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="e9a72-104">You can select an application to display a trend chart that shows the number of faults over time for specific services within the application.</span></span> <span data-ttu-id="e9a72-105">特定のサービスを選択するには、そのサービスのエラーを示すレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9a72-105">Selecting a specific service displays a report that lists the faults for that service.</span></span> <span data-ttu-id="e9a72-106">Microsoft Excel のスプレッドシートとしてエラーの一覧をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e9a72-106">You can also export the list of faults as a Microsoft Excel spreadsheet.</span></span>  
  
### <a name="to-view-charts-and-lists-of-faults-over-time-by-application-or-service"></a><span data-ttu-id="e9a72-107">アプリケーションまたはサービス別、時間の経過と共にグラフとエラーの一覧を表示するには</span><span class="sxs-lookup"><span data-stu-id="e9a72-107">To view charts and lists of faults over time by application or service</span></span>  
  
1.  <span data-ttu-id="e9a72-108">開く、[ポータル レポート ページ](../esb-toolkit/portal-reports-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9a72-108">Open the [Portal Reports Page](../esb-toolkit/portal-reports-page.md).</span></span>  
  
2.  <span data-ttu-id="e9a72-109">をクリックして、**アプリケーションの選択**最初のグラフの上にリンクし選択するか表示されるインストール済みの Microsoft BizTalk Server アプリケーションの一覧でチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e9a72-109">Click the **Select Applications** link above the first chart, and then select or clear the check boxes in the list of installed Microsoft BizTalk Server applications that appears.</span></span> <span data-ttu-id="e9a72-110">またはすべてのアプリケーションを選択して表示されるリンクを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9a72-110">You can also use the links that appear to select all or none of the applications.</span></span> <span data-ttu-id="e9a72-111">をクリックして**保存**選択したアプリケーションの情報を表示する**キャンセル**変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="e9a72-111">Click **Save** to show the information for the selected applications, or click **Cancel** to abandon your changes.</span></span>  
  
3.  <span data-ttu-id="e9a72-112">グラフの情報を表示する期間を変更するには、次のように選択します。**時間、日、週、月、四半期、年、** または**すべて**最初のグラフの上のドロップダウン リストでします。</span><span class="sxs-lookup"><span data-stu-id="e9a72-112">To change the period for which the charts display information, select **Hour, Day, Week, Month, Quarter, Year,** or **ALL** in the drop-down list above the first chart.</span></span>  
  
4.  <span data-ttu-id="e9a72-113">各アプリケーション内でサービスのエラーの傾向グラフを表示するには、グラフ キー セクションでアプリケーションの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9a72-113">Click the name of an application in the chart keys section to display a trend chart for faults for each of the services within that application.</span></span>  
  
5.  <span data-ttu-id="e9a72-114">選択したサービスのすべてのエラーの一覧を表示するには、このグラフでのサービスの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9a72-114">Click the name of a service in this chart to display a table listing all the faults for the selected service.</span></span>  
  
6.  <span data-ttu-id="e9a72-115">クリックして**Excel にエクスポート**Microsoft Excel で表示できる形式でのエラーの一覧をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e9a72-115">Click **Export To Excel** to download the list of faults in a format that you can view in Microsoft Excel.</span></span>