---
title: アプリケーションまたはサービスによって送信推移 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e50ea53-421a-4807-a178-a265431f9216
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c6b9ac149f241c0069de05bcd7b1478367c7321
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400205"
---
# <a name="resubmissions-over-time-by-application-or-service"></a><span data-ttu-id="96642-102">アプリケーションまたはサービスによって送信推移</span><span class="sxs-lookup"><span data-stu-id="96642-102">Resubmissions over Time by Application or Service</span></span>
<span data-ttu-id="96642-103">このオプションは、アプリケーションの指定されたセットの指定された期間に失敗したメッセージの再送信の数を表示します。</span><span class="sxs-lookup"><span data-stu-id="96642-103">This option displays a count of failed message resubmissions over a specified period for a specified set of applications.</span></span> <span data-ttu-id="96642-104">特定のサービス、アプリケーション内で時間の経過と共に再送信の数を示す傾向グラフを表示するアプリケーションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="96642-104">You can select an application to display a trend chart showing the number of resubmissions over time for specific services within the application.</span></span> <span data-ttu-id="96642-105">特定のサービスを選択するには、そのサービスの再送信を示すレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96642-105">Selecting a specific service displays a report that lists the resubmissions for that service.</span></span> <span data-ttu-id="96642-106">Microsoft Excel のスプレッドシートとしての再送信の一覧をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="96642-106">You can also export the list of resubmissions as a Microsoft Excel spreadsheet.</span></span>  
  
### <a name="to-view-charts-and-lists-of-resubmissions-over-time-by-application-or-service"></a><span data-ttu-id="96642-107">アプリケーションまたはサービス別、時間の経過と共にグラフと再送信のリストを表示するには</span><span class="sxs-lookup"><span data-stu-id="96642-107">To view charts and lists of resubmissions over time by application or service</span></span>  
  
1.  <span data-ttu-id="96642-108">開く、[ポータル レポート ページ](../esb-toolkit/portal-reports-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="96642-108">Open the [Portal Reports Page](../esb-toolkit/portal-reports-page.md).</span></span>  
  
2.  <span data-ttu-id="96642-109">をクリックして、**アプリケーションの選択**最初のグラフの上にリンクし選択するか表示されるインストール済みの Microsoft BizTalk Server アプリケーションの一覧でチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="96642-109">Click the **Select Applications** link above the first chart, and then select or clear the check boxes in the list of installed Microsoft BizTalk Server applications that appears.</span></span> <span data-ttu-id="96642-110">またはすべてのアプリケーションを選択して表示されるリンクを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="96642-110">You can also use the links that appear to select all or none of the applications.</span></span> <span data-ttu-id="96642-111">をクリックして**保存**選択したアプリケーションの情報を表示する**キャンセル**変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="96642-111">Click **Save** to show the information for the selected applications, or click **Cancel** to abandon your changes.</span></span>  
  
3.  <span data-ttu-id="96642-112">グラフの情報を表示する期間を変更するには、次のように選択します。**時間、日、週、月、四半期、年、** または**すべて**最初のグラフの上のドロップダウン リストでします。</span><span class="sxs-lookup"><span data-stu-id="96642-112">To change the period for which the charts display information, select **Hour, Day, Week, Month, Quarter, Year,** or **ALL** in the drop-down list above the first chart.</span></span>  
  
4.  <span data-ttu-id="96642-113">そのアプリケーション内のサービスごとの再送信のトレンド グラフを表示するには、グラフ キー セクションでアプリケーションの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96642-113">Click the name of an application in the chart keys section to display a trend chart for resubmissions for each of the services within that application.</span></span>  
  
5.  <span data-ttu-id="96642-114">選択したサービスの再送信をすべて一覧表示するテーブルを表示するには、このグラフでのサービスの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96642-114">Click the name of a service in this chart to display a table listing all the resubmissions for the selected service.</span></span>  
  
6.  <span data-ttu-id="96642-115">クリックして**Excel にエクスポート**Microsoft Excel で表示できる形式での再送信の一覧をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="96642-115">Click **Export To Excel** to download the list of resubmissions in a format that you can view in Microsoft Excel.</span></span>