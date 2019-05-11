---
title: HubScenario サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb6990ec-aea2-4362-8573-7f737a4fc7f1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcd7f7d08e1451bfe50d2558b8f7c6b24d897957
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283608"
---
# <a name="hubscenario-sample"></a><span data-ttu-id="0e6d6-102">HubScenario サンプル</span><span class="sxs-lookup"><span data-stu-id="0e6d6-102">HubScenario Sample</span></span>
<span data-ttu-id="0e6d6-103">HubScenario サンプルでは、ハブ シナリオでのメッセージ送信を管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-103">The HubScenario sample demonstrates how to manage message transmission in a hub scenario.</span></span> <span data-ttu-id="0e6d6-104">最終的な受信者に送信されるメッセージに中間ハブに送信されるメッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-104">It transforms a message sent to an intermediary hub into a message to be sent to the final recipient.</span></span>  
  
 <span data-ttu-id="0e6d6-105">HubScenario は、サービスのコンテンツから最終受信者の DUNS 番号を抽出します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-105">HubScenario extracts the DUNS number of the final recipient from the service content.</span></span> <span data-ttu-id="0e6d6-106">署名と暗号化の証明書、および送信先の URL を管理します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-106">It manages signing and encryption certificates, and the destination URL.</span></span> <span data-ttu-id="0e6d6-107">最終的な受信者に新しいメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-107">It generates a new message for the final recipient.</span></span>  
  
 <span data-ttu-id="0e6d6-108">このサンプルでは、3A4 要求と応答メッセージ、および 0 の C 1 つの要求メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-108">This sample handles 3A4 request and response messages, and 0C1 request messages.</span></span> <span data-ttu-id="0e6d6-109">HubScenario を使用して、目的のアプリケーションを作成するときに各メッセージ プロセス PIP (Partner Interface) のルーチンを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-109">When you use HubScenario to create an application for your purposes, you will have to generate routines for each message Partner Interface Process (PIP).</span></span>  
  
 <span data-ttu-id="0e6d6-110">HubScenario サンプルには、プロジェクトと HubScenario.odx プロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-110">The HubScenario sample includes HubHelper.cs and HubScenario.odx projects.</span></span>  
  
 <span data-ttu-id="0e6d6-111">HubScenario サンプルには、HubScenario.odx オーケストレーションで使用するための受信ポート (MessagesToLOB_Receive_Port) のバインドをインポートして、受信場所 (MessagesToLOB_Receive_Location) を使用できるバインド ファイルも含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-111">The HubScenario sample also includes a binding file that you can use to import bindings for a receive port (MessagesToLOB_Receive_Port) and receive location (MessagesToLOB_Receive_Location) for use with the HubScenario.odx orchestration.</span></span> <span data-ttu-id="0e6d6-112">このバインド ファイル (HubScenarioBinding.xml) にある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet \SDK\HubScenario します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-112">This binding file (HubScenarioBinding.xml) is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet \SDK\HubScenario.</span></span> <span data-ttu-id="0e6d6-113">バインドをインポートするのにには、BTSTask コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-113">Use the BTSTask command to import the bindings.</span></span> <span data-ttu-id="0e6d6-114">詳細については、BizTalk Server ヘルプの「ImportBindings コマンド」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-114">For more information, see the "ImportBindings Command" topic in BizTalk Server Help.</span></span>  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="0e6d6-115">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="0e6d6-115">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="0e6d6-116">Visual Studio で開く\<ドライブ\>: \Program Files\Microsoft BizTalk\<バージョン\>RosettaNet\SDK\HubScenario\HubScenario.btproj のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-116">In Visual Studio, open \<drive\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj.</span></span> <span data-ttu-id="0e6d6-117">ソリューション エクスプ ローラーで HubScenario プロジェクトを右クリックし、し、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-117">In Solution Explorer, right-click the HubScenario project, and then click Properties.</span></span> <span data-ttu-id="0e6d6-118">HubScenario プロジェクトのプロパティ ページで、署名 タブで選択**アセンブリに署名** チェック ボックスを選択し、 **HubScenario.snk**で**厳密な名前キーファイルを選択して**クリック**Ok**します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-118">In the Properties page for the HubScenario project, in the Signing tab select **Sign the assembly** checkbox, and select **HubScenario.snk** in **Choose a strong name key file** and click **Ok**.</span></span>  
  
2. <span data-ttu-id="0e6d6-119">ソリューション エクスプ ローラーで HubHelper プロジェクトを右クリックし、し、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-119">In Solution Explorer, right-click the HubHelper project, and then click Properties.</span></span> <span data-ttu-id="0e6d6-120">HubHelper プロジェクトのプロパティ ページで、署名 タブでサインオン アセンブリのチェック ボックスを確認します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-120">In the Properties page for the HubHelper project, in the Signing tab check Sign the assembly checkbox.</span></span> <span data-ttu-id="0e6d6-121">厳密な名前キー ファイルのフィールドを選択して、新しい種類の選択**HubHelper.snk**キー ファイル名をクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-121">In Choose a strong name key file field, select new type **HubHelper.snk** as Key file name and click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0e6d6-122">HubScenario および HubHelper プロジェクトでアセンブリ キー ファイルを手動で入力はない場合、アセンブリは展開しません。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-122">If you do not manually enter the assembly key file in the HubScenario and HubHelper projects, the assemblies will not deploy.</span></span>  
  
3. <span data-ttu-id="0e6d6-123">コマンド プロンプトに移動します。 *\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\hubscenario フォルダー。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-123">At a command prompt, move to *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\HubScenario folder.</span></span> <span data-ttu-id="0e6d6-124">ファイル Setup.bat を実行します (または、64 ビット コンピューターで Setupx64.bat を実行します。)</span><span class="sxs-lookup"><span data-stu-id="0e6d6-124">Run the file Setup.bat (or on a 64-bit computer, run Setupx64.bat).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="0e6d6-125">使用例</span><span class="sxs-lookup"><span data-stu-id="0e6d6-125">Demonstrates</span></span>  
 <span data-ttu-id="0e6d6-126">HubScenario.ods オーケストレーションでは、次のタスクを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-126">The HubScenario.ods orchestration demonstrates how to perform the following tasks:</span></span>  
  
1. <span data-ttu-id="0e6d6-127">基幹業務アプリケーションからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-127">Receives the message from the line-of-business application.</span></span>  
  
2. <span data-ttu-id="0e6d6-128">削除、`CDATA`から、サービス コンテンツを XML 文字列を返す要素。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-128">Removes the `CDATA` element from the service content, returning the XML string.</span></span>  
  
3. <span data-ttu-id="0e6d6-129">最後のメッセージの送信先パーティ名、PIPCode、PIPInstanceID、および PIPVersion を取得します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-129">Retrieves the destination party name, PIPCode, PIPInstanceID, and PIPVersion for the final message.</span></span>  
  
4. <span data-ttu-id="0e6d6-130">最終の受信者の DUNS 番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-130">Retrieves the DUNS number for the final recipient.</span></span>  
  
5. <span data-ttu-id="0e6d6-131">メッセージのカテゴリを指定し、サービスのコンテンツを適切なスキーマへの参照を含む DOCTYPE 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-131">Determines the category of the message, and adds the DOCTYPE element that contains a reference to the appropriate schema to the service content.</span></span>  
  
6. <span data-ttu-id="0e6d6-132">新しい送信先パーティ名、DUNS 番号、PIP コード情報、およびサービスのコンテンツを含むメッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-132">Constructs a message with the new destination party name, DUNS number, PIP code information, and service content.</span></span>  
  
7. <span data-ttu-id="0e6d6-133">処理するためのメッセージを送信する[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-133">Submits the message for processing by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="0e6d6-134">これは、呼び出しを`SubmitRNIF.SubmitMessage`します。</span><span class="sxs-lookup"><span data-stu-id="0e6d6-134">This is a call to `SubmitRNIF.SubmitMessage`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e6d6-135">参照</span><span class="sxs-lookup"><span data-stu-id="0e6d6-135">See Also</span></span>  
 <span data-ttu-id="0e6d6-136">[サンプルのハブベース シナリオ](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0e6d6-136">[Sample Hub-Based Scenario](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md) </span></span>  
 [<span data-ttu-id="0e6d6-137">オーケストレーション サンプル</span><span class="sxs-lookup"><span data-stu-id="0e6d6-137">Orchestration Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)