---
title: "メッセージのアラートの作成、表示、およびエラーを削除する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59df2b40-b42c-4167-873c-0819839919da
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9451ecb9cbeaf2077712f6e6b55a36dab7988c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-viewing-and-deleting-fault-message-alerts"></a><span data-ttu-id="42e1c-102">作成、表示、およびエラー メッセージの通知を削除します。</span><span class="sxs-lookup"><span data-stu-id="42e1c-102">Creating, Viewing, and Deleting Fault Message Alerts</span></span>
<span data-ttu-id="42e1c-103">ポータルから、エラー メッセージが受信したときに、ESB の管理ポータルがアラートを生成することができます、アラートの指定された条件と、メッセージ内の値の比較に基づいています。</span><span class="sxs-lookup"><span data-stu-id="42e1c-103">The ESB Management Portal can generate alerts when fault messages arrive at the portal, based on a comparison of values in the message with criteria specified for the alert.</span></span> <span data-ttu-id="42e1c-104">ポータルでは個別にリンクされているアラートの通知とユーザーのリストを保持してもと、事前にアラートを生成するときにこれらのユーザーが通知します。</span><span class="sxs-lookup"><span data-stu-id="42e1c-104">The portal can also maintain a list of notifications linked to individual alerts and users, and it will notify these users when it proactively raises alerts.</span></span>  
  
### <a name="to-create-and-configure-a-new-alert"></a><span data-ttu-id="42e1c-105">作成して、新しいアラートを構成するには</span><span class="sxs-lookup"><span data-stu-id="42e1c-105">To create and configure a new alert</span></span>  
  
1.  <span data-ttu-id="42e1c-106">開く、[ポータル アラート ページ](../esb-toolkit/portal-alerts-page.md)に既存のアラートの一覧と、これらのアラートを現在のサブスクリプションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e1c-106">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="42e1c-107">クリックして、**警告の作成**開くためのリンク、[アラート ページの追加](../esb-toolkit/add-alert-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="42e1c-107">Click the **Create Alert** link to open the [Add Alert Page](../esb-toolkit/add-alert-page.md).</span></span>  
  
3.  <span data-ttu-id="42e1c-108">**アラート名の入力**テキスト ボックスで、新しい警告の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="42e1c-108">In the **Enter Alert Name** text box, type a name for the new alert.</span></span>  
  
4.  <span data-ttu-id="42e1c-109">**条件**セクションのアラートの追加 ページで、フィールドを選択します (など**アプリケーション**、**エラーの種類**、または**エラーの重大度**) で、**条件**ドロップ ダウン リスト以外の比較の種類を選択 (など、+、=、! =、> =、 \<=、または**と同様に**) で、**演算子**ドロップダウン リストと型3 番目のリストまたはテキスト ボックスから値を選択または (という**値**)。</span><span class="sxs-lookup"><span data-stu-id="42e1c-109">In the **Conditions** section of the Add Alert page, select a field (such as **Application**, **Error Type**, or **Fault Severity**) in the **Criteria** drop-down list; select a comparison type (such as +, =, !=, >=, \<=, or **like**) in the **Operator** drop-down list; and type or select a value from the third list or text box (named **Value**).</span></span> <span data-ttu-id="42e1c-110">選択すると、**条件**値に設定するページが変更され、テキスト ボックスまたは一致する値をドロップダウン リストを表示します。</span><span class="sxs-lookup"><span data-stu-id="42e1c-110">As you select a **Criteria** value, the page changes to display either a text box or a drop-down list for the matching value.</span></span> <span data-ttu-id="42e1c-111">使用してすべての条件が結合され、 **AND**演算子。</span><span class="sxs-lookup"><span data-stu-id="42e1c-111">All conditions are combined using the **AND** operator.</span></span>  
  
5.  <span data-ttu-id="42e1c-112">クリックして、**追加**リンクの一覧にこの条件を追加して、必要な場合は、他の条件を追加する前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="42e1c-112">Click the **Add** link to add this condition to the list, and then repeat the previous step to add more conditions if required.</span></span>  
  
6.  <span data-ttu-id="42e1c-113">クリックして、**保存**条件と指定した名前で新しいアラートを作成するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="42e1c-113">Click the **Save** button to create a new alert with the specified name and conditions.</span></span>  
  
### <a name="to-view-details-of-an-existing-alert-or-delete-an-existing-alert"></a><span data-ttu-id="42e1c-114">既存のアラートの詳細を表示したり、既存のアラートを削除するには</span><span class="sxs-lookup"><span data-stu-id="42e1c-114">To view details of an existing alert or delete an existing alert</span></span>  
  
1.  <span data-ttu-id="42e1c-115">開く、[ポータル警告 ページ](../esb-toolkit/portal-alerts-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="42e1c-115">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md).</span></span>  
  
2.  <span data-ttu-id="42e1c-116">アラートを削除しても、**アラートの削除**既存のアラートの [アクション] 列のアイコン。</span><span class="sxs-lookup"><span data-stu-id="42e1c-116">To delete an alert, click the **Delete Alert** icon in the Action column of an existing alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42e1c-117">管理者以外のユーザーには、顧客が所有者、およびをサブスクライバーが存在しない現在のアラートのみを削除できます。</span><span class="sxs-lookup"><span data-stu-id="42e1c-117">Non-administrative users can delete only alerts for which they are an owner, and for which there are currently no subscribers.</span></span> <span data-ttu-id="42e1c-118">他の通知を削除して、管理者として、ポータルにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42e1c-118">You must log on to the portal as an administrator to delete other alerts.</span></span>  
  
3.  <span data-ttu-id="42e1c-119">アラートの詳細を表示する をクリックして、**ビュー**既存のアラートの アクション 列のアイコン。</span><span class="sxs-lookup"><span data-stu-id="42e1c-119">To view details of an alert, click the **View** icon in the Action column of an existing alert.</span></span> <span data-ttu-id="42e1c-120">これは、アラート ビューアー ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="42e1c-120">This opens the Alert Viewer page.</span></span>  
  
4.  <span data-ttu-id="42e1c-121">をクリックして**Excel にエクスポート**Microsoft Excel で表示できる形式でアラートの完全な一覧をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="42e1c-121">Click **Export To Excel** to download the complete list of alerts in a format that you can view in Microsoft Excel.</span></span>