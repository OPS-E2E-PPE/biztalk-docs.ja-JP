---
title: "レッスン 2: フラット ファイル送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, flat files
- flat files, send ports
- creating, send ports
- send ports, creating
ms.assetid: 33dceb0d-85f5-4e19-820f-cd33b60cd32a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d438a6fa68136b05b358a81f4b026350d92a6af4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a><span data-ttu-id="17d68-102">レッスン 2: フラット ファイル送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="17d68-102">Lesson 2: Adding a Flat File Send Port</span></span>
<span data-ttu-id="17d68-103">このレッスンでは、送信ポートと送信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="17d68-103">In this lesson, you configure the send port and the send location.</span></span> <span data-ttu-id="17d68-104">メッセージを送信する方法を定義するのにには、送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="17d68-104">You use the send port to define how you want messages sent.</span></span> <span data-ttu-id="17d68-105">送信メッセージのファイル フォルダーの場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="17d68-105">You also create a file folder location for sent messages.</span></span>  
  
### <a name="to-add-a-flat-file-send-port"></a><span data-ttu-id="17d68-106">フラット ファイル送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="17d68-106">To add a flat file send port</span></span>  
  
1.  <span data-ttu-id="17d68-107">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-107">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="17d68-108">送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_FlatFile_SendPort**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-108">In the Send Port Properties dialog box, in the **Name** box, type **MT103_FlatFile_SendPort**.</span></span>  
  
3.  <span data-ttu-id="17d68-109">**トランスポート**] セクションの**型**ボックス、ドロップダウン リストをクリックし、[**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-109">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="17d68-110">クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。</span><span class="sxs-lookup"><span data-stu-id="17d68-110">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="17d68-111">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-111">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="17d68-112">フォルダーの参照 ダイアログ ボックスで、移動、 **\<ドライブ\>: \Labs**フォルダー、およびクリック**新しいフォルダーの作成**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-112">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs** folder, and then click **Make New Folder**.</span></span>  
  
7.  <span data-ttu-id="17d68-113">作成、**送信**フォルダーに**\<ドライブ\>: \Labs**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-113">Create an **Outbound** folder in **\<drive\>:\Labs**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="17d68-114">**ファイル名**ボックスに、入力**%MessageID%.txt**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-114">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="17d68-115">送信ポートのプロパティ] ダイアログ ボックスのドロップダウン リストをクリックして、**送信パイプライン**ボックスし、[ **MT103SendPipeline**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-115">In the Send Port Properties dialog box, click the drop-down list for the **Send pipeline** box, and then select **MT103SendPipeline**.</span></span>  
  
10. <span data-ttu-id="17d68-116">左側のウィンドウでをクリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="17d68-116">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="17d68-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="17d68-117">Use this</span></span>|<span data-ttu-id="17d68-118">目的</span><span class="sxs-lookup"><span data-stu-id="17d68-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="17d68-119">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="17d68-119">**Property**</span></span>|<span data-ttu-id="17d68-120">選択**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-120">Select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="17d68-121">**演算子**</span><span class="sxs-lookup"><span data-stu-id="17d68-121">**Operator**</span></span>|<span data-ttu-id="17d68-122">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-122">Select **==**.</span></span>|  
    |<span data-ttu-id="17d68-123">**値**</span><span class="sxs-lookup"><span data-stu-id="17d68-123">**Value**</span></span>|<span data-ttu-id="17d68-124">型**MT103_XML_ReceivePort**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-124">Type **MT103_XML_ReceivePort**.</span></span>|  
  
11. <span data-ttu-id="17d68-125">をクリックして**適用**、クリックして**[ok] です。**</span><span class="sxs-lookup"><span data-stu-id="17d68-125">Click **Apply**, and then click **OK.**</span></span>  
  
12. <span data-ttu-id="17d68-126">**送信ポート** ウィンドウを右クリックして**MT103_FlatFile_SendPort**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="17d68-126">In the **Send Ports** pane, right-click **MT103_FlatFile_SendPort**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="17d68-127">進みます[第 5 章: フラット ファイルを追加する受信場所および送信ポートの XML](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="17d68-127">Proceed to [Module 5: Adding a Flat File Receive Location and XML Send Port](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md).</span></span>