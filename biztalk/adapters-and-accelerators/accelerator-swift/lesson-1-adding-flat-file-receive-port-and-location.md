---
title: 'レッスン 1: のフラット ファイルを追加する受信ポートと場所 |Microsoft ドキュメント'
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
ms.openlocfilehash: 9856e0da6e8a4bc958b5fe08e0e1b5e87494531b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961120"
---
# <a name="lesson-1-adding-flat-file-receive-port-and-location"></a><span data-ttu-id="e0231-102">レッスン 1: フラット ファイルの追加の受信ポートと受信場所</span><span class="sxs-lookup"><span data-stu-id="e0231-102">Lesson 1: Adding Flat File Receive Port and Location</span></span>
<span data-ttu-id="e0231-103">受信ポートは、常に、受信ポートを追加するときに構成する必要がある、関連付けられている受信場所を持ちます。</span><span class="sxs-lookup"><span data-stu-id="e0231-103">The receive port always has an associated receive location that you must configure when you add the receive port.</span></span> <span data-ttu-id="e0231-104">受信場所では、受信メッセージとメッセージの処理に使用するパイプラインの特定のアドレスを定義します。</span><span class="sxs-lookup"><span data-stu-id="e0231-104">A receive location defines a specific address for an incoming message and the pipeline that you use to process the message.</span></span>  
  
### <a name="to-add-a-receive-port"></a><span data-ttu-id="e0231-105">受信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="e0231-105">To add a receive port</span></span>  
  
1.  <span data-ttu-id="e0231-106">BizTalk Server 管理コンソールで、右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-106">In the BizTalk Server Administration Console, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="e0231-107">受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_FlatFile_ReceivePort**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-107">In the Receive Port Properties dialog box, in the **Name** box, type **MT103_FlatFile_ReceivePort**.</span></span>  
  
3.  <span data-ttu-id="e0231-108">をクリックして**適用**をクリックして、ポートのバインド**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-108">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="e0231-109">BizTalk Server 管理コンソールで、右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-109">In the BizTalk Server Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
5.  <span data-ttu-id="e0231-110">[受信ポート] ダイアログ ボックスのをクリックして**MT103_FlatFile_ReceivePort**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-110">In the Select a Receive Port dialog box, click **MT103_FlatFile_ReceivePort**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="e0231-111">受信場所のプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_FlatFile_ReceiveLocation**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-111">In the Receive Location Properties dialog box, in the **Name** box, type **MT103_FlatFile_ReceiveLocation**.</span></span>  
  
7.  <span data-ttu-id="e0231-112">**トランスポート**] セクションの**型**テキスト ボックスがドロップダウン リストをクリックし、[**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-112">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
8.  <span data-ttu-id="e0231-113">クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。</span><span class="sxs-lookup"><span data-stu-id="e0231-113">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
9. <span data-ttu-id="e0231-114">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-114">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
10. <span data-ttu-id="e0231-115">フォルダーの参照 ダイアログ ボックスで、移動、 **\<ドライブ\>: \Labs\Inbound**フォルダー、およびクリック**新しいフォルダーの作成**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-115">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs\Inbound** folder, and then click **Make New Folder**.</span></span>  
  
11. <span data-ttu-id="e0231-116">作成、 **FlatFile**フォルダー **\<ドライブ\>: \Labs\Inbound**、順にクリック **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="e0231-116">Create a **FlatFile** folder in **\<drive\>:\Labs\Inbound**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="e0231-117">**ファイル マスク**ボックスに、入力 **\*.txt**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-117">In the **File mask** box, type **\*.txt**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="e0231-118">受信場所のプロパティ ダイアログ ボックスでいることを確認**BizTalkServerApplication**として入力された、**受信ハンドラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="e0231-118">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  
  
14. <span data-ttu-id="e0231-119">**受信パイプライン**ボックスで、 **MT103ReceivePipeline**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="e0231-119">For the **Receive Pipeline** box, select **MT103ReceivePipeline** from the drop-down list.</span></span>  
  
15. <span data-ttu-id="e0231-120">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-120">Click **Apply**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="e0231-121">BizTalk Server 管理コンソールで、をクリックして**受信場所**を右クリックして**MT103_FlatFile_ReceiveLocation**、クリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="e0231-121">In the BizTalk Server Administration Console, click **Receive Locations**, right-click **MT103_FlatFile_ReceiveLocation**, and then click **Enable**.</span></span>  
  
 <span data-ttu-id="e0231-122">進みます[レッスン 2: XML 送信ポートを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0231-122">Proceed to [Lesson 2: Adding an XML Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).</span></span>