---
title: Windows SharePoint Services アダプターのパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41583fde-530a-4070-9647-f1ab6273aadf
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1af70299f5e308d1fc40fa6206f0ebfabff22a06
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973288"
---
# <a name="windows-sharepoint-services-adapter-performance-counters"></a><span data-ttu-id="e8236-102">Windows SharePoint Services アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="e8236-102">Windows SharePoint Services Adapter Performance Counters</span></span>
<span data-ttu-id="e8236-103">パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="e8236-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="e8236-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e8236-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="e8236-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:Windows Sharepoint Services アダプター**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="e8236-105">The following performance counters are accessible for each host instance under the **BizTalk:Windows Sharepoint Services Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="e8236-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="e8236-106">**Category**</span></span>|<span data-ttu-id="e8236-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="e8236-107">**Counter**</span></span>|<span data-ttu-id="e8236-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="e8236-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="e8236-109">BizTalk:Windows Sharepoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="e8236-109">BizTalk:Windows Sharepoint Services Adapter</span></span>|<span data-ttu-id="e8236-110">% Receive Message Failures</span><span class="sxs-lookup"><span data-stu-id="e8236-110">% Receive Message Failures</span></span>|<span data-ttu-id="e8236-111">受信エラーにより、BizTalk Server によって処理されなかった Windows SharePoint Services ファイルの比率。</span><span class="sxs-lookup"><span data-stu-id="e8236-111">The percentage of Windows SharePoint Services files that have not been processed by BizTalk Server due to receive errors.</span></span>|  
||<span data-ttu-id="e8236-112">% Send Message Failures</span><span class="sxs-lookup"><span data-stu-id="e8236-112">% Send Message Failures</span></span>|<span data-ttu-id="e8236-113">BizTalk Server が Windows SharePoint Services に送信を試みたメッセージのうち、送信に失敗したメッセージの比率。</span><span class="sxs-lookup"><span data-stu-id="e8236-113">The percentage of failed messages BizTalk Server attempted to send to Windows SharePoint Services.</span></span>|  
||<span data-ttu-id="e8236-114">% Web Service Call Failures</span><span class="sxs-lookup"><span data-stu-id="e8236-114">% Web Service Call Failures</span></span>|<span data-ttu-id="e8236-115">Windows SharePoint Services アダプター Web サービス呼び出しでエラーが発生した比率。</span><span class="sxs-lookup"><span data-stu-id="e8236-115">The percentage of Windows SharePoint Services adapter Web service calls that have failed.</span></span>|  
||<span data-ttu-id="e8236-116">Total Receive Commit Failures</span><span class="sxs-lookup"><span data-stu-id="e8236-116">Total Receive Commit Failures</span></span>|<span data-ttu-id="e8236-117">SharePoint ドキュメントのステータス更新時に発生した Windows SharePoint Services エラーの総数。</span><span class="sxs-lookup"><span data-stu-id="e8236-117">The total number of Windows SharePoint Services errors that were raised when updating the status of the SharePoint documents.</span></span>|  
||<span data-ttu-id="e8236-118">Total Receive Message Failures</span><span class="sxs-lookup"><span data-stu-id="e8236-118">Total Receive Message Failures</span></span>|<span data-ttu-id="e8236-119">受信した Windows SharePoint Services ファイルのうち、エラーにより、BizTalk Server によって処理されなかったファイルの総数。</span><span class="sxs-lookup"><span data-stu-id="e8236-119">The total number of Windows SharePoint Services files received that have not been processed by BizTalk Server due to errors.</span></span>|  
||<span data-ttu-id="e8236-120">Total Received Messages</span><span class="sxs-lookup"><span data-stu-id="e8236-120">Total Received Messages</span></span>|<span data-ttu-id="e8236-121">Windows SharePoint Services アダプターによって受信された Windows SharePoint Services ファイルの総数。処理に失敗したファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8236-121">The total number of Windows SharePoint Services files received by the Windows SharePoint Services adapter, including files that failed to process.</span></span>|  
||<span data-ttu-id="e8236-122">Total Send Message Failures</span><span class="sxs-lookup"><span data-stu-id="e8236-122">Total Send Message Failures</span></span>|<span data-ttu-id="e8236-123">BizTalk Server が Windows SharePoint Services に送信を試みたメッセージのうち、送信に失敗したメッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="e8236-123">The total number of failed messages BizTalk Server attempted to send to Windows SharePoint Services.</span></span>|  
||<span data-ttu-id="e8236-124">Total Sent Messages</span><span class="sxs-lookup"><span data-stu-id="e8236-124">Total Sent Messages</span></span>|<span data-ttu-id="e8236-125">BizTalk Server が Windows SharePoint Services に送信したメッセージの総数。処理に失敗したファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8236-125">The total number of messages BizTalk Server sent to Windows SharePoint Services, including files that failed to process.</span></span>|  
||<span data-ttu-id="e8236-126">Total Web Service Call Failures</span><span class="sxs-lookup"><span data-stu-id="e8236-126">Total Web Service Call Failures</span></span>|<span data-ttu-id="e8236-127">Windows SharePoint Services アダプター Web サービス呼び出しでエラーが発生した回数の合計。</span><span class="sxs-lookup"><span data-stu-id="e8236-127">The total number of Windows SharePoint Services adapter Web service calls that have failed.</span></span>|  
||<span data-ttu-id="e8236-128">Web Service Calls per Second</span><span class="sxs-lookup"><span data-stu-id="e8236-128">Web Service Calls per Second</span></span>|<span data-ttu-id="e8236-129">Windows SharePoint Services アダプター Web サービス呼び出しでエラーが発生した 1 秒あたりの回数。</span><span class="sxs-lookup"><span data-stu-id="e8236-129">The number of Windows SharePoint Services adapter Web service calls per second.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="e8236-130">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="e8236-130">To access performance counters</span></span>  
 <span data-ttu-id="e8236-131">パフォーマンス カウンターにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8236-131">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="e8236-132">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="e8236-132">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="e8236-133">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。</span><span class="sxs-lookup"><span data-stu-id="e8236-133">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="e8236-134">**パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="e8236-134">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="e8236-135">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:Windows Sharepoint Services アダプター**パフォーマンス カウンター オブジェクトを選択監視するカウンター</span><span class="sxs-lookup"><span data-stu-id="e8236-135">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:Windows Sharepoint Services Adapter** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="e8236-136">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。</span><span class="sxs-lookup"><span data-stu-id="e8236-136">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="e8236-137">使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。</span><span class="sxs-lookup"><span data-stu-id="e8236-137">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="e8236-138">カウンターを追加すると、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e8236-138">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="e8236-139">選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="e8236-139">The selected performance counters appear on the **Performance Monitor** screen.</span></span>