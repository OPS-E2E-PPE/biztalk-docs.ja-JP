---
title: "修復と再送信するメッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccd720b4-44a2-4c44-bf6e-8cf5e9ded1aa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e524ffca1b79032dce55f74e195032d14ec1bf9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="repairing-and-resubmitting-a-message"></a><span data-ttu-id="22c52-102">修復と再送信するメッセージ</span><span class="sxs-lookup"><span data-stu-id="22c52-102">Repairing and Resubmitting a Message</span></span>
<span data-ttu-id="22c52-103">修復する失敗したメッセージを再送信するには、ESB の管理ポータルの [エラー] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="22c52-103">To repair and resubmit a failed message, use the Faults page of the ESB Management Portal.</span></span>  
  
### <a name="to-repair-and-resubmit-a-message-for-processing"></a><span data-ttu-id="22c52-104">修復処理のためのメッセージを再送信するには</span><span class="sxs-lookup"><span data-stu-id="22c52-104">To repair and resubmit a message for processing</span></span>  
  
1.  <span data-ttu-id="22c52-105">必要なエラー メッセージを確認、[ポータル エラー ページ](../esb-toolkit/portal-faults-page.md)ESB 管理ポータルのページです。</span><span class="sxs-lookup"><span data-stu-id="22c52-105">Locate the desired fault message on the [Portal Faults Page](../esb-toolkit/portal-faults-page.md) page of the ESB Management Portal.</span></span> <span data-ttu-id="22c52-106">エラー ページでフィルター処理機能を使用して、特定のメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="22c52-106">Use the filtering capabilities on the Faults page to search for a specific message.</span></span> <span data-ttu-id="22c52-107">空のままにコントロールのいずれかのすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="22c52-107">Leave any of the controls empty to retrieve all messages.</span></span> <span data-ttu-id="22c52-108">非常に大きな障害データベースでフィルター処理が適切な結果を表示するのに数秒間かかる場合がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22c52-108">Note that filtering on a very large fault database may take several seconds to display the appropriate results.</span></span> <span data-ttu-id="22c52-109">図 1 は、エラー ページを示しています。</span><span class="sxs-lookup"><span data-stu-id="22c52-109">Figure 1 illustrates the Faults page.</span></span>  
  
     <span data-ttu-id="22c52-110">![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")</span><span class="sxs-lookup"><span data-stu-id="22c52-110">![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")</span></span>  
  
     <span data-ttu-id="22c52-111">**図 1**</span><span class="sxs-lookup"><span data-stu-id="22c52-111">**Figure 1**</span></span>  
  
     <span data-ttu-id="22c52-112">**ESB の管理ポータルの [エラー] ページ**</span><span class="sxs-lookup"><span data-stu-id="22c52-112">**The Faults page of the ESB Management Portal**</span></span>  
  
2.  <span data-ttu-id="22c52-113">任意の場所を開くには必要なエラー メッセージの行をクリックして、[ポータル フォールト メッセージ ビューアー](../esb-toolkit/portal-fault-message-viewer.md)ページ[エラーの詳細ビュー](../esb-toolkit/fault-details-view.md)です。</span><span class="sxs-lookup"><span data-stu-id="22c52-113">Click anywhere in the row of the desired fault message to open the [Portal Fault Message Viewer](../esb-toolkit/portal-fault-message-viewer.md) page in [Fault Details View](../esb-toolkit/fault-details-view.md).</span></span>  
  
3.  <span data-ttu-id="22c52-114">エラー メッセージ内のメッセージの一覧にエラーの詳細ビューの一番下までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="22c52-114">Scroll to the bottom of the Fault Details view to the list of messages contained within the fault message.</span></span> <span data-ttu-id="22c52-115">図 2 を示しています、**メッセージ**フォールト ビューアー ページのセクションです。</span><span class="sxs-lookup"><span data-stu-id="22c52-115">Figure 2 illustrates the **Messages** section of the Fault Viewer page.</span></span>  
  
     <span data-ttu-id="22c52-116">![メッセージのセクション](../esb-toolkit/media/ch8-messagessection.gif "Ch8 MessagesSection")</span><span class="sxs-lookup"><span data-stu-id="22c52-116">![Messages Section](../esb-toolkit/media/ch8-messagessection.gif "Ch8-MessagesSection")</span></span>  
  
     <span data-ttu-id="22c52-117">**図 2**</span><span class="sxs-lookup"><span data-stu-id="22c52-117">**Figure 2**</span></span>  
  
     <span data-ttu-id="22c52-118">**ESB の管理ポータルの [フォールト ビューアー] ページの Messages セクション**</span><span class="sxs-lookup"><span data-stu-id="22c52-118">**The Messages section of the Fault Viewer page of the ESB Management Portal**</span></span>  
  
4.  <span data-ttu-id="22c52-119">再送信するメッセージのメッセージ id をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22c52-119">Click the message identifier of the message you want to resubmit.</span></span> <span data-ttu-id="22c52-120">内のメッセージが開きます[メッセージの詳細ビュー](../esb-toolkit/message-details-view.md)図 3 に示すように個々 のメッセージとメッセージの内容の詳細が示されます。</span><span class="sxs-lookup"><span data-stu-id="22c52-120">This opens the message in [Message Details View](../esb-toolkit/message-details-view.md), which shows details of the individual message and the message content, as illustrated in Figure 3.</span></span>  
  
     <span data-ttu-id="22c52-121">![メッセージのビューアー](../esb-toolkit/media/ch8-messageviewer.gif "Ch8 MessageViewer")</span><span class="sxs-lookup"><span data-stu-id="22c52-121">![Message Viewer](../esb-toolkit/media/ch8-messageviewer.gif "Ch8-MessageViewer")</span></span>  
  
     <span data-ttu-id="22c52-122">**図 3**</span><span class="sxs-lookup"><span data-stu-id="22c52-122">**Figure 3**</span></span>  
  
     <span data-ttu-id="22c52-123">**ESB の管理ポータルの [メッセージ ビューアー] ページ**</span><span class="sxs-lookup"><span data-stu-id="22c52-123">**The Message Viewer page of the ESB Management Portal**</span></span>  
  
5.  <span data-ttu-id="22c52-124">クリックして、**編集**編集モード、および必要に応じて、メッセージの内容を編集に切り替えるには、メッセージ コンテンツを含むテキスト ボックスの下のリンク。</span><span class="sxs-lookup"><span data-stu-id="22c52-124">Click the **Edit** link under the text box that contains the message content to switch to edit mode, and then edit the message contents as required.</span></span> <span data-ttu-id="22c52-125">たとえば、メッセージ内に含まれるサービスのメソッドの呼び出しのパラメーターを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22c52-125">For example, you may need to change the parameters for service method invocations contained within the message.</span></span> <span data-ttu-id="22c52-126">再送信されたときに、メッセージの拒否を防ぐために (XML またはフラット ファイル形式) などのネイティブのドキュメントのスタイルに従う必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22c52-126">Note that you must adhere to the native document style (such as XML or flat file format) to prevent rejection of the message when resubmitted.</span></span> <span data-ttu-id="22c52-127">図 4 を示しています、**メッセージの詳細**メッセージ エディター ページのセクションでします。</span><span class="sxs-lookup"><span data-stu-id="22c52-127">Figure 4 illustrates the **Message Details** section of the Message Editor page.</span></span>  
  
     <span data-ttu-id="22c52-128">![メッセージの詳細](../esb-toolkit/media/ch8-messagedetails.gif "Ch8 MessageDetails")</span><span class="sxs-lookup"><span data-stu-id="22c52-128">![Message Details](../esb-toolkit/media/ch8-messagedetails.gif "Ch8-MessageDetails")</span></span>  
  
     <span data-ttu-id="22c52-129">**図 4**</span><span class="sxs-lookup"><span data-stu-id="22c52-129">**Figure 4**</span></span>  
  
     <span data-ttu-id="22c52-130">**ESB の管理ポータルの [メッセージ ビューアー] ページの [メッセージの詳細] セクション**</span><span class="sxs-lookup"><span data-stu-id="22c52-130">**The Message Details section of the Message Viewer page of the ESB Management Portal**</span></span>  
  
6.  <span data-ttu-id="22c52-131">メッセージを編集した後に、メッセージのテキスト ボックスの下のドロップダウン リストで再送信場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="22c52-131">After editing the message, select a resubmission location in the drop-down list under the message text box.</span></span> <span data-ttu-id="22c52-132">この一覧は、使用可能なエンドポイントの動的に取得した一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="22c52-132">This list shows the dynamically retrieved list of available endpoints.</span></span> <span data-ttu-id="22c52-133">再送信エンドポイントとして構成されたエンドポイントを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22c52-133">You must select an endpoint configured as a resubmission endpoint.</span></span> <span data-ttu-id="22c52-134">次のエンドポイントの再送信に適したのとおりです。</span><span class="sxs-lookup"><span data-stu-id="22c52-134">The following endpoints are suitable for resubmission:</span></span>  
  
    -   <span data-ttu-id="22c52-135">**WCF 入り口**です。</span><span class="sxs-lookup"><span data-stu-id="22c52-135">**WCF On-Ramp**.</span></span> <span data-ttu-id="22c52-136">このエンドポイントの ESB 行程 Services WCF 入り口、XML ファイルに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="22c52-136">This endpoint is the ESB Itinerary Services WCF on-ramp and is available only for XML files.</span></span> <span data-ttu-id="22c52-137">ポータルの Web.config ファイルでは、この入り口の URL を定義します。</span><span class="sxs-lookup"><span data-stu-id="22c52-137">The portal Web.config file defines the URL for this on-ramp.</span></span>  
  
    -   <span data-ttu-id="22c52-138">**SOAP 入り口**です。</span><span class="sxs-lookup"><span data-stu-id="22c52-138">**SOAP On-Ramp**.</span></span> <span data-ttu-id="22c52-139">このエンドポイントの ESB 行程サービス ASMX 入り口、XML ファイルに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="22c52-139">This endpoint is the ESB Itinerary Services ASMX on-ramp and is available only for XML files.</span></span> <span data-ttu-id="22c52-140">ポータルの Web.config ファイルでは、この入り口の URL を定義します。</span><span class="sxs-lookup"><span data-stu-id="22c52-140">The portal Web.config file defines the URL for this on-ramp.</span></span>  
  
    -   <span data-ttu-id="22c52-141">**いずれかの受信場所の BizTalk HTTP アダプターを使用して**です。</span><span class="sxs-lookup"><span data-stu-id="22c52-141">**Any receive location using the BizTalk HTTP adapter**.</span></span> <span data-ttu-id="22c52-142">このオプションは XML ファイルとフラット ファイルの使用です。</span><span class="sxs-lookup"><span data-stu-id="22c52-142">This option is available for XML files and flat files.</span></span>  
  
7.  <span data-ttu-id="22c52-143">クリックして、**を再送信**メッセージ再送信へのリンク。</span><span class="sxs-lookup"><span data-stu-id="22c52-143">Click the **Resubmit** link to resubmit the message.</span></span> <span data-ttu-id="22c52-144">示すメッセージ、**再送信状態**メッセージ コンテンツのテキスト ボックスの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="22c52-144">A message indicating the **Resubmission Status** appears under the message content text box.</span></span>  
  
8.  <span data-ttu-id="22c52-145">必要な場合、開く、[監査ログ ページ](../esb-toolkit/audit-log-page.md)から、**管理者**図 5 に示すように、メッセージの再送信を確認します。</span><span class="sxs-lookup"><span data-stu-id="22c52-145">If required, open the [Audit Log Page](../esb-toolkit/audit-log-page.md) from the **Admin** tab to confirm message resubmission, as illustrated in Figure 5.</span></span>  
  
     <span data-ttu-id="22c52-146">![AuditLog ページの小さなビュー](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8 AuditLogPageSmallView")</span><span class="sxs-lookup"><span data-stu-id="22c52-146">![AuditLog Page Small View](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8-AuditLogPageSmallView")</span></span>  
  
     <span data-ttu-id="22c52-147">**図 5**</span><span class="sxs-lookup"><span data-stu-id="22c52-147">**Figure 5**</span></span>  
  
     <span data-ttu-id="22c52-148">**ESB の管理ポータルの [監査ログ] ページ**</span><span class="sxs-lookup"><span data-stu-id="22c52-148">**The Audit Log page of the ESB Management Portal**</span></span>