---
title: POP3 アダプターのパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f799175e-e9e7-4937-93bd-aaec1c43b75a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c53bd0a487924a50155f388b6a657541ebe8fd3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971408"
---
# <a name="pop3-adapter-performance-counters"></a><span data-ttu-id="af7f9-102">POP3 アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="af7f9-102">POP3 Adapter Performance Counters</span></span>
<span data-ttu-id="af7f9-103">パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="af7f9-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="af7f9-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="af7f9-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="af7f9-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:POP3 Receive Adapter**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="af7f9-105">The following performance counters are accessible for each host instance under the **BizTalk:POP3 Receive Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="af7f9-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="af7f9-106">**Category**</span></span>|<span data-ttu-id="af7f9-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="af7f9-107">**Counter**</span></span>|<span data-ttu-id="af7f9-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="af7f9-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="af7f9-109">BizTalk:POP3 Receive Adapter</span><span class="sxs-lookup"><span data-stu-id="af7f9-109">BizTalk:POP3 Receive Adapter</span></span>|<span data-ttu-id="af7f9-110">Active sessions</span><span class="sxs-lookup"><span data-stu-id="af7f9-110">Active sessions</span></span>|<span data-ttu-id="af7f9-111">POP3 アダプターが同時に管理している確立済みの POP3 接続数。</span><span class="sxs-lookup"><span data-stu-id="af7f9-111">Number of open POP3 connections the POP3 adapter is managing at a time.</span></span>|  
||<span data-ttu-id="af7f9-112">Bytes received</span><span class="sxs-lookup"><span data-stu-id="af7f9-112">Bytes received</span></span>|<span data-ttu-id="af7f9-113">POP3 アダプターがメール サーバーからダウンロードした合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="af7f9-113">Total number of bytes downloaded by the POP3 adapter from a mail server.</span></span>|  
||<span data-ttu-id="af7f9-114">Bytes receive/Sec</span><span class="sxs-lookup"><span data-stu-id="af7f9-114">Bytes receive/Sec</span></span>|<span data-ttu-id="af7f9-115">POP3 アダプターがメール サーバーからダウンロードした 1 秒あたりのバイト数。</span><span class="sxs-lookup"><span data-stu-id="af7f9-115">Number of bytes downloaded by the POP3 adapter from a mail server per second.</span></span>|  
||<span data-ttu-id="af7f9-116">Messages received</span><span class="sxs-lookup"><span data-stu-id="af7f9-116">Messages received</span></span>|<span data-ttu-id="af7f9-117">POP3 アダプターがメール サーバーからダウンロードした電子メール メッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="af7f9-117">Total number of email messages downloaded by the POP3 adapter from a mail server.</span></span>|  
||<span data-ttu-id="af7f9-118">Messages received/Sec</span><span class="sxs-lookup"><span data-stu-id="af7f9-118">Messages received/Sec</span></span>|<span data-ttu-id="af7f9-119">POP3 アダプターがメール サーバーからダウンロードした 1 秒あたりの電子メール メッセージ数。</span><span class="sxs-lookup"><span data-stu-id="af7f9-119">Number of email messages downloaded by the POP3 adapter from mail server per second.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="af7f9-120">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="af7f9-120">To access performance counters</span></span>  
 <span data-ttu-id="af7f9-121">POP3 アダプターのパフォーマンス カウンターにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="af7f9-121">Follow these steps to access performance counters for the POP3 adapter:</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="af7f9-122">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="af7f9-122">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="af7f9-123">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。</span><span class="sxs-lookup"><span data-stu-id="af7f9-123">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="af7f9-124">**パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="af7f9-124">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="af7f9-125">**カウンターの追加**] ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **[BizTalk:POP3 Receive Adapter**パフォーマンス カウンター オブジェクトとカウンターを選択します。監視</span><span class="sxs-lookup"><span data-stu-id="af7f9-125">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:POP3 Receive Adapter** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="af7f9-126">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。</span><span class="sxs-lookup"><span data-stu-id="af7f9-126">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="af7f9-127">使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。</span><span class="sxs-lookup"><span data-stu-id="af7f9-127">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="af7f9-128">カウンターを追加すると、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="af7f9-128">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="af7f9-129">選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="af7f9-129">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af7f9-130">参照</span><span class="sxs-lookup"><span data-stu-id="af7f9-130">See Also</span></span>  
 [<span data-ttu-id="af7f9-131">BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="af7f9-131">Monitoring BizTalk Server</span></span>](../core/monitoring-biztalk-server.md)  
 <span data-ttu-id="af7f9-132">[POP3 アダプタでのマルチパート メッセージの処理](../core/processing-multi-part-messages-with-the-pop3-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="af7f9-132">[Processing Multi Part Messages with the POP3 Adapter](../core/processing-multi-part-messages-with-the-pop3-adapter.md) </span></span>  
 [<span data-ttu-id="af7f9-133">クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点</span><span class="sxs-lookup"><span data-stu-id="af7f9-133">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)