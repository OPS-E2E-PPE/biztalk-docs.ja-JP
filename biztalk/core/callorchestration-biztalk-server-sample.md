---
title: CallOrchestration (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, calling
- examples, orchestrations
ms.assetid: 0c4194f0-c1e2-419a-8a1a-a3c96e8d2667
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 614cbb4531d0d7052263e5e4c7d73ec209e9b685
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021880"
---
# <a name="callorchestration-biztalk-server-sample"></a><span data-ttu-id="e20c5-102">CallOrchestration (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="e20c5-102">CallOrchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="e20c5-103">CallOrchestration サンプルは、1 つの BizTalk オーケストレーションから別のオーケストレーションを呼び出す方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="e20c5-103">The CallOrchestration sample demonstrates how to call one BizTalk orchestration from another orchestration.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e20c5-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="e20c5-104">What This Sample Does</span></span>  
 <span data-ttu-id="e20c5-105">このサンプルでは、1 つのオーケストレーションから別のオーケストレーションを呼び出すために、次の一連の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-105">This sample demonstrates one orchestration calling another orchestration using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="e20c5-106">1 番目のオーケストレーションで、注文書 (PO) メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-106">The primary orchestration receives a purchase order (PO) message.</span></span>  
  
2.  <span data-ttu-id="e20c5-107">PO の出荷金額を決定するため、1 番目のオーケストレーションから 2 番目のオーケストレーションを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-107">The primary orchestration calls the secondary orchestration to determine the shipping price for the PO.</span></span>  
  
3.  <span data-ttu-id="e20c5-108">2 番目のオーケストレーションで、要求された出荷金額を計算し、結果を 1 番目のオーケストレーションに返します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-108">The secondary orchestration calculates the requested shipping price and returns it to the primary orchestration.</span></span>  
  
4.  <span data-ttu-id="e20c5-109">1 番目のオーケストレーションで、返された出荷金額を PO メッセージに反映します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-109">The primary orchestration updates the PO message with the returned shipping price.</span></span>  
  
5.  <span data-ttu-id="e20c5-110">1 番目のオーケストレーションで、更新した PO メッセージを確認用のフォルダに格納します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-110">The primary orchestration puts the updated PO message into a folder for your inspection.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="e20c5-111">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="e20c5-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="e20c5-112">このサンプルの主な目的は、1 つのオーケストレーション内から別のオーケストレーションを呼び出す方法を示すことです。</span><span class="sxs-lookup"><span data-stu-id="e20c5-112">The primary purpose of this sample is to show you how to call an orchestration from within another orchestration.</span></span> <span data-ttu-id="e20c5-113">オーケストレーションの呼び出しは、ビジネス プロセスを再利用可能なコンポーネントに分割する 1 つの方法であり、</span><span class="sxs-lookup"><span data-stu-id="e20c5-113">The ability to call orchestrations gives you a way to divide your business processes into reusable components.</span></span> <span data-ttu-id="e20c5-114">頻繁に使用するプロセスを取り出して個別のオーケストレーションを作成すれば、他でも再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e20c5-114">You can factor your common processes out into separate orchestrations for others to re-use.</span></span>  
  
 <span data-ttu-id="e20c5-115">このサンプルで、**オーケストレーションの呼び出し**receivePO.odx 内の図形 findShippingPrice.odx を呼び出すし、入れ子になったオーケストレーション findShippingPrice.odx を計算して、購入を送信する前に、出荷金額を返すを待ちます順序。</span><span class="sxs-lookup"><span data-stu-id="e20c5-115">In this sample, the **Call Orchestration** shape in receivePO.odx invokes findShippingPrice.odx and waits for the nested orchestration, findShippingPrice.odx, to calculate and return the shipping price before sending the purchase order.</span></span> <span data-ttu-id="e20c5-116">オーケストレーション findShippingPrice.odx での出荷金額の計算には、次のロジックを使用します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-116">The orchestration findShippingPrice.odx uses the following logic to calculate the shipping price:</span></span>  
  
```  
If ( weight * shippingRate ) < minShippingPrice Then  
    shippingPrice = minShippingPrice  
Else  
    shippingPrice = weight * shippingRate  
End If  
```  
  
 <span data-ttu-id="e20c5-117">サンプルの入力 PO ファイル InputPO.xml では、重みが 20 と指定されています。このため、出力 PO メッセージでは出荷金額が 10 から 20 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="e20c5-117">The sample input PO file, InputPO.xml, specifies a weight of 20, resulting in the output PO message having its shipping price changed from 10 to 20.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e20c5-118">アトミック オーケストレーションから、長時間実行されるトランザクションを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="e20c5-118">You cannot call a long-running transaction from an atomic orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e20c5-119">使用方法の違い、**オーケストレーションの呼び出し**図形と**オーケストレーションの開始**図形がオーケストレーションを呼び出すときに、入れ子になったオーケストレーションが返されるまでの呼び出し元が待機続行しています。</span><span class="sxs-lookup"><span data-stu-id="e20c5-119">The difference between using the **Call Orchestration** shape and the **Start Orchestration** shape is that when calling an orchestration, the caller waits for the nested orchestration to return before continuing.</span></span> <span data-ttu-id="e20c5-120">後者の場合、呼び出し元のオーケストレーションは別のオーケストレーションを開始した後すぐプロセス フローの次の手順に進む点です。</span><span class="sxs-lookup"><span data-stu-id="e20c5-120">When starting an orchestration from an orchestration, after the caller initiates the action, the caller moves forward to the next step in the process flow.</span></span> <span data-ttu-id="e20c5-121">後者の場合、呼び出されたオーケストレーションは呼び出し元とは独立して、自身のプロセス フローを最後まで実行します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-121">The orchestration that was invoked by the caller runs independently until it finishes the process flow.</span></span> <span data-ttu-id="e20c5-122">詳細については、[オーケストレーションの呼び出し図形を構成する方法](../core/how-to-configure-the-call-orchestration-shape.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e20c5-122">For more information, see [How to Configure the Call Orchestration Shape](../core/how-to-configure-the-call-orchestration-shape.md).</span></span> <span data-ttu-id="e20c5-123">参照してください[オーケストレーションの開始図形を構成する方法](../core/how-to-configure-the-start-orchestration-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-123">Also see [How to Configure the Start Orchestration Shape](../core/how-to-configure-the-start-orchestration-shape.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e20c5-124">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="e20c5-124">Where to Find This Sample</span></span>  
 <span data-ttu-id="e20c5-125">\<*パスのサンプル*\>\Orchestrations\CallOrchestration\\</span><span class="sxs-lookup"><span data-stu-id="e20c5-125">\<*Samples Path*\>\Orchestrations\CallOrchestration\\</span></span>  
  
 <span data-ttu-id="e20c5-126">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="e20c5-126">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e20c5-127">ファイル</span><span class="sxs-lookup"><span data-stu-id="e20c5-127">File(s)</span></span>|<span data-ttu-id="e20c5-128">説明</span><span class="sxs-lookup"><span data-stu-id="e20c5-128">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e20c5-129">CallOrchestration.btproj、CallOrchestration.sln</span><span class="sxs-lookup"><span data-stu-id="e20c5-129">CallOrchestration.btproj, CallOrchestration.sln</span></span>|<span data-ttu-id="e20c5-130">このサンプルのプロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e20c5-130">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="e20c5-131">CallOrchestrationBinding.xml</span><span class="sxs-lookup"><span data-stu-id="e20c5-131">CallOrchestrationBinding.xml</span></span>|<span data-ttu-id="e20c5-132">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e20c5-132">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="e20c5-133">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="e20c5-133">Cleanup.bat</span></span>|<span data-ttu-id="e20c5-134">アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e20c5-134">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="e20c5-135">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="e20c5-135">Removes send and receive ports.</span></span> <span data-ttu-id="e20c5-136">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="e20c5-136">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="e20c5-137">findShippingPrice.odx</span><span class="sxs-lookup"><span data-stu-id="e20c5-137">findShippingPrice.odx</span></span>|<span data-ttu-id="e20c5-138">2 番目のオーケストレーションとして動作する BizTalk オーケストレーションです。1 番目のオーケストレーション receivePO.odx から呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e20c5-138">BizTalk orchestration that serves as a secondary orchestration, called from the primary orchestration, receivePO.odx.</span></span>|  
|<span data-ttu-id="e20c5-139">InputPO.xml</span><span class="sxs-lookup"><span data-stu-id="e20c5-139">InputPO.xml</span></span>|<span data-ttu-id="e20c5-140">ファイル PO.xsd で定義されているスキーマに準拠した、サンプルの入力 PO メッセージです。</span><span class="sxs-lookup"><span data-stu-id="e20c5-140">Sample input PO message that conforms to the schema defined in the file PO.xsd.</span></span>|  
|<span data-ttu-id="e20c5-141">PO.xsd</span><span class="sxs-lookup"><span data-stu-id="e20c5-141">PO.xsd</span></span>|<span data-ttu-id="e20c5-142">サンプルの入力ファイル InputPO.xml などの受信 PO メッセージの構造を定義するスキーマです。このスキーマでは、スキーマ内の 3 つの要素すべてに対してプロパティの昇格が定義されています。</span><span class="sxs-lookup"><span data-stu-id="e20c5-142">Schema that defines the structure of inbound PO messages such as the sample input file InputPO.xml, and defines property promotion for all three elements in the schema.</span></span>|  
|<span data-ttu-id="e20c5-143">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="e20c5-143">PropertySchema.xsd</span></span>|<span data-ttu-id="e20c5-144">スキーマ PO.xsd 内の 3 つの要素すべてに対するプロパティの昇格に参加している、プロパティ スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e20c5-144">Property schema file that participates in property promotion for all three elements in the schema PO.xsd.</span></span>|  
|<span data-ttu-id="e20c5-145">receivePO.odx</span><span class="sxs-lookup"><span data-stu-id="e20c5-145">receivePO.odx</span></span>|<span data-ttu-id="e20c5-146">このサンプルで、1 番目のオーケストレーションとして動作する BizTalk オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="e20c5-146">BizTalk orchestration that serves as the primary orchestration in this sample.</span></span> <span data-ttu-id="e20c5-147">PO メッセージを受信フォルダから取得した後、他のオーケストレーション findShippingPrice.odx を呼び出して、計算された出荷金額をメッセージに反映します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-147">It retrieves PO messages from the receive folder and then calls the other orchestration, findShippingPrice.odx, to calculate and update the shipping price.</span></span>|  
|<span data-ttu-id="e20c5-148">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="e20c5-148">Setup.bat</span></span>|<span data-ttu-id="e20c5-149">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e20c5-149">Used to build and initialize this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="e20c5-150">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="e20c5-150">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-callorchestration-sample"></a><span data-ttu-id="e20c5-151">CallOrchestration サンプルをビルドおよび初期化するには</span><span class="sxs-lookup"><span data-stu-id="e20c5-151">To build and initialize the CallOrchestration sample</span></span>  
  
1. <span data-ttu-id="e20c5-152">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-152">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="e20c5-153">\<*パスのサンプル*\>\Orchestrations\CallOrchestration\\</span><span class="sxs-lookup"><span data-stu-id="e20c5-153">\<*Samples Path*\>\Orchestrations\CallOrchestration\\</span></span>  
  
2. <span data-ttu-id="e20c5-154">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-154">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="e20c5-155">CallOrchestration フォルダに、このサンプルの入力 (In) フォルダと出力 (Out) フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-155">Creates the input (In) and output (Out) folders for this sample in the CallOrchestration folder.</span></span>  
  
   - <span data-ttu-id="e20c5-156">このサンプルの両方のオーケストレーションを含む [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし展開します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-156">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project, containing both orchestrations, for this sample.</span></span>  
  
   - <span data-ttu-id="e20c5-157">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="e20c5-157">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
   - <span data-ttu-id="e20c5-158">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-158">Enables the receive location, and starts the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e20c5-159">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e20c5-159">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="e20c5-160">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="e20c5-160">Running This Sample</span></span>  
  
#### <a name="to-run-the-callorchestration-sample"></a><span data-ttu-id="e20c5-161">CallOrchestration サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="e20c5-161">To run the CallOrchestration sample</span></span>  
  
1.  <span data-ttu-id="e20c5-162">ファイル InputPO.xml を In フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e20c5-162">Put a copy of the file InputPO.xml into the In folder.</span></span>  
  
2.  <span data-ttu-id="e20c5-163">更新された XML PO ファイルが Out フォルダに作成されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-163">Observe the updated XML PO file created in the Out folder.</span></span> <span data-ttu-id="e20c5-164">このファイルには元の PO メッセージが含まれます。このメッセージには、前述のように計算後の出荷費用が反映されています。</span><span class="sxs-lookup"><span data-stu-id="e20c5-164">It contains the original PO message, modified to include a shipping cost calculated as explained earlier.</span></span> <span data-ttu-id="e20c5-165">このファイルの名前の形式が\< *MessageID*\>、.xml、 *\<MessageID\>* メッセージを一意に識別するために生成される GUID.</span><span class="sxs-lookup"><span data-stu-id="e20c5-165">The format of the name of this file is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="e20c5-166">このサンプルのアンインストール</span><span class="sxs-lookup"><span data-stu-id="e20c5-166">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-callorchestration-sample"></a><span data-ttu-id="e20c5-167">CallOrchestration サンプルをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="e20c5-167">To uninstall the CallOrchestration sample</span></span>  
  
1. <span data-ttu-id="e20c5-168">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-168">In a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="e20c5-169">\<*パスのサンプル*\>\Orchestrations\CallOrchestration\\</span><span class="sxs-lookup"><span data-stu-id="e20c5-169">\<*Samples Path*\>\Orchestrations\CallOrchestration\\</span></span>  
  
2. <span data-ttu-id="e20c5-170">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="e20c5-170">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e20c5-171">参照</span><span class="sxs-lookup"><span data-stu-id="e20c5-171">See Also</span></span>  
 [<span data-ttu-id="e20c5-172">オーケストレーション (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e20c5-172">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)