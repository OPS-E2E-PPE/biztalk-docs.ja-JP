---
title: ポータル警告 ページ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 131b4750-ce3d-445f-be0e-6bf499734c69
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db094dafd795b27095179b38c55e81bc36d44be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65294941"
---
# <a name="portal-alerts-page"></a><span data-ttu-id="0472a-102">ポータルのアラート ページ</span><span class="sxs-lookup"><span data-stu-id="0472a-102">Portal Alerts Page</span></span>
<span data-ttu-id="0472a-103">図 1 は、アラート ページで、2 つのセクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="0472a-103">Figure 1 shows the Alerts page, which contains two sections:</span></span>  

- <span data-ttu-id="0472a-104">メインのセクションでは、新しいアラートと、既存のアラートの一覧を作成するリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0472a-104">The main section displays a link to create a new alert and a list of existing alerts.</span></span> <span data-ttu-id="0472a-105">各アラートには、アラートにサブスクライブすることができますを対応するリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="0472a-105">Each alert has a corresponding link that allows you to subscribe to the alert.</span></span> <span data-ttu-id="0472a-106">アラートの詳細を表示、警告の新しいサブスクリプションを作成およびアラートを削除するアクション列のアイコンをクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0472a-106">You can also click the icons in the Action column to view details of the alert, create a new subscription for the alert, and delete the alert.</span></span>  

- <span data-ttu-id="0472a-107">**マイ サブスクリプション**セクションには、ポータル内で定義したサブスクリプションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0472a-107">The **My Subscriptions** section displays a list of subscriptions you have defined within the portal.</span></span> <span data-ttu-id="0472a-108">編集し、この一覧にリンクを使用して、既存のサブスクリプションの登録を解除できます。</span><span class="sxs-lookup"><span data-stu-id="0472a-108">You can edit and unsubscribe your existing subscriptions using the links in this list.</span></span>  

  <span data-ttu-id="0472a-109">![ポータル アラート ページ](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8 PortalAlertsPage")</span><span class="sxs-lookup"><span data-stu-id="0472a-109">![Portal Alerts Page](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8-PortalAlertsPage")</span></span>  

  <span data-ttu-id="0472a-110">**図 1**</span><span class="sxs-lookup"><span data-stu-id="0472a-110">**Figure 1**</span></span>  

  <span data-ttu-id="0472a-111">**ESB 管理ポータルのアラート ページ**</span><span class="sxs-lookup"><span data-stu-id="0472a-111">**The ESB Management Portal Alerts page**</span></span>  

  <span data-ttu-id="0472a-112">ESB アラート サービスは、ESB 管理ポータルに到着すると例外の値に一致する指定した条件に基づいてアラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="0472a-112">The ESB Alert Service generates alerts based on criteria you specify that match the values in exceptions as they arrive at the ESB Management Portal.</span></span> <span data-ttu-id="0472a-113">一致して、さまざまなフィールドを正確に制御するため、例外がどのアラートの例外の可能な各型が一致を比較することができます。</span><span class="sxs-lookup"><span data-stu-id="0472a-113">You can match and compare a range of fields in an exception to control accurately which alerts will match each possible type of exception.</span></span> <span data-ttu-id="0472a-114">ポータルでは、定義するアラートの種類をマップするサブスクリプションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0472a-114">The portal also allows you to create subscriptions that map to the different types of alerts you define.</span></span> <span data-ttu-id="0472a-115">一致するアラートが発生した場合、これらのサブスクリプションはユーザーに通知できます。</span><span class="sxs-lookup"><span data-stu-id="0472a-115">These subscriptions can notify users when the matching alert occurs.</span></span>  

  <span data-ttu-id="0472a-116">次の一覧では、ESB 管理ポータルのアラート ページの機能を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0472a-116">The following list explains how you can use the features of the ESB Management Portal Alerts page:</span></span>  

- <span data-ttu-id="0472a-117">新しい警告を作成する をクリックして、**アラートの作成**をアラートの追加 ページを表示するページの上部にあるリンクです。</span><span class="sxs-lookup"><span data-stu-id="0472a-117">To create a new alert, click the **Create Alert** link at the top of the page to open the Add Alert page.</span></span>  

- <span data-ttu-id="0472a-118">を表示または既存のアラートを編集するには、ページのメイン セクションでは、アラートの [アクション] 列の虫眼鏡アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0472a-118">To view or edit an existing alert, click the magnifying glass icon in the Action column for the alert in the main section of the page.</span></span> <span data-ttu-id="0472a-119">開き、[アラート ビューアー ページ](../esb-toolkit/alert-viewer-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="0472a-119">This opens the [Alert Viewer Page](../esb-toolkit/alert-viewer-page.md).</span></span>  

- <span data-ttu-id="0472a-120">既存のアラートを購読するには、新しいサブスクリプション アイコンを開くには、アラートの横にある [アクション] 列をクリックして、[アラート サブスクリプションの追加およびサブスクリプション ページの編集](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)です。</span><span class="sxs-lookup"><span data-stu-id="0472a-120">To subscribe to an existing alert, click the new subscription icon the Action column next to the alert to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  

- <span data-ttu-id="0472a-121">オプションを使用して、管理者としてこのページを開いたかどうか、**管理者**タブ メニュー (の代わりにから、**アラート** タブ)、十字アイコンをクリックすると、一覧のアラートの横の アクション 列アラートとリンクされたサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="0472a-121">If you opened this page as an administrator using the options on the **Admin** tab menu (instead of from the **Alerts** tab), you can click the cross mark icon the Action column next to any of the alerts in the list to delete the alert and any linked subscriptions.</span></span>  

- <span data-ttu-id="0472a-122">既存のサブスクリプションを編集する をクリックして、**編集**の一覧でそのサブスクリプションの横にあるリンク、**マイ サブスクリプション**に開くページのセクション、[アラート サブスクリプションの追加と編集サブスクリプション ページ](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)します。</span><span class="sxs-lookup"><span data-stu-id="0472a-122">To edit an existing subscription, click the **Edit** link next to that subscription in the list in the **My Subscriptions** section of the page to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  

- <span data-ttu-id="0472a-123">既存のサブスクリプションを削除する をクリックして、 **Unsubscribe**の一覧でそのサブスクリプションの横にあるリンク、**マイ サブスクリプション**ページのセクション。</span><span class="sxs-lookup"><span data-stu-id="0472a-123">To remove an existing subscription, click the **Unsubscribe** link next to that subscription in the list in the **My Subscriptions** section of the page.</span></span>  

- <span data-ttu-id="0472a-124">アラートのリスト全体を Excel にエクスポートするには、クリックして**を Excel にエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="0472a-124">To export the entire list of alerts to Microsoft Excel, click **Export to Excel**.</span></span>
