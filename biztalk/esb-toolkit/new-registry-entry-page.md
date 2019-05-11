---
title: 新しいレジストリ エントリ ページ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 204c547c-ed0e-4a1f-a0b2-ce5da00d9c42
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 146e3032a6b9d3b57b23a6607eb40b61a92bb5bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400071"
---
# <a name="new-registry-entry-page"></a><span data-ttu-id="20490-102">新しいレジストリ エントリ ページ</span><span class="sxs-lookup"><span data-stu-id="20490-102">New Registry Entry Page</span></span>
<span data-ttu-id="20490-103">図 1 は、指定された Microsoft BizTalk Server の ESB アプリケーションで、既存のエンドポイントの一覧を表示することができます、ESB 管理ポータル新しいレジストリ エントリ ページを示します。</span><span class="sxs-lookup"><span data-stu-id="20490-103">Figure 1 shows the ESB Management Portal New Registry Entry page where you can view a list of the existing endpoints in a specified Microsoft BizTalk Server ESB application.</span></span>  
  
 <span data-ttu-id="20490-104">![新しいレジストリ エントリ ページ](../esb-toolkit/media/ch8-newregistryentrypage.gif "Ch8 NewRegistryEntryPage")</span><span class="sxs-lookup"><span data-stu-id="20490-104">![New Registry Entry Page](../esb-toolkit/media/ch8-newregistryentrypage.gif "Ch8-NewRegistryEntryPage")</span></span>  
  
 <span data-ttu-id="20490-105">**図 1**</span><span class="sxs-lookup"><span data-stu-id="20490-105">**Figure 1**</span></span>  
  
 <span data-ttu-id="20490-106">**ESB 管理ポータル新しいレジストリ エントリ ページ**</span><span class="sxs-lookup"><span data-stu-id="20490-106">**The ESB Management Portal New Registry Entry page**</span></span>  
  
 <span data-ttu-id="20490-107">次の一覧では、ESB 管理ポータル新しいレジストリ エントリ ページの機能を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="20490-107">The following list explains how you can use the features of the ESB Management Portal New Registry Entry page:</span></span>  
  
-   <span data-ttu-id="20490-108">種類、状態、および表示するエンドポイントを含む BizTalk アプリケーションを指定するのにには、ページの上部にある 3 つのドロップダウン リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="20490-108">Use the three drop-down lists near the top of the page to specify the type, status, and BizTalk application that contains the endpoints you want to view:</span></span>  
  
    -   <span data-ttu-id="20490-109">最初の (エンドポイントの種類) ドロップダウン リストで選択**受信場所、送信ポート、** または**のすべてのエンドポイント**します。</span><span class="sxs-lookup"><span data-stu-id="20490-109">In the first (endpoint type) drop-down list, you can select **Receive Locations, Send Ports,** or **All Endpoints**.</span></span>  
  
    -   <span data-ttu-id="20490-110">2 つ目の (ステータス) ドロップダウン リストで選択**登録されている、NotRegistered、保留中、** または**すべて**します。</span><span class="sxs-lookup"><span data-stu-id="20490-110">In the second (status) drop-down list, you can select **Registered, NotRegistered, Pending,** or **All**.</span></span>  
  
    -   <span data-ttu-id="20490-111">3 番目の (BizTalk アプリケーション) ドロップダウン リストでは、現在インストールされている BizTalk アプリケーションの 1 つを選択できます。</span><span class="sxs-lookup"><span data-stu-id="20490-111">In the third (BizTalk application) drop-down list, you can select one of the currently installed BizTalk applications.</span></span>  
  
-   <span data-ttu-id="20490-112">アプリケーションとエンドポイントの条件を指定するには後、は、一致するエンドポイントの一覧を表示する BizTalk アプリケーションのドロップダウン リストの横にある矢印アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20490-112">After specifying the application and endpoint criteria, click the arrow icon next to the BizTalk application drop-down list to display a list of matching endpoints.</span></span>  
  
-   <span data-ttu-id="20490-113">エンドポイントの一覧には、エンドポイントの一致の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="20490-113">The list of endpoints contains details of matching endpoints.</span></span> <span data-ttu-id="20490-114">動的エンドポイントはそれぞれ、一覧には表示およびこのエンドポイントを公開する保留中の要求の詳細を編集できるリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="20490-114">For each one that is not a dynamic endpoint, the list contains a link that allows you to view and edit the details of a pending request to publish this endpoint.</span></span>  
  
-   <span data-ttu-id="20490-115">をクリックして、**詳細の表示**リンクを開くリストのいずれかの行、[レジストリ詳細ページ](../esb-toolkit/registry-details-page.md)要求を変更して、エンドポイントを発行できます。</span><span class="sxs-lookup"><span data-stu-id="20490-115">Click the **View Detail** link in any row of the list to open the [Registry Details Page](../esb-toolkit/registry-details-page.md) where you can modify the request and publish the endpoint.</span></span>