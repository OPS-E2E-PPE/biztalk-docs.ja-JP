---
title: "ビジネス ルールを使用して、3A4 プライベート応答側オーケストレーション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33d87952-def6-4202-b535-3d80171332eb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 130349d707c8e4382c50cd7b65d01d346bf0a7fc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="3a4-private-responder-orchestration-using-a-business-rule"></a><span data-ttu-id="fb7a8-102">ビジネス ルールを使用して、3A4 プライベート応答側オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="fb7a8-102">3A4 Private Responder Orchestration Using a Business Rule</span></span>
<span data-ttu-id="fb7a8-103">PIP3A4PrivateResponder.odx サンプルは、ビジネス ルールを組み込んでいる PIP (Partner Interface Process) 固有の応答側プライベート プロセスの実装方法を示した、プライベート プロセス オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-103">The PIP3A4PrivateResponder.odx sample is a private-process orchestration that demonstrates how to implement a Partner Interface Process (PIP)-specific responder private process incorporating a business rule.</span></span> <span data-ttu-id="fb7a8-104">このプロセスの詳細については、次を参照してください。[プライベート プロセス オーケストレーションのビジネス ルールの定義](../../adapters-and-accelerators/accelerator-rosettanet/defining-a-business-rule-for-a-private-process-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-104">For more information about this process, see [Defining a Business Rule for a Private Process Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/defining-a-business-rule-for-a-private-process-orchestration.md).</span></span>  
  
 <span data-ttu-id="fb7a8-105">既定では、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]セットアップ プログラムのインストールのサンプルを\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator forRosettanet \sdk\pipautomation\3a4 にあります。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-105">By default, the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Setup program installs the sample in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="fb7a8-106">手順</span><span class="sxs-lookup"><span data-stu-id="fb7a8-106">Procedures</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="fb7a8-107">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="fb7a8-107">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="fb7a8-108">コマンド プロンプトで、 *\<ドライブ\>*: \Program Files\ Microsoft BizTalk Accelerator for RosettaNet\<バージョン\>\SDK\PIPAutomation\3A4 フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-108">At a command prompt, locate the *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for RosettaNet \<version\>\SDK\PIPAutomation\3A4 folder.</span></span>  
  
2.  <span data-ttu-id="fb7a8-109">ファイル Setup.bat を実行します。このファイルによって、Binding.xml バインド ファイルを使用して次のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-109">Run the file Setup.bat, which uses the Binding.xml binding file to perform the following actions:</span></span>  
  
    -   <span data-ttu-id="fb7a8-110">Helper プロジェクトをコンパイルし、グローバル アセンブリ キャッシュにアセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-110">Compiles the Helper project and registers the assembly in the global assembly cache.</span></span>  
  
    -   <span data-ttu-id="fb7a8-111">PIP3APrivateResponder プロジェクトをコンパイルし、グローバル アセンブリ キャッシュにアセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-111">Compiles the PIP3APrivateResponder project and registers the assembly in the global assembly cache.</span></span>  
  
    -   <span data-ttu-id="fb7a8-112">LOB_To_PrivateResponder 受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-112">Creates the LOB_To_PrivateResponder receive port.</span></span>  
  
    -   <span data-ttu-id="fb7a8-113">LOB_To_PrivateResponder 受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-113">Creates the LOB_To_PrivateResponder receive location.</span></span>  
  
    -   <span data-ttu-id="fb7a8-114">PrivateResponder_To_LOB 送信ポートを作成し、開始します。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-114">Creates and starts the PrivateResponder_To_LOB send port.</span></span>  
  
    -   <span data-ttu-id="fb7a8-115">PIP3A4PrivateResponderProcess オーケストレーションをコンパイルし、展開します。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-115">Compiles and deploys the PIP3A4PrivateResponderProcess orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fb7a8-116">BizTalk エクスプローラを使用して、PIP3A4PrivateResponderProcess オーケストレーションのポート バインド構成を完成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-116">You must complete the port binding configuration of the PIP3A4PrivateResponderProcess orchestration using BizTalk Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fb7a8-117">setup.bat による変更を元に戻すには、手動で PIP3A4PrivateResponder.odx オーケストレーションの登録を解除し、Helper および PIP3A4PrivateResponder のアセンブリの展開を解除し、samplebtarnpolicy ルールのポリシーの展開を解除して削除します。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-117">To undo changes made by setup.bat, manually unenlist the PIP3A4PrivateResponder.odx orchestration, undeploy the Helper and PIP3A4PrivateResponder assemblies, and undeploy and then delete the samplebtarnpolicy rules policy.</span></span> <span data-ttu-id="fb7a8-118">ある Cleanup.bat を使用することはできません、 *\<ドライブ\>*: \Program Files\ Microsoft BizTalk Accelerator for RosettaNet\<バージョン\>\SDK\PIPAutomation\3A4 フォルダーの変更を元に戻すsetup.bat によって行われます。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-118">You cannot use Cleanup.bat in the *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for RosettaNet \<version\>\SDK\PIPAutomation\3A4 folder to undo changes made by setup.bat.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="fb7a8-119">使用例</span><span class="sxs-lookup"><span data-stu-id="fb7a8-119">Demonstrates</span></span>  
 <span data-ttu-id="fb7a8-120">このサンプルは、3A4 要求アクションとシグナル メッセージをサブスクライブし、</span><span class="sxs-lookup"><span data-stu-id="fb7a8-120">This sample subscribes 3A4 request action and signal messages.</span></span> <span data-ttu-id="fb7a8-121">3A4 の同期処理と非同期処理のどちらでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-121">It works in both 3A4 synchronous and asynchronous processes.</span></span> <span data-ttu-id="fb7a8-122">これ以外の PIP メッセージは、すべて汎用の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] プライベート プロセスを引き続き使用してルーティングします。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-122">All other PIP messages still route through the generic [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] private process.</span></span> <span data-ttu-id="fb7a8-123">このサンプルにより、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] のビジネス ルール エンジンが呼び出され、着信 3A4 要求メッセージがルール エンジンに渡されます。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-123">This sample invokes the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Business Rule Engine, and passes to the Rule Engine the incoming 3A4 request message.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="fb7a8-124">samplebtarnpolicy.xml という名前のサンプルのビジネス ルール ポリシーが提供\<*ドライブ*\>: \Program Files\ Microsoft BizTalk Accelerator for RosettaNet\<バージョン\>\SDK\PipAutomation\3A4 です。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-124"> provides a sample business-rule policy named samplebtarnpolicy.xml in \<*drive*\>:\Program Files\ Microsoft BizTalk Accelerator for RosettaNet \<version\>\SDK\PipAutomation\3A4.</span></span> <span data-ttu-id="fb7a8-125">詳細については、次を参照してください。[サンプル BTARN ビジネス ポリシー](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)です。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-125">For more information, see [Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md).</span></span>  
  
 <span data-ttu-id="fb7a8-126">このサンプルを使用するには、ビジネス ルールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-126">To work with the sample, set up a business rule.</span></span> <span data-ttu-id="fb7a8-127">メッセージがビジネス ルールに適合すると、受信アクション メッセージが MessagesToLOB テーブルに保存され、Delivered Status が 2 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-127">If the message meets the business rule, then the process saves the incoming action message in the MessagesToLOB table, setting the Delivered Status to 2.</span></span> <span data-ttu-id="fb7a8-128">この要求の確認を生成する必要がないことを基幹業務アプリケーションが認識できるように、[Delivered] 列の値はゼロ以外である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-128">The Delivered column value must be nonzero, so that the line-of-business application knows that it does not have to generate a confirmation for this request.</span></span> <span data-ttu-id="fb7a8-129">次に、3A4 要求メッセージが 3A4 確認メッセージにマップされ、`SubmitRNIF` メソッドを使用して応答が MessageStorageIn テーブルに送信されます。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-129">The process then maps the 3A4 request message to a 3A4 confirmation message, and submits the response to the MessageStorageIn table using the `SubmitRNIF` method.</span></span>  
  
 <span data-ttu-id="fb7a8-130">メッセージがビジネス ルールに適合しない場合、受信アクション メッセージは MessageStorageOut テーブルに保存され、Delivered Status は 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-130">If the message does not meet the business rule, the process saves the incoming action message in the MessageStorageOut table, and sets Delivered Status to 0.</span></span>  
  
 <span data-ttu-id="fb7a8-131">このサンプルには、PIP3A4PrivateResponder.odx のオーケストレーションで使用する送信ポート (PrivateResponder_To_LOB)、受信ポート (LOB_To_PrivateResponder)、および受信場所 (LOB_To_PrivateResponder) を設定するためのバインド ファイル (Binding.xml) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-131">This sample includes a binding file (Binding.xml) that you can use to set up a send port (PrivateResponder_To_LOB), a receive port (LOB_To_PrivateResponder), and a receive location (LOB_To_PrivateResponder) for use with the PIP3A4PrivateResponder.odx orchestration.</span></span> <span data-ttu-id="fb7a8-132">これらのバインドを Binding.xml ファイルにインポートするには、BTSTask コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-132">Use the BTSTask command to import the bindings in the Binding.xml file.</span></span> <span data-ttu-id="fb7a8-133">詳細については、BizTalk Server ヘルプの「ImportBindings コマンド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb7a8-133">For more information, see the "ImportBindings Command" topic in BizTalk Server Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7a8-134">参照</span><span class="sxs-lookup"><span data-stu-id="fb7a8-134">See Also</span></span>  
 <span data-ttu-id="fb7a8-135">[ダブル アクション PIPAutomation オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="fb7a8-135">[Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md) </span></span>  
 <span data-ttu-id="fb7a8-136">[サンプル BTARN ビジネス ポリシー](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span><span class="sxs-lookup"><span data-stu-id="fb7a8-136">[Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span></span>  
 [<span data-ttu-id="fb7a8-137">オーケストレーション サンプル</span><span class="sxs-lookup"><span data-stu-id="fb7a8-137">Orchestration Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)