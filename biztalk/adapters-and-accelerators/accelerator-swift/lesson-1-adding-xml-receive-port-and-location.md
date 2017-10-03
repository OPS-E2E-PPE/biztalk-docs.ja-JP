---
title: "レッスン 1: は、ポートと受信場所に表示される XML の追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- receive ports, creating
- creating, receive ports
ms.assetid: 252bc080-3820-44cc-8749-715869f3f684
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 186cbb4e021a281ab834f04097f005c2597fbd37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-1-adding-xml-receive-port-and-location"></a><span data-ttu-id="8d60e-102">レッスン 1: XML の受信ポートと受信場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="8d60e-102">Lesson 1: Adding XML Receive Port and Location</span></span>
<span data-ttu-id="8d60e-103">受信ポートとは、類似する受信場所の論理的なグループです。</span><span class="sxs-lookup"><span data-stu-id="8d60e-103">A receive port is a logical grouping of similar receive locations.</span></span> <span data-ttu-id="8d60e-104">受信場所は、受信メッセージとメッセージを処理するために使用するパイプラインの特定のアドレス (URL またはファイルの場所) などを定義します。</span><span class="sxs-lookup"><span data-stu-id="8d60e-104">A receive location defines a specific address (such as a URL or file location) for an incoming message and the pipeline that is used to process the message.</span></span>  
  
### <a name="to-add-a-receive-port"></a><span data-ttu-id="8d60e-105">受信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="8d60e-105">To add a receive port</span></span>  
  
1.  <span data-ttu-id="8d60e-106">開始**BizTalk Server 管理コンソール**コンソールです。</span><span class="sxs-lookup"><span data-stu-id="8d60e-106">Start **BizTalk Server Administration** console.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8d60e-107">BizTalk Server 管理コンソール開くこともできますから Visual Studio 内をクリックして**BizTalk Server 管理コンソール**で、**ツール**メニュー。</span><span class="sxs-lookup"><span data-stu-id="8d60e-107">The BizTalk Server Administration Console can also be opened from within Visual Studio by clicking **BizTalk Server Administration** in the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="8d60e-108">BizTalk Server 管理コンソールで、展開、 **BizTalk Server 管理コンソール** ノード、 **BizTalk グループ** ノード、**アプリケーション**ノード、し、**BizTalk アプリケーション 1**ノード。</span><span class="sxs-lookup"><span data-stu-id="8d60e-108">In the BizTalk Server Administration Console, expand the **BizTalk Server Administration** node, then the **BizTalk Group** node, then the **Applications** node, and then the **BizTalk Application 1** node.</span></span>  
  
3.  <span data-ttu-id="8d60e-109">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-109">Right-click **Receive Ports**, point to **New**, and then click **One-Way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="8d60e-110">受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_XML_ReceivePort**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-110">In the Receive Port Properties dialog box, in the **Name** box, type **MT103_XML_ReceivePort**.</span></span>  
  
5.  <span data-ttu-id="8d60e-111">をクリックして**適用**をクリックして、ポートのバインド**[ok] です。**</span><span class="sxs-lookup"><span data-stu-id="8d60e-111">Click **Apply** to bind the port, and then click **OK.**</span></span>  
  
6.  <span data-ttu-id="8d60e-112">右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-112">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="8d60e-113">[受信ポート] ダイアログ ボックスのをクリックして**MT103_XML_ReceivePort**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-113">In the Select a Receive Port dialog box, click **MT103_XML_ReceivePort**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8d60e-114">受信場所のプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_XML_ReceiveLocation**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-114">In the Receive Location Properties dialog box, in the **Name** box, type **MT103_XML_ReceiveLocation**.</span></span>  
  
9. <span data-ttu-id="8d60e-115">**トランスポート**] セクションの**型**テキスト ボックスがドロップダウン リストをクリックし、[**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-115">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="8d60e-116">クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。</span><span class="sxs-lookup"><span data-stu-id="8d60e-116">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="8d60e-117">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-117">In the FILE Transport Properties dialog box, click **Browse**.</span></span> <span data-ttu-id="8d60e-118">移動、 **\<ドライブ >: \Labs**フォルダー、およびクリック**新しいフォルダーの作成**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-118">Move to the **\<drive>:\Labs** folder, and then click **Make New Folder**.</span></span>  
  
12. <span data-ttu-id="8d60e-119">フォルダーの参照 ダイアログ ボックスで、作成、**受信**フォルダー **\<ドライブ >: \Labs**、し、作成、 **XMLFile**フォルダー  **\<ドライブ >: \Labs\Inbound**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-119">In the Browse For Folder dialog box, create an **Inbound** folder in **\<drive>:\Labs**, and then create an **XMLFile** folder in **\<drive>:\Labs\Inbound**.</span></span> <span data-ttu-id="8d60e-120">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d60e-120">Click **OK**.</span></span>  
  
13. <span data-ttu-id="8d60e-121">FILE トランスポートのプロパティ ダイアログ ボックスでいることを確認 **\*.xml**で入力した、**ファイル マスク**ボックスし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-121">In the FILE Transport Properties dialog box, ensure that **\*.xml** is entered in the **File Mask** box, and then click **OK**.</span></span>  
  
14. <span data-ttu-id="8d60e-122">受信場所のプロパティ ダイアログ ボックスでいることを確認**BizTalkServerApplication**として入力された、**受信ハンドラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="8d60e-122">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  
  
15. <span data-ttu-id="8d60e-123">**受信パイプライン**ボックスで、 **XMLReceive**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="8d60e-123">For the **Receive Pipeline** box, select **XMLReceive** from the drop-down list.</span></span>  
  
16. <span data-ttu-id="8d60e-124">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-124">Click **Apply**, and then click **OK**.</span></span>  
  
17. <span data-ttu-id="8d60e-125">BizTalk Server 管理コンソールで、をクリックして**受信場所**を右クリックして**MT103_XML_ReceiveLocation**、クリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-125">In the BizTalk Server Administration Console, click **Receive Locations**, right-click **MT103_XML_ReceiveLocation**, and then click **Enable**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8d60e-126">受信場所を有効にすると、BizTalk は積極的に自分のファイル フォルダーをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="8d60e-126">After you enable the receive location, BizTalk actively polls your file folder.</span></span>  
  
 <span data-ttu-id="8d60e-127">進みます[レッスン 2: フラット ファイル送信ポートを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-a-flat-file-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="8d60e-127">Proceed to [Lesson 2: Adding the Flat File Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-a-flat-file-send-port.md).</span></span>