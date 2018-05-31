---
title: アラートを購読する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfa46b63-c1c7-47cd-86b0-557fd322dc8f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02ef5f136002f5afca6e062362b92d25a20baa99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295482"
---
# <a name="subscribing-to-alerts"></a><span data-ttu-id="fb078-102">アラートを購読するには</span><span class="sxs-lookup"><span data-stu-id="fb078-102">Subscribing to Alerts</span></span>
### <a name="to-subscribe-to-an-alert"></a><span data-ttu-id="fb078-103">警告をサブスクライブするには</span><span class="sxs-lookup"><span data-stu-id="fb078-103">To subscribe to an alert</span></span>  
  
1.  <span data-ttu-id="fb078-104">開く、[ポータル アラート ページ](../esb-toolkit/portal-alerts-page.md)に既存のアラートの一覧と、これらのアラートを現在のサブスクリプションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb078-104">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="fb078-105">[アクション] 列、 **AddSubscriber**既存のアラートのアイコン。</span><span class="sxs-lookup"><span data-stu-id="fb078-105">In the Action column, click the **AddSubscriber** icon for an existing alert.</span></span> <span data-ttu-id="fb078-106">開き、[アラート サブスクリプションの追加およびサブスクリプション ページの編集](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)です。</span><span class="sxs-lookup"><span data-stu-id="fb078-106">This opens the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
3.  <span data-ttu-id="fb078-107">ポータルでは、ポータルへのアクセスに使用するアカウントに関連付けられている電子メール アドレスにアラート通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="fb078-107">The portal sends alert notifications to the e-mail address associated with the account you use to access the portal.</span></span> <span data-ttu-id="fb078-108">別の電子メール アドレスを使用するには、横にチェック ボックスを選択、**カスタム電子メール**テキスト ボックス、およびテキスト ボックスに優先電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="fb078-108">If you want to use a different e-mail address, select the check box next to the **Custom Email** text box, and then type the preferred e-mail address in the text box.</span></span>  
  
4.  <span data-ttu-id="fb078-109">チェック ボックスをオン、**スケジュール**セクションで、ポータルのアラートを送信するとで期間の開始と終了時刻を指定する必要がありますと期間を指定する場合、 **Start Time**と**EndTime**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="fb078-109">Select the check box in the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **EndTime** drop-down lists.</span></span>  
  
5.  <span data-ttu-id="fb078-110">ときにすることはできませんが表示され、アラートに対して操作を実行する期間がある場合で開始と終了日を入力、**ブラック アウト期間**ボックス。</span><span class="sxs-lookup"><span data-stu-id="fb078-110">If there is a period when you will be unable to receive and act upon alerts, type the start and end dates in the **Black-out Period** boxes.</span></span>  
  
6.  <span data-ttu-id="fb078-111">選択、**間隔**で**分**ポータルが発生したアラートの比較し、同じアラートの複数のインスタンスが発生した場合は、1 つのみを送信中にします。</span><span class="sxs-lookup"><span data-stu-id="fb078-111">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="fb078-112">これは、迅速に発生したエラーが多数の同一の警告メッセージを作成することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="fb078-112">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
7.  <span data-ttu-id="fb078-113">クリックして、**保存**クリックすると、新しいサブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb078-113">Click the **Save** button to create the new subscription.</span></span>  
  
### <a name="to-edit-an-existing-alert-subscription"></a><span data-ttu-id="fb078-114">既存のアラート配信登録を編集するには</span><span class="sxs-lookup"><span data-stu-id="fb078-114">To edit an existing alert subscription</span></span>  
  
1.  <span data-ttu-id="fb078-115">開く、[ポータル アラート ページ](../esb-toolkit/portal-alerts-page.md)に既存のアラートの一覧と、これらのアラートを現在のサブスクリプションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb078-115">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="fb078-116">クリックして、**編集**の一覧で、変更するサブスクリプションの隣にあるリンク、**個人用サブスクリプション**を開くには、ページのセクションで、[アラート サブスクリプションの追加とサブスクリプションページの編集](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span><span class="sxs-lookup"><span data-stu-id="fb078-116">Click the **Edit** link next to the subscription you want to modify in the list in the **My Subscriptions** section of the page to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
3.  <span data-ttu-id="fb078-117">ポータルでは、ポータルへのアクセスに使用するアカウントに関連付けられている電子メール アドレスにアラート通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="fb078-117">The portal sends alert notifications to the e-mail address associated with the account you use to access the portal.</span></span> <span data-ttu-id="fb078-118">別の電子メール アドレスを使用するには、横にチェック ボックスを選択、**カスタム電子メール**テキスト ボックス、およびテキスト ボックスに優先電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="fb078-118">If you want to use a different e-mail address, select the check box next to the **Custom Email** text box, and then type the preferred e-mail address in the text box.</span></span>  
  
4.  <span data-ttu-id="fb078-119">チェック ボックスをオン、**スケジュール**セクションで、ポータルのアラートを送信するとで期間の開始と終了時刻を指定する必要がありますと期間を指定する場合、 **Start Time**と**EndTime**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="fb078-119">Select the check box in the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **EndTime** drop-down lists.</span></span>  
  
5.  <span data-ttu-id="fb078-120">開始と終了日を入力、**ブラック アウト期間**とすることはできませんが表示され、アラートに対して操作を実行する期間があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="fb078-120">Type the start and end dates for a **Black-out Period** if there is a period when you will be unable to receive and act upon alerts.</span></span>  
  
6.  <span data-ttu-id="fb078-121">選択、**間隔**で**分**ポータルが発生したアラートの比較し、同じアラートの複数のインスタンスの発生時に 1 つだけ送信中にします。</span><span class="sxs-lookup"><span data-stu-id="fb078-121">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and will send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="fb078-122">これは、迅速に発生したエラーが多数の同一の警告メッセージを作成することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="fb078-122">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
7.  <span data-ttu-id="fb078-123">クリックして、**保存**サブスクリプションを更新するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb078-123">Click the **Save** button to update the subscription.</span></span>  
  
### <a name="to-delete-an-existing-alert-subscription"></a><span data-ttu-id="fb078-124">既存のアラート配信登録を削除するには</span><span class="sxs-lookup"><span data-stu-id="fb078-124">To delete an existing alert subscription</span></span>  
  
1.  <span data-ttu-id="fb078-125">開く、[ポータル アラート ページ](../esb-toolkit/portal-alerts-page.md)に既存のアラートの一覧と、これらのアラートを現在のサブスクリプションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb078-125">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="fb078-126">クリックして、**削除**の一覧で、削除するサブスクリプションの隣にあるリンク、**個人用サブスクリプション**ページのセクションです。</span><span class="sxs-lookup"><span data-stu-id="fb078-126">Click the **Delete** link next to the subscription you want to delete in the list in the **My Subscriptions** section of the page.</span></span>