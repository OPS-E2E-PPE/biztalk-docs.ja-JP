---
title: エンコードのサポートを拡張 |Microsoft ドキュメント
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
ms.openlocfilehash: 9e36c3baff4ac33f2878295791bb3f6615c1b25d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204834"
---
# <a name="extended-encoding-support"></a><span data-ttu-id="56999-102">エンコードのサポートを拡張</span><span class="sxs-lookup"><span data-stu-id="56999-102">Extended Encoding Support</span></span>
<span data-ttu-id="56999-103">既定で、HL7 の受信パイプライン、BTAHL72X がのみ ASCII エンコードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="56999-103">By default, the HL7 receive pipeline, BTAHL72X, only supports ASCII encoding.</span></span> <span data-ttu-id="56999-104">つまり、この値に置き換え、127 より大きいと、入力メッセージの任意の文字"?"。</span><span class="sxs-lookup"><span data-stu-id="56999-104">This means that any characters in an input message with an equivalent value greater than 127 are replaced with "?".</span></span> <span data-ttu-id="56999-105">これは、127 より大きい値を等価の値を持つ文字は、ASCII 文字セットで表されないためです。</span><span class="sxs-lookup"><span data-stu-id="56999-105">This is because characters with an equivalent value greater than 127 are not represented in the ASCII character set.</span></span>  
  
 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]<span data-ttu-id="56999-106">2 つの新しいエンコードをサポートをします。</span><span class="sxs-lookup"><span data-stu-id="56999-106"> provides support for two new encodings:</span></span>  
  
-   <span data-ttu-id="56999-107">西ヨーロッパ言語</span><span class="sxs-lookup"><span data-stu-id="56999-107">Western European</span></span>  
  
-   <span data-ttu-id="56999-108">UTF-8</span><span class="sxs-lookup"><span data-stu-id="56999-108">UTF-8</span></span>  
  
 <span data-ttu-id="56999-109">作成して拡張エンコードのサポートを実装するカスタム パイプライン コンポーネントをビルドします。</span><span class="sxs-lookup"><span data-stu-id="56999-109">You create and build a custom pipeline component to implement extended encoding support.</span></span> <span data-ttu-id="56999-110">カスタム パイプライン コンポーネントは、BTAHL7 2.X 逆アセンブラーです。</span><span class="sxs-lookup"><span data-stu-id="56999-110">The custom pipeline component uses the BTAHL7 2.X Disassembler.</span></span> <span data-ttu-id="56999-111">メッセージを処理するカスタム パイプラインを使用する受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="56999-111">You create a receive location that uses the custom pipeline to process messages.</span></span> <span data-ttu-id="56999-112">カスタム パイプラインと受信場所をテストするには、BTAHL7 2.XSendPipeline を使用する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="56999-112">To test the receive location and custom pipeline, you create a send port that uses the BTAHL7 2.XSendPipeline.</span></span>  
  
### <a name="to-create-a-custom-pipeline"></a><span data-ttu-id="56999-113">カスタム パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="56999-113">To create a custom pipeline</span></span>  
  
1.  <span data-ttu-id="56999-114">[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]、追加、新しい**空の BizTalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="56999-114">In [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], add a new **Empty BizTalk Server Project**.</span></span>  
  
2.  <span data-ttu-id="56999-115">ソリューション エクスプ ローラーで、新しいプロジェクトを右クリックし、をクリックして**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="56999-115">In Solution Explorer, right-click the new project, click **Add**, and then click **New Item**.</span></span>  
  
3.  <span data-ttu-id="56999-116">**新しい項目の追加** ダイアログ ボックスで、追加、新しい**受信パイプライン**です。</span><span class="sxs-lookup"><span data-stu-id="56999-116">In the **Add New Item** dialog box, add a new **Receive Pipeline**.</span></span>  
  
4.  <span data-ttu-id="56999-117">パイプライン ツールボックスからドラッグ、 **BTAHL7 2.X 逆アセンブラー**パイプライン エディタを上にドロップし、**逆アセンブル**ステージ**ここにドロップ**ターゲットです。</span><span class="sxs-lookup"><span data-stu-id="56999-117">From the pipeline toolbox, drag the **BTAHL7 2.X Disassembler** to the pipeline editor and drop it onto the **Disassemble** stage **Drop Here** target.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56999-118">BTAHL7 2.7 逆アセンブラーでない場合、ツールボックスのツールボックスを右クリックし、をクリックして**アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="56999-118">If the BTAHL7 2.7 Disassembler is not in the toolbox, right-click in the toolbox, and click **Choose Items**.</span></span> <span data-ttu-id="56999-119">**ツールボックス アイテムの選択** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで、、 **BTAHL7 2.X 逆アセンブラー**チェック ボックスをクリックして**ok**.</span><span class="sxs-lookup"><span data-stu-id="56999-119">In the **Choose Toolbox Items** dialog box, on the **BizTalk Pipeline Component** tab, select the **BTAHL7 2.X Disassembler** check box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="56999-120">[プロパティ] ウィンドウで、 **BTAHL7 2.X 逆アセンブラー**から、**エンコード charset**ドロップダウン リストで、**西ヨーロッパ言語**または**UTF8**エンコードします。</span><span class="sxs-lookup"><span data-stu-id="56999-120">In the Properties pane for the **BTAHL7 2.X Disassembler**, from the **Encoding charset** drop-down list, select **Western European** or **UTF8** encoding.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56999-121">HL7 には、ASCII (既定)、西ヨーロッパ言語、および UTF8 エンコードのみサポートしています。</span><span class="sxs-lookup"><span data-stu-id="56999-121">HL7 only supports ASCII (the default), Western European, and UTF8 encoding.</span></span> <span data-ttu-id="56999-122">HL7 はそれらをサポートしないため、他のエンコード オプションを選択しません。</span><span class="sxs-lookup"><span data-stu-id="56999-122">Do not select the other encoding options because HL7 does not support them.</span></span>  
  
6.  <span data-ttu-id="56999-123">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56999-123">On the **File** menu, click **Save All**.</span></span>  
  
7.  <span data-ttu-id="56999-124">プロジェクトを配置する。</span><span class="sxs-lookup"><span data-stu-id="56999-124">Deploy the project.</span></span>  
  
     <span data-ttu-id="56999-125">新しい受信場所で続行します。</span><span class="sxs-lookup"><span data-stu-id="56999-125">Create a new receive location to continue.</span></span>  
  
### <a name="to-create-a-receive-location-that-uses-the-custom-pipeline"></a><span data-ttu-id="56999-126">カスタム パイプラインを使用する受信場所を作成するには</span><span class="sxs-lookup"><span data-stu-id="56999-126">To create a receive location that uses the custom pipeline</span></span>  
  
1.  <span data-ttu-id="56999-127">**開始** メニューのをクリックして**プログラム**、をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、クリックして**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="56999-127">On the **Start** menu, click **Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="56999-128">BizTalk Server 管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションの展開パイプライン アセンブリ用に指定した (既定では、 **BizTalk アプリケーション 1**) を右クリックして**受信場所**、をポイント**新規**をクリックし、**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="56999-128">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand the application you designated for your pipeline assembly (by default, **BizTalk Application 1**), right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
3.  <span data-ttu-id="56999-129">**受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**ドロップダウン リストで、作成したパイプラインのカスタムの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="56999-129">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, select the name of the custom pipeline you created.</span></span> <span data-ttu-id="56999-130">(これは、名前のカスタム パイプライン オブジェクト、BTAHL7 ではないのパイプラインの 2 倍にします)。</span><span class="sxs-lookup"><span data-stu-id="56999-130">(This is the name of the custom pipeline object, not the BTAHL7 2X pipeline.)</span></span>  
  
### <a name="to-create-a-send-port-to-test-the-receive-location-and-pipeline"></a><span data-ttu-id="56999-131">受信場所およびパイプラインをテストする送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="56999-131">To create a send port to test the receive location and pipeline</span></span>  
  
1.  <span data-ttu-id="56999-132">**開始** メニューのをクリックして**プログラム**、をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、クリックして**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="56999-132">On the **Start** menu, click **Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="56999-133">BizTalk Server 管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションの展開パイプライン アセンブリの指定 (既定では、 **BizTalk アプリケーション 1**) を右クリックして**送信ポート**、をポイント**新規**をクリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="56999-133">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand the application you designated for your pipeline assembly (by default, **BizTalk Application 1**), right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="56999-134">**送信ポートのプロパティ** ダイアログ ボックスで、**送信パイプライン**ドロップダウン リストで、 **BTAHL72XSendPipeline**です。</span><span class="sxs-lookup"><span data-stu-id="56999-134">In the **Send Port Properties** dialog box, in the **Send pipeline** drop-down list, select **BTAHL72XSendPipeline**.</span></span>  
  
### <a name="to-test-the-receive-location-and-pipeline"></a><span data-ttu-id="56999-135">受信場所およびパイプラインをテストするには</span><span class="sxs-lookup"><span data-stu-id="56999-135">To test the receive location and pipeline</span></span>  
  
-   <span data-ttu-id="56999-136">特殊文字を含む、カスタム パイプラインで受信場所で指定された場所に指定した同じエンコードで保存したファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="56999-136">Drop a file containing special characters and saved with the same encoding you specified in the custom pipeline into the location designated in the receive location.</span></span> <span data-ttu-id="56999-137">出力場所にファイルには、特殊文字を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56999-137">The file at the output location should preserve the special characters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56999-138">サポートされているエンコードを使用するファイルを処理しようとする場合 (のみ ASCII、西ヨーロッパ言語、および UTF8 がサポートされていることに注意してください) エラーの ID を持つアプリケーション イベント ビューアーにエラーが記録: 5633 です。</span><span class="sxs-lookup"><span data-stu-id="56999-138">If you attempt to process a file that uses a non-supported encoding (remember that only ASCII, Western European, and UTF8 are supported), an error is logged in the Application Event Viewer with error ID: 5633.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56999-139">UTF8 エンコーディング用に構成されたカスタム パイプラインをテストする場合は、メソッドに渡すメッセージをバイト オーダー マーク (BOM) 文字をアタッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56999-139">If you are testing a custom pipeline configured for UTF8 encoding, you should attach Byte Order Mark (BOM) characters to the message you are passing.</span></span> <span data-ttu-id="56999-140">西ヨーロッパ言語エンコード用に構成されたカスタム パイプラインをテストする場合は、BOM 文字をアタッチできません。</span><span class="sxs-lookup"><span data-stu-id="56999-140">If you are testing a custom pipeline configured for Western European encoding, do not attach BOM characters.</span></span>