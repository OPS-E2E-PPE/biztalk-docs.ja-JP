---
title: アラート ([管理] ビュー) の管理 |Microsoft Docs
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
ms.openlocfilehash: 71c73788b50154aa49e1773f8c3dc072a81c36a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261454"
---
# <a name="manage-alerts-administration-view"></a><span data-ttu-id="bc4ee-102">アラート ([管理] ビュー) の管理します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-102">Manage Alerts (Administration View)</span></span>
<span data-ttu-id="bc4ee-103">図 1 は、管理ビューは、管理者はすべてのアラートとアクティビティの概要の一覧を表示する使用して、[アラート] ページを示します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-103">Figure 1 shows the Alerts page in administration view, which administrators can use to view a list of all alerts and a summary of their activity.</span></span> <span data-ttu-id="bc4ee-104">テーブルは、各アラートの行を表示します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-104">A table displays a row for each alert.</span></span> <span data-ttu-id="bc4ee-105">行ごとに示します、警告名、作成者の名前、全般的な統計 (最後の 1 時間、日、または 1 か月以内のアラートのアクティブ化の数) などのアラートの一覧、および cli のセットを含むアクション列を表示するリンクを含むアラートのサブスクライバーの数アラートのアクションを実行する ckable アイコン。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-105">Each row shows the alert name, the name of the creator, general statistics for the alert (such as number of alert activations within the last hour, day, or month), a count of subscribers for the alerts with a link to view a list, and an Actions column containing a set of clickable icons to perform actions on the alert.</span></span>  
  
 <span data-ttu-id="bc4ee-106">![[アラート] ページを管理](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8 ManageAlertsPage")</span><span class="sxs-lookup"><span data-stu-id="bc4ee-106">![Manage Alerts Page](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8-ManageAlertsPage")</span></span>  
  
 <span data-ttu-id="bc4ee-107">**図 1**</span><span class="sxs-lookup"><span data-stu-id="bc4ee-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="bc4ee-108">**ESB 管理ポータル管理アラート (管理 ビュー) ページ**</span><span class="sxs-lookup"><span data-stu-id="bc4ee-108">**The ESB Management Portal Manage Alerts (Administration view) page**</span></span>  
  
 <span data-ttu-id="bc4ee-109">次の一覧では、ESB 管理ポータルの管理 [アラート] ページの機能を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-109">The following list explains how you can use the features of the ESB Management Portal Manage Alerts page:</span></span>  
  
-   <span data-ttu-id="bc4ee-110">をクリックして、**アラートの作成**新しいアラートを作成するページの上部にあるリンクです。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-110">Click the **Create Alert** link at the top of the page to create a new alert.</span></span>  
  
-   <span data-ttu-id="bc4ee-111">をクリックして、 **Excel にエクスポート**アラートの一覧を Microsoft Excel のスプレッドシートとしてエクスポートへのリンク。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-111">Click the **Export To Excel** link to export the list of alerts as a Microsoft Excel spreadsheet.</span></span>  
  
-   <span data-ttu-id="bc4ee-112">をクリックして、+**のサブスクライバーの表示**警告のサブスクライバーの一覧を表示する行にリンクします。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-112">Click the + **View Subscribers** link in a row to show a list of subscribers for the alert.</span></span> <span data-ttu-id="bc4ee-113">リストが、行内で展開され、管理者は、サブスクライバーを警告から削除できるようにするそれぞれのアクション 列に削除アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-113">The list expands within the row, and a delete icon appears in the Actions column for each one that allows administrators to remove a subscriber from the alert.</span></span> <span data-ttu-id="bc4ee-114">同時に、リンクの変更-**サブスクライバーの非表示にする**サブスクライバーの一覧を縮小することができます。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-114">At the same time, the link changes to - **Hide Subscribers**, allowing you to collapse the list of subscribers.</span></span>  
  
-   <span data-ttu-id="bc4ee-115">その行でアラートのタスクを実行するアクション 列にアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-115">Click an icon in the Actions column to perform a task for the alerts in that row.</span></span> <span data-ttu-id="bc4ee-116">(表示される順序) のアイコンと、タスク、次に示します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-116">The icons (in the order they appear) and the tasks are the following:</span></span>  
  
    -   <span data-ttu-id="bc4ee-117">**アラートの詳細を表示します。**</span><span class="sxs-lookup"><span data-stu-id="bc4ee-117">**View alert details.**</span></span> <span data-ttu-id="bc4ee-118">このアイコンは、選択したアラートの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-118">This icon displays details of the selected alert.</span></span>  
  
    -   <span data-ttu-id="bc4ee-119">**履歴を表示**します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-119">**View history**.</span></span> <span data-ttu-id="bc4ee-120">このアイコンは、選択したアラートのすべてのアクティブ化を含むテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-120">This icon displays a table containing all the activations for the selected alert.</span></span>  
  
    -   <span data-ttu-id="bc4ee-121">**サブスクライバーの追加**します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-121">**Add subscriber**.</span></span> <span data-ttu-id="bc4ee-122">このアイコンでは、選択したアラートにサブスクライバーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-122">This icon allows administrators to add a subscriber to the selected alert.</span></span>  
  
    -   <span data-ttu-id="bc4ee-123">**警告の編集**します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-123">**Edit alert**.</span></span> <span data-ttu-id="bc4ee-124">このリンクでは、アラートの詳細を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-124">This link allows administrators to edit the alert details.</span></span>  
  
    -   <span data-ttu-id="bc4ee-125">**アラートを削除**します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-125">**Delete alert**.</span></span> <span data-ttu-id="bc4ee-126">このリンクは、アラートと関連付けられているすべてのサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="bc4ee-126">This link deletes the alert and all associated subscriptions.</span></span>