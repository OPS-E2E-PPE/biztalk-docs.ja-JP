---
title: エンコードのサポートを拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a40fa6-d0da-416e-97fb-675ddde3f005
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41275124cdf0db7329751c5973bbde0685bd49ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255298"
---
# <a name="extended-encoding-support"></a><span data-ttu-id="a4511-102">エンコードのサポートを拡張</span><span class="sxs-lookup"><span data-stu-id="a4511-102">Extended Encoding Support</span></span>
<span data-ttu-id="a4511-103">既定では HL7 受信のみ BTAHL72X、パイプラインでは ASCII エンコーディングがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a4511-103">By default, the HL7 receive pipeline, BTAHL72X, only supports ASCII encoding.</span></span> <span data-ttu-id="a4511-104">つまり、値 127 の置き換えよりも大きいと、入力メッセージの任意の文字"?"。</span><span class="sxs-lookup"><span data-stu-id="a4511-104">This means that any characters in an input message with an equivalent value greater than 127 are replaced with "?".</span></span> <span data-ttu-id="a4511-105">これは、127 より大きい値と文字は、ASCII 文字セットでは表されないためです。</span><span class="sxs-lookup"><span data-stu-id="a4511-105">This is because characters with an equivalent value greater than 127 are not represented in the ASCII character set.</span></span>  
  
 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] <span data-ttu-id="a4511-106">新しい 2 つのエンコーディングをサポートをします。</span><span class="sxs-lookup"><span data-stu-id="a4511-106">provides support for two new encodings:</span></span>  
  
- <span data-ttu-id="a4511-107">西ヨーロッパ言語</span><span class="sxs-lookup"><span data-stu-id="a4511-107">Western European</span></span>  
  
- <span data-ttu-id="a4511-108">UTF-8</span><span class="sxs-lookup"><span data-stu-id="a4511-108">UTF-8</span></span>  
  
  <span data-ttu-id="a4511-109">作成して拡張エンコードのサポートを実装するカスタム パイプライン コンポーネントをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a4511-109">You create and build a custom pipeline component to implement extended encoding support.</span></span> <span data-ttu-id="a4511-110">カスタム パイプライン コンポーネントは、BTAHL7 2.X 逆アセンブラーです。</span><span class="sxs-lookup"><span data-stu-id="a4511-110">The custom pipeline component uses the BTAHL7 2.X Disassembler.</span></span> <span data-ttu-id="a4511-111">メッセージを処理するカスタム パイプラインを使用する受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="a4511-111">You create a receive location that uses the custom pipeline to process messages.</span></span> <span data-ttu-id="a4511-112">カスタム パイプラインと受信場所をテストするには、BTAHL7 2.XSendPipeline を使用する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4511-112">To test the receive location and custom pipeline, you create a send port that uses the BTAHL7 2.XSendPipeline.</span></span>  
  
### <a name="to-create-a-custom-pipeline"></a><span data-ttu-id="a4511-113">カスタム パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="a4511-113">To create a custom pipeline</span></span>  
  
1. <span data-ttu-id="a4511-114">[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]、新しい追加**空の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="a4511-114">In [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], add a new **Empty BizTalk Server Project**.</span></span>  
  
2. <span data-ttu-id="a4511-115">ソリューション エクスプ ローラーで新しいプロジェクトを右クリックし、をクリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="a4511-115">In Solution Explorer, right-click the new project, click **Add**, and then click **New Item**.</span></span>  
  
3. <span data-ttu-id="a4511-116">**新しい項目の追加** ダイアログ ボックスで、新しい追加**受信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="a4511-116">In the **Add New Item** dialog box, add a new **Receive Pipeline**.</span></span>  
  
4. <span data-ttu-id="a4511-117">パイプラインのツールボックスからドラッグ、 **BTAHL7 2.X 逆アセンブラー**パイプライン エディターにドロップ、**逆アセンブル**ステージ**ここにドロップ**ターゲット。</span><span class="sxs-lookup"><span data-stu-id="a4511-117">From the pipeline toolbox, drag the **BTAHL7 2.X Disassembler** to the pipeline editor and drop it onto the **Disassemble** stage **Drop Here** target.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a4511-118">BTAHL7 2.7 逆アセンブラーがツールボックスにない場合は、ツールボックスで、右クリックし、クリックして**アイテムの選択**します。</span><span class="sxs-lookup"><span data-stu-id="a4511-118">If the BTAHL7 2.7 Disassembler is not in the toolbox, right-click in the toolbox, and click **Choose Items**.</span></span> <span data-ttu-id="a4511-119">**ツールボックス アイテムの選択** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで、、 **BTAHL7 2.X 逆アセンブラー**チェック ボックスをオンにし**ok**.</span><span class="sxs-lookup"><span data-stu-id="a4511-119">In the **Choose Toolbox Items** dialog box, on the **BizTalk Pipeline Component** tab, select the **BTAHL7 2.X Disassembler** check box, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="a4511-120">[プロパティ] ウィンドウで、 **BTAHL7 2.X 逆アセンブラー**から、**エンコード charset**ドロップダウン リストで、**西ヨーロッパ言語**または**UTF8**エンコードします。</span><span class="sxs-lookup"><span data-stu-id="a4511-120">In the Properties pane for the **BTAHL7 2.X Disassembler**, from the **Encoding charset** drop-down list, select **Western European** or **UTF8** encoding.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a4511-121">HL7 には、ASCII (既定)、西ヨーロッパ言語、および UTF8 エンコードのみサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a4511-121">HL7 only supports ASCII (the default), Western European, and UTF8 encoding.</span></span> <span data-ttu-id="a4511-122">HL7 をサポートしていないため、他のエンコード オプションを選択しません。</span><span class="sxs-lookup"><span data-stu-id="a4511-122">Do not select the other encoding options because HL7 does not support them.</span></span>  
  
6. <span data-ttu-id="a4511-123">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4511-123">On the **File** menu, click **Save All**.</span></span>  
  
7. <span data-ttu-id="a4511-124">プロジェクトをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="a4511-124">Deploy the project.</span></span>  
  
    <span data-ttu-id="a4511-125">新しい受信場所で続行します。</span><span class="sxs-lookup"><span data-stu-id="a4511-125">Create a new receive location to continue.</span></span>  
  
### <a name="to-create-a-receive-location-that-uses-the-custom-pipeline"></a><span data-ttu-id="a4511-126">カスタム パイプラインを使用する受信場所を作成するには</span><span class="sxs-lookup"><span data-stu-id="a4511-126">To create a receive location that uses the custom pipeline</span></span>  
  
1. <span data-ttu-id="a4511-127">**開始** メニューのをクリックして**プログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリックし、 **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a4511-127">On the **Start** menu, click **Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a4511-128">BizTalk Server 管理コンソールで [ [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションの展開パイプライン アセンブリの指定した (既定では、 **BizTalk アプリケーション 1**)、右クリックして**受信場所**、] をポイント**新規**、順にクリックします**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="a4511-128">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand the application you designated for your pipeline assembly (by default, **BizTalk Application 1**), right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
3. <span data-ttu-id="a4511-129">**受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**-ドロップダウン リストで、作成したパイプラインのカスタムの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4511-129">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, select the name of the custom pipeline you created.</span></span> <span data-ttu-id="a4511-130">(これは、BTAHL7 ではない、カスタムのパイプライン オブジェクトの名前をパイプラインの 2 倍にします)。</span><span class="sxs-lookup"><span data-stu-id="a4511-130">(This is the name of the custom pipeline object, not the BTAHL7 2X pipeline.)</span></span>  
  
### <a name="to-create-a-send-port-to-test-the-receive-location-and-pipeline"></a><span data-ttu-id="a4511-131">受信場所とパイプラインをテストする送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="a4511-131">To create a send port to test the receive location and pipeline</span></span>  
  
1. <span data-ttu-id="a4511-132">**開始** メニューのをクリックして**プログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリックし、 **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a4511-132">On the **Start** menu, click **Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a4511-133">BizTalk Server 管理コンソールで [ [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションの展開パイプライン アセンブリの指定した (既定では、 **BizTalk アプリケーション 1**)、右クリック**送信ポート**、] をポイント**新規**順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a4511-133">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand the application you designated for your pipeline assembly (by default, **BizTalk Application 1**), right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3. <span data-ttu-id="a4511-134">**送信ポートのプロパティ** ダイアログ ボックスで、**送信パイプライン**ドロップダウン リストで、 **BTAHL72XSendPipeline**します。</span><span class="sxs-lookup"><span data-stu-id="a4511-134">In the **Send Port Properties** dialog box, in the **Send pipeline** drop-down list, select **BTAHL72XSendPipeline**.</span></span>  
  
### <a name="to-test-the-receive-location-and-pipeline"></a><span data-ttu-id="a4511-135">受信場所とパイプラインをテストするには</span><span class="sxs-lookup"><span data-stu-id="a4511-135">To test the receive location and pipeline</span></span>  
  
-   <span data-ttu-id="a4511-136">特殊文字を含むカスタム パイプラインで受信場所で指定されている場所に指定した同じエンコードで保存されたファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="a4511-136">Drop a file containing special characters and saved with the same encoding you specified in the custom pipeline into the location designated in the receive location.</span></span> <span data-ttu-id="a4511-137">出力場所にファイルには、特殊文字を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4511-137">The file at the output location should preserve the special characters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4511-138">サポートされているエンコードを使用するファイルを処理しようとしたかどうか (のみ ASCII、西ヨーロッパ言語、および UTF8 がサポートされていることに注意してください)、エラーの ID を持つアプリケーション イベント ビューアーでエラーが記録されます。5633.</span><span class="sxs-lookup"><span data-stu-id="a4511-138">If you attempt to process a file that uses a non-supported encoding (remember that only ASCII, Western European, and UTF8 are supported), an error is logged in the Application Event Viewer with error ID: 5633.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4511-139">UTF8 エンコード用に構成されたカスタム パイプラインをテストする場合は、バイト オーダー マーク (BOM) 文字をメソッドに渡すメッセージに添付する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4511-139">If you are testing a custom pipeline configured for UTF8 encoding, you should attach Byte Order Mark (BOM) characters to the message you are passing.</span></span> <span data-ttu-id="a4511-140">西ヨーロッパのエンコード用に構成されたカスタム パイプラインをテストする場合は、BOM 文字をアタッチできません。</span><span class="sxs-lookup"><span data-stu-id="a4511-140">If you are testing a custom pipeline configured for Western European encoding, do not attach BOM characters.</span></span>