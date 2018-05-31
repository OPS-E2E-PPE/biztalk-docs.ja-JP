---
title: 新しいレジストリ エントリ ページ |Microsoft ドキュメント
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
ms.openlocfilehash: 56fa56bff9d1418cc54430a6ab61140821a4ccc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294394"
---
# <a name="new-registry-entry-page"></a><span data-ttu-id="9b6a3-102">[新しいレジストリ エントリ] ページ</span><span class="sxs-lookup"><span data-stu-id="9b6a3-102">New Registry Entry Page</span></span>
<span data-ttu-id="9b6a3-103">図 1 は、Microsoft BizTalk Server ESB アプリケーションで指定した既存のエンドポイントの一覧を表示できます ESB 管理ポータル新しいレジストリ エントリ ページを示します。</span><span class="sxs-lookup"><span data-stu-id="9b6a3-103">Figure 1 shows the ESB Management Portal New Registry Entry page where you can view a list of the existing endpoints in a specified Microsoft BizTalk Server ESB application.</span></span>  
  
 <span data-ttu-id="9b6a3-104">![新しいレジストリ エントリ ページ](../esb-toolkit/media/ch8-newregistryentrypage.gif "Ch8 NewRegistryEntryPage")</span><span class="sxs-lookup"><span data-stu-id="9b6a3-104">![New Registry Entry Page](../esb-toolkit/media/ch8-newregistryentrypage.gif "Ch8-NewRegistryEntryPage")</span></span>  
  
 <span data-ttu-id="9b6a3-105">**図 1**</span><span class="sxs-lookup"><span data-stu-id="9b6a3-105">**Figure 1**</span></span>  
  
 <span data-ttu-id="9b6a3-106">**ESB 管理ポータル新しいレジストリ エントリ ページ**</span><span class="sxs-lookup"><span data-stu-id="9b6a3-106">**The ESB Management Portal New Registry Entry page**</span></span>  
  
 <span data-ttu-id="9b6a3-107">次の一覧では、ESB 管理ポータル新しいレジストリ エントリ ページの機能を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b6a3-107">The following list explains how you can use the features of the ESB Management Portal New Registry Entry page:</span></span>  
  
-   <span data-ttu-id="9b6a3-108">種類、状態、および表示するエンドポイントを含む BizTalk アプリケーションを指定するのにには、ページの上部にある 3 つのドロップダウン リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b6a3-108">Use the three drop-down lists near the top of the page to specify the type, status, and BizTalk application that contains the endpoints you want to view:</span></span>  
  
    -   <span data-ttu-id="9b6a3-109">最初の (エンドポイントの種類) ドロップダウン リストで選択**受信場所、送信ポート、** または**のすべてのエンドポイント**です。</span><span class="sxs-lookup"><span data-stu-id="9b6a3-109">In the first (endpoint type) drop-down list, you can select **Receive Locations, Send Ports,** or **All Endpoints**.</span></span>  
  
    -   <span data-ttu-id="9b6a3-110">2 つ目の (状態) ドロップダウン リストで選択**登録されている、NotRegistered、保留中、** または**すべて**です。</span><span class="sxs-lookup"><span data-stu-id="9b6a3-110">In the second (status) drop-down list, you can select **Registered, NotRegistered, Pending,** or **All**.</span></span>  
  
    -   <span data-ttu-id="9b6a3-111">3 番目の (BizTalk アプリケーション) ドロップダウン リストでは、現在インストールされている BizTalk アプリケーションの 1 つを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9b6a3-111">In the third (BizTalk application) drop-down list, you can select one of the currently installed BizTalk applications.</span></span>  
  
-   <span data-ttu-id="9b6a3-112">アプリケーションとエンドポイントの条件を指定してから、一致するエンドポイントの一覧を表示する BizTalk アプリケーションのドロップダウン リストの横にある矢印アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b6a3-112">After specifying the application and endpoint criteria, click the arrow icon next to the BizTalk application drop-down list to display a list of matching endpoints.</span></span>  
  
-   <span data-ttu-id="9b6a3-113">エンドポイントの一覧には、一致するエンドポイントの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b6a3-113">The list of endpoints contains details of matching endpoints.</span></span> <span data-ttu-id="9b6a3-114">各動的エンドポイントではないのリストで表示し、このエンドポイントを公開する要求の保留状態の詳細を編集できるリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b6a3-114">For each one that is not a dynamic endpoint, the list contains a link that allows you to view and edit the details of a pending request to publish this endpoint.</span></span>  
  
-   <span data-ttu-id="9b6a3-115">クリックして、**詳細の表示**リンクを開くには、リストのいずれかの行、[レジストリ詳細 ページ](../esb-toolkit/registry-details-page.md)要求を変更し、エンドポイントを公開できます。</span><span class="sxs-lookup"><span data-stu-id="9b6a3-115">Click the **View Detail** link in any row of the list to open the [Registry Details Page](../esb-toolkit/registry-details-page.md) where you can modify the request and publish the endpoint.</span></span>