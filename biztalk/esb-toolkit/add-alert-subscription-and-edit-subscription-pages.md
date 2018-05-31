---
title: アラート配信登録を追加し、[サブスクリプション] ページを編集 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad5e99f1-714e-458b-b5f0-85ac69be5335
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49bed9959b51439f21d625795a69804fd41d77ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290042"
---
# <a name="add-alert-subscription-and-edit-subscription-pages"></a><span data-ttu-id="0991b-102">アラート配信登録を追加し、[サブスクリプション] ページの編集</span><span class="sxs-lookup"><span data-stu-id="0991b-102">Add Alert Subscription and Edit Subscription Pages</span></span>
<span data-ttu-id="0991b-103">アラート サブスクリプションの追加およびサブスクリプションの編集ページは似ています。</span><span class="sxs-lookup"><span data-stu-id="0991b-103">The Add Alert Subscription and Edit Subscription pages are similar.</span></span> <span data-ttu-id="0991b-104">異なり、サブスクリプションの編集 ページにサブスクライバー ID (現在のポータルのユーザーの Microsoft Windows アカウント) およびボタンのさまざまなセットがあります。</span><span class="sxs-lookup"><span data-stu-id="0991b-104">They differ in that the Edit Subscription page shows the subscriber ID (the Microsoft Windows account of the current portal user), and has a different set of buttons.</span></span> <span data-ttu-id="0991b-105">図 1 は、アラート サブスクリプションの追加およびサブスクリプションの編集ページを示しています。</span><span class="sxs-lookup"><span data-stu-id="0991b-105">Figure 1 shows the Add Alert Subscription and Edit Subscription pages.</span></span>  
  
 <span data-ttu-id="0991b-106">![警告編集サブスクリプションの追加](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8 AddAlertEditSubscription")</span><span class="sxs-lookup"><span data-stu-id="0991b-106">![Add Alert Edit Subscription](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8-AddAlertEditSubscription")</span></span>  
  
 <span data-ttu-id="0991b-107">**図 1**</span><span class="sxs-lookup"><span data-stu-id="0991b-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="0991b-108">**ESB 管理ポータル アラート サブスクリプションの追加およびサブスクリプションの編集ページ**</span><span class="sxs-lookup"><span data-stu-id="0991b-108">**The ESB Management Portal Add Alert Subscription and Edit Subscription pages**</span></span>  
  
 <span data-ttu-id="0991b-109">アラート サブスクリプションの追加およびサブスクリプションの編集ページでを指定し、次の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0991b-109">The Add Alert Subscription and Edit Subscription pages allow you to specify and modify the following:</span></span>  
  
-   <span data-ttu-id="0991b-110">サブスクリプションの場合ではなく、Microsoft Windows アカウントの電子メール アドレス) を使用するカスタムの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="0991b-110">A custom e-mail address to use for the subscription (instead of your Microsoft Windows account e-mail address)</span></span>  
  
-   <span data-ttu-id="0991b-111">アラート通知を承認すると期間</span><span class="sxs-lookup"><span data-stu-id="0991b-111">The time period when you will accept alert notifications</span></span>  
  
-   <span data-ttu-id="0991b-112">休暇などのイベントに対して「ブラック アウト」期間</span><span class="sxs-lookup"><span data-stu-id="0991b-112">A "black-out" period for events such as vacations</span></span>  
  
-   <span data-ttu-id="0991b-113">そこで、ポータルは送信しません重複するアラートの間隔</span><span class="sxs-lookup"><span data-stu-id="0991b-113">The interval over which the portal will not send duplicate alerts</span></span>  
  
 <span data-ttu-id="0991b-114">アラート サブスクリプションの追加およびサブスクリプションの編集ページで、次を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0991b-114">You can do the following on the Add Alert Subscription and Edit Subscription pages:</span></span>  
  
-   <span data-ttu-id="0991b-115">次のチェック ボックスをオン、**カスタム電子メール**テキスト ボックスには、標準的な Windows アカウントの電子メール アドレスに異なるサブスクリプションの電子メール アドレスを使用する場合と、テキスト ボックスに優先電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="0991b-115">Select the check box next to the **Custom Email** text box if you want to use an e-mail address for the subscription that is different to your standard Windows account e-mail address, and then type the preferred e-mail address in the text box.</span></span>  
  
-   <span data-ttu-id="0991b-116">上部にあるチェック ボックスをオン、**スケジュール**セクションで、ポータルのアラートを送信するとで期間の開始と終了時刻を指定する必要がありますと期間を指定する場合、 **Start Time**と**終了時刻**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="0991b-116">Select the check box at the top of the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **End Time** drop-down lists.</span></span> <span data-ttu-id="0991b-117">この期間の範囲外で発生するアラートが置かれ、指定した期間中に配信されます。</span><span class="sxs-lookup"><span data-stu-id="0991b-117">Alerts occurring outside this period are queued and delivered during the specified period.</span></span>  
  
-   <span data-ttu-id="0991b-118">開始日と終了日を入力、**ブラック アウト期間**とすることはできませんを受信して警告の処理期間があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="0991b-118">Type the start date and end date for a **Black-out Period** if there is a period when you will be unable to receive and act on alerts.</span></span> <span data-ttu-id="0991b-119">2 つの日付形式年/月/日を使用します。</span><span class="sxs-lookup"><span data-stu-id="0991b-119">Use the format mm/dd/yyyy for the two dates.</span></span>  
  
-   <span data-ttu-id="0991b-120">選択、**間隔**で**分**ポータルが発生したアラートの比較し、同じアラートの複数のインスタンスが発生した場合は、1 つのみを送信中にします。</span><span class="sxs-lookup"><span data-stu-id="0991b-120">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="0991b-121">これは、迅速に発生したエラーが多数の同一の警告メッセージを作成することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="0991b-121">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
-   <span data-ttu-id="0991b-122">クリックして、**保存**を作成またはサブスクリプションの更新ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0991b-122">Click the **Save** button to create or update the subscription.</span></span>  
  
-   <span data-ttu-id="0991b-123">クリックして、**削除**(サブスクリプションの編集 ページでのみ使用可能) を選択したサブスクリプションを削除するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0991b-123">Click the **Delete** button (available only on the Edit Subscription page) to delete the selected subscription.</span></span>  
  
-   <span data-ttu-id="0991b-124">クリックして、**キャンセル**に戻る ボタン、[アラート ビューアー ページ](../esb-toolkit/alert-viewer-page.md)作成または、サブスクリプションを変更することがなくです。</span><span class="sxs-lookup"><span data-stu-id="0991b-124">Click the **Cancel** button to go back to the [Alert Viewer Page](../esb-toolkit/alert-viewer-page.md) without creating or modifying the subscription.</span></span>