---
title: アラート配信登録を追加し、サブスクリプション ページの編集 |Microsoft Docs
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
ms.openlocfilehash: 1b843bde8905d8b6803dda56a6370f70c934a610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013451"
---
# <a name="add-alert-subscription-and-edit-subscription-pages"></a><span data-ttu-id="e6e31-102">アラート配信登録を追加し、サブスクリプション ページの編集</span><span class="sxs-lookup"><span data-stu-id="e6e31-102">Add Alert Subscription and Edit Subscription Pages</span></span>
<span data-ttu-id="e6e31-103">アラート配信登録の追加とサブスクリプションの編集ページに似ています。</span><span class="sxs-lookup"><span data-stu-id="e6e31-103">The Add Alert Subscription and Edit Subscription pages are similar.</span></span> <span data-ttu-id="e6e31-104">サブスクリプションの編集 ページでサブスクライバー ID (ポータルの現在のユーザーの Microsoft Windows アカウント) を示しています、ボタンのさまざまなセットが異なります。</span><span class="sxs-lookup"><span data-stu-id="e6e31-104">They differ in that the Edit Subscription page shows the subscriber ID (the Microsoft Windows account of the current portal user), and has a different set of buttons.</span></span> <span data-ttu-id="e6e31-105">図 1 は、アラート配信登録の追加とサブスクリプションの編集ページを示します。</span><span class="sxs-lookup"><span data-stu-id="e6e31-105">Figure 1 shows the Add Alert Subscription and Edit Subscription pages.</span></span>  

 <span data-ttu-id="e6e31-106">![警告編集サブスクリプションの追加](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8 AddAlertEditSubscription")</span><span class="sxs-lookup"><span data-stu-id="e6e31-106">![Add Alert Edit Subscription](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8-AddAlertEditSubscription")</span></span>  

 <span data-ttu-id="e6e31-107">**図 1**</span><span class="sxs-lookup"><span data-stu-id="e6e31-107">**Figure 1**</span></span>  

 <span data-ttu-id="e6e31-108">**ESB 管理ポータル アラート サブスクリプションの追加とサブスクリプションの編集ページ**</span><span class="sxs-lookup"><span data-stu-id="e6e31-108">**The ESB Management Portal Add Alert Subscription and Edit Subscription pages**</span></span>  

 <span data-ttu-id="e6e31-109">アラート配信登録の追加とサブスクリプションの編集ページを指定し、次の変更を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6e31-109">The Add Alert Subscription and Edit Subscription pages allow you to specify and modify the following:</span></span>  

- <span data-ttu-id="e6e31-110">(代わりに、Microsoft Windows アカウントの電子メール アドレス) のサブスクリプションを使用するカスタムの電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="e6e31-110">A custom e-mail address to use for the subscription (instead of your Microsoft Windows account e-mail address)</span></span>  

- <span data-ttu-id="e6e31-111">アラート通知を承認すると期間</span><span class="sxs-lookup"><span data-stu-id="e6e31-111">The time period when you will accept alert notifications</span></span>  

- <span data-ttu-id="e6e31-112">休暇などのイベントの「ブラック アウト」期間</span><span class="sxs-lookup"><span data-stu-id="e6e31-112">A "black-out" period for events such as vacations</span></span>  

- <span data-ttu-id="e6e31-113">どのポータルは送信しませんアラートが重複して間隔</span><span class="sxs-lookup"><span data-stu-id="e6e31-113">The interval over which the portal will not send duplicate alerts</span></span>  

  <span data-ttu-id="e6e31-114">アラート配信登録の追加とサブスクリプションの編集ページでは、次を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e6e31-114">You can do the following on the Add Alert Subscription and Edit Subscription pages:</span></span>  

- <span data-ttu-id="e6e31-115">次のチェック ボックスをオン、**カスタム電子メール**テキスト ボックスは、標準の Windows アカウント電子メール アドレス、異なるサブスクリプションの電子メール アドレスを使用する場合と、テキスト ボックスに優先電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e6e31-115">Select the check box next to the **Custom Email** text box if you want to use an e-mail address for the subscription that is different to your standard Windows account e-mail address, and then type the preferred e-mail address in the text box.</span></span>  

- <span data-ttu-id="e6e31-116">上部にあるチェック ボックスをオン、**スケジュール**セクションときに、ポータルをアラートを送信し、で期間の開始および終了時刻を指定する必要があります期間を指定する場合、**開始時刻**と**終了時刻**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="e6e31-116">Select the check box at the top of the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **End Time** drop-down lists.</span></span> <span data-ttu-id="e6e31-117">この期間の範囲外で発生するアラートがキューに登録し、指定した期間中に配信します。</span><span class="sxs-lookup"><span data-stu-id="e6e31-117">Alerts occurring outside this period are queued and delivered during the specified period.</span></span>  

- <span data-ttu-id="e6e31-118">開始日と終了日を入力、**ブラック アウト期間**ときにできないことを受信して警告の処理期間があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="e6e31-118">Type the start date and end date for a **Black-out Period** if there is a period when you will be unable to receive and act on alerts.</span></span> <span data-ttu-id="e6e31-119">2 つの日付形式年/月/日を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6e31-119">Use the format mm/dd/yyyy for the two dates.</span></span>  

- <span data-ttu-id="e6e31-120">選択、**間隔**で**分**ポータルが発生したアラートの比較し、同じアラートの複数のインスタンスが発生した場合は、1 つだけを送信中にします。</span><span class="sxs-lookup"><span data-stu-id="e6e31-120">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="e6e31-121">これは迅速に発生する障害が多数の同一の警告メッセージを作成することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="e6e31-121">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  

- <span data-ttu-id="e6e31-122">をクリックして、**保存**を作成またはサブスクリプションの更新ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6e31-122">Click the **Save** button to create or update the subscription.</span></span>  

- <span data-ttu-id="e6e31-123">をクリックして、**削除**選択したサブスクリプションを削除する (サブスクリプションの編集 ページでのみ使用可能) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6e31-123">Click the **Delete** button (available only on the Edit Subscription page) to delete the selected subscription.</span></span>  

- <span data-ttu-id="e6e31-124">をクリックして、**キャンセル**に戻る ボタン、[アラート ビューアー ページ](../esb-toolkit/alert-viewer-page.md)作成したり、サブスクリプションを変更せずにします。</span><span class="sxs-lookup"><span data-stu-id="e6e31-124">Click the **Cancel** button to go back to the [Alert Viewer Page](../esb-toolkit/alert-viewer-page.md) without creating or modifying the subscription.</span></span>
