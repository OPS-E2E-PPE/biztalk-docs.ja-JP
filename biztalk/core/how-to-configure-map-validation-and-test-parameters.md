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
ms.openlocfilehash: 0c39b185284d3787e88abcd70bcb6827385361bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341393"
---
# <a name="how-to-configure-map-validation-and-test-parameters"></a><span data-ttu-id="b97d2-102">マップの検証を構成する方法とパラメーターをテストします。</span><span class="sxs-lookup"><span data-stu-id="b97d2-102">How to Configure Map Validation and Test Parameters</span></span>
<span data-ttu-id="b97d2-103">検証して、マップのテスト、前に、マップの検証とテストのパラメーターを設定する必要があります、**プロパティ**マップのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="b97d2-103">Before validating and testing a map, you need to set the map validation and test parameters in the **Properties** window of the map.</span></span>  
  
## <a name="configure-the-map-validation-and-test-parameters"></a><span data-ttu-id="b97d2-104">マップの検証とテストのパラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-104">Configure the map validation and test parameters</span></span>  
  
1.  <span data-ttu-id="b97d2-105">ソリューション エクスプ ローラーでマップを構成し、をクリックするのプロパティ ページを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-105">In Solution Explorer, right-click the map whose property pages you want to configure, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b97d2-106">[プロパティ] ウィンドウで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-106">In the Properties window, do the following.</span></span>  
  
    |<span data-ttu-id="b97d2-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b97d2-107">Use this</span></span>|<span data-ttu-id="b97d2-108">目的</span><span class="sxs-lookup"><span data-stu-id="b97d2-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b97d2-109">**TestMap 入力を検証します。**</span><span class="sxs-lookup"><span data-stu-id="b97d2-109">**Validate TestMap Input**</span></span>|<span data-ttu-id="b97d2-110">インスタンス メッセージをマップをテストする前に、送信元スキーマに対して検証するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-110">Configure whether you want to have the instance message validated against the source schema before you test the map.</span></span>|  
    |<span data-ttu-id="b97d2-111">**TestMap 出力を検証します。**</span><span class="sxs-lookup"><span data-stu-id="b97d2-111">**Validate TestMap Output**</span></span>|<span data-ttu-id="b97d2-112">インスタンス メッセージをマップをテストした後に、送信先スキーマに対して検証するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-112">Configure whether you want to have the instance message validated against the destination schema after you test the map.</span></span>|  
    |<span data-ttu-id="b97d2-113">**TestMap の入力インスタンス**</span><span class="sxs-lookup"><span data-stu-id="b97d2-113">**TestMap Input Instance**</span></span>|<span data-ttu-id="b97d2-114">マップをテストするときに使用するインスタンス メッセージ データの場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-114">Configure the location of the instance message data to use when you test the map.</span></span><br /><br /> <span data-ttu-id="b97d2-115">構成する必要があるこのプロパティを設定する場合、 **TestMap の入力**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b97d2-115">If you configure this property, you must also configure the **TestMap Input** property.</span></span>|  
    |<span data-ttu-id="b97d2-116">**TestMap 出力インスタンス**</span><span class="sxs-lookup"><span data-stu-id="b97d2-116">**TestMap Output Instance**</span></span>|<span data-ttu-id="b97d2-117">格納するマップのテスト操作の出力先ファイルの場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-117">Configure the location of the file where you want the output of the test map operation to be stored.</span></span><br /><br /> <span data-ttu-id="b97d2-118">構成する必要があるこのプロパティを設定する場合、 **TestMap 出力**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b97d2-118">If you configure this property, you must also configure the **TestMap Output** property.</span></span>|  
    |<span data-ttu-id="b97d2-119">**TestMap の入力**</span><span class="sxs-lookup"><span data-stu-id="b97d2-119">**TestMap Input**</span></span>|<span data-ttu-id="b97d2-120">入力インスタンス データの形式を構成します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-120">Configure the input instance data format.</span></span>|  
    |<span data-ttu-id="b97d2-121">**TestMap の出力**</span><span class="sxs-lookup"><span data-stu-id="b97d2-121">**TestMap Output**</span></span>|<span data-ttu-id="b97d2-122">マップをテストするときに使用する出力のデータ型を構成します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-122">Configure the output data type to use when you test the map.</span></span>|  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b97d2-123">マップをテストする場合は、まず、マップのプロパティを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b97d2-123">If you want to test your map, you must configure the map properties first.</span></span>  

<span data-ttu-id="b97d2-124">作成したマップは後、は、検証するのには、次の手順の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b97d2-124">After you have developed your map, one of the next steps is to validate it.</span></span> <span data-ttu-id="b97d2-125">このトピックでは、マップを検証するための詳細な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-125">This topic provides step-by-step instructions for validating maps.</span></span>  
  
## <a name="validate-a-biztalk-map"></a><span data-ttu-id="b97d2-126">BizTalk マップを検証します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-126">Validate a BizTalk map</span></span>  
  
1.  <span data-ttu-id="b97d2-127">ソリューション エクスプ ローラーで、検証するマップを開きます。</span><span class="sxs-lookup"><span data-stu-id="b97d2-127">In Solution Explorer, open the map that you want to validate.</span></span>  
  
2.  <span data-ttu-id="b97d2-128">ソリューション エクスプ ローラーで、マップを右クリックし、**マップの検証**です。</span><span class="sxs-lookup"><span data-stu-id="b97d2-128">In Solution Explorer, right-click the map, and then select **Validate Map**.</span></span>  
  
3.  <span data-ttu-id="b97d2-129">**出力**ウィンドウで、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-129">In the **Output** window, verify the results.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b97d2-130">出力でカスタム データまたは定数を使用する場合、送信元のテスト データと送信先の定数値のデータ型が有効であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b97d2-130">If you use custom data or constants in your output, you must verify that the data types of your source test data and target constant values are valid.</span></span> <span data-ttu-id="b97d2-131">マップを検証するときに BizTalk マッパーには、インスタンス データのスキーマで定義されている任意のデータ型に違反しているかどうかはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="b97d2-131">When you validate a map, BizTalk Mapper does not check if the instance data violates any data types defined in the schemas.</span></span> <span data-ttu-id="b97d2-132">これは、マップのテストまたはインスタンス データの BizTalk エディターを使用して検証するときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="b97d2-132">This is done when you test the map or validate the instance data with BizTalk Editor.</span></span> 

## <a name="test-a-biztalk-map"></a><span data-ttu-id="b97d2-133">BizTalk マップをテストします。</span><span class="sxs-lookup"><span data-stu-id="b97d2-133">Test a BizTalk map</span></span>

<span data-ttu-id="b97d2-134">作成したマップは後、は、テストを次の手順の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b97d2-134">After you have developed your map, one of the next steps is to test it.</span></span> <span data-ttu-id="b97d2-135">このトピックでは、マップ コンパイラによって生成された XSLT を表示する手順も含め、マップをテストするための手順が説明します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-135">This topic provides step-by-step instructions for testing maps including steps to view the XSLT generated by the map compiler.</span></span>  
  
1.  <span data-ttu-id="b97d2-136">ソリューション エクスプ ローラーで、テスト、および選択するマップを右クリックして**テスト マップ**します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-136">In Solution Explorer, right-click the map you want to test, and then select **Test Map**.</span></span>  
  
2.  <span data-ttu-id="b97d2-137">結果を確認、**出力**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="b97d2-137">Verify the results in the **Output** window.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b97d2-138">入力を構成し、マップをテストする前に、[プロパティ] ウィンドウで、インスタンスのプロパティを出力することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b97d2-138">It is recommended that you configure the input and output instance properties in the Properties window before you test a map.</span></span>  
  
## <a name="review-the-xslt"></a><span data-ttu-id="b97d2-139">XSLT を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b97d2-139">Review the XSLT</span></span>  
 <span data-ttu-id="b97d2-140">マップ コンパイラによって生成された XSLT を理解すると便利です。</span><span class="sxs-lookup"><span data-stu-id="b97d2-140">It is often useful to inspect the XSLT generated by the map compiler.</span></span> <span data-ttu-id="b97d2-141">XSLT を検査する利点のいくつか挙げます。</span><span class="sxs-lookup"><span data-stu-id="b97d2-141">Some of the benefits of inspecting XSLT include:</span></span>  
  
- <span data-ttu-id="b97d2-142">ループまたはカスタム functoid を使用している場合は、ループの実行方法とカスタム functoid を呼び出す方法をより深く理解されます。</span><span class="sxs-lookup"><span data-stu-id="b97d2-142">If you are using looping or custom functoids, you will better understand how the looping is performed and how the custom functoid is invoked.</span></span>  
  
- <span data-ttu-id="b97d2-143">複雑なマップがある場合は、XSLT の確認を変換マップを変換する方法を確認することが有効にして、あります insight 構造を改良し、置換、またはいずれかの効率化する方法のまたはパーツの詳細はします。</span><span class="sxs-lookup"><span data-stu-id="b97d2-143">If you have a complicated map, reviewing the XSLT will enable you to see how the map is translated into a transform, and may give you insight on how to better structure, replace, or streamline one or more parts.</span></span>  
  
- <span data-ttu-id="b97d2-144">カスタム スクリプトや他の成果物を使用している場合、XSLT の確認ができます、スクリプト、成果物、およびマップの他の部分がやり取りする方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b97d2-144">If you are using custom scripts or other artifacts, reviewing the XSLT will enable you to see how the scripts, artifacts, and other parts of the map interact.</span></span>  
  
  <span data-ttu-id="b97d2-145">つまり、XSLT の確認は、マップをデバッグする優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="b97d2-145">In other words, reviewing the XSLT is a great way to debug a map.</span></span>  
  
#### <a name="view-the-xslt-generated-by-the-map-compiler"></a><span data-ttu-id="b97d2-146">マップ コンパイラによって生成された XSLT を表示します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-146">View the XSLT generated by the map compiler</span></span>  
  
1.  <span data-ttu-id="b97d2-147">Visual Studio の BizTalk プロジェクトから選択、**ソリューション エクスプ ローラー** ] タブで、マップを右クリックし、[**マップの検証**です。</span><span class="sxs-lookup"><span data-stu-id="b97d2-147">From a Visual Studio BizTalk project, select the **Solution Explorer** tab, right-click a map, and then select **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="b97d2-148">XSL ファイルの URL を確認する出力ウィンドウをスクロールします。</span><span class="sxs-lookup"><span data-stu-id="b97d2-148">Scroll the Output window to find the URL for the XSL file.</span></span> <span data-ttu-id="b97d2-149">キーを押して**CTRL**ファイルを表示する URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="b97d2-149">Press **CTRL**, and select the URL to view the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b97d2-150">XSL ファイルに加えられた変更は、マップには反映されません、次回のビルドで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b97d2-150">Changes made to the XSL file are not reflected in the map and are overwritten on the next build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b97d2-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="b97d2-151">See also</span></span>  

[<span data-ttu-id="b97d2-152">マップをデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="b97d2-152">How to Debug Maps</span></span>](../core/how-to-debug-maps.md)  
[<span data-ttu-id="b97d2-153">マップのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b97d2-153">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)  