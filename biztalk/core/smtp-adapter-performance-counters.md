---
title: "SMTP アダプターのパフォーマンス カウンター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c7aa7dd-1674-4bbb-b22f-92204d55c4b8
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e839a1aefa7a1b7ea7f35bd3cba58e01720db15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter-performance-counters"></a><span data-ttu-id="056fe-102">SMTP アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="056fe-102">SMTP Adapter Performance Counters</span></span>
<span data-ttu-id="056fe-103">パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="056fe-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="056fe-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="056fe-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="056fe-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:SMTP Send Adapter**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="056fe-105">The following performance counters are accessible for each host instance under the **BizTalk:SMTP Send Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="056fe-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="056fe-106">**Category**</span></span>|<span data-ttu-id="056fe-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="056fe-107">**Counter**</span></span>|<span data-ttu-id="056fe-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="056fe-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="056fe-109">BizTalk:SMTP 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="056fe-109">BizTalk:SMTP Send Adapter</span></span>|<span data-ttu-id="056fe-110">Messages sent</span><span class="sxs-lookup"><span data-stu-id="056fe-110">Messages sent</span></span>|<span data-ttu-id="056fe-111">SMTP アダプターによって送信されたメッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="056fe-111">Total number of messages sent by the SMTP adapter.</span></span> <span data-ttu-id="056fe-112">カウンターは、メッセージが SMTP サーバーに送信された場合にのみ増やされます。</span><span class="sxs-lookup"><span data-stu-id="056fe-112">The counter is incremented only for messages that have been transmitted to the SMTP server.</span></span>|  
||<span data-ttu-id="056fe-113">Messages Sent/sec</span><span class="sxs-lookup"><span data-stu-id="056fe-113">Messages sent/Sec</span></span>|<span data-ttu-id="056fe-114">SMTP アダプターが 1 秒あたりに送信したメッセージ数。</span><span class="sxs-lookup"><span data-stu-id="056fe-114">Number of messages sent by the SMTP adapter per second.</span></span> <span data-ttu-id="056fe-115">このカウンターの対象となるのは、SMTP サーバーに送信されたメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="056fe-115">The counter applies only to messages that have been transmitted to the SMTP server.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="056fe-116">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="056fe-116">To access performance counters</span></span>  
 <span data-ttu-id="056fe-117">パフォーマンス カウンターにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="056fe-117">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="056fe-118">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="056fe-118">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="056fe-119">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。</span><span class="sxs-lookup"><span data-stu-id="056fe-119">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="056fe-120">**パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="056fe-120">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="056fe-121">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:SMTP Send Adapter**パフォーマンス カウンター オブジェクトとカウンターを選択します。監視</span><span class="sxs-lookup"><span data-stu-id="056fe-121">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:SMTP Send Adapter**performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="056fe-122">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。</span><span class="sxs-lookup"><span data-stu-id="056fe-122">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="056fe-123">使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**>。</span><span class="sxs-lookup"><span data-stu-id="056fe-123">To select all available counter instances, select \<**All instances**>.</span></span>  
  
5.  <span data-ttu-id="056fe-124">カウンターを追加すると、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="056fe-124">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="056fe-125">選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="056fe-125">The selected performance counters appear on the **Performance Monitor** screen.</span></span>