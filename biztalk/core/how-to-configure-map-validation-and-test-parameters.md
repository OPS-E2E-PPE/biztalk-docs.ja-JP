---
title: マップの検証を構成する方法とパラメーターのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1768918c-e94f-476f-b288-9e030c691177
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7aaa62e74f1c49f2e43d96c7d546af023847d91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967411"
---
# <a name="how-to-configure-map-validation-and-test-parameters"></a><span data-ttu-id="3058b-102">マップの検証を構成する方法とパラメーターをテストします。</span><span class="sxs-lookup"><span data-stu-id="3058b-102">How to Configure Map Validation and Test Parameters</span></span>
<span data-ttu-id="3058b-103">検証して、マップのテスト、前に、マップの検証とテストのパラメーターを設定する必要があります、**プロパティ**マップのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="3058b-103">Before validating and testing a map, you need to set the map validation and test parameters in the **Properties** window of the map.</span></span>  
  
## <a name="configure-the-map-validation-and-test-parameters"></a><span data-ttu-id="3058b-104">マップの検証とテストのパラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="3058b-104">Configure the map validation and test parameters</span></span>  
  
1.  <span data-ttu-id="3058b-105">ソリューション エクスプ ローラーでマップを構成し、をクリックするのプロパティ ページを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="3058b-105">In Solution Explorer, right-click the map whose property pages you want to configure, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3058b-106">プロパティ ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3058b-106">In the Properties window, do the following.</span></span>  
  
    |<span data-ttu-id="3058b-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3058b-107">Use this</span></span>|<span data-ttu-id="3058b-108">目的</span><span class="sxs-lookup"><span data-stu-id="3058b-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="3058b-109">**TestMap 入力を検証します。**</span><span class="sxs-lookup"><span data-stu-id="3058b-109">**Validate TestMap Input**</span></span>|<span data-ttu-id="3058b-110">マップのテストの前に、インスタンス メッセージを送信元スキーマと照合して検証するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="3058b-110">Configure whether you want to have the instance message validated against the source schema before you test the map.</span></span>|  
    |<span data-ttu-id="3058b-111">**TestMap 出力を検証します。**</span><span class="sxs-lookup"><span data-stu-id="3058b-111">**Validate TestMap Output**</span></span>|<span data-ttu-id="3058b-112">マップのテストの後で、インスタンス メッセージを送信先スキーマと照合して検証するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="3058b-112">Configure whether you want to have the instance message validated against the destination schema after you test the map.</span></span>|  
    |<span data-ttu-id="3058b-113">**TestMap の入力インスタンス**</span><span class="sxs-lookup"><span data-stu-id="3058b-113">**TestMap Input Instance**</span></span>|<span data-ttu-id="3058b-114">マップのテストの際に使用するインスタンス メッセージ データの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="3058b-114">Configure the location of the instance message data to use when you test the map.</span></span><br /><br /> <span data-ttu-id="3058b-115">構成する必要があるこのプロパティを設定する場合、 **TestMap の入力**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3058b-115">If you configure this property, you must also configure the **TestMap Input** property.</span></span>|  
    |<span data-ttu-id="3058b-116">**TestMap 出力インスタンス**</span><span class="sxs-lookup"><span data-stu-id="3058b-116">**TestMap Output Instance**</span></span>|<span data-ttu-id="3058b-117">マップのテスト操作の出力を格納するファイルの場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="3058b-117">Configure the location of the file where you want the output of the test map operation to be stored.</span></span><br /><br /> <span data-ttu-id="3058b-118">構成する必要があるこのプロパティを設定する場合、 **TestMap 出力**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3058b-118">If you configure this property, you must also configure the **TestMap Output** property.</span></span>|  
    |<span data-ttu-id="3058b-119">**TestMap の入力**</span><span class="sxs-lookup"><span data-stu-id="3058b-119">**TestMap Input**</span></span>|<span data-ttu-id="3058b-120">入力インスタンスのデータ形式を設定します。</span><span class="sxs-lookup"><span data-stu-id="3058b-120">Configure the input instance data format.</span></span>|  
    |<span data-ttu-id="3058b-121">**TestMap の出力**</span><span class="sxs-lookup"><span data-stu-id="3058b-121">**TestMap Output**</span></span>|<span data-ttu-id="3058b-122">マップのテストの際に使用する出力データ形式を設定します。</span><span class="sxs-lookup"><span data-stu-id="3058b-122">Configure the output data type to use when you test the map.</span></span>|  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3058b-123">マップをテストする場合は、マップのプロパティを先に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3058b-123">If you want to test your map, you must configure the map properties first.</span></span>  

<span data-ttu-id="3058b-124">作成したマップは検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3058b-124">After you have developed your map, one of the next steps is to validate it.</span></span> <span data-ttu-id="3058b-125">このトピックでは、マップを検証するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3058b-125">This topic provides step-by-step instructions for validating maps.</span></span>  
  
## <a name="validate-a-biztalk-map"></a><span data-ttu-id="3058b-126">BizTalk マップを検証します。</span><span class="sxs-lookup"><span data-stu-id="3058b-126">Validate a BizTalk map</span></span>  
  
1.  <span data-ttu-id="3058b-127">ソリューション エクスプローラーで、検証するマップを開きます。</span><span class="sxs-lookup"><span data-stu-id="3058b-127">In Solution Explorer, open the map that you want to validate.</span></span>  
  
2.  <span data-ttu-id="3058b-128">ソリューション エクスプ ローラーで、マップを右クリックし、**マップの検証**です。</span><span class="sxs-lookup"><span data-stu-id="3058b-128">In Solution Explorer, right-click the map, and then select **Validate Map**.</span></span>  
  
3.  <span data-ttu-id="3058b-129">**出力**ウィンドウで、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="3058b-129">In the **Output** window, verify the results.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3058b-130">出力でカスタム データまたは定数を使用する場合、送信元のテスト データと送信先の定数値のデータ型が有効であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3058b-130">If you use custom data or constants in your output, you must verify that the data types of your source test data and target constant values are valid.</span></span> <span data-ttu-id="3058b-131">マップを検証する場合、BizTalk マッパーでは、スキーマで定義されているデータ型にインスタンス データが違反しているかどうかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="3058b-131">When you validate a map, BizTalk Mapper does not check if the instance data violates any data types defined in the schemas.</span></span> <span data-ttu-id="3058b-132">データ型の確認は、BizTalk エディターでマップのテストまたはインスタンス データの検証を行うと実行されます。</span><span class="sxs-lookup"><span data-stu-id="3058b-132">This is done when you test the map or validate the instance data with BizTalk Editor.</span></span> 

## <a name="test-a-biztalk-map"></a><span data-ttu-id="3058b-133">BizTalk マップをテストします。</span><span class="sxs-lookup"><span data-stu-id="3058b-133">Test a BizTalk map</span></span>

<span data-ttu-id="3058b-134">作成したマップはテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3058b-134">After you have developed your map, one of the next steps is to test it.</span></span> <span data-ttu-id="3058b-135">ここでは、マップ コンパイラによって生成された XSLT を表示する手順も含め、マップをテストするための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3058b-135">This topic provides step-by-step instructions for testing maps including steps to view the XSLT generated by the map compiler.</span></span>  
  
1.  <span data-ttu-id="3058b-136">ソリューション エクスプ ローラーで、テスト、および選択するマップを右クリックして**テスト マップ**します。</span><span class="sxs-lookup"><span data-stu-id="3058b-136">In Solution Explorer, right-click the map you want to test, and then select **Test Map**.</span></span>  
  
2.  <span data-ttu-id="3058b-137">結果を確認、**出力**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="3058b-137">Verify the results in the **Output** window.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3058b-138">マップをテストする前に、プロパティ ウィンドウで、入力インスタンスと出力インスタンスのプロパティを構成しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3058b-138">It is recommended that you configure the input and output instance properties in the Properties window before you test a map.</span></span>  
  
## <a name="review-the-xslt"></a><span data-ttu-id="3058b-139">XSLT を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3058b-139">Review the XSLT</span></span>  
 <span data-ttu-id="3058b-140">マップ コンパイラによって生成された XSLT を理解すると、多くの場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3058b-140">It is often useful to inspect the XSLT generated by the map compiler.</span></span> <span data-ttu-id="3058b-141">XSLT の理解によって得ることができるメリットの一部を次に挙げます。</span><span class="sxs-lookup"><span data-stu-id="3058b-141">Some of the benefits of inspecting XSLT include:</span></span>  
  
- <span data-ttu-id="3058b-142">ループまたはカスタム Functoid を使用している場合、ループの実行方法やカスタム Functoid の呼び出し方法についての理解が深まります。</span><span class="sxs-lookup"><span data-stu-id="3058b-142">If you are using looping or custom functoids, you will better understand how the looping is performed and how the custom functoid is invoked.</span></span>  
  
- <span data-ttu-id="3058b-143">複雑なマップがある場合は、XSLT の確認を変換マップを変換する方法を確認することが有効にして、あります insight 構造を改良し、置換、またはいずれかの効率化する方法のまたはパーツの詳細はします。</span><span class="sxs-lookup"><span data-stu-id="3058b-143">If you have a complicated map, reviewing the XSLT will enable you to see how the map is translated into a transform, and may give you insight on how to better structure, replace, or streamline one or more parts.</span></span>  
  
- <span data-ttu-id="3058b-144">カスタム スクリプトや他の成果物を使用している場合、XSLT の確認ができます、スクリプト、成果物、およびマップの他の部分がやり取りする方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3058b-144">If you are using custom scripts or other artifacts, reviewing the XSLT will enable you to see how the scripts, artifacts, and other parts of the map interact.</span></span>  
  
  <span data-ttu-id="3058b-145">XSLT を確認することで、マップを適切にデバッグすることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="3058b-145">In other words, reviewing the XSLT is a great way to debug a map.</span></span>  
  
#### <a name="view-the-xslt-generated-by-the-map-compiler"></a><span data-ttu-id="3058b-146">マップ コンパイラによって生成された XSLT を表示します。</span><span class="sxs-lookup"><span data-stu-id="3058b-146">View the XSLT generated by the map compiler</span></span>  
  
1.  <span data-ttu-id="3058b-147">Visual Studio の BizTalk プロジェクトから選択、**ソリューション エクスプ ローラー** ] タブで、マップを右クリックし、[**マップの検証**です。</span><span class="sxs-lookup"><span data-stu-id="3058b-147">From a Visual Studio BizTalk project, select the **Solution Explorer** tab, right-click a map, and then select **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="3058b-148">[出力] ウィンドウをスクロールして、XSL ファイルの URL を探します。</span><span class="sxs-lookup"><span data-stu-id="3058b-148">Scroll the Output window to find the URL for the XSL file.</span></span> <span data-ttu-id="3058b-149">キーを押して**CTRL**ファイルを表示する URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="3058b-149">Press **CTRL**, and select the URL to view the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3058b-150">XSL ファイルに加えられた変更は、マップには反映されません、次回のビルドで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="3058b-150">Changes made to the XSL file are not reflected in the map and are overwritten on the next build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3058b-151">参照</span><span class="sxs-lookup"><span data-stu-id="3058b-151">See also</span></span>  

[<span data-ttu-id="3058b-152">マップをデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="3058b-152">How to Debug Maps</span></span>](../core/how-to-debug-maps.md)  
[<span data-ttu-id="3058b-153">マップのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3058b-153">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)  