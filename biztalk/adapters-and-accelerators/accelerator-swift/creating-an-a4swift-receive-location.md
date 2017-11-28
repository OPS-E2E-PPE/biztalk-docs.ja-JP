---
title: "受信場所の作成、A4SWIFT |Microsoft ドキュメント"
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
ms.assetid: 712cf42f-8d71-47e9-b2bf-3da158b74fe4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3f0835c6d83efc9db91f5c1d63e91f4c143399d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-an-a4swift-receive-location"></a><span data-ttu-id="dc398-102">受信場所の A4SWIFT の作成</span><span class="sxs-lookup"><span data-stu-id="dc398-102">Creating an A4SWIFT Receive Location</span></span>
<span data-ttu-id="dc398-103">作成する必要があります、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] SWIFT ネットワークからのメッセージの受信を有効にする受信場所[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="dc398-103">You must create an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive location to enable message reception from the SWIFT network by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], as shown in the following figure.</span></span> <span data-ttu-id="dc398-104">受信場所は、受信ファイル フォルダーからフラット ファイル メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="dc398-104">The receive location receives flat file messages from an inbound file folder.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")  
  
 <span data-ttu-id="dc398-105">**概要**</span><span class="sxs-lookup"><span data-stu-id="dc398-105">**Summary**</span></span>  
  
 <span data-ttu-id="dc398-106">作成し、一方向の受信ポートにバインドする作成して次のプロパティおよびコンポーネントで受信場所を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dc398-106">Create and bind a one-way receive port, and then create and enable a receive location with the following properties and components:</span></span>  
  
|<span data-ttu-id="dc398-107">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dc398-107">Property/Components</span></span>|<span data-ttu-id="dc398-108">設定</span><span class="sxs-lookup"><span data-stu-id="dc398-108">Setting</span></span>|  
|--------------------------|-------------|  
|<span data-ttu-id="dc398-109">受信ポート</span><span class="sxs-lookup"><span data-stu-id="dc398-109">Receive port</span></span>|<span data-ttu-id="dc398-110">一方向のポート</span><span class="sxs-lookup"><span data-stu-id="dc398-110">One-way port</span></span>|  
|<span data-ttu-id="dc398-111">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="dc398-111">Transport type</span></span>|<span data-ttu-id="dc398-112">FILE</span><span class="sxs-lookup"><span data-stu-id="dc398-112">FILE</span></span>|  
|<span data-ttu-id="dc398-113">アドレスの URI</span><span class="sxs-lookup"><span data-stu-id="dc398-113">Address URI</span></span>|<span data-ttu-id="dc398-114">メッセージを受信するフォルダーの名前</span><span class="sxs-lookup"><span data-stu-id="dc398-114">Name of the folder that you want to receive the message</span></span>|  
|<span data-ttu-id="dc398-115">ファイル マスク</span><span class="sxs-lookup"><span data-stu-id="dc398-115">File mask</span></span>|<span data-ttu-id="dc398-116">\*.*\<拡張子 >*ここで、 \<*拡張子*>、入力方向の拡張機能は、フラット ファイル メッセージ</span><span class="sxs-lookup"><span data-stu-id="dc398-116">\*.*\<extension>*, where \<*extension*> is the extension of the incoming flat file message</span></span>|  
|<span data-ttu-id="dc398-117">[受信ハンドラー]</span><span class="sxs-lookup"><span data-stu-id="dc398-117">Receive handler</span></span>|<span data-ttu-id="dc398-118">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="dc398-118">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="dc398-119">受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="dc398-119">Receive pipeline</span></span>|<span data-ttu-id="dc398-120">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc398-120">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created</span></span>|  
  
### <a name="to-add-the-receive-port-and-location"></a><span data-ttu-id="dc398-121">受信ポートと受信場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="dc398-121">To add the receive port and location</span></span>  
  
1.  <span data-ttu-id="dc398-122">開始**BizTalk Server 管理コンソール**コンソールです。</span><span class="sxs-lookup"><span data-stu-id="dc398-122">Start **BizTalk Server Administration** console.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dc398-123">BizTalk Server 管理コンソール開くこともできますから Visual Studio 内をクリックして**BizTalk Server 管理コンソール**で、**ツール**メニュー。</span><span class="sxs-lookup"><span data-stu-id="dc398-123">The BizTalk Server Administration Console can also be opened from within Visual Studio by clicking **BizTalk Server Administration** in the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="dc398-124">管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalkアプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="dc398-124">In Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="dc398-125">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="dc398-125">Right-click **Receive Ports**, point to **New**, and then click **One-Way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="dc398-126">受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc398-126">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port.</span></span>  
  
5.  <span data-ttu-id="dc398-127">をクリックして**適用**をクリックして、ポートのバインド**OK**です。</span><span class="sxs-lookup"><span data-stu-id="dc398-127">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="dc398-128">右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="dc398-128">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="dc398-129">受信ポート ダイアログ ボックスの選択 で、作成した受信ポート をクリックし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="dc398-129">In the Select a Receive Port dialog box, click the receive port that you just created, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="dc398-130">受信場所のプロパティ ダイアログ ボックスで、**名前**ボックスで、受信場所の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc398-130">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location.</span></span>  
  
9. <span data-ttu-id="dc398-131">**トランスポート**] セクションの**型**テキスト ボックスがドロップダウン リストをクリックし、[**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="dc398-131">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="dc398-132">クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。</span><span class="sxs-lookup"><span data-stu-id="dc398-132">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="dc398-133">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="dc398-133">In the FILE Transport Properties dialog box, click **Browse**.</span></span> <span data-ttu-id="dc398-134">メッセージを受信するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="dc398-134">Move to the folder that you want to receive the message.</span></span> <span data-ttu-id="dc398-135">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc398-135">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dc398-136">このフォルダーが存在しない場合を使用してそれを作成、**新しいフォルダーの作成**コマンド。</span><span class="sxs-lookup"><span data-stu-id="dc398-136">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  
  
12. <span data-ttu-id="dc398-137">ファイル トランスポートのプロパティ ダイアログ ボックスで、**ファイル マスク**ボックスに、入力  **\*.\<*拡張子*>**ここで、 \<*拡張子*>、入力方向の拡張機能は、などのフラットファイルメッセージ**.txt**です。</span><span class="sxs-lookup"><span data-stu-id="dc398-137">In the FILE Transport Properties dialog box, in the **File Mask** box, enter **\*.\<*extension*>**, where \<*extension*> is the extension of the incoming flat file message, such as **.txt**.</span></span> <span data-ttu-id="dc398-138">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc398-138">Click **OK**.</span></span>  
  
13. <span data-ttu-id="dc398-139">受信場所のプロパティ ダイアログ ボックスでいることを確認**BizTalkServerApplication**として入力された、**受信ハンドラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="dc398-139">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  
  
14. <span data-ttu-id="dc398-140">**受信パイプライン**ボックスで、ドロップダウン リストから、カスタム受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc398-140">For the **Receive Pipeline** box, select your custom receive pipeline from the drop-down list.</span></span>  
  
15. <span data-ttu-id="dc398-141">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="dc398-141">Click **Apply**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="dc398-142">BizTalk Server 管理コンソールで、をクリックして**受信場所**作成した受信場所を右クリックし、クリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="dc398-142">In the BizTalk Server Administration Console, click **Receive Locations**, right-click the receive location that you just created, and then click **Enable**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dc398-143">受信場所を有効にすると、BizTalk は積極的に自分のファイル フォルダーをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="dc398-143">After you enable the receive location, BizTalk actively polls your file folder.</span></span>