---
title: 作成、表示、およびエラーを削除するメッセージのアラート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59df2b40-b42c-4167-873c-0819839919da
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f38c365e1d26c384ff9437059dccbd17f6c2182
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394661"
---
# <a name="creating-viewing-and-deleting-fault-message-alerts"></a><span data-ttu-id="8d0ee-102">エラー メッセージ アラートの作成、表示、および削除</span><span class="sxs-lookup"><span data-stu-id="8d0ee-102">Creating, Viewing, and Deleting Fault Message Alerts</span></span>
<span data-ttu-id="8d0ee-103">ESB 管理ポータルは、ポータルでエラー メッセージが到着したときにアラートを生成する、アラートに対して指定した条件を持つメッセージ内の値の比較に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-103">The ESB Management Portal can generate alerts when fault messages arrive at the portal, based on a comparison of values in the message with criteria specified for the alert.</span></span> <span data-ttu-id="8d0ee-104">ポータルは個々 にリンクされているアラートの通知とユーザーの一覧を管理もでき、事前にアラートを生成するときにこれらのユーザーに通知がします。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-104">The portal can also maintain a list of notifications linked to individual alerts and users, and it will notify these users when it proactively raises alerts.</span></span>  
  
### <a name="to-create-and-configure-a-new-alert"></a><span data-ttu-id="8d0ee-105">作成して、新しいアラートを構成するには</span><span class="sxs-lookup"><span data-stu-id="8d0ee-105">To create and configure a new alert</span></span>  
  
1.  <span data-ttu-id="8d0ee-106">開く、[ポータル アラート ページ](../esb-toolkit/portal-alerts-page.md)にこれらのアラートを現在のサブスクリプションと既存のアラートの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-106">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="8d0ee-107">をクリックして、**アラートの作成**開くためのリンク、[アラート ページの追加](../esb-toolkit/add-alert-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-107">Click the **Create Alert** link to open the [Add Alert Page](../esb-toolkit/add-alert-page.md).</span></span>  
  
3.  <span data-ttu-id="8d0ee-108">**アラート名の入力**テキスト ボックスで、新しい警告の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-108">In the **Enter Alert Name** text box, type a name for the new alert.</span></span>  
  
4.  <span data-ttu-id="8d0ee-109">**条件**セクション、[アラートの追加] ページのフィールドを選択します (など**アプリケーション**、**エラーの種類**、または**エラーの重大度**) で、**条件**ドロップダウン リストは比較の種類を選択します (など +、=、! =、> =、< =、または**など**) で、**演算子**し、ドロップダウン リストを入力または選択を3 番目のリストまたはテキスト ボックスから値 (名前付き**値**)。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-109">In the **Conditions** section of the Add Alert page, select a field (such as **Application**, **Error Type**, or **Fault Severity**) in the **Criteria** drop-down list; select a comparison type (such as +, =, !=, >=, <=, or **like**) in the **Operator** drop-down list; and type or select a value from the third list or text box (named **Value**).</span></span> <span data-ttu-id="8d0ee-110">選択すると、**条件**値、テキスト ボックスまたは一致する値をドロップダウン リストのいずれかを表示するページの変更。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-110">As you select a **Criteria** value, the page changes to display either a text box or a drop-down list for the matching value.</span></span> <span data-ttu-id="8d0ee-111">すべての条件を結合を使用して、 **AND**演算子。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-111">All conditions are combined using the **AND** operator.</span></span>  
  
5.  <span data-ttu-id="8d0ee-112">をクリックして、**追加**リンクの一覧にこの条件を追加して、必要な場合は、さらに条件を追加する前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-112">Click the **Add** link to add this condition to the list, and then repeat the previous step to add more conditions if required.</span></span>  
  
6.  <span data-ttu-id="8d0ee-113">をクリックして、**保存**条件と指定した名前で新しいアラートを作成するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-113">Click the **Save** button to create a new alert with the specified name and conditions.</span></span>  
  
### <a name="to-view-details-of-an-existing-alert-or-delete-an-existing-alert"></a><span data-ttu-id="8d0ee-114">既存のアラートの詳細を表示したり、既存のアラートを削除するには</span><span class="sxs-lookup"><span data-stu-id="8d0ee-114">To view details of an existing alert or delete an existing alert</span></span>  
  
1.  <span data-ttu-id="8d0ee-115">開く、[ポータル アラート ページ](../esb-toolkit/portal-alerts-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-115">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md).</span></span>  
  
2.  <span data-ttu-id="8d0ee-116">アラートを削除しても、**アラートの削除**既存のアラートのアクション列のアイコン。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-116">To delete an alert, click the **Delete Alert** icon in the Action column of an existing alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8d0ee-117">管理者以外のユーザーは、所有者が、このサブスクライバーが存在しない現在アラートのみを削除できます。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-117">Non-administrative users can delete only alerts for which they are an owner, and for which there are currently no subscribers.</span></span> <span data-ttu-id="8d0ee-118">その他のアラートを削除するに管理者としてポータルにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-118">You must log on to the portal as an administrator to delete other alerts.</span></span>  
  
3.  <span data-ttu-id="8d0ee-119">アラートの詳細を表示する をクリックして、**ビュー**既存のアラートのアクション列のアイコン。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-119">To view details of an alert, click the **View** icon in the Action column of an existing alert.</span></span> <span data-ttu-id="8d0ee-120">アラート ビューアー ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-120">This opens the Alert Viewer page.</span></span>  
  
4.  <span data-ttu-id="8d0ee-121">クリックして**Excel にエクスポート**を Microsoft Excel で表示できる形式でアラートの完全な一覧をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8d0ee-121">Click **Export To Excel** to download the complete list of alerts in a format that you can view in Microsoft Excel.</span></span>