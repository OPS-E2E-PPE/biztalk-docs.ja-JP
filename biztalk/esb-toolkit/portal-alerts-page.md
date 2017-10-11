---
title: "ポータル警告 ページ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 131b4750-ce3d-445f-be0e-6bf499734c69
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba854c269db4a1d7eabb021a974fa9614abb7690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="portal-alerts-page"></a><span data-ttu-id="51886-102">[ポータル警告] ページ</span><span class="sxs-lookup"><span data-stu-id="51886-102">Portal Alerts Page</span></span>
<span data-ttu-id="51886-103">図 1 は、通知ページで、2 つのセクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="51886-103">Figure 1 shows the Alerts page, which contains two sections:</span></span>  
  
-   <span data-ttu-id="51886-104">メインのセクションでは、新しいアラートと既存のアラートの一覧を作成するリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51886-104">The main section displays a link to create a new alert and a list of existing alerts.</span></span> <span data-ttu-id="51886-105">各アラートには、アラートにサブスクライブすることができますを対応するリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="51886-105">Each alert has a corresponding link that allows you to subscribe to the alert.</span></span> <span data-ttu-id="51886-106">アラートの詳細を表示、警告のサブスクリプションの新規作成、およびアラートを削除するアクション列内のアイコンをクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="51886-106">You can also click the icons in the Action column to view details of the alert, create a new subscription for the alert, and delete the alert.</span></span>  
  
-   <span data-ttu-id="51886-107">**個人用サブスクリプション**セクションには、ポータル内で定義したサブスクリプションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51886-107">The **My Subscriptions** section displays a list of subscriptions you have defined within the portal.</span></span> <span data-ttu-id="51886-108">編集し、この一覧でリンクを使用して、既存のサブスクリプションを購読解除できます。</span><span class="sxs-lookup"><span data-stu-id="51886-108">You can edit and unsubscribe your existing subscriptions using the links in this list.</span></span>  
  
 <span data-ttu-id="51886-109">![ポータル警告 ページ](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8 PortalAlertsPage")</span><span class="sxs-lookup"><span data-stu-id="51886-109">![Portal Alerts Page](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8-PortalAlertsPage")</span></span>  
  
 <span data-ttu-id="51886-110">**図 1**</span><span class="sxs-lookup"><span data-stu-id="51886-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="51886-111">**ESB 管理ポータルのアラート ページ**</span><span class="sxs-lookup"><span data-stu-id="51886-111">**The ESB Management Portal Alerts page**</span></span>  
  
 <span data-ttu-id="51886-112">ESB 警告サービスは、ESB の管理ポータルに到着すると例外の値に一致する指定した条件に基づいて警告を生成します。</span><span class="sxs-lookup"><span data-stu-id="51886-112">The ESB Alert Service generates alerts based on criteria you specify that match the values in exceptions as they arrive at the ESB Management Portal.</span></span> <span data-ttu-id="51886-113">一致し、どのアラートの例外の可能な各型は一致を正確に制御、例外内のフィールドの範囲を比較できます。</span><span class="sxs-lookup"><span data-stu-id="51886-113">You can match and compare a range of fields in an exception to control accurately which alerts will match each possible type of exception.</span></span> <span data-ttu-id="51886-114">ポータルでは、定義するアラートの種類にマップするサブスクリプションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="51886-114">The portal also allows you to create subscriptions that map to the different types of alerts you define.</span></span> <span data-ttu-id="51886-115">一致するアラートが発生したときに、これらのサブスクリプションはユーザーに通知できます。</span><span class="sxs-lookup"><span data-stu-id="51886-115">These subscriptions can notify users when the matching alert occurs.</span></span>  
  
 <span data-ttu-id="51886-116">次の一覧では、ESB 管理ポータルのアラート ページの機能を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="51886-116">The following list explains how you can use the features of the ESB Management Portal Alerts page:</span></span>  
  
-   <span data-ttu-id="51886-117">新しい警告を作成する をクリックして、**作成アラート**ページを開くには、アラートの追加 ページの上部にあるリンクします。</span><span class="sxs-lookup"><span data-stu-id="51886-117">To create a new alert, click the **Create Alert** link at the top of the page to open the Add Alert page.</span></span>  
  
-   <span data-ttu-id="51886-118">を表示または既存の警告を編集するには、ページのメインのセクションで、アラートの [アクション] 列の虫眼鏡アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51886-118">To view or edit an existing alert, click the magnifying glass icon in the Action column for the alert in the main section of the page.</span></span> <span data-ttu-id="51886-119">開き、[アラート ビューアー ページ](../esb-toolkit/alert-viewer-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="51886-119">This opens the [Alert Viewer Page](../esb-toolkit/alert-viewer-page.md).</span></span>  
  
-   <span data-ttu-id="51886-120">既存のアラートを購読するには、新しいサブスクリプション アイコンを開くには、アラートの横にある [アクション] 列をクリックして、[アラート サブスクリプションの追加およびサブスクリプション ページの編集](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)です。</span><span class="sxs-lookup"><span data-stu-id="51886-120">To subscribe to an existing alert, click the new subscription icon the Action column next to the alert to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
-   <span data-ttu-id="51886-121">オプションを使用して、管理者としてこのページを開いたかどうか、 **Admin**  タブ メニュー (の代わりにから、**アラート** タブ)、クロス マーク アイコンをクリックすると、リスト内の警告のいずれかの横にある アクション 列アラートとそのリンクのサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="51886-121">If you opened this page as an administrator using the options on the **Admin** tab menu (instead of from the **Alerts** tab), you can click the cross mark icon the Action column next to any of the alerts in the list to delete the alert and any linked subscriptions.</span></span>  
  
-   <span data-ttu-id="51886-122">既存のサブスクリプションを編集する をクリックして、**編集**リンクの一覧にそのサブスクリプションの横にある、**個人用サブスクリプション**を開くには、ページのセクションで、[アラート サブスクリプションの追加と編集[サブスクリプション] ページ](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)です。</span><span class="sxs-lookup"><span data-stu-id="51886-122">To edit an existing subscription, click the **Edit** link next to that subscription in the list in the **My Subscriptions** section of the page to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
-   <span data-ttu-id="51886-123">既存のサブスクリプションを削除する をクリックして、 **Unsubscribe**リンクの一覧にそのサブスクリプションの横にある、**個人用サブスクリプション**ページのセクションです。</span><span class="sxs-lookup"><span data-stu-id="51886-123">To remove an existing subscription, click the **Unsubscribe** link next to that subscription in the list in the **My Subscriptions** section of the page.</span></span>  
  
-   <span data-ttu-id="51886-124">アラートのリスト全体を Microsoft Excel にエクスポートするには、クリックして**を Excel にエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="51886-124">To export the entire list of alerts to Microsoft Excel, click **Export to Excel**.</span></span>