---
title: 受信場所を作成、A4SWIFT |Microsoft Docs
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
ms.assetid: 712cf42f-8d71-47e9-b2bf-3da158b74fe4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b19330a4d4ab207c7d5e0f920dadb432b733df19
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968371"
---
# <a name="creating-an-a4swift-receive-location"></a><span data-ttu-id="68b6e-102">受信場所を A4SWIFT の作成</span><span class="sxs-lookup"><span data-stu-id="68b6e-102">Creating an A4SWIFT Receive Location</span></span>
<span data-ttu-id="68b6e-103">作成する必要があります、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]受信場所で行う SWIFT ネットワークからのメッセージの受信を有効にする[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="68b6e-103">You must create an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive location to enable message reception from the SWIFT network by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], as shown in the following figure.</span></span> <span data-ttu-id="68b6e-104">受信場所は、受信ファイルのフォルダーからフラット ファイル メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-104">The receive location receives flat file messages from an inbound file folder.</span></span>  

 <span data-ttu-id="68b6e-105">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")</span><span class="sxs-lookup"><span data-stu-id="68b6e-105">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")</span></span>  

 <span data-ttu-id="68b6e-106">**概要**</span><span class="sxs-lookup"><span data-stu-id="68b6e-106">**Summary**</span></span>  

 <span data-ttu-id="68b6e-107">作成し、一方向の受信ポートのバインドを作成し、次のプロパティおよびコンポーネントの受信場所を有効にします。</span><span class="sxs-lookup"><span data-stu-id="68b6e-107">Create and bind a one-way receive port, and then create and enable a receive location with the following properties and components:</span></span>  


| <span data-ttu-id="68b6e-108">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="68b6e-108">Property/Components</span></span> |                                                             <span data-ttu-id="68b6e-109">設定</span><span class="sxs-lookup"><span data-stu-id="68b6e-109">Setting</span></span>                                                             |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="68b6e-110">受信ポート</span><span class="sxs-lookup"><span data-stu-id="68b6e-110">Receive port</span></span>     |                                                          <span data-ttu-id="68b6e-111">一方向のポート</span><span class="sxs-lookup"><span data-stu-id="68b6e-111">One-way port</span></span>                                                           |
|   <span data-ttu-id="68b6e-112">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="68b6e-112">Transport type</span></span>    |                                                              <span data-ttu-id="68b6e-113">FILE</span><span class="sxs-lookup"><span data-stu-id="68b6e-113">FILE</span></span>                                                               |
|     <span data-ttu-id="68b6e-114">アドレスの URI</span><span class="sxs-lookup"><span data-stu-id="68b6e-114">Address URI</span></span>     |                                     <span data-ttu-id="68b6e-115">メッセージを受信するフォルダーの名前</span><span class="sxs-lookup"><span data-stu-id="68b6e-115">Name of the folder that you want to receive the message</span></span>                                     |
|      <span data-ttu-id="68b6e-116">ファイル マスク</span><span class="sxs-lookup"><span data-stu-id="68b6e-116">File mask</span></span>      |                  <span data-ttu-id="68b6e-117">\*.*\<拡張子\>* ここで、 \<*拡張子*\>入力方向の拡張機能は、フラット ファイル メッセージ</span><span class="sxs-lookup"><span data-stu-id="68b6e-117">\*.*\<extension\>*, where \<*extension*\> is the extension of the incoming flat file message</span></span>                   |
|   <span data-ttu-id="68b6e-118">[受信ハンドラー]</span><span class="sxs-lookup"><span data-stu-id="68b6e-118">Receive handler</span></span>   |                                                    <span data-ttu-id="68b6e-119">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="68b6e-119">BizTalkServerApplication</span></span>                                                     |
|  <span data-ttu-id="68b6e-120">受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="68b6e-120">Receive pipeline</span></span>   | <span data-ttu-id="68b6e-121">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-121">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created</span></span> |

### <a name="to-add-the-receive-port-and-location"></a><span data-ttu-id="68b6e-122">場所と受信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="68b6e-122">To add the receive port and location</span></span>  

1.  <span data-ttu-id="68b6e-123">開始**BizTalk Server 管理**コンソール。</span><span class="sxs-lookup"><span data-stu-id="68b6e-123">Start **BizTalk Server Administration** console.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="68b6e-124">BizTalk Server 管理コンソールで開くこともできますから Visual Studio 内でクリックして**BizTalk Server 管理**で、**ツール**メニュー。</span><span class="sxs-lookup"><span data-stu-id="68b6e-124">The BizTalk Server Administration Console can also be opened from within Visual Studio by clicking **BizTalk Server Administration** in the **Tools** menu.</span></span>  

2.  <span data-ttu-id="68b6e-125">管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalkアプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-125">In Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  

3.  <span data-ttu-id="68b6e-126">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-126">Right-click **Receive Ports**, point to **New**, and then click **One-Way Receive Port**.</span></span>  

4.  <span data-ttu-id="68b6e-127">受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-127">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port.</span></span>  

5.  <span data-ttu-id="68b6e-128">をクリックして**適用**をクリックして、ポートのバインド**OK**します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-128">Click **Apply** to bind the port, and then click **OK**.</span></span>  

6.  <span data-ttu-id="68b6e-129">右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-129">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  

7.  <span data-ttu-id="68b6e-130">受信ポートのダイアログ ボックスの選択 で、作成した受信ポート をクリックし、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-130">In the Select a Receive Port dialog box, click the receive port that you just created, and then click **OK**.</span></span>  

8.  <span data-ttu-id="68b6e-131">受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに、受信場所の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-131">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location.</span></span>  

9. <span data-ttu-id="68b6e-132">**トランスポート**セクションの**型**テキスト ボックス、ドロップダウン リストをクリックし、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-132">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  

10. <span data-ttu-id="68b6e-133">をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b6e-133">Click the **Configure** button to the right of the Type drop-down list.</span></span>  

11. <span data-ttu-id="68b6e-134">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-134">In the FILE Transport Properties dialog box, click **Browse**.</span></span> <span data-ttu-id="68b6e-135">メッセージを受信するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-135">Move to the folder that you want to receive the message.</span></span> <span data-ttu-id="68b6e-136">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b6e-136">Click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="68b6e-137">このフォルダーが存在しない場合を使用してそれを作成、**フォルダの新規**コマンド。</span><span class="sxs-lookup"><span data-stu-id="68b6e-137">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  

12. <span data-ttu-id="68b6e-138">ファイル トランスポートのプロパティ ダイアログ ボックスでの**ファイル マスク**ボックスに、入力 **\*.\<*拡張子*\>** ここで、 \<*拡張子*\>入力方向の拡張機能は、などのフラットファイルメッセージ **.txt**します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-138">In the FILE Transport Properties dialog box, in the **File Mask** box, enter **\*.\<*extension*\>**, where \<*extension*\> is the extension of the incoming flat file message, such as **.txt**.</span></span> <span data-ttu-id="68b6e-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b6e-139">Click **OK**.</span></span>  

13. <span data-ttu-id="68b6e-140">受信場所のプロパティ ダイアログ ボックスで、ことを確認します**BizTalkServerApplication**の入力、**受信ハンドラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="68b6e-140">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  

14. <span data-ttu-id="68b6e-141">**受信パイプライン**ボックスで、ドロップダウン リストから、カスタム受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-141">For the **Receive Pipeline** box, select your custom receive pipeline from the drop-down list.</span></span>  

15. <span data-ttu-id="68b6e-142">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-142">Click **Apply**, and then click **OK**.</span></span>  

16. <span data-ttu-id="68b6e-143">BizTalk Server 管理コンソールで、次のようにクリックします。**受信場所**作成した受信場所を右クリックし、クリック**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="68b6e-143">In the BizTalk Server Administration Console, click **Receive Locations**, right-click the receive location that you just created, and then click **Enable**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="68b6e-144">受信場所を有効にすると、BizTalk は、ファイル フォルダーを積極的にポーリングします。</span><span class="sxs-lookup"><span data-stu-id="68b6e-144">After you enable the receive location, BizTalk actively polls your file folder.</span></span>