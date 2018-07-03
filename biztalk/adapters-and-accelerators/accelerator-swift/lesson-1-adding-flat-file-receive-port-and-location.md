---
title: 'レッスン 1: は、受信ポートと場所を受信フラット ファイルの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- receive ports, creating
- creating, receive ports
ms.assetid: 881f58d8-f541-4a85-b534-cb1ca627c002
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e23525715be1816684ffa680f99cf8f8bd88ceca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966267"
---
# <a name="lesson-1-adding-flat-file-receive-port-and-location"></a><span data-ttu-id="3cf85-102">レッスン 1: フラット ファイルの追加の受信ポートと場所</span><span class="sxs-lookup"><span data-stu-id="3cf85-102">Lesson 1: Adding Flat File Receive Port and Location</span></span>
<span data-ttu-id="3cf85-103">受信ポートは、受信ポートを追加する際に構成する必要があります、関連付けられている受信場所を常に持ちます。</span><span class="sxs-lookup"><span data-stu-id="3cf85-103">The receive port always has an associated receive location that you must configure when you add the receive port.</span></span> <span data-ttu-id="3cf85-104">受信場所では、特定のアドレスの受信メッセージとメッセージの処理に使用するパイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-104">A receive location defines a specific address for an incoming message and the pipeline that you use to process the message.</span></span>  
  
### <a name="to-add-a-receive-port"></a><span data-ttu-id="3cf85-105">受信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="3cf85-105">To add a receive port</span></span>  
  
1. <span data-ttu-id="3cf85-106">右クリックし、BizTalk Server 管理コンソールで**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**。</span><span class="sxs-lookup"><span data-stu-id="3cf85-106">In the BizTalk Server Administration Console, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2. <span data-ttu-id="3cf85-107">受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MT103_FlatFile_ReceivePort**します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-107">In the Receive Port Properties dialog box, in the **Name** box, type **MT103_FlatFile_ReceivePort**.</span></span>  
  
3. <span data-ttu-id="3cf85-108">をクリックして**適用**をクリックして、ポートのバインド**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-108">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="3cf85-109">右クリックし、BizTalk Server 管理コンソールで**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**。</span><span class="sxs-lookup"><span data-stu-id="3cf85-109">In the BizTalk Server Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
5. <span data-ttu-id="3cf85-110">受信ポートのダイアログ ボックスのをクリックして**MT103_FlatFile_ReceivePort**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-110">In the Select a Receive Port dialog box, click **MT103_FlatFile_ReceivePort**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="3cf85-111">受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MT103_FlatFile_ReceiveLocation**します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-111">In the Receive Location Properties dialog box, in the **Name** box, type **MT103_FlatFile_ReceiveLocation**.</span></span>  
  
7. <span data-ttu-id="3cf85-112">**トランスポート**セクションの**型**テキスト ボックス、ドロップダウン リストをクリックし、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-112">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
8. <span data-ttu-id="3cf85-113">をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3cf85-113">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
9. <span data-ttu-id="3cf85-114">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-114">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
10. <span data-ttu-id="3cf85-115">フォルダーの参照 ダイアログ ボックスで、移動、 **\<ドライブ\>: \Labs\Inbound**フォルダー、およびクリック**フォルダの新規**。</span><span class="sxs-lookup"><span data-stu-id="3cf85-115">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs\Inbound** folder, and then click **Make New Folder**.</span></span>  
  
11. <span data-ttu-id="3cf85-116">作成、 **FlatFile**フォルダー **\<ドライブ\>: \Labs\Inbound**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="3cf85-116">Create a **FlatFile** folder in **\<drive\>:\Labs\Inbound**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="3cf85-117">**ファイル マスク**ボックスに「  **\*.txt**順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-117">In the **File mask** box, type **\*.txt**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="3cf85-118">受信場所のプロパティ ダイアログ ボックスで、ことを確認します**BizTalkServerApplication**の入力、**受信ハンドラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="3cf85-118">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  
  
14. <span data-ttu-id="3cf85-119">**受信パイプライン**ボックスで、 **MT103ReceivePipeline**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3cf85-119">For the **Receive Pipeline** box, select **MT103ReceivePipeline** from the drop-down list.</span></span>  
  
15. <span data-ttu-id="3cf85-120">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-120">Click **Apply**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="3cf85-121">BizTalk Server 管理コンソールで、次のようにクリックします。**受信場所**、右クリック**MT103_FlatFile_ReceiveLocation**、順にクリックします**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-121">In the BizTalk Server Administration Console, click **Receive Locations**, right-click **MT103_FlatFile_ReceiveLocation**, and then click **Enable**.</span></span>  
  
    <span data-ttu-id="3cf85-122">続行する[レッスン 2: XML の送信ポートを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="3cf85-122">Proceed to [Lesson 2: Adding an XML Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).</span></span>