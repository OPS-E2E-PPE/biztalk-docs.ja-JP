---
title: Windows SharePoint Services アダプターのパフォーマンス カウンター |Microsoft Docs
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
ms.openlocfilehash: 1346bc558bd9881d9eb925856f79277a831c2665
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240365"
---
# <a name="windows-sharepoint-services-adapter-performance-counters"></a><span data-ttu-id="b5399-102">Windows SharePoint Services アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="b5399-102">Windows SharePoint Services Adapter Performance Counters</span></span>
<span data-ttu-id="b5399-103">パフォーマンス カウンターを使用して、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="b5399-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="b5399-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b5399-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="b5399-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできますが、 **BizTalk:Windows Sharepoint Services アダプター**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="b5399-105">The following performance counters are accessible for each host instance under the **BizTalk:Windows Sharepoint Services Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="b5399-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="b5399-106">**Category**</span></span>|<span data-ttu-id="b5399-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="b5399-107">**Counter**</span></span>|<span data-ttu-id="b5399-108">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="b5399-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="b5399-109">BizTalk:Windows Sharepoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="b5399-109">BizTalk:Windows Sharepoint Services Adapter</span></span>|<span data-ttu-id="b5399-110">% は、メッセージのエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b5399-110">% Receive Message Failures</span></span>|<span data-ttu-id="b5399-111">受信エラーにより、BizTalk Server で処理されていない Windows SharePoint Services ファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="b5399-111">The percentage of Windows SharePoint Services files that have not been processed by BizTalk Server due to receive errors.</span></span>|  
||<span data-ttu-id="b5399-112">送信メッセージのエラー %</span><span class="sxs-lookup"><span data-stu-id="b5399-112">% Send Message Failures</span></span>|<span data-ttu-id="b5399-113">BizTalk Server-が Windows SharePoint Services に送信しようとした失敗したメッセージの割合。</span><span class="sxs-lookup"><span data-stu-id="b5399-113">The percentage of failed messages BizTalk Server attempted to send to Windows SharePoint Services.</span></span>|  
||<span data-ttu-id="b5399-114">%Web サービスの呼び出しエラー</span><span class="sxs-lookup"><span data-stu-id="b5399-114">% Web Service Call Failures</span></span>|<span data-ttu-id="b5399-115">失敗した Windows SharePoint Services アダプター Web サービス呼び出しの割合。</span><span class="sxs-lookup"><span data-stu-id="b5399-115">The percentage of Windows SharePoint Services adapter Web service calls that have failed.</span></span>|  
||<span data-ttu-id="b5399-116">合計は、コミット エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5399-116">Total Receive Commit Failures</span></span>|<span data-ttu-id="b5399-117">SharePoint のドキュメントの状態を更新するときに発生した Windows SharePoint Services エラーの合計数。</span><span class="sxs-lookup"><span data-stu-id="b5399-117">The total number of Windows SharePoint Services errors that were raised when updating the status of the SharePoint documents.</span></span>|  
||<span data-ttu-id="b5399-118">合計受信メッセージのエラー</span><span class="sxs-lookup"><span data-stu-id="b5399-118">Total Receive Message Failures</span></span>|<span data-ttu-id="b5399-119">エラーにより BizTalk Server で処理されていない Windows SharePoint Services ファイルの合計数を受信します。</span><span class="sxs-lookup"><span data-stu-id="b5399-119">The total number of Windows SharePoint Services files received that have not been processed by BizTalk Server due to errors.</span></span>|  
||<span data-ttu-id="b5399-120">受信したメッセージの総数</span><span class="sxs-lookup"><span data-stu-id="b5399-120">Total Received Messages</span></span>|<span data-ttu-id="b5399-121">処理に失敗したファイルを含む、Windows SharePoint Services アダプターによって受信された Windows SharePoint Services ファイルの合計数。</span><span class="sxs-lookup"><span data-stu-id="b5399-121">The total number of Windows SharePoint Services files received by the Windows SharePoint Services adapter, including files that failed to process.</span></span>|  
||<span data-ttu-id="b5399-122">メッセージの合計送信エラー</span><span class="sxs-lookup"><span data-stu-id="b5399-122">Total Send Message Failures</span></span>|<span data-ttu-id="b5399-123">BizTalk Server が、Windows SharePoint Services に送信しようとしています。 失敗したメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="b5399-123">The total number of failed messages BizTalk Server attempted to send to Windows SharePoint Services.</span></span>|  
||<span data-ttu-id="b5399-124">送信されたメッセージの合計</span><span class="sxs-lookup"><span data-stu-id="b5399-124">Total Sent Messages</span></span>|<span data-ttu-id="b5399-125">BizTalk Server が処理に失敗したファイルを含む、Windows SharePoint Services に送信されるメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="b5399-125">The total number of messages BizTalk Server sent to Windows SharePoint Services, including files that failed to process.</span></span>|  
||<span data-ttu-id="b5399-126">合計の Web サービスの呼び出しエラー</span><span class="sxs-lookup"><span data-stu-id="b5399-126">Total Web Service Call Failures</span></span>|<span data-ttu-id="b5399-127">失敗した Windows SharePoint Services アダプター Web サービス呼び出しの合計数。</span><span class="sxs-lookup"><span data-stu-id="b5399-127">The total number of Windows SharePoint Services adapter Web service calls that have failed.</span></span>|  
||<span data-ttu-id="b5399-128">1 秒あたりの web サービス呼び出し</span><span class="sxs-lookup"><span data-stu-id="b5399-128">Web Service Calls per Second</span></span>|<span data-ttu-id="b5399-129">1 秒あたりの呼び出しを Windows SharePoint Services アダプター Web サービスの数。</span><span class="sxs-lookup"><span data-stu-id="b5399-129">The number of Windows SharePoint Services adapter Web service calls per second.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="b5399-130">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="b5399-130">To access performance counters</span></span>  
 <span data-ttu-id="b5399-131">パフォーマンス カウンターにアクセスするのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5399-131">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="b5399-132">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="b5399-132">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="b5399-133">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**パフォーマンス モニター**します。</span><span class="sxs-lookup"><span data-stu-id="b5399-133">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="b5399-134">**パフォーマンス モニター**  ダイアログ ボックスで、展開**監視ツール**を選択します**パフォーマンス モニター**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="b5399-134">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="b5399-135">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:Windows Sharepoint Services アダプター**パフォーマンス カウンター オブジェクトを選択監視するカウンター</span><span class="sxs-lookup"><span data-stu-id="b5399-135">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:Windows Sharepoint Services Adapter** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="b5399-136">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**します。</span><span class="sxs-lookup"><span data-stu-id="b5399-136">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="b5399-137">使用可能なカウンターのインスタンスすべてを選択する\<**すべてのインスタンス**\>します。</span><span class="sxs-lookup"><span data-stu-id="b5399-137">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="b5399-138">カウンターを追加すると、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="b5399-138">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="b5399-139">選択したパフォーマンス カウンターが表示される、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="b5399-139">The selected performance counters appear on the **Performance Monitor** screen.</span></span>