---
title: レッスン 2:フラット ファイル送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, flat files
- flat files, send ports
- creating, send ports
- send ports, creating
ms.assetid: 33dceb0d-85f5-4e19-820f-cd33b60cd32a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc7a9be734f2b4f360dd006492a9c9298bd0658b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377490"
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a><span data-ttu-id="791cd-102">レッスン 2:フラット ファイル送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="791cd-102">Lesson 2: Adding a Flat File Send Port</span></span>
<span data-ttu-id="791cd-103">このレッスンでは、送信ポートおよび送信場所を構成できます。</span><span class="sxs-lookup"><span data-stu-id="791cd-103">In this lesson, you configure the send port and the send location.</span></span> <span data-ttu-id="791cd-104">メッセージを送信する方法を定義するのにには、送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="791cd-104">You use the send port to define how you want messages sent.</span></span> <span data-ttu-id="791cd-105">送信されたメッセージのファイル フォルダーの場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="791cd-105">You also create a file folder location for sent messages.</span></span>  

### <a name="to-add-a-flat-file-send-port"></a><span data-ttu-id="791cd-106">フラット ファイル送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="791cd-106">To add a flat file send port</span></span>  

1. <span data-ttu-id="791cd-107">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。</span><span class="sxs-lookup"><span data-stu-id="791cd-107">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="791cd-108">送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MT103_FlatFile_SendPort**します。</span><span class="sxs-lookup"><span data-stu-id="791cd-108">In the Send Port Properties dialog box, in the **Name** box, type **MT103_FlatFile_SendPort**.</span></span>  

3. <span data-ttu-id="791cd-109">**トランスポート**セクションの**型**ボックス、ドロップダウン リストをクリックし、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="791cd-109">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  

4. <span data-ttu-id="791cd-110">をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="791cd-110">Click the **Configure** button to the right of the Type drop-down list.</span></span>  

5. <span data-ttu-id="791cd-111">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="791cd-111">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  

6. <span data-ttu-id="791cd-112">フォルダーの参照 ダイアログ ボックスで、移動、 **\<ドライブ\>: \Labs**フォルダー、およびクリック**フォルダの新規**。</span><span class="sxs-lookup"><span data-stu-id="791cd-112">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs** folder, and then click **Make New Folder**.</span></span>  

7. <span data-ttu-id="791cd-113">作成、**送信**フォルダー **\<ドライブ\>: \Labs**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="791cd-113">Create an **Outbound** folder in **\<drive\>:\Labs**, and then click **OK**.</span></span>  

8. <span data-ttu-id="791cd-114">**ファイル名**ボックスに「 **%MessageID%.txt**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="791cd-114">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  

9. <span data-ttu-id="791cd-115">送信ポートのプロパティ ダイアログ ボックスで、クリックしてのドロップダウン リスト、**送信パイプライン**ボックスを選び**MT103SendPipeline**します。</span><span class="sxs-lookup"><span data-stu-id="791cd-115">In the Send Port Properties dialog box, click the drop-down list for the **Send pipeline** box, and then select **MT103SendPipeline**.</span></span>  

10. <span data-ttu-id="791cd-116">左側のウィンドウで次のようにクリックします。**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="791cd-116">In the left pane, click **Filters**, and then do the following:</span></span>  


    |   <span data-ttu-id="791cd-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="791cd-117">Use this</span></span>   |           <span data-ttu-id="791cd-118">目的</span><span class="sxs-lookup"><span data-stu-id="791cd-118">To do this</span></span>            |
    |--------------|---------------------------------|
    | <span data-ttu-id="791cd-119">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="791cd-119">**Property**</span></span> | <span data-ttu-id="791cd-120">選択**BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="791cd-120">Select **BTS.ReceivePortName**.</span></span> |
    | <span data-ttu-id="791cd-121">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="791cd-121">**Operator**</span></span> |         <span data-ttu-id="791cd-122">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="791cd-122">Select **==**.</span></span>          |
    |  <span data-ttu-id="791cd-123">**[値]**</span><span class="sxs-lookup"><span data-stu-id="791cd-123">**Value**</span></span>   | <span data-ttu-id="791cd-124">型**MT103_XML_ReceivePort**します。</span><span class="sxs-lookup"><span data-stu-id="791cd-124">Type **MT103_XML_ReceivePort**.</span></span> |


11. <span data-ttu-id="791cd-125">クリックして**適用**、順にクリックします**ok をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="791cd-125">Click **Apply**, and then click **OK.**</span></span>  

12. <span data-ttu-id="791cd-126">**送信ポート**ウィンドウで、右クリックして**MT103_FlatFile_SendPort**、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="791cd-126">In the **Send Ports** pane, right-click **MT103_FlatFile_SendPort**, and then click **Start**.</span></span>  

    <span data-ttu-id="791cd-127">続行する[第 5 章。受信場所と XML 送信ポートのフラット ファイルを追加](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="791cd-127">Proceed to [Module 5: Adding a Flat File Receive Location and XML Send Port](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md).</span></span>