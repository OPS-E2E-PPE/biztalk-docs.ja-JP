---
title: "HubScenario サンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb6990ec-aea2-4362-8573-7f737a4fc7f1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b9b2770f1d14d716149025ac44cb3cdffbbb23b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hubscenario-sample"></a><span data-ttu-id="734b2-102">HubScenario サンプル</span><span class="sxs-lookup"><span data-stu-id="734b2-102">HubScenario Sample</span></span>
<span data-ttu-id="734b2-103">HubScenario サンプルは、ハブ シナリオでのメッセージの送信を管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="734b2-103">The HubScenario sample demonstrates how to manage message transmission in a hub scenario.</span></span> <span data-ttu-id="734b2-104">このサンプルでは、中間のハブに送信されたメッセージを最終受信者に送信するメッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="734b2-104">It transforms a message sent to an intermediary hub into a message to be sent to the final recipient.</span></span>  
  
 <span data-ttu-id="734b2-105">HubScenario は、サービス コンテンツから最終受信者の DUNS 番号を抽出します。</span><span class="sxs-lookup"><span data-stu-id="734b2-105">HubScenario extracts the DUNS number of the final recipient from the service content.</span></span> <span data-ttu-id="734b2-106">さらに、著名証明書、暗号化証明書、および送信先 URL を管理します。</span><span class="sxs-lookup"><span data-stu-id="734b2-106">It manages signing and encryption certificates, and the destination URL.</span></span> <span data-ttu-id="734b2-107">そして、最終受信者への新しいメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="734b2-107">It generates a new message for the final recipient.</span></span>  
  
 <span data-ttu-id="734b2-108">このサンプルでは、3A4 要求メッセージと応答メッセージ、および 0C1 要求メッセージを取り扱います。</span><span class="sxs-lookup"><span data-stu-id="734b2-108">This sample handles 3A4 request and response messages, and 0C1 request messages.</span></span> <span data-ttu-id="734b2-109">HubScenario を使用して各自の目的に合ったアプリケーションを作成するには、各メッセージ PIP (Partner Interface Process) に対してルーチンを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="734b2-109">When you use HubScenario to create an application for your purposes, you will have to generate routines for each message Partner Interface Process (PIP).</span></span>  
  
 <span data-ttu-id="734b2-110">HubScenario サンプルには、HubHelper.cs プロジェクトと HubScenario.odx プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="734b2-110">The HubScenario sample includes HubHelper.cs and HubScenario.odx projects.</span></span>  
  
 <span data-ttu-id="734b2-111">HubScenario サンプルには、受信ポート (MessagesToLOB_Receive_Port) と受信場所 (MessagesToLOB_Receive_Location) のバインドのインポートに使用できるバインド ファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="734b2-111">The HubScenario sample also includes a binding file that you can use to import bindings for a receive port (MessagesToLOB_Receive_Port) and receive location (MessagesToLOB_Receive_Location) for use with the HubScenario.odx orchestration.</span></span> <span data-ttu-id="734b2-112">このバインド ファイル (HubScenarioBinding.xml) にあります*\<ドライブ >*: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk\<バージョン > Accelerator for RosettaNet \SDK\HubScenario です。</span><span class="sxs-lookup"><span data-stu-id="734b2-112">This binding file (HubScenarioBinding.xml) is located in *\<drive>*:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk \<version> Accelerator for RosettaNet \SDK\HubScenario.</span></span> <span data-ttu-id="734b2-113">バインドのインポートには BTSTask コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="734b2-113">Use the BTSTask command to import the bindings.</span></span> <span data-ttu-id="734b2-114">詳細については、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ヘルプの「ImportBindings コマンド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="734b2-114">For more information, see the "ImportBindings Command" topic in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="734b2-115">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="734b2-115">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="734b2-116">Visual Studio で開く\<ドライブ >: \Program Files\Microsoft Microsoft BizTalk\<バージョン > Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj です。</span><span class="sxs-lookup"><span data-stu-id="734b2-116">In Visual Studio, open \<drive>:\Program Files\Microsoft Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj.</span></span> <span data-ttu-id="734b2-117">ソリューション エクスプローラーで HubScenario プロジェクトを右クリックし、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734b2-117">In Solution Explorer, right-click the HubScenario project, and then click Properties.</span></span> <span data-ttu-id="734b2-118">HubScenario プロジェクトの プロパティ ページで 署名 タブを選択**アセンブリに署名** チェック ボックスを選択して**HubScenario.snk**で**厳密な名前キーファイルを選択して** をクリック**Ok**です。</span><span class="sxs-lookup"><span data-stu-id="734b2-118">In the Properties page for the HubScenario project, in the Signing tab select **Sign the assembly** checkbox, and select **HubScenario.snk** in **Choose a strong name key file** and click **Ok**.</span></span>  
  
2.  <span data-ttu-id="734b2-119">ソリューション エクスプローラーで HubHelper プロジェクトを右クリックして、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734b2-119">In Solution Explorer, right-click the HubHelper project, and then click Properties.</span></span> <span data-ttu-id="734b2-120">HubHelper プロジェクトのプロパティ ページの [署名] タブで、[アセンブリの署名] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="734b2-120">In the Properties page for the HubHelper project, in the Signing tab check Sign the assembly checkbox.</span></span> <span data-ttu-id="734b2-121">厳密な名前キー ファイルのフィールドを選択して、新しい種類を選択**HubHelper.snk**キー ファイル名とクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="734b2-121">In Choose a strong name key file field, select new type **HubHelper.snk** as Key file name and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="734b2-122">HubScenario および HubHelper プロジェクトに手動でアセンブリ キー ファイルを入力しないと、これらのアセンブリは展開されません。</span><span class="sxs-lookup"><span data-stu-id="734b2-122">If you do not manually enter the assembly key file in the HubScenario and HubHelper projects, the assemblies will not deploy.</span></span>  
  
3.  <span data-ttu-id="734b2-123">コマンド プロンプトに移動*\<ドライブ >*: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk\hubscenario フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="734b2-123">At a command prompt, move to *\<drive>*:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\HubScenario folder.</span></span> <span data-ttu-id="734b2-124">ファイル Setup.bat を実行します (64 ビット コンピューターの場合は、Setupx64.bat を実行します)。</span><span class="sxs-lookup"><span data-stu-id="734b2-124">Run the file Setup.bat (or on a 64-bit computer, run Setupx64.bat).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="734b2-125">使用例</span><span class="sxs-lookup"><span data-stu-id="734b2-125">Demonstrates</span></span>  
 <span data-ttu-id="734b2-126">HubScenario.ods オーケストレーションは、次のタスクを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="734b2-126">The HubScenario.ods orchestration demonstrates how to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="734b2-127">基幹業務アプリケーションからメッセージを受信する。</span><span class="sxs-lookup"><span data-stu-id="734b2-127">Receives the message from the line-of-business application.</span></span>  
  
2.  <span data-ttu-id="734b2-128">Service Content から `CDATA` 要素を削除し、XML 文字列を返す。</span><span class="sxs-lookup"><span data-stu-id="734b2-128">Removes the `CDATA` element from the service content, returning the XML string.</span></span>  
  
3.  <span data-ttu-id="734b2-129">最終メッセージの相手側パーティ名、PIPCode、PIPInstanceID、PIPVersion を取得する。</span><span class="sxs-lookup"><span data-stu-id="734b2-129">Retrieves the destination party name, PIPCode, PIPInstanceID, and PIPVersion for the final message.</span></span>  
  
4.  <span data-ttu-id="734b2-130">最終受信者の DUNS 番号を取得する。</span><span class="sxs-lookup"><span data-stu-id="734b2-130">Retrieves the DUNS number for the final recipient.</span></span>  
  
5.  <span data-ttu-id="734b2-131">メッセージのカテゴリを判断し、正しいスキーマへの参照を含んでいる DOCTYPE 要素をサービス コンテンツに追加する。</span><span class="sxs-lookup"><span data-stu-id="734b2-131">Determines the category of the message, and adds the DOCTYPE element that contains a reference to the appropriate schema to the service content.</span></span>  
  
6.  <span data-ttu-id="734b2-132">新しい相手側パーティ名、DUNS 番号、PIP コード情報、およびサービス コンテンツによりメッセージを構築する。</span><span class="sxs-lookup"><span data-stu-id="734b2-132">Constructs a message with the new destination party name, DUNS number, PIP code information, and service content.</span></span>  
  
7.  <span data-ttu-id="734b2-133">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] で処理するために、メッセージを送信する。</span><span class="sxs-lookup"><span data-stu-id="734b2-133">Submits the message for processing by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="734b2-134">これにより、`SubmitRNIF.SubmitMessage` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="734b2-134">This is a call to `SubmitRNIF.SubmitMessage`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="734b2-135">参照</span><span class="sxs-lookup"><span data-stu-id="734b2-135">See Also</span></span>  
 <span data-ttu-id="734b2-136">[サンプルのハブベース シナリオ](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="734b2-136">[Sample Hub-Based Scenario](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md) </span></span>  
 [<span data-ttu-id="734b2-137">オーケストレーション サンプル</span><span class="sxs-lookup"><span data-stu-id="734b2-137">Orchestration Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)