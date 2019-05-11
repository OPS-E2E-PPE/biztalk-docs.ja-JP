---
title: ダブル アクション PIPAutomation オーケストレーション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9159f7b1-cb83-41f1-8637-39c5ddcc63ae
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 830846dd25bef7748fb6bcf77a112c03c3a152ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283741"
---
# <a name="double-action-pipautomation-orchestration"></a><span data-ttu-id="dcd34-102">ダブル アクション PIPAutomation オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="dcd34-102">Double Action PIPAutomation Orchestration</span></span>
<span data-ttu-id="dcd34-103">DoubleAction.odx サンプルは、ダブル アクションの Partner Interface Process (Pip) の応答を自動的に生成するためのオーケストレーションを実装する方法を示しています。 0c2、0 C 4、3 a 2、3A4 とします。</span><span class="sxs-lookup"><span data-stu-id="dcd34-103">The DoubleAction.odx sample illustrates how to implement an orchestration to automatically generate responses for the double-action Partner Interface Processes (PIPs) 0C2, 0C4, 3A2, and 3A4.</span></span> <span data-ttu-id="dcd34-104">追加のダブル アクション Pip をサポートするには、このサンプル プロジェクトを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-104">You can extend this sample project to support additional double-action PIPs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcd34-105">サンプル フォルダーに用意されているマップはサンプルです。</span><span class="sxs-lookup"><span data-stu-id="dcd34-105">The maps provided in the sample folder are samples.</span></span> <span data-ttu-id="dcd34-106">これらを使用するには、特定の要件に基づいてそれらを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd34-106">To use them, you must change them based on your specific requirements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcd34-107">ダブル アクション Pip のみ、いないシングル アクション Pip をサポートするには、このサンプル プロジェクトを拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd34-107">You should extend this sample project to support double-action PIPs only, not single-action PIPs.</span></span> <span data-ttu-id="dcd34-108">シングル アクション PIP を処理するように拡張する場合、このオーケストレーションはエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-108">This orchestration will return an error if you extend it to process a single-action PIP.</span></span> <span data-ttu-id="dcd34-109">このオーケストレーションがシングル アクション Pip を処理しないことを確認するには、後述の「シングル アクション メッセージをフィルター処理を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcd34-109">To ensure that this orchestration will not process single-action PIPs, see the Filtering Out Single-Action Messages section below.</span></span>  
  
 <span data-ttu-id="dcd34-110">既定では、Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]セットアップ プログラムによってこのサンプルで\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-110">By default, the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Setup program installs this sample in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction.</span></span>  
  
 <span data-ttu-id="dcd34-111">このサンプル プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-111">This sample project includes:</span></span>  
  
- <span data-ttu-id="dcd34-112">ストアド プロシージャ (`PipAutomationGetAction)`メッセージを取得する新しいアクション Pip の 0c2、0 C 4、3 a 2、および 3A4 します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-112">A stored procedure (`PipAutomationGetAction)` to retrieve new action messages for the PIPs 0C2, 0C4, 3A2, and 3A4.</span></span>  
  
- <span data-ttu-id="dcd34-113">受信場所 (MessagesToLOB_Receive_Location) は、SQL ストアド プロシージャにバインドします。</span><span class="sxs-lookup"><span data-stu-id="dcd34-113">A receive location (MessagesToLOB_Receive_Location) bound to the SQL stored procedure.</span></span>  
  
- <span data-ttu-id="dcd34-114">各 PIP を処理するオーケストレーション (DoubleAction.odx) は、各 PIP のマップに基づく適切な応答を生成し、応答を BTARNDATA データベースの MessagesFromLOB テーブルに保存します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-114">An orchestration (DoubleAction.odx) that processes each PIP, generates the appropriate response based on a map for each PIP, and saves the response in the MessagesFromLOB table of the BTARNDATA database.</span></span> <span data-ttu-id="dcd34-115">オーケストレーションを使用して、`RNIFSubmit`メッセージを送信する Microsoft.Solutions.BTARN.Shared.dll からメソッド。</span><span class="sxs-lookup"><span data-stu-id="dcd34-115">The orchestration uses the `RNIFSubmit` method from Microsoft.Solutions.BTARN.Shared.dll to submit the message.</span></span>  
  
- <span data-ttu-id="dcd34-116">Setup.bat ファイルは DoubleAction オーケストレーションで使用する MessagesToLOB_Receive_Port の作成を使用してバインド ファイル (DoubleActionBinding.xml)。</span><span class="sxs-lookup"><span data-stu-id="dcd34-116">A binding file (DoubleActionBinding.xml) that the file Setup.bat uses to create the MessagesToLOB_Receive_Port for use with the DoubleAction orchestration.</span></span>  
  
- <span data-ttu-id="dcd34-117">セットアップ ファイル、サンプルをビルドして初期化します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-117">A setup file to build and initialize the sample.</span></span> <span data-ttu-id="dcd34-118">BizTalk Server が 32 ビット コンピューターで実行している場合は、setup.bat ファイルを実行、\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet \SDK\PIPAutomation\DoubleAction フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-118">If BizTalk Server is running on a 32-bit computer, run the file setup.bat in the \<drive\>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet \SDK\PIPAutomation\DoubleAction folder.</span></span> <span data-ttu-id="dcd34-119">BizTalk Server が 64 ビット コンピューターで実行している場合は、同じフォルダーにある setupx64.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-119">If BizTalk Server is running on a 64-bit computer, run setupx64.bat in the same folder.</span></span>  
  
  <span data-ttu-id="dcd34-120">オーケストレーションでは、(ソース ファイルは、DoubleAction ディレクトリ内の DoubleAction.sql が)、BTARNData データベースの PipAutomationGetAction ストアド プロシージャを使用してメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-120">The orchestration receives messages using the PipAutomationGetAction stored procedure in the BTARNData database (the source file is DoubleAction.sql in the DoubleAction directory).</span></span> <span data-ttu-id="dcd34-121">このストアド プロシージャは MessagesToLOB テーブルからメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-121">This stored procedure retrieves the messages from the MessagesToLOB table.</span></span>  
  
  <span data-ttu-id="dcd34-122">追加のダブル アクション Pip をサポートするには、このサンプル プロジェクトを拡張するには、ダブル アクション PIP のオーケストレーションで、パスを追加します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-122">To extend this sample project to support additional double-action PIPs, add a path in the orchestration for the double-action PIP.</span></span> <span data-ttu-id="dcd34-123">このパスは、要求メッセージに対する応答メッセージを構成するマップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-123">This path will include a map that will construct a respond message to a request message.</span></span> <span data-ttu-id="dcd34-124">たとえば、マップを参照してください、 [3 a 2 応答のマップ サンプルを 3 a 2 要求](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)と[3A4 要求から 3A4 応答のマップ サンプルへ&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-124">For example maps, see the [3A2 Request to 3A2 Response Map Sample](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md) and the [3A4 Request to 3A4 Response Map Sample &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md).</span></span>  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="dcd34-125">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="dcd34-125">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="dcd34-126">コマンド プロンプトで、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction フォルダー。</span><span class="sxs-lookup"><span data-stu-id="dcd34-126">At a command prompt, locate the *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction folder.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="dcd34-127">セットアップ プログラムを実行する前にメモ帳で DoubleAction.sql (上記のフォルダー) 内のファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-127">Before running the Setup program, open the file DoubleAction.sql (in the above folder) in Notepad.</span></span> <span data-ttu-id="dcd34-128">**ファイル** メニューのをクリックして**付けて**します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-128">On the **File** menu, click **Save As**.</span></span> <span data-ttu-id="dcd34-129">**エンコード**一覧で、[ **ANSI**、] をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-129">In the **Encoding** list, select **ANSI**, and then click **Save**.</span></span> <span data-ttu-id="dcd34-130">をクリックして**はい**既存のファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="dcd34-130">Click **Yes** to overwrite the existing file.</span></span>  
  
2. <span data-ttu-id="dcd34-131">BizTalk Server が 32 ビット コンピューターで実行している場合は、setup.bat ファイルを実行、\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction フォルダー。</span><span class="sxs-lookup"><span data-stu-id="dcd34-131">If your BizTalk Server is running on a 32-bit computer, run the file setup.bat in the \<drive\>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction folder.</span></span> <span data-ttu-id="dcd34-132">BizTalk Server のインストールが 64 ビット コンピューターで実行している場合は、同じフォルダーに setupx64.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-132">If your BizTalk Server installation is running on a 64-bit computer, run setupx64.bat in the same folder.</span></span> <span data-ttu-id="dcd34-133">バッチ ファイルでは、次の操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-133">The batch file will perform the following actions:</span></span>  
  
   - <span data-ttu-id="dcd34-134">SQL ストアド プロシージャを作成します (`PipAutomationGetAction`)、アクション メッセージを MessagesToLOB テーブルから取得する、BTARNDATA データベースです。</span><span class="sxs-lookup"><span data-stu-id="dcd34-134">Creates a SQL stored procedure (`PipAutomationGetAction`) in the BTARNDATA database to retrieve the action message from the MessagesToLOB table.</span></span> <span data-ttu-id="dcd34-135">こう取得したレコードは再び読み取られます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-135">This also ensures that the retrieved records will not be read again.</span></span>  
  
   - <span data-ttu-id="dcd34-136">コンパイル、HeaderHelper[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]プロジェクトし、グローバル アセンブリ キャッシュにアセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-136">Compiles the HeaderHelper [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] project and registers the assembly in the global assembly cache.</span></span>  
  
   - <span data-ttu-id="dcd34-137">作成し、バインド、BizTalk Server SQL 受信ポート (MessagesToLOB_Receive_Port)。</span><span class="sxs-lookup"><span data-stu-id="dcd34-137">Creates and binds the BizTalk Server SQL receive port (MessagesToLOB_Receive_Port).</span></span>  
  
   - <span data-ttu-id="dcd34-138">受信場所 (MessagesToLOB_Receive_Location) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dcd34-138">Enables the receive location (MessagesToLOB_Receive_Location).</span></span>  
  
   - <span data-ttu-id="dcd34-139">コンパイルし、ダブル アクション PIPAutomation オーケストレーション (DoubleAction.odx) を展開します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-139">Compiles and deploys the Double-Action PIPAutomation Orchestration (DoubleAction.odx).</span></span>  
  
   - <span data-ttu-id="dcd34-140">バインドし、BizTalk Server オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-140">Binds and starts the BizTalk Server orchestration.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="dcd34-141">サンプルでは、コンパイル中にいくつかの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-141">The sample displays some warnings while compiling.</span></span> <span data-ttu-id="dcd34-142">これらの警告を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-142">You can ignore these warnings.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="dcd34-143">サンプルが既定のホスト名を使用して**BizTalkServerApplication**プロジェクトをデプロイするときにします。</span><span class="sxs-lookup"><span data-stu-id="dcd34-143">The sample uses the default host name **BizTalkServerApplication** when deploying the project.</span></span> <span data-ttu-id="dcd34-144">別のホストのサンプルを実行するには、下の DoubleActionBinding.xml で既定のホスト名を編集する必要があります\<SDK\>\PIPAutomation\DoubleAction フォルダ。</span><span class="sxs-lookup"><span data-stu-id="dcd34-144">If you would like to run the sample under a different host, you will need to edit the default host names found in DoubleActionBinding.xml under \<SDK\>\PIPAutomation\DoubleAction folder.</span></span>  
  
### <a name="to-run-the-double-action-pipautomation-sample"></a><span data-ttu-id="dcd34-145">ダブル アクション PIPAutomation サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="dcd34-145">To run the Double-Action PIPAutomation sample</span></span>  
  
1. <span data-ttu-id="dcd34-146">ホーム ロールがイニシエーターが 3A4 アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-146">Create a 3A4 agreement where the home role is an initiator.</span></span> <span data-ttu-id="dcd34-147">ホーム組織の GBI を 123456789 に設定し、GBI を 987654321 にパートナーを設定します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-147">Set the GBI for the home organization to 123456789, and set the GBI for the partner to 987654321.</span></span> <span data-ttu-id="dcd34-148">これにより、SDK の LOBApplication フォルダー下の SampleInstances フォルダーにサンプルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-148">This lets you use the samples provided in the SampleInstances folder under the LOBApplication folder in the SDK.</span></span>  
  
2. <span data-ttu-id="dcd34-149">Loopback アグリーメント ミラー ユーティリティを使用して、手順 1. で作成した 3A4 PIP のミラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-149">Using the Loopback agreement-mirroring utility, create a mirror for the 3A4 PIP created in step 1.</span></span>  
  
3. <span data-ttu-id="dcd34-150">LOBApplication.exe SDK ユーティリティを使用して、3A4 PIP 要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-150">Using the LOBApplication.exe SDK utility, submit a 3A4 PIP Request message.</span></span> <span data-ttu-id="dcd34-151">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK にはフォルダーに入力のサンプルが含まれています\<*インストール ディレクトリ*\>\SDK\LOBApplication\SampleInstances\3A4_Request.xml します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-151">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes an input sample in the folder \<*Installation Directory*\>\SDK\LOBApplication\SampleInstances\3A4_Request.xml.</span></span>  
  
4. <span data-ttu-id="dcd34-152">BTARNDATA データベースでは、次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-152">Run the following query on the BTARNDATA database:</span></span>  
  
   ```  
   Select * from MessagesToLOB  
   ```  
  
5. <span data-ttu-id="dcd34-153">数秒後は、このテーブルに 4 つの新しいメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-153">After several seconds, four new messages appear in this table.</span></span> <span data-ttu-id="dcd34-154">そのうち 2 つは、受信確認シグナルです。</span><span class="sxs-lookup"><span data-stu-id="dcd34-154">Two of them are acknowledgment signals.</span></span> <span data-ttu-id="dcd34-155">1 つのシグナルは Async 3A4 要求メッセージです。</span><span class="sxs-lookup"><span data-stu-id="dcd34-155">One signal is the Async 3A4 Request Message.</span></span> <span data-ttu-id="dcd34-156">1 つのシグナルは Async 3A4 応答メッセージです。</span><span class="sxs-lookup"><span data-stu-id="dcd34-156">One signal is the Async 3A4 Response Message.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="dcd34-157">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-157">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="dcd34-158">Setup.bat を再度実行する前に Cleanup.bat を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd34-158">You must run Cleanup.bat before running Setup.bat again.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcd34-159">コメント</span><span class="sxs-lookup"><span data-stu-id="dcd34-159">Remarks</span></span>  
 <span data-ttu-id="dcd34-160">パブリック オーケストレーションでは、受信確認 (ACK および NACK シグナル メッセージ) が自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-160">The public orchestration automatically generates acknowledgments (ACK and NACK signal messages).</span></span> <span data-ttu-id="dcd34-161">基幹業務 (LOB) アプリケーションは、それらを生成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dcd34-161">The line-of-business (LOB) application does not need to generate them.</span></span>  
  
 <span data-ttu-id="dcd34-162">MessagesFromLOB テーブルにルーティングされるメッセージの形式を lobmessage と呼びます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-162">The format of the message that is routed to the MessagesFromLOB table is called LOBMessage.</span></span> <span data-ttu-id="dcd34-163">スキーマは、C:\Program files \microsoft BizTalk Accelerator RosettaNet\SDK\RNIFSchemas\GlobalSchemas\LOBMessage.xsd for で使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-163">The schema is available in C:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\RNIFSchemas\GlobalSchemas\LOBMessage.xsd.</span></span> <span data-ttu-id="dcd34-164">使用する場合、`RNIFSubmit`メソッドがありません、メッセージの形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-164">If you use the `RNIFSubmit` method, you do not have to work with the message format.</span></span> <span data-ttu-id="dcd34-165">のみ、ServiceContent に追加情報を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd34-165">You only need to submit the ServiceContent with the additional information.</span></span> <span data-ttu-id="dcd34-166">`RNIFSubmit` MessagesFromLOB テーブルにレコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-166">`RNIFSubmit` populates the record in the MessagesFromLOB table.</span></span>  
  
## <a name="filtering-out-single-action-messages"></a><span data-ttu-id="dcd34-167">シングル アクション メッセージをフィルター処理</span><span class="sxs-lookup"><span data-stu-id="dcd34-167">Filtering Out Single-Action Messages</span></span>  
 <span data-ttu-id="dcd34-168">このオーケストレーションはダブル アクション メッセージのみを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd34-168">This orchestration should receive only double-action messages.</span></span> <span data-ttu-id="dcd34-169">シングル アクション Pip をサポートするには、このサンプル プロジェクトを拡張する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="dcd34-169">You should not extend this sample project to support single-action PIPs.</span></span> <span data-ttu-id="dcd34-170">このオーケストレーションを使用して、シングル アクション メッセージを処理する場合は、BTARN によってエラーが通知されます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-170">BTARN will post errors if you use this orchestration to process single-action messages.</span></span> <span data-ttu-id="dcd34-171">シングル アクション メッセージの受信からオーケストレーションを防ぐためには、PIPAutomationGetAction ストアド プロシージャに次の行を変更します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-171">In order to prevent the orchestration from receiving a single-action message, change the following line in the PIPAutomationGetAction stored procedure:</span></span>  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB  
```  
  
 <span data-ttu-id="dcd34-172">上記の行には、シングル アクション メッセージをフィルター処理する WHERE 句を追加します。</span><span class="sxs-lookup"><span data-stu-id="dcd34-172">To the above line, add a WHERE clause that will filter out single-action messages.</span></span> <span data-ttu-id="dcd34-173">すべてのシングル アクション メッセージ処理するには WHERE 句が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dcd34-173">Include in the WHERE clause all the single-action messages that you will be processing.</span></span> <span data-ttu-id="dcd34-174">行は、次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd34-174">The line should be as follows:</span></span>  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB WHERE PIPCode NOT IN ( '0A1', '3B2', '3C3', '0C1', '0C3' )  
```  
  
## <a name="see-also"></a><span data-ttu-id="dcd34-175">参照</span><span class="sxs-lookup"><span data-stu-id="dcd34-175">See Also</span></span>  
 <span data-ttu-id="dcd34-176">[3 a 2 要求を 3 a 2 応答のマップ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md) </span><span class="sxs-lookup"><span data-stu-id="dcd34-176">[3A2 Request to 3A2 Response Map Sample](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md) </span></span>  
 <span data-ttu-id="dcd34-177">[3A4 要求から 3A4 応答のマップ サンプルへ](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md) </span><span class="sxs-lookup"><span data-stu-id="dcd34-177">[3A4 Request to 3A4 Response Map Sample](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md) </span></span>  
 [<span data-ttu-id="dcd34-178">オーケストレーション サンプル</span><span class="sxs-lookup"><span data-stu-id="dcd34-178">Orchestration Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)