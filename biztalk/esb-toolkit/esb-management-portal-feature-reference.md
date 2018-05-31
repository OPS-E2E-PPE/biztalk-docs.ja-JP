---
title: 管理ポータルの機能の参照を ESB |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8470b3af-8124-401b-b80f-3dc7346fed96
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdb9bd39ed46a7307d7fa6a6f57e5559a2fe46d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294410"
---
# <a name="esb-management-portal-feature-reference"></a><span data-ttu-id="a6c9a-102">ESB 管理ポータル機能リファレンス</span><span class="sxs-lookup"><span data-stu-id="a6c9a-102">ESB Management Portal Feature Reference</span></span>
<span data-ttu-id="a6c9a-103">ESB 管理ポータルでは、簡単に監視、管理、および ESB アプリケーションをデバッグするエラー情報のビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-103">The ESB Management Portal provides views of fault information that make it easy to monitor, manage, and debug ESB applications.</span></span> <span data-ttu-id="a6c9a-104">アラートの管理、UDDI 情報を発行し、ポータルの管理に使用できる機能も用意されています。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-104">It also provides features that you can use to manage alerts, publish UDDI information, and administer the portal.</span></span> <span data-ttu-id="a6c9a-105">ポータルを開くには、http://localhost/ESB.Portal/ に移動します。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-105">To open the portal, go to http://localhost/ESB.Portal/.</span></span>  
  
 <span data-ttu-id="a6c9a-106">ポータルで、次のビューがあります。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-106">The following views are available in the portal:</span></span>  
  
-   <span data-ttu-id="a6c9a-107">[ポータルのホーム ページ](../esb-toolkit/portal-home-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-107">[Portal Home Page](../esb-toolkit/portal-home-page.md).</span></span> <span data-ttu-id="a6c9a-108">このページには、アプリケーション全体の状態、エラーの概要、UDDI の登録、およびエラーとアプリケーションの種類によっての内訳を表示するグラフの最近の要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-108">This page displays the overall application state, a summary of faults, recent requests for UDDI registration, and charts that show a breakdown of faults by type and by application.</span></span>  
  
-   <span data-ttu-id="a6c9a-109">[ポータル ページが違反](../esb-toolkit/portal-faults-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-109">[Portal Faults Page](../esb-toolkit/portal-faults-page.md).</span></span> <span data-ttu-id="a6c9a-110">このページには、各フォールト; のプロパティの切り詰められた一覧が表示されます。さまざまな条件によってエラーの分析をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-110">This page displays a truncated list of properties for each fault; it supports analysis of faults by a range of criteria.</span></span>  
  
-   <span data-ttu-id="a6c9a-111">[ポータルのフォールト メッセージ ビューアー](../esb-toolkit/portal-fault-message-viewer.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-111">[Portal Fault Message Viewer](../esb-toolkit/portal-fault-message-viewer.md).</span></span> <span data-ttu-id="a6c9a-112">このページにはアクセスのみが、ポータルのエラー ページ。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-112">This page is accessible only though the Portal Faults page.</span></span> <span data-ttu-id="a6c9a-113">個々 のエラー メッセージの詳細を表示し、修復し、メッセージを再送信することができます。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-113">It displays details of individual fault messages and allows you to repair and resubmit messages.</span></span>  
  
-   <span data-ttu-id="a6c9a-114">[ポータル警告 ページ](../esb-toolkit/portal-alerts-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-114">[Portal Alerts Page](../esb-toolkit/portal-alerts-page.md).</span></span> <span data-ttu-id="a6c9a-115">このページで、ユーザーを作成および変更のアラートおよびアラートの電子メール設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-115">This page allows users to create and modify alerts and to configure alert email settings.</span></span> <span data-ttu-id="a6c9a-116">ポータルでは、ときに特定の種類のエラー、または任意のエラー アラートの電子メール メッセージを送信できますが行われます。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-116">The portal can send an alert email message when a specific type of fault, or any fault, occurs.</span></span>  
  
-   <span data-ttu-id="a6c9a-117">[ポータル レポート ページ](../esb-toolkit/portal-reports-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-117">[Portal Reports Page](../esb-toolkit/portal-reports-page.md).</span></span> <span data-ttu-id="a6c9a-118">このページは、エラー、警告、およびアプリケーションの観点からのメッセージの再送信アクティビティを示すグラフが表示されます、アプリケーション内で個々 のサービスの正常性の分析をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-118">This page displays charts indicating the fault, alert, and message resubmission activity from an application perspective and supports analysis of the health of the individual services within applications.</span></span>  
  
-   <span data-ttu-id="a6c9a-119">[レジストリのポータル ページ](../esb-toolkit/portal-registry-pages.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-119">[Portal Registry Pages](../esb-toolkit/portal-registry-pages.md).</span></span> <span data-ttu-id="a6c9a-120">このページでは、UDDI サービスをユーザーに (Microsoft BizTalk Server の受信場所) には、サービス エンドポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-120">This page allows users to publish service endpoints (such as Microsoft BizTalk Server receive locations) to the UDDI service.</span></span> <span data-ttu-id="a6c9a-121">UDDI サービスは、組織内にサービス エンドポイントの中央のレジストリとして機能します。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-121">The UDDI service acts as a central registry of service endpoints within an organization.</span></span>  
  
-   <span data-ttu-id="a6c9a-122">[ポータルの管理ページ](../esb-toolkit/portal-admin-pages.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-122">[Portal Admin Pages](../esb-toolkit/portal-admin-pages.md).</span></span> <span data-ttu-id="a6c9a-123">このページでは、ポータル設定を構成、監査ログを編集および再送信されたメッセージの表示、およびユーザーとグループのアラートを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-123">This page allows administrators to configure portal settings, view an audit log of edited and resubmitted messages, and manage alerts for users and groups.</span></span>  
  
-   <span data-ttu-id="a6c9a-124">[ポータル個人用設定 ページ](../esb-toolkit/portal-my-settings-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-124">[Portal My Settings Page](../esb-toolkit/portal-my-settings-page.md).</span></span> <span data-ttu-id="a6c9a-125">このページでは、既定のアプリケーションと、ポータルの期間フィルターを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="a6c9a-125">This page allows users to select the default application and time-period filters for the portal.</span></span>