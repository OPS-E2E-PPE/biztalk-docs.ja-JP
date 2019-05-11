---
title: アラートの購読 |Microsoft Docs
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
ms.openlocfilehash: e402d37ba9e680b3cb41db6c935990a47569b484
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268995"
---
# <a name="subscribing-to-alerts"></a><span data-ttu-id="fa179-102">アラートを購読するには</span><span class="sxs-lookup"><span data-stu-id="fa179-102">Subscribing to Alerts</span></span>
### <a name="to-subscribe-to-an-alert"></a><span data-ttu-id="fa179-103">アラートを購読するには</span><span class="sxs-lookup"><span data-stu-id="fa179-103">To subscribe to an alert</span></span>  
  
1.  <span data-ttu-id="fa179-104">開く、[ポータル アラート ページ](../esb-toolkit/portal-alerts-page.md)にこれらのアラートを現在のサブスクリプションと既存のアラートの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa179-104">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="fa179-105">[アクション] 列、 **AddSubscriber**既存の警告のアイコン。</span><span class="sxs-lookup"><span data-stu-id="fa179-105">In the Action column, click the **AddSubscriber** icon for an existing alert.</span></span> <span data-ttu-id="fa179-106">開き、[アラート配信登録を追加し、サブスクリプション ページの編集](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)します。</span><span class="sxs-lookup"><span data-stu-id="fa179-106">This opens the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
3.  <span data-ttu-id="fa179-107">ポータルでは、ポータルへのアクセスに使用するアカウントに関連付けられている電子メール アドレスにアラート通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="fa179-107">The portal sends alert notifications to the e-mail address associated with the account you use to access the portal.</span></span> <span data-ttu-id="fa179-108">別の電子メール アドレスを使用する場合は、横にチェック ボックスを選択、**カスタム電子メール**テキスト ボックス、およびテキスト ボックスに優先電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="fa179-108">If you want to use a different e-mail address, select the check box next to the **Custom Email** text box, and then type the preferred e-mail address in the text box.</span></span>  
  
4.  <span data-ttu-id="fa179-109">チェック ボックスをオン、**スケジュール**セクションときに、ポータルをアラートを送信し、で期間の開始および終了時刻を指定する必要があります期間を指定する場合、**開始時刻**と**EndTime**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="fa179-109">Select the check box in the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **EndTime** drop-down lists.</span></span>  
  
5.  <span data-ttu-id="fa179-110">ときにできないことを受信し、アラートに対して操作を実行期間がある場合で開始と終了日を入力、**ブラック アウト期間**ボックス。</span><span class="sxs-lookup"><span data-stu-id="fa179-110">If there is a period when you will be unable to receive and act upon alerts, type the start and end dates in the **Black-out Period** boxes.</span></span>  
  
6.  <span data-ttu-id="fa179-111">選択、**間隔**で**分**ポータルが発生したアラートの比較し、同じアラートの複数のインスタンスが発生した場合は、1 つだけを送信中にします。</span><span class="sxs-lookup"><span data-stu-id="fa179-111">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="fa179-112">これは迅速に発生する障害が多数の同一の警告メッセージを作成することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="fa179-112">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
7.  <span data-ttu-id="fa179-113">をクリックして、**保存**新しいサブスクリプションを作成するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa179-113">Click the **Save** button to create the new subscription.</span></span>  
  
### <a name="to-edit-an-existing-alert-subscription"></a><span data-ttu-id="fa179-114">既存のアラート配信登録を編集するには</span><span class="sxs-lookup"><span data-stu-id="fa179-114">To edit an existing alert subscription</span></span>  
  
1.  <span data-ttu-id="fa179-115">開く、[ポータル アラート ページ](../esb-toolkit/portal-alerts-page.md)にこれらのアラートを現在のサブスクリプションと既存のアラートの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa179-115">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="fa179-116">をクリックして、**編集**の一覧で、変更するサブスクリプションの横にあるリンク、**マイ サブスクリプション**に開くページのセクション、[アラート サブスクリプションの追加とサブスクリプションページの編集](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span><span class="sxs-lookup"><span data-stu-id="fa179-116">Click the **Edit** link next to the subscription you want to modify in the list in the **My Subscriptions** section of the page to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
3.  <span data-ttu-id="fa179-117">ポータルでは、ポータルへのアクセスに使用するアカウントに関連付けられている電子メール アドレスにアラート通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="fa179-117">The portal sends alert notifications to the e-mail address associated with the account you use to access the portal.</span></span> <span data-ttu-id="fa179-118">別の電子メール アドレスを使用する場合は、横にチェック ボックスを選択、**カスタム電子メール**テキスト ボックス、およびテキスト ボックスに優先電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="fa179-118">If you want to use a different e-mail address, select the check box next to the **Custom Email** text box, and then type the preferred e-mail address in the text box.</span></span>  
  
4.  <span data-ttu-id="fa179-119">チェック ボックスをオン、**スケジュール**セクションときに、ポータルをアラートを送信し、で期間の開始および終了時刻を指定する必要があります期間を指定する場合、**開始時刻**と**EndTime**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="fa179-119">Select the check box in the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **EndTime** drop-down lists.</span></span>  
  
5.  <span data-ttu-id="fa179-120">開始と終了日を入力、**ブラック アウト期間**ときにできないことを受信し、アラートに対して操作を実行期間があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="fa179-120">Type the start and end dates for a **Black-out Period** if there is a period when you will be unable to receive and act upon alerts.</span></span>  
  
6.  <span data-ttu-id="fa179-121">選択、**間隔**で**分**ポータルは、発生したアラートを比較し、同じアラートの複数のインスタンスが発生すると 1 つだけ送信中にします。</span><span class="sxs-lookup"><span data-stu-id="fa179-121">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and will send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="fa179-122">これは迅速に発生する障害が多数の同一の警告メッセージを作成することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="fa179-122">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
7.  <span data-ttu-id="fa179-123">をクリックして、**保存**サブスクリプションを更新するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa179-123">Click the **Save** button to update the subscription.</span></span>  
  
### <a name="to-delete-an-existing-alert-subscription"></a><span data-ttu-id="fa179-124">既存のアラート配信登録を削除するには</span><span class="sxs-lookup"><span data-stu-id="fa179-124">To delete an existing alert subscription</span></span>  
  
1.  <span data-ttu-id="fa179-125">開く、[ポータル アラート ページ](../esb-toolkit/portal-alerts-page.md)にこれらのアラートを現在のサブスクリプションと既存のアラートの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa179-125">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="fa179-126">をクリックして、**削除**の一覧で、削除するサブスクリプションの横にあるリンク、**マイ サブスクリプション**ページのセクション。</span><span class="sxs-lookup"><span data-stu-id="fa179-126">Click the **Delete** link next to the subscription you want to delete in the list in the **My Subscriptions** section of the page.</span></span>