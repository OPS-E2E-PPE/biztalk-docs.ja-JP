---
title: ポータル ページのエラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b11e3492-da1a-43f3-acf8-3775b5cbc2c5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 294ba24516cccbf6c15ada26d28f169a6eb45c98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294610"
---
# <a name="portal-faults-page"></a><span data-ttu-id="64780-102">ポータルのエラー ページ</span><span class="sxs-lookup"><span data-stu-id="64780-102">Portal Faults Page</span></span>
<span data-ttu-id="64780-103">図 1 は、エラー ページを示します。</span><span class="sxs-lookup"><span data-stu-id="64780-103">Figure 1 shows the Faults page.</span></span> <span data-ttu-id="64780-104">このページは、各エラーの主なプロパティを表示し、並べ替えやフィルタ リングのエラーの種類や時間などの条件の範囲内でエラーの詳細な分析をサポートする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="64780-104">This page displays the main properties of each fault, and it provides sorting and filtering capabilities that support detailed analysis of faults over a range of criteria, such as error type and time.</span></span> <span data-ttu-id="64780-105">それぞれの障害へのリンクでは、フォールト メッセージ ビューアーで詳細を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="64780-105">A link for each fault allows you to view more details in the Fault Message Viewer.</span></span>  
  
 <span data-ttu-id="64780-106">![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")</span><span class="sxs-lookup"><span data-stu-id="64780-106">![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")</span></span>  
  
 <span data-ttu-id="64780-107">**図 1**</span><span class="sxs-lookup"><span data-stu-id="64780-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="64780-108">**ESB の管理ポータルの [エラー] ページ**</span><span class="sxs-lookup"><span data-stu-id="64780-108">**The Faults page of the ESB Management Portal**</span></span>  
  
 <span data-ttu-id="64780-109">次の一覧では、ESB 管理ポータルのエラー ページの機能を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64780-109">The following list explains how you can use the features of the ESB Management Portal Faults page:</span></span>  
  
-   <span data-ttu-id="64780-110">ページに表示されるエラーの一覧をフィルター処理するには、エラーの一覧の上のテキスト ボックス、ドロップダウン リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="64780-110">To filter the list of faults displayed in the page, use the drop-down lists and text boxes above the list of faults.</span></span> <span data-ttu-id="64780-111">次のように表示される行をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="64780-111">You can filter the rows displayed in the following ways:</span></span>  
  
    -   <span data-ttu-id="64780-112">インストール済みの BizTalk アプリケーションのいずれかを選択して、**アプリケーション**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="64780-112">Select any one of the installed BizTalk applications in the **Application** drop-down list.</span></span>  
  
    -   <span data-ttu-id="64780-113">選択して、障害が発生した期間を指定**時間、日、週、月、四半期、年、** または**すべて**で、**最後内のレコードを取得**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="64780-113">Specify the period within which the fault occurred by selecting **hour, day, week, month, quarter, year,** or **all** in the **Retrieve records within last** drop-down list.</span></span>  
  
    -   <span data-ttu-id="64780-114">内のページに表示する行の数を指定、 **1 ページあたりのレコード**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="64780-114">Specify how many rows you want to display on the page in the **Records Per Page** drop-down list.</span></span>  
  
    -   <span data-ttu-id="64780-115">エラー コード番号を入力、**フォールト コード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="64780-115">Type a fault code number in the **Fault Code** text box.</span></span>  
  
    -   <span data-ttu-id="64780-116">障害カテゴリ名の一部またはすべてを入力、**エラー分類**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="64780-116">Type all or part of the fault category name in the **Fault Category** text box.</span></span>  
  
    -   <span data-ttu-id="64780-117">エラーの種類のテキストの一部またはすべてを入力、**エラーの種類**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="64780-117">Type all or part of the error type text in the **Error Type** text box.</span></span>  
  
    -   <span data-ttu-id="64780-118">最小および最大のエラーの重大度の値を入力 (など**警告、エラー、重大、** または**重大**) で、 **Min エラーの重大度**と**Max エラー重大度**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="64780-118">Type a value for the minimum and/or maximum fault severity (such as **Warning, Error, Severe,** or **Critical**) in the **Min Fault Severity** and **Max Fault Severity** text boxes.</span></span>  
  
-   <span data-ttu-id="64780-119">これらのコントロールの 1 つ以上の値を指定した後にをクリックして、**フィルターの適用**指定されたすべての条件を適用するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="64780-119">After you specify the values for one or more of these controls, click the **Apply Filters** button to apply all the specified criteria.</span></span>  
  
-   <span data-ttu-id="64780-120">その列の内容の順序でフォールト メッセージ行を表示する列見出しをクリックし、もう一度クリックして一覧の逆の順序で表示します。</span><span class="sxs-lookup"><span data-stu-id="64780-120">Click a column heading to display the fault message rows in the order of that column contents, and then click again to display the list in reverse order.</span></span>  
  
-   <span data-ttu-id="64780-121">一覧に表示されるエラーの詳細を表示する編集が含まれているメッセージを再送信、内をクリックしてで開くには、そのエラーの行、[ポータル フォールト メッセージ ビューアー](../esb-toolkit/portal-fault-message-viewer.md)です。</span><span class="sxs-lookup"><span data-stu-id="64780-121">To display more details of a fault shown in the list, or to edit and resubmit the message it contains, click anywhere in the row for that fault to open it in the [Portal Fault Message Viewer](../esb-toolkit/portal-fault-message-viewer.md).</span></span>