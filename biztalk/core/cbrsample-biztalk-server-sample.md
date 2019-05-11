---
title: CBRSample (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, routing
- messages, filters
- outbound maps
- examples, messages
- messages, routing
- examples, outbound maps
- examples, filters
- messages, examples
ms.assetid: 8fba494c-9257-4eed-8b6a-867056147c2c
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f850f3f64fbc13596c5548fadf57c5055052a244
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357583"
---
# <a name="cbrsample-biztalk-server-sample"></a><span data-ttu-id="13380-102">CBRSample (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="13380-102">CBRSample (BizTalk Server Sample)</span></span>
<span data-ttu-id="13380-103">CBRSample サンプルはフィルターと送信を変換するマップを適用する方法とコンテンツに基づいてインスタンス メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="13380-103">The CBRSample sample demonstrates how to apply filters and an outbound map to transform and route instance messages based on content.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="13380-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="13380-104">What This Sample Does</span></span>  
 <span data-ttu-id="13380-105">このサンプルでは、名前、アドレス、および国コードに基づいて 2 つのフォルダーのいずれかの連絡先情報を格納しているメッセージのルーティングを示します。</span><span class="sxs-lookup"><span data-stu-id="13380-105">This sample demonstrates the routing of a message containing name, address, and contact information to one of two folders based on country code.</span></span> <span data-ttu-id="13380-106">具体的には、このサンプルは以下の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="13380-106">Specifically, this sample does the following:</span></span>  

1.  <span data-ttu-id="13380-107">サンプル メッセージ形式基本的な情報を含むユーザー ID と完全名、国コード、および電話番号情報とアドレスを持つ id を含む個人に関するを定義します。</span><span class="sxs-lookup"><span data-stu-id="13380-107">Defines a sample message format containing basic information about a person including identity with user ID and full name, address with country code, and phone contact information.</span></span>  

2.  <span data-ttu-id="13380-108">昇格、 **CountryCode**その it をコントロールの変換およびルーティングにポート フィルタで使用できるように、入力ドキュメントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="13380-108">Promotes the **CountryCode** property in the input document so that it can be used in a port filter to control transformation and routing.</span></span>  

3.  <span data-ttu-id="13380-109">メッセージをカナダ バージョンに変換と**CountryCode**は 200 または米国バージョンと**CountryCode**が 100 にします。</span><span class="sxs-lookup"><span data-stu-id="13380-109">Transforms the message into a Canadian version when **CountryCode** is equal to 200 or a U.S. version when **CountryCode**is equal to 100.</span></span> <span data-ttu-id="13380-110">どちらの変換が中間を除くすべてのデータの初期を通過 (**初期**)。</span><span class="sxs-lookup"><span data-stu-id="13380-110">Both transforms pass through all data except middle initial (**Initial**).</span></span> <span data-ttu-id="13380-111">カナダ バージョンにもマップ**状態**に**Province**と**ZipCode**に**PinCode**します。</span><span class="sxs-lookup"><span data-stu-id="13380-111">The Canadian version also maps **State** to **Province** and **ZipCode** to **PinCode**.</span></span>  

4.  <span data-ttu-id="13380-112">ディレクトリの米国およびカナダ バージョンのメッセージを CAN ディレクトリには、米国のメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="13380-112">Routes U.S. messages to the US directory and Canadian messages to the CAN directory.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="13380-113">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="13380-113">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="13380-114">デザインは、既定の送信送受信 XML パイプライン、プロパティの昇格、サブスクリプション フィルター、および送信マップ内で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="13380-114">The design relies on the default send and receive XML pipelines, property promotion, subscription filters, and outbound maps within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to route messages.</span></span> <span data-ttu-id="13380-115">次の表は、デザイン要素とその選択理由を示します。</span><span class="sxs-lookup"><span data-stu-id="13380-115">The following table shows design elements and their justification.</span></span>  


|        <span data-ttu-id="13380-116">デザイン要素</span><span class="sxs-lookup"><span data-stu-id="13380-116">Design element</span></span>        |                                                                                                          <span data-ttu-id="13380-117">選択理由</span><span class="sxs-lookup"><span data-stu-id="13380-117">Reason(s) selected</span></span>                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="13380-118">既定の XML 受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="13380-118">Default XML receive pipeline</span></span> | <span data-ttu-id="13380-119">-XMLReceive パイプラインには、プロパティの昇格がサポートしていますPassThruReceive パイプラインは提供されません。</span><span class="sxs-lookup"><span data-stu-id="13380-119">-   The XMLReceive pipeline supports property promotion; the PassThruReceive pipeline does not.</span></span><br /><span data-ttu-id="13380-120">-受信メッセージは既に XML 形式で、基本の逆アセンブリとパーティの解決以外の処理は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="13380-120">-   The inbound message is already in XML format and does not require processing beyond basic disassembly and party resolution.</span></span> |
|      <span data-ttu-id="13380-121">プロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="13380-121">Property promotion</span></span>      |          <span data-ttu-id="13380-122">-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ルーティングを実行するフィールドをプロパティに依存します。</span><span class="sxs-lookup"><span data-stu-id="13380-122">-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]depends upon property fields to do routing.</span></span> <span data-ttu-id="13380-123">識別フィールドはオーケストレーションによって使用されるため、ルーティングには使用できません。</span><span class="sxs-lookup"><span data-stu-id="13380-123">Distinguished fields are used by orchestrations and cannot be used for routing.</span></span>           |
|     <span data-ttu-id="13380-124">サブスクリプション フィルター</span><span class="sxs-lookup"><span data-stu-id="13380-124">Subscription filter</span></span>      |                                                <span data-ttu-id="13380-125">-サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャすることで実際のルーティングを実行します。</span><span class="sxs-lookup"><span data-stu-id="13380-125">-   The subscription filter performs the actual routing by capturing messages that meet one or more criteria based on property fields.</span></span>                                                |
|         <span data-ttu-id="13380-126">送信マップ</span><span class="sxs-lookup"><span data-stu-id="13380-126">Outbound map</span></span>         |                                                     <span data-ttu-id="13380-127">マップでは、1 つの形式から別のデータを変換します。</span><span class="sxs-lookup"><span data-stu-id="13380-127">-   Maps transform data from one format to another.</span></span> <span data-ttu-id="13380-128">サンプルは、受信メッセージを米国またはカナダのいずれかの形式にマップします。</span><span class="sxs-lookup"><span data-stu-id="13380-128">The sample maps an inbound message to either a U.S. or Canadian format.</span></span>                                                      |
|         <span data-ttu-id="13380-129">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="13380-129">XMLTransmit</span></span>          |                                                         <span data-ttu-id="13380-130">-送信 XML メッセージの基本的なアセンブリを実行します。追加サポートを提供している PassThruTransmit パイプラインはありません。</span><span class="sxs-lookup"><span data-stu-id="13380-130">-   Performs basic assembly of outgoing XML messages; the PassThruTransmit pipeline provides no additional support.</span></span>                                                          |

 <span data-ttu-id="13380-131">この基本パターンを拡張しより複雑なシナリオのために使用します。</span><span class="sxs-lookup"><span data-stu-id="13380-131">This basic pattern can be extended and used for more complex scenarios.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="13380-132">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="13380-132">Where to Find This Sample</span></span>  
 <span data-ttu-id="13380-133">このサンプルは <`Samples Path>`\Messaging\CBRSample\\します。</span><span class="sxs-lookup"><span data-stu-id="13380-133">This sample is located at <`Samples Path>`\Messaging\CBRSample\\.</span></span>  

 <span data-ttu-id="13380-134">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="13380-134">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="13380-135">ファイル</span><span class="sxs-lookup"><span data-stu-id="13380-135">File(s)</span></span>|<span data-ttu-id="13380-136">説明</span><span class="sxs-lookup"><span data-stu-id="13380-136">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13380-137">CBRDataCAN.Xml, CBRDataUS.Xml</span><span class="sxs-lookup"><span data-stu-id="13380-137">CBRDataCAN.Xml, CBRDataUS.Xml</span></span>|<span data-ttu-id="13380-138">ファイル CBRInputSchema.xsd で定義されたスキーマに準拠しているサンプル入力ファイル。</span><span class="sxs-lookup"><span data-stu-id="13380-138">Sample input files that conform to the schema defined in the file CBRInputSchema.xsd.</span></span>|  
|<span data-ttu-id="13380-139">CBRInput2CANMap.btm, CBRInput2USMap.btm</span><span class="sxs-lookup"><span data-stu-id="13380-139">CBRInput2CANMap.btm, CBRInput2USMap.btm</span></span>|<span data-ttu-id="13380-140">それぞれカナダ ファイルと米国形式の変換をマップします。</span><span class="sxs-lookup"><span data-stu-id="13380-140">Map files for the Canadian and U.S. format transformations, respectively.</span></span>|  
|<span data-ttu-id="13380-141">CBRInputSchema.xsd, CBROutputSchemaCAN.xsd, CBROutputSchemaUS.xsd</span><span class="sxs-lookup"><span data-stu-id="13380-141">CBRInputSchema.xsd, CBROutputSchemaCAN.xsd, CBROutputSchemaUS.xsd</span></span>|<span data-ttu-id="13380-142">スキーマ ファイル入力形式、カナダ出力形式、および米国では、それぞれの形式を出力します。</span><span class="sxs-lookup"><span data-stu-id="13380-142">Schema files for the input format, the Canadian output format, and the U.S. output format, respectively.</span></span>|  
|<span data-ttu-id="13380-143">CBRPromotedPropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="13380-143">CBRPromotedPropertySchema.xsd</span></span>|<span data-ttu-id="13380-144">対応する昇格させたプロパティのスキーマ ファイル、 **CountryCode** XML 内の要素は、ファイルを入力します。</span><span class="sxs-lookup"><span data-stu-id="13380-144">Schema file for the promoted property that corresponds to the **CountryCode** element in the XML input files.</span></span>|  
|<span data-ttu-id="13380-145">CBRSample.btproj, CBRSample.sln</span><span class="sxs-lookup"><span data-stu-id="13380-145">CBRSample.btproj, CBRSample.sln</span></span>|<span data-ttu-id="13380-146">このサンプルの BizTalk プロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="13380-146">BizTalk project and solution files for this sample.</span></span>|  
|<span data-ttu-id="13380-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="13380-147">Cleanup.bat</span></span>|<span data-ttu-id="13380-148">アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="13380-148">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="13380-149">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="13380-149">Removes send and receive ports.</span></span> <span data-ttu-id="13380-150">必要に応じて、インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="13380-150">Removes Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="13380-151">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="13380-151">Setup.bat</span></span>|<span data-ttu-id="13380-152">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="13380-152">Used to build and initialize this sample.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="13380-153">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="13380-153">How to Use This Sample</span></span>  
 <span data-ttu-id="13380-154">コンテンツに基づいてメッセージのルーティングに必要なアクションの動作例としては、このサンプルを使用します。</span><span class="sxs-lookup"><span data-stu-id="13380-154">Use this sample as a working example of the actions required to route a message based on content.</span></span>  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="13380-155">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="13380-155">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="13380-156">初期化 CBRSample サンプルをビルドし、する必要がありますを構築し、このサンプルでは、BizTalk プロジェクトを配置する受信ポートと場所、構成を 2 つの異なる送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="13380-156">To build and initialize the CBRSample sample, you need to build and deploy the BizTalk project for this sample, configure the receive port and location, and configure two different send ports.</span></span>  

#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a><span data-ttu-id="13380-157">このサンプルの BizTalk プロジェクト ビルドおよび配置するには</span><span class="sxs-lookup"><span data-stu-id="13380-157">To build and deploy the BizTalk project for this sample</span></span>  

1. <span data-ttu-id="13380-158">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="13380-158">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="13380-159">`<Samples Path>` **\Messaging\CBRSample**</span><span class="sxs-lookup"><span data-stu-id="13380-159">`<Samples Path>` **\Messaging\CBRSample**</span></span>  

2. <span data-ttu-id="13380-160">実行**Setup.bat**、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="13380-160">Run **Setup.bat**, which performs the following actions:</span></span>  

   - <span data-ttu-id="13380-161">入力を作成します (**で**) と出力フォルダ (**米国**と**できます**) このサンプルの。</span><span class="sxs-lookup"><span data-stu-id="13380-161">Creates the input (**In**) and output folders (**US** and **CAN**) for this sample.</span></span>  

   - <span data-ttu-id="13380-162">コンパイルし、Microsoft の展開[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="13380-162">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  

   - <span data-ttu-id="13380-163">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="13380-163">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="13380-164">このサンプルでは、作成してポートをバインドするときに、次の警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="13380-164">This sample displays the following warning when creating and binding the ports:</span></span>  
   > 
   >  <span data-ttu-id="13380-165">**警告:受信ハンドラーが指定されていない受信場所"CBRReceiveLocation";最初の更新の受信トランスポートの種類に一致するハンドラー。**</span><span class="sxs-lookup"><span data-stu-id="13380-165">**Warning: Receive handler not specified for receive location "CBRReceiveLocation"; updating with first receive handler with matching transport type.**</span></span>  
   > 
   >  <span data-ttu-id="13380-166">この警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="13380-166">You can safely ignore this warning.</span></span> <span data-ttu-id="13380-167">(インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)</span><span class="sxs-lookup"><span data-stu-id="13380-167">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="13380-168">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13380-168">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="13380-169">開き、Setup.bat を実行することがなく、このサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13380-169">If you choose to open and build the project in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="13380-170">結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。</span><span class="sxs-lookup"><span data-stu-id="13380-170">Use this key pair to sign the resulting assembly.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="13380-171">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="13380-171">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="13380-172">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="13380-172">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

#### <a name="to-prepare-to-configure-the-receive-port-and-location-and-the-send-ports"></a><span data-ttu-id="13380-173">受信ポートと場所、および送信ポートを構成する準備を行う</span><span class="sxs-lookup"><span data-stu-id="13380-173">To prepare to configure the receive port and location, and the send ports</span></span>  

1.  <span data-ttu-id="13380-174">**Microsoft SQL Management Studio**、適切な BizTalk 管理データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="13380-174">In **Microsoft SQL Management Studio**, select the correct BizTalk Management database.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="13380-175">BizTalk 管理データベースは、BizTalk 構成データベースとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="13380-175">The BizTalk Management database is also referred to as the BizTalk Configuration database.</span></span>  

#### <a name="to-configure-enlist-and-start-the-us-send-port"></a><span data-ttu-id="13380-176">米国の送信ポートを構成し、参加、開始するには</span><span class="sxs-lookup"><span data-stu-id="13380-176">To configure, enlist, and start the U.S. send port</span></span>  

1.  <span data-ttu-id="13380-177">BizTalk Server 管理コンソールで [**送信ポート**を右クリックして **[cbrussendport]**、] をクリックし、**編集**。</span><span class="sxs-lookup"><span data-stu-id="13380-177">In the BizTalk Server Administration console, expand **Send Ports**, right-click **CBRUSSendPort**, and then click **Edit**.</span></span>  

2.  <span data-ttu-id="13380-178">**静的な一方向送信ポート プロパティ** ダイアログ ボックスのダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。フィルター**, を設定して、新しい行を追加 **プロパティ** に **CBRSample.CountryCode**, したまま、 **演算子** 列に設定 **==**, と設定、 **値** 列を **100**します。</span><span class="sxs-lookup"><span data-stu-id="13380-178">In the **Static One-Way Send Port Properties** dialog box, in the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Filters**, and then add a new row by setting **Property** to **CBRSample.CountryCode**, leaving the **Operator** column set to **==**, and setting the **Value** column to **100**.</span></span>  

3.  <span data-ttu-id="13380-179">ダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。送信マップ**, 、設定されて、 **に適用するマップ** プロパティを **CBRSample.CBRInput2USMap**, 、順にクリック **OK**します。</span><span class="sxs-lookup"><span data-stu-id="13380-179">In the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Outbound Maps**, set the **Map to apply** property to **CBRSample.CBRInput2USMap**, and then click **OK**.</span></span> <span data-ttu-id="13380-180">マップを表示するスクロール ボタンをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13380-180">You may have to click the scroll button to bring the map into view.</span></span>  

#### <a name="to-configure-enlist-and-start-the-canadian-send-port"></a><span data-ttu-id="13380-181">構成、参加、およびカナダの送信ポートを開始するには</span><span class="sxs-lookup"><span data-stu-id="13380-181">To configure, enlist, and start the Canadian send port</span></span>  

1. <span data-ttu-id="13380-182">BizTalk Server 管理コンソールで [**送信ポート**を右クリックして **[cbrcansendport]**、] をクリックし、**編集**。</span><span class="sxs-lookup"><span data-stu-id="13380-182">In the BizTalk Server Administration console, expand **Send Ports**, right-click **CBRCANSendPort**, and then click **Edit**.</span></span>  

2. <span data-ttu-id="13380-183">**静的な一方向送信ポート プロパティ** ダイアログ ボックスのダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。フィルター**, を設定して、新しい行を追加 **プロパティ** に **CBRSample.CountryCode**, したまま、 **演算子** 列に設定 **==**, と設定、 **値** 列を **200**します。</span><span class="sxs-lookup"><span data-stu-id="13380-183">In the **Static One-Way Send Port Properties** dialog box, in the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Filters**, and then add a new row by setting **Property** to **CBRSample.CountryCode**, leaving the **Operator** column set to **==**, and setting the **Value** column to **200**.</span></span>  

3. <span data-ttu-id="13380-184">ダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。送信マップ**, 、設定されて、 **に適用するマップ** プロパティを **CBRSample.CBRInput2CANMap**, 、順にクリック **OK**します。</span><span class="sxs-lookup"><span data-stu-id="13380-184">In the folder tree to the left of the dialog box, select **Filters & Mapping &#124; Outbound Maps**, set the **Map to apply** property to **CBRSample.CBRInput2CANMap**, and then click **OK**.</span></span>  

   <span data-ttu-id="13380-185">次の手順では、受信ポートに送信ポートを接続します。</span><span class="sxs-lookup"><span data-stu-id="13380-185">These steps connect the send port to the receive port.</span></span> <span data-ttu-id="13380-186">サンプルの使用は、ドキュメントをルーティングするプロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="13380-186">The sample uses promoted properties to route the documents.</span></span>  

   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="13380-187">このサンプルを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="13380-187">is ready now to work with this sample.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="13380-188">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="13380-188">Running This Sample</span></span>  
 <span data-ttu-id="13380-189">CBRSample サンプルを実行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="13380-189">Use the following procedure to run the CBRSample sample.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="13380-190">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="13380-190">To run this sample</span></span>  

1. <span data-ttu-id="13380-191">入力ファイルをコピー **CBRDataCAN.xml**と**CBRDataUS.xml**、次の入力フォルダに。</span><span class="sxs-lookup"><span data-stu-id="13380-191">Copy the input files, **CBRDataCAN.xml** and **CBRDataUS.xml**, into the following input folder:</span></span>  

    <span data-ttu-id="13380-192">`<Samples Path>` **\Messaging\CBRSample\In**</span><span class="sxs-lookup"><span data-stu-id="13380-192">`<Samples Path>` **\Messaging\CBRSample\In**</span></span>  

2. <span data-ttu-id="13380-193">これらの各ファイルを変換する方法を確認し、2 つの出力フォルダーの値に基づいて、次のいずれかにルーティング、 **CountryCode**要素 (100 または 200)。</span><span class="sxs-lookup"><span data-stu-id="13380-193">Observe how each of these files is transformed and routed to one of the following two output folders based on the value of their **CountryCode** element (100 versus 200):</span></span>  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="13380-194">変換およびルーティング、入力ファイル**CBRDataCAN.xml**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="13380-194">transforms and routes the input file **CBRDataCAN.xml** to the folder:</span></span>  

      <span data-ttu-id="13380-195">`<Samples Path>` **\Messaging\CBRSample\CAN**</span><span class="sxs-lookup"><span data-stu-id="13380-195">`<Samples Path>` **\Messaging\CBRSample\CAN**</span></span>  

   - <span data-ttu-id="13380-196">BizTalk Server が変換および入力ファイルをルーティング**CBRDataUS.xml**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="13380-196">BizTalk Server transforms and routes the input file **CBRDataUS.xml** to the folder:</span></span>  

      <span data-ttu-id="13380-197">`<Samples Path>` **\Messaging\CBRSample\US**</span><span class="sxs-lookup"><span data-stu-id="13380-197">`<Samples Path>` **\Messaging\CBRSample\US**</span></span>  

## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="13380-198">クラスまたはメソッドのこのサンプルで使用</span><span class="sxs-lookup"><span data-stu-id="13380-198">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="13380-199">[なし] :</span><span class="sxs-lookup"><span data-stu-id="13380-199">None.</span></span>  

## <a name="see-also"></a><span data-ttu-id="13380-200">参照</span><span class="sxs-lookup"><span data-stu-id="13380-200">See Also</span></span>  
 <span data-ttu-id="13380-201">[既定のパイプライン](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="13380-201">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="13380-202">[送信ポートの送信マップを構成する方法](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="13380-202">[How to Configure Outbound Maps for a Send Port](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span></span>  
 [<span data-ttu-id="13380-203">Messaging (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="13380-203">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)