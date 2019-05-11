---
title: ESB 管理ポータルとエラー メッセージ ビューアー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4a1636c-2e45-4ee5-92c2-81c976582da3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97b577e280eabece88a9d8196432fb013780c46c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399727"
---
# <a name="the-esb-management-portal-and-fault-message-viewer"></a><span data-ttu-id="4a90a-102">ESB 管理ポータルとエラー メッセージ ビューアー</span><span class="sxs-lookup"><span data-stu-id="4a90a-102">The ESB Management Portal and Fault Message Viewer</span></span>
<span data-ttu-id="4a90a-103">主要なコンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は Web ベース ポータルを提供する例外のさまざまな管理とアラートの通知機能は、さらに、便利な構成管理と Universal Description, Discovery, and Integration (機能UDDI) 登録のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4a90a-103">A major component of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is a Web-based portal that provides a wide range of exception management and alert notification features; in addition, it acts as a useful configuration management and Universal Description, Discovery, and Integration (UDDI) registration interface.</span></span> <span data-ttu-id="4a90a-104">図 1 は、現在実行中のアプリケーションの正常性の概要を提供すると、ポータルのホーム ページを示します。</span><span class="sxs-lookup"><span data-stu-id="4a90a-104">Figure 1 shows the home page of the portal, which provides an overview of the health of the currently running applications.</span></span>  
  
 <span data-ttu-id="4a90a-105">![ポータルのホーム ページ](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")</span><span class="sxs-lookup"><span data-stu-id="4a90a-105">![Portal Home Page](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")</span></span>  
  
 <span data-ttu-id="4a90a-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="4a90a-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="4a90a-107">**ESB 管理ポータルのホーム ページ**</span><span class="sxs-lookup"><span data-stu-id="4a90a-107">**The home page of the ESB Management Portal**</span></span>  
  
 <span data-ttu-id="4a90a-108">ユーザーは、図 2 に示すように、エラーのアンビエントと静的のプロパティと、エラー メッセージに含まれる元のメッセージの一覧を表示する、ESB 管理ポータルに表示されるエラー メッセージを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4a90a-108">Users can select a fault message displayed in the ESB Management Portal to view the ambient and static properties of the fault and a list of the original messages contained in the fault message, as shown in Figure 2.</span></span>  
  
 <span data-ttu-id="4a90a-109">![[エラー ビューアー] ページ](../esb-toolkit/media/ch4-faultviewerpage.gif "Ch4 FaultViewerPage")</span><span class="sxs-lookup"><span data-stu-id="4a90a-109">![Faul tViewer Page](../esb-toolkit/media/ch4-faultviewerpage.gif "Ch4-FaultViewerPage")</span></span>  
  
 <span data-ttu-id="4a90a-110">**図 2**</span><span class="sxs-lookup"><span data-stu-id="4a90a-110">**Figure 2**</span></span>  
  
 <span data-ttu-id="4a90a-111">**ESB 管理ポータルの ESB エラー ビューアー ページ**</span><span class="sxs-lookup"><span data-stu-id="4a90a-111">**The ESB Fault Viewer page of the ESB Management Portal**</span></span>  
  
 <span data-ttu-id="4a90a-112">ESB 管理ポータルに表示される ESB エラー メッセージの処理のために送信されたときに、元のメッセージの値にエラーの結果があります。</span><span class="sxs-lookup"><span data-stu-id="4a90a-112">ESB Fault messages displayed in the ESB Management Portal may be the result of an error in the values of the original message when submitted for processing.</span></span> <span data-ttu-id="4a90a-113">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]管理者またはユーザーは、失敗したメッセージを編集して、入り口処理のために送信するのには、「修復し、再送信」機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4a90a-113">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports "repair and resubmit" functionality, which allows administrators or users to edit failed messages and to submit them to an on-ramp for processing.</span></span>  
  
 <span data-ttu-id="4a90a-114">含まれるメッセージが開かれ、1 つメッセージ表示 ページのビューで選択するメッセージの詳細、図 3 に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="4a90a-114">Selecting one of the contained messages opens the Message View page in Message Details view, as shown in Figure 3.</span></span> <span data-ttu-id="4a90a-115">このビューでは、ユーザーがコンテンツや、メッセージのダウンロード をクリックして、メッセージを表示できます**編集**が修復し、メッセージを再送信、編集ビューに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="4a90a-115">In this view, users can see the message content, download the message, or click **Edit** to switch to Edit view, where they can repair and resubmit the message.</span></span>  
  
 <span data-ttu-id="4a90a-116">![メッセージ ビューアー ページ](../esb-toolkit/media/ch4-messageviewerpage.gif "Ch4 MessageViewerPage")</span><span class="sxs-lookup"><span data-stu-id="4a90a-116">![Message Viewer Page](../esb-toolkit/media/ch4-messageviewerpage.gif "Ch4-MessageViewerPage")</span></span>  
  
 <span data-ttu-id="4a90a-117">**図 3**</span><span class="sxs-lookup"><span data-stu-id="4a90a-117">**Figure 3**</span></span>  
  
 <span data-ttu-id="4a90a-118">**エラーの詳細ビューを表示、ESB メッセージ ビューアー**</span><span class="sxs-lookup"><span data-stu-id="4a90a-118">**The ESB Message Viewer showing the Fault Details view**</span></span>  
  
 <span data-ttu-id="4a90a-119">フォールト ビューアー、メッセージの再送信のプロセス一覧については、使用する手法など、ESB 管理ポータルの使用法のオプションの詳細と並べ替え、およびエラーの分析を参照してください[による BizTalk ESB の管理Toolkit](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a90a-119">For a complete description and usage options of the ESB Management Portal, including the Fault Viewer, the message resubmission process, and the techniques used for listing, sorting, and analyzing faults, see [Administration with the BizTalk ESB Toolkit](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md).</span></span>