---
title: アラート ([管理] ビュー) を管理する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27f8bf7d-15b7-448d-8c13-e4969b90d021
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc5472e96414fe5141de27630ebe3c810d2df28c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294442"
---
# <a name="manage-alerts-administration-view"></a><span data-ttu-id="30753-102">アラート ([管理] ビュー) を管理します。</span><span class="sxs-lookup"><span data-stu-id="30753-102">Manage Alerts (Administration View)</span></span>
<span data-ttu-id="30753-103">図 1 は、管理者を使用してすべての通知とユーザーのアクティビティの概要の一覧を表示、管理ビューで、[アラート] ページを示します。</span><span class="sxs-lookup"><span data-stu-id="30753-103">Figure 1 shows the Alerts page in administration view, which administrators can use to view a list of all alerts and a summary of their activity.</span></span> <span data-ttu-id="30753-104">テーブルには、各アラートについての行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="30753-104">A table displays a row for each alert.</span></span> <span data-ttu-id="30753-105">各行は、警告名、作成者の名前、(最後の 1 時間、日、または月以内のアラートのアクティブ化の数) などのアラートの全般的な統計を示していますリンクで、アラートの一覧、および cli のセットを含むアクション列を表示するサブスクライバーの数。アラートの操作を実行する ckable アイコン。</span><span class="sxs-lookup"><span data-stu-id="30753-105">Each row shows the alert name, the name of the creator, general statistics for the alert (such as number of alert activations within the last hour, day, or month), a count of subscribers for the alerts with a link to view a list, and an Actions column containing a set of clickable icons to perform actions on the alert.</span></span>  
  
 <span data-ttu-id="30753-106">![[アラート] ページを管理](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8 ManageAlertsPage")</span><span class="sxs-lookup"><span data-stu-id="30753-106">![Manage Alerts Page](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8-ManageAlertsPage")</span></span>  
  
 <span data-ttu-id="30753-107">**図 1**</span><span class="sxs-lookup"><span data-stu-id="30753-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="30753-108">**ESB の管理ポータルの管理に関するアラート ([管理] ビュー) ページ**</span><span class="sxs-lookup"><span data-stu-id="30753-108">**The ESB Management Portal Manage Alerts (Administration view) page**</span></span>  
  
 <span data-ttu-id="30753-109">次の一覧では、ESB 管理ポータルの [警告] ページの機能を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="30753-109">The following list explains how you can use the features of the ESB Management Portal Manage Alerts page:</span></span>  
  
-   <span data-ttu-id="30753-110">クリックして、**アラートの作成**新しい警告を作成するページの上部にあるリンクします。</span><span class="sxs-lookup"><span data-stu-id="30753-110">Click the **Create Alert** link at the top of the page to create a new alert.</span></span>  
  
-   <span data-ttu-id="30753-111">クリックして、 **Excel にエクスポート**アラートの一覧を Microsoft Excel のスプレッドシートとしてエクスポートへのリンク。</span><span class="sxs-lookup"><span data-stu-id="30753-111">Click the **Export To Excel** link to export the list of alerts as a Microsoft Excel spreadsheet.</span></span>  
  
-   <span data-ttu-id="30753-112">クリックして、+**ビュー サブスクライバー**警告のサブスクライバーの一覧を表示する行にリンクします。</span><span class="sxs-lookup"><span data-stu-id="30753-112">Click the + **View Subscribers** link in a row to show a list of subscribers for the alert.</span></span> <span data-ttu-id="30753-113">一覧が、行内で展開し、管理者は、サブスクライバーを警告から削除できるようにするそれぞれの [アクション] 列で、削除アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30753-113">The list expands within the row, and a delete icon appears in the Actions column for each one that allows administrators to remove a subscriber from the alert.</span></span> <span data-ttu-id="30753-114">同時に、リンクの変更-**を非表示にサブスクライバー**サブスクライバーの一覧を縮小することができます。</span><span class="sxs-lookup"><span data-stu-id="30753-114">At the same time, the link changes to - **Hide Subscribers**, allowing you to collapse the list of subscribers.</span></span>  
  
-   <span data-ttu-id="30753-115">その行でアラートのタスクを実行するアクション列にアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="30753-115">Click an icon in the Actions column to perform a task for the alerts in that row.</span></span> <span data-ttu-id="30753-116">(表示される順) にアイコンとタスク次に示します。</span><span class="sxs-lookup"><span data-stu-id="30753-116">The icons (in the order they appear) and the tasks are the following:</span></span>  
  
    -   <span data-ttu-id="30753-117">**アラートの詳細を表示します。**</span><span class="sxs-lookup"><span data-stu-id="30753-117">**View alert details.**</span></span> <span data-ttu-id="30753-118">このアイコンは、選択したアラートの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="30753-118">This icon displays details of the selected alert.</span></span>  
  
    -   <span data-ttu-id="30753-119">**履歴を表示**です。</span><span class="sxs-lookup"><span data-stu-id="30753-119">**View history**.</span></span> <span data-ttu-id="30753-120">このアイコンは、選択したアラートのすべてのアクティブ化を含むテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="30753-120">This icon displays a table containing all the activations for the selected alert.</span></span>  
  
    -   <span data-ttu-id="30753-121">**サブスクライバーの追加**です。</span><span class="sxs-lookup"><span data-stu-id="30753-121">**Add subscriber**.</span></span> <span data-ttu-id="30753-122">このアイコンでは、選択したアラートにサブスクライバーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="30753-122">This icon allows administrators to add a subscriber to the selected alert.</span></span>  
  
    -   <span data-ttu-id="30753-123">**警告の編集**です。</span><span class="sxs-lookup"><span data-stu-id="30753-123">**Edit alert**.</span></span> <span data-ttu-id="30753-124">このリンクでは、アラートの詳細を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="30753-124">This link allows administrators to edit the alert details.</span></span>  
  
    -   <span data-ttu-id="30753-125">**アラートを削除**です。</span><span class="sxs-lookup"><span data-stu-id="30753-125">**Delete alert**.</span></span> <span data-ttu-id="30753-126">このリンクは、アラートと関連付けられているすべてのサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="30753-126">This link deletes the alert and all associated subscriptions.</span></span>