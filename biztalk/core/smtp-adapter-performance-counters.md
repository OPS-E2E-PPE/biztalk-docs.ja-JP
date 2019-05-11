---
title: SMTP アダプターのパフォーマンス カウンター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c7aa7dd-1674-4bbb-b22f-92204d55c4b8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 739f926ed4b42b254c5c57e5f71a1cb914dbcb5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401847"
---
# <a name="smtp-adapter-performance-counters"></a><span data-ttu-id="a03dd-102">SMTP アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="a03dd-102">SMTP Adapter Performance Counters</span></span>
<span data-ttu-id="a03dd-103">パフォーマンス カウンターを使用して、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="a03dd-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="a03dd-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a03dd-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="a03dd-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできますが、 **BizTalk:SMTP Send Adapter**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="a03dd-105">The following performance counters are accessible for each host instance under the **BizTalk:SMTP Send Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="a03dd-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="a03dd-106">**Category**</span></span>|<span data-ttu-id="a03dd-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="a03dd-107">**Counter**</span></span>|<span data-ttu-id="a03dd-108">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="a03dd-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="a03dd-109">BizTalk:SMTP 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="a03dd-109">BizTalk:SMTP Send Adapter</span></span>|<span data-ttu-id="a03dd-110">送信されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="a03dd-110">Messages sent</span></span>|<span data-ttu-id="a03dd-111">SMTP アダプターによって送信されたメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="a03dd-111">Total number of messages sent by the SMTP adapter.</span></span> <span data-ttu-id="a03dd-112">カウンターは、SMTP サーバーに送信されたメッセージに対してのみインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="a03dd-112">The counter is incremented only for messages that have been transmitted to the SMTP server.</span></span>|  
||<span data-ttu-id="a03dd-113">メッセージの送信/秒</span><span class="sxs-lookup"><span data-stu-id="a03dd-113">Messages sent/Sec</span></span>|<span data-ttu-id="a03dd-114">1 秒あたりの SMTP アダプターによって送信されたメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="a03dd-114">Number of messages sent by the SMTP adapter per second.</span></span> <span data-ttu-id="a03dd-115">このカウンターは、SMTP サーバーに送信されたメッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a03dd-115">The counter applies only to messages that have been transmitted to the SMTP server.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="a03dd-116">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="a03dd-116">To access performance counters</span></span>  
 <span data-ttu-id="a03dd-117">パフォーマンス カウンターにアクセスするのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-117">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="a03dd-118">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="a03dd-118">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="a03dd-119">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**パフォーマンス モニター**します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-119">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="a03dd-120">**パフォーマンス モニター**  ダイアログ ボックスで、展開**監視ツール**を選択します**パフォーマンス モニター**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="a03dd-120">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="a03dd-121">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:SMTP Send Adapter**パフォーマンス カウンター オブジェクトとカウンターを選択します監視</span><span class="sxs-lookup"><span data-stu-id="a03dd-121">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:SMTP Send Adapter**performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="a03dd-122">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-122">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="a03dd-123">使用可能なカウンターのインスタンスすべてを選択する\<**すべてのインスタンス**\>します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-123">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="a03dd-124">カウンターを追加すると、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-124">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="a03dd-125">選択したパフォーマンス カウンターが表示される、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="a03dd-125">The selected performance counters appear on the **Performance Monitor** screen.</span></span>