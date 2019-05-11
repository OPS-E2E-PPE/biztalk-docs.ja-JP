---
title: エラー処理 (BizTalk Server Samples フォルダー) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, errors
- errors, examples
- examples, messages
- messages, examples
- messages, errors
ms.assetid: b39791ed-277b-4625-b9a9-72480a1b6ff6
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfff362d6d12e68ad7c0ef9258cccfd68dff1a0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348197"
---
# <a name="error-handling-biztalk-server-samples-folder"></a><span data-ttu-id="894a7-102">エラー処理 (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="894a7-102">Error Handling (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="894a7-103">このサンプルの目的は、コンテンツ ベースのルーティング (CBR) アプリケーション用のエラー処理機能を構築することです。</span><span class="sxs-lookup"><span data-stu-id="894a7-103">The purpose of this sample is to build an error-handling functionality for the content-based routing (CBR) application.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="894a7-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="894a7-104">Prerequisites</span></span>  
 <span data-ttu-id="894a7-105">サンプルを実行するには、または後でインストールした Microsoft Office InfoPath 2010 をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="894a7-105">To run the sample, it is recommended that you have Microsoft Office InfoPath 2010 or later installed.</span></span> <span data-ttu-id="894a7-106">InfoPath を使用せずにサンプルを実行することもできますが、その場合、経費報告書の内容および HTTP アダプターを経由した経費報告書の送信は確認できません。</span><span class="sxs-lookup"><span data-stu-id="894a7-106">You can run the sample without using InfoPath, but in that case you cannot see the expense reports and the submission of expense reports through the HTTP adapter.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="894a7-107">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="894a7-107">What This Sample Does</span></span>  
 <span data-ttu-id="894a7-108">このサンプルは、経費報告書処理システムの一部を実装します。</span><span class="sxs-lookup"><span data-stu-id="894a7-108">The sample implements part of an expense report processing system.</span></span> <span data-ttu-id="894a7-109">具体的には、このサンプルは以下の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="894a7-109">Specifically, this sample does the following:</span></span>  

1. <span data-ttu-id="894a7-110">経費報告書に関する情報を含む経費報告書のスキーマおよび部門名を含む個々の送信者を定義します。</span><span class="sxs-lookup"><span data-stu-id="894a7-110">Defines an expense report schema containing information about an expense report and the individual submitter including department name.</span></span>  

2. <span data-ttu-id="894a7-111">ディレクトリを経由した、または InfoPath を使用する Web サービスを経由した経費報告書の送信を可能にします。</span><span class="sxs-lookup"><span data-stu-id="894a7-111">Provides for the submission of the expense report through a directory or through a Web service using InfoPath.</span></span>  

3. <span data-ttu-id="894a7-112">昇格、**部門**と**correlationID**ルーティングを制御するポート フィルタで使用できるように、メッセージのプロパティを文書化します。</span><span class="sxs-lookup"><span data-stu-id="894a7-112">Promotes the **Department** and **correlationID** properties in the message document so that it can be used in a port filter to control routing.</span></span>  

4. <span data-ttu-id="894a7-113">マーケティング部門に属する経費報告書をディレクトリ内のファイルにルーティングし、この部門のバックエンド システムへの配信をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="894a7-113">Routes expense reports belonging to the Marketing department to a file in a directory, simulating delivery to the department's back-end system.</span></span>  

5. <span data-ttu-id="894a7-114">マーケティング以外の部門に属する経費報告書について失敗したメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="894a7-114">Generates a failed message for expense reports belonging to departments other than Marketing.</span></span> <span data-ttu-id="894a7-115">失敗したメッセージには、エラー コードやエラーの説明など、エラーに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="894a7-115">The failed message includes information about the error including error code and error description.</span></span>  

6. <span data-ttu-id="894a7-116">失敗したメッセージを、手動で修正および再送信されるように、受信者 (ビジネス ユーザーまたはアプリケーション オペレーター) にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="894a7-116">Routes failed messages to a human recipient (a business user or application operator) for correction and resubmission.</span></span>  

7. <span data-ttu-id="894a7-117">再送信された経費報告書を前述の部門に基づいてルーティングします。</span><span class="sxs-lookup"><span data-stu-id="894a7-117">Routes resubmitted expense reports based on department as described above.</span></span>  

   <span data-ttu-id="894a7-118">この作業の多くは BizTalk のオーケストレーション スケジュールによって行われます。</span><span class="sxs-lookup"><span data-stu-id="894a7-118">Much of this work is done through a BizTalk orchestration schedule.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="894a7-119">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="894a7-119">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="894a7-120">このデザインでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内の既定の送受信 XML パイプライン、プロパティの昇格、サブスクリプション フィルター、およびオーケストレーション スケジュールを使用して、メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="894a7-120">The design relies on the default send and receive XML pipelines, property promotion, subscription filters, and orchestration schedules within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to route messages.</span></span> <span data-ttu-id="894a7-121">デザイン要素とその選択理由を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="894a7-121">Design elements and their justification are listed in the following table.</span></span>  


|         <span data-ttu-id="894a7-122">デザイン要素</span><span class="sxs-lookup"><span data-stu-id="894a7-122">Design element</span></span>         |                                                                                                                                                                 <span data-ttu-id="894a7-123">選択理由</span><span class="sxs-lookup"><span data-stu-id="894a7-123">Reason(s) selected</span></span>                                                                                                                                                                 |
|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="894a7-124">既定の XML 受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="894a7-124">Default XML receive pipeline</span></span>  |                                                        <span data-ttu-id="894a7-125">-XMLReceive パイプラインには、プロパティの昇格がサポートしていますPassThruReceive パイプラインは提供されません。</span><span class="sxs-lookup"><span data-stu-id="894a7-125">-   The XMLReceive pipeline supports property promotion; the PassThruReceive pipeline does not.</span></span><br /><span data-ttu-id="894a7-126">-受信メッセージは既に XML 形式で、基本の逆アセンブリとパーティの解決以外の処理は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="894a7-126">-   The inbound message is already in XML format and does not require processing beyond basic disassembly and party resolution.</span></span>                                                        |
|  <span data-ttu-id="894a7-127">失敗したメッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="894a7-127">Routing for failed messages</span></span>   | <span data-ttu-id="894a7-128">受信ポートは、失敗したメッセージを中断し、既定では、否定受信確認応答を生成します。</span><span class="sxs-lookup"><span data-stu-id="894a7-128">-   Receive ports suspend failed messages and generate a negative acknowledgment by default.</span></span> <span data-ttu-id="894a7-129">ルーティングが有効の場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は処理に失敗したメッセージを、別の受信ポートやオーケストレーション スケジュールなど、メッセージをサブスクライブするアプリケーションにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="894a7-129">When routing is enabled [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] attempts to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span> |
|       <span data-ttu-id="894a7-130">プロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="894a7-130">Property promotion</span></span>       |                                                                                                   <span data-ttu-id="894a7-131">-BizTalk Server は、ルーティングを実行するフィールドをプロパティに依存します。</span><span class="sxs-lookup"><span data-stu-id="894a7-131">-   BizTalk Server depends upon property fields to do routing.</span></span> <span data-ttu-id="894a7-132">識別フィールドはオーケストレーションによって使用されるため、ルーティングには使用できません。</span><span class="sxs-lookup"><span data-stu-id="894a7-132">Distinguished fields are used by orchestrations and cannot be used for routing.</span></span>                                                                                                   |
|      <span data-ttu-id="894a7-133">サブスクリプション フィルター</span><span class="sxs-lookup"><span data-stu-id="894a7-133">Subscription filter</span></span>       |                                                                                                          <span data-ttu-id="894a7-134">-サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャすることでルーティングを実行します。</span><span class="sxs-lookup"><span data-stu-id="894a7-134">-   The subscription filter performs the routing by capturing messages that meet one or more criteria based on property fields.</span></span>                                                                                                           |
| <span data-ttu-id="894a7-135">BizTalk オーケストレーション スケジュール</span><span class="sxs-lookup"><span data-stu-id="894a7-135">BizTalk orchestration schedule</span></span> |                                                                  <span data-ttu-id="894a7-136">-失敗したメッセージに情報を追加する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="894a7-136">-   Provides the opportunity to add information to failed messages.</span></span><br /><span data-ttu-id="894a7-137">-人間の介入は専用の場所に失敗したメッセージのルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="894a7-137">-   Enables routing of failed messages to a dedicated location for human intervention.</span></span><br /><span data-ttu-id="894a7-138">-プロセスは、経費報告書を再送信します。</span><span class="sxs-lookup"><span data-stu-id="894a7-138">-   Processes resubmitted expense reports.</span></span>                                                                   |
|          <span data-ttu-id="894a7-139">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="894a7-139">XMLTransmit</span></span>           |                                                                                                                <span data-ttu-id="894a7-140">-送信 XML メッセージの基本的なアセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="894a7-140">-   Performs basic assembly of outgoing XML messages.</span></span> <span data-ttu-id="894a7-141">PassThruTransmit パイプラインでは追加のサポートは行われません。</span><span class="sxs-lookup"><span data-stu-id="894a7-141">The PassThruTransmit pipeline provides no additional support.</span></span>                                                                                                                 |

## <a name="where-to-find-this-sample"></a><span data-ttu-id="894a7-142">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="894a7-142">Where to Find This Sample</span></span>  
 <span data-ttu-id="894a7-143">このサンプルは <`Samples Path>`\Messaging\ErrorHandling\\します。</span><span class="sxs-lookup"><span data-stu-id="894a7-143">This sample is located at <`Samples Path>`\Messaging\ErrorHandling\\.</span></span>  

 <span data-ttu-id="894a7-144">次の表には、このサンプルのファイルの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="894a7-144">The following table contains a list of files for this sample.</span></span>  

|<span data-ttu-id="894a7-145">ファイル</span><span class="sxs-lookup"><span data-stu-id="894a7-145">File</span></span>|<span data-ttu-id="894a7-146">説明</span><span class="sxs-lookup"><span data-stu-id="894a7-146">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="894a7-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="894a7-147">Cleanup.bat</span></span>|<span data-ttu-id="894a7-148">アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="894a7-148">Used to undeploy assemblies and remove them from the global assembly cache.</span></span><br /><br /> <span data-ttu-id="894a7-149">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="894a7-149">Removes send and receive ports.</span></span><br /><br /> <span data-ttu-id="894a7-150">必要に応じて、インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="894a7-150">Removes Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="894a7-151">ErrorHandling.sln</span><span class="sxs-lookup"><span data-stu-id="894a7-151">ErrorHandling.sln</span></span>|<span data-ttu-id="894a7-152">サンプルの Visual Studio ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="894a7-152">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="894a7-153">ErrorHandlingBinding.xml</span><span class="sxs-lookup"><span data-stu-id="894a7-153">ErrorHandlingBinding.xml</span></span>|<span data-ttu-id="894a7-154">サンプルのバインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="894a7-154">Binding file for the sample.</span></span>|  
|<span data-ttu-id="894a7-155">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="894a7-155">Setup.bat</span></span>|<span data-ttu-id="894a7-156">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="894a7-156">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="894a7-157">Expense Report – John Doe.xml</span><span class="sxs-lookup"><span data-stu-id="894a7-157">Expense Report – John Doe.xml</span></span>|<span data-ttu-id="894a7-158">経費報告書の InfoPath ドキュメント例です。</span><span class="sxs-lookup"><span data-stu-id="894a7-158">Example expense report InfoPath document.</span></span>|  
|<span data-ttu-id="894a7-159">Invalid Expense Report – John Doe.xml</span><span class="sxs-lookup"><span data-stu-id="894a7-159">Invalid Expense Report – John Doe.xml</span></span>|<span data-ttu-id="894a7-160">無効なデータを含む経費報告書の InfoPath ドキュメント例です。</span><span class="sxs-lookup"><span data-stu-id="894a7-160">Example expense report InfoPath document with invalid data in it.</span></span>|  
|<span data-ttu-id="894a7-161">ErrorHandler フォルダー内 : </span><span class="sxs-lookup"><span data-stu-id="894a7-161">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="894a7-162">ErrorHandler.btproj</span><span class="sxs-lookup"><span data-stu-id="894a7-162">ErrorHandler.btproj</span></span>|<span data-ttu-id="894a7-163">オーケストレーションの BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="894a7-163">BizTalk project for orchestration.</span></span>|  
|<span data-ttu-id="894a7-164">ErrorHandler フォルダー内 : </span><span class="sxs-lookup"><span data-stu-id="894a7-164">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="894a7-165">ResubmitLogic.odx</span><span class="sxs-lookup"><span data-stu-id="894a7-165">ResubmitLogic.odx</span></span>|<span data-ttu-id="894a7-166">失敗したメッセージをサブスクライブし、手動で修正できるように受信者に送信し、修正されたメッセージをルーティングするためにサーバーに再送信するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="894a7-166">Orchestration that subscribes to failed messages, sends them to the human recipient for correction, and then resubmits corrected messages back into the server for routing.</span></span>|  
|<span data-ttu-id="894a7-167">ErrorHandler フォルダー内 : </span><span class="sxs-lookup"><span data-stu-id="894a7-167">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="894a7-168">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="894a7-168">SuspendMessage.odx</span></span>|<span data-ttu-id="894a7-169">エラー処理オーケストレーション内で処理できない中断メッセージに使用するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="894a7-169">Orchestration used for suspending messages that cannot be processed within the error-handling orchestration.</span></span>|  
|<span data-ttu-id="894a7-170">InfoPathForms フォルダー内:</span><span class="sxs-lookup"><span data-stu-id="894a7-170">In InfoPathForms folder:</span></span><br /><br /> <span data-ttu-id="894a7-171">Expense Report.xsn</span><span class="sxs-lookup"><span data-stu-id="894a7-171">Expense Report.xsn</span></span><br /><br /> <span data-ttu-id="894a7-172">Expense Report - Resubmit.xsn</span><span class="sxs-lookup"><span data-stu-id="894a7-172">Expense Report - Resubmit.xsn</span></span>|<span data-ttu-id="894a7-173">経費報告書の InfoPath フォームと、失敗したメッセージの表示と再送信に使用されるフォームです。</span><span class="sxs-lookup"><span data-stu-id="894a7-173">Expense report InfoPath form and form used for viewing and resubmitting failed messages.</span></span>|  
|<span data-ttu-id="894a7-174">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="894a7-174">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="894a7-175">ExpenseReportSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="894a7-175">ExpenseReportSchema.xsd</span></span>|<span data-ttu-id="894a7-176">経費報告ドキュメントの XML スキーマです。</span><span class="sxs-lookup"><span data-stu-id="894a7-176">XML schema for the expense report document.</span></span>|  
|<span data-ttu-id="894a7-177">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="894a7-177">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="894a7-178">PipelinesAndSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="894a7-178">PipelinesAndSchemas.btproj</span></span>|<span data-ttu-id="894a7-179">サンプルの BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="894a7-179">BizTalk project for the sample.</span></span>|  
|<span data-ttu-id="894a7-180">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="894a7-180">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="894a7-181">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="894a7-181">PropertySchema.xsd</span></span>|<span data-ttu-id="894a7-182">サンプルのプロパティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="894a7-182">Property schema for the sample.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="894a7-183">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="894a7-183">How to Use This Sample</span></span>  
 <span data-ttu-id="894a7-184">このサンプルは、独自のエラー処理手順を作成するための開始点として使用できます。</span><span class="sxs-lookup"><span data-stu-id="894a7-184">This sample provides a starting point for creating your own error handling procedure.</span></span>  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="894a7-185">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="894a7-185">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-compose-sample"></a><span data-ttu-id="894a7-186">Compose サンプルをビルドして初期化するには</span><span class="sxs-lookup"><span data-stu-id="894a7-186">To build and initialize the Compose sample</span></span>  

1. <span data-ttu-id="894a7-187">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="894a7-187">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="894a7-188"><`Samples Path`>**\Messaging\ErrorHandling**</span><span class="sxs-lookup"><span data-stu-id="894a7-188"><`Samples Path`>**\Messaging\ErrorHandling**</span></span>  

2. <span data-ttu-id="894a7-189">実行**Setup.bat**、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="894a7-189">Run **Setup.bat**, which performs the following actions:</span></span>  

   - <span data-ttu-id="894a7-190">3 つのフォルダーを作成します。**ExpenseReportIn**、 **ExpenseReportOut**、および**ResubmittedReportIn**次のパス。</span><span class="sxs-lookup"><span data-stu-id="894a7-190">Creates three folders: **ExpenseReportIn**, **ExpenseReportOut**, and **ResubmittedReportIn** under the following path:</span></span>  

      <span data-ttu-id="894a7-191"><`Samples Path`>**\Messaging\ErrorHandling**</span><span class="sxs-lookup"><span data-stu-id="894a7-191"><`Samples Path`>**\Messaging\ErrorHandling**</span></span>  

   - <span data-ttu-id="894a7-192">コピーし、InfoPath フォームを公開**Expense Report.xsn**と**Expense Report – Resubmit.xsn**フォルダーに**C:\Temp\InfoPathForms**します。</span><span class="sxs-lookup"><span data-stu-id="894a7-192">Copies and publishes the InfoPath forms **Expense Report.xsn** and **Expense Report – Resubmit.xsn** into the folder **C:\Temp\InfoPathForms**.</span></span>  

   - <span data-ttu-id="894a7-193">このサンプル用の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="894a7-193">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  

   - <span data-ttu-id="894a7-194">という仮想ディレクトリを作成します。 **ExpenseReports**します。</span><span class="sxs-lookup"><span data-stu-id="894a7-194">Creates a virtual directory called **ExpenseReports**.</span></span>  

   - <span data-ttu-id="894a7-195">呼ばれる新しい BizTalk アプリケーションを作成します。 **Error Handling Sample**し、そこにサンプル アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="894a7-195">Creates a new BizTalk application called **Error Handling Sample** and deploys the sample assemblies into it.</span></span>  

   - <span data-ttu-id="894a7-196">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成してバインドします。</span><span class="sxs-lookup"><span data-stu-id="894a7-196">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive locations, and the send and receive ports.</span></span>  

   - <span data-ttu-id="894a7-197">オーケストレーションを参加させて開始し、受信場所を有効にしてから、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="894a7-197">Enlists and starts orchestrations, enables the receive locations, and starts the send ports.</span></span>  

      <span data-ttu-id="894a7-198">Setup.bat を実行せずに、このサンプルのプロジェクトを開いてビルドする場合は、最初に .NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="894a7-198">If you choose to open and build the projects in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="894a7-199">このキー ペアは、サンプル アセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="894a7-199">Use this key pair to sign the sample assemblies.</span></span>  

3. <span data-ttu-id="894a7-200">このサンプルを実行する前に、ことを確認します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でビルドまたは初期化プロセス中にエラーが報告されません。</span><span class="sxs-lookup"><span data-stu-id="894a7-200">Before attempting to run this sample, confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build or initialization process.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="894a7-201">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="894a7-201">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="894a7-202">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="894a7-202">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

4. <span data-ttu-id="894a7-203">インターネット インフォメーション サービス (IIS) 7.0 を使用している場合は、サンプルが使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の HTTP 受信場所に対応している仮想ディレクトリの設定を調整するために、追加の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="894a7-203">If you are using Internet Information Services (IIS) 7.0, you need to perform additional configuration steps to adjust the setting for the virtual directory that corresponds to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP receive location used by the sample.</span></span> <span data-ttu-id="894a7-204">IIS を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="894a7-204">Configure IIS by doing the following:</span></span>  

   1. <span data-ttu-id="894a7-205">IIS 7.0 マネージャーを使用して、BizTalk 分離ホスト ユーザー グループ用の新しいアプリケーション プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="894a7-205">Using IIS 7.0 Manager, create a new application pool for the BizTalk Isolated Host Users group.</span></span>  

   2. <span data-ttu-id="894a7-206">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 分離ホスト ユーザーの ID で実行するようにアプリケーション プールを構成します</span><span class="sxs-lookup"><span data-stu-id="894a7-206">Configure the application pool to run under the identity of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Isolated Host user.</span></span> <span data-ttu-id="894a7-207">(他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信場所用に構成されているアプリケーション プールがある場合は、この手順を省略できます)。</span><span class="sxs-lookup"><span data-stu-id="894a7-207">(You may skip this step if you already have an application pool configured for other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP receive locations.)</span></span>  

   3. <span data-ttu-id="894a7-208">仮想ディレクトリの構成**ExpenseReport** HTTP の受信前の手順で作成したアプリケーション プールを使用します。</span><span class="sxs-lookup"><span data-stu-id="894a7-208">Configure the virtual directory **ExpenseReport** to use the HTTP receive application pool created in the previous step.</span></span>  

      <span data-ttu-id="894a7-209">BTSHTTPReceive.dll ISAPI 拡張機能用の Web サーバー拡張をまだ作成していない場合は、ここで作成し、そのステータスを [許可] に設定して有効にします。</span><span class="sxs-lookup"><span data-stu-id="894a7-209">If you do not already have a Web server extension for the BTSHTTPReceive.dll ISAPI extension, create and enable it by setting its status to "Allowed".</span></span> <span data-ttu-id="894a7-210">これを行う IIS 7.0 の IIS 管理コンソールを使用して (か直接**管理ツール**またはコンピュータの管理コンソールを使用) 次のようにします。</span><span class="sxs-lookup"><span data-stu-id="894a7-210">You can do this in IIS 7.0 by using the IIS Management console (either directly under **Administrative Tools** or through the Computer Management console) as follows:</span></span>  

   4. <span data-ttu-id="894a7-211">展開、**インターネット インフォメーション サービス マネージャー**ツリー。</span><span class="sxs-lookup"><span data-stu-id="894a7-211">Expand the **Internet Information Services Manager** tree.</span></span>  

   5. <span data-ttu-id="894a7-212">をクリックして、 **Web サービス拡張**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="894a7-212">Click the **Web Service Extensions** folder.</span></span>  

   6. <span data-ttu-id="894a7-213">管理コンソールの右側のウィンドウで次のようにクリックします。**新しい Web サービス拡張機能の追加**します。</span><span class="sxs-lookup"><span data-stu-id="894a7-213">In the right pane of the management console, click **Add a new Web Service extension**.</span></span>  

   7. <span data-ttu-id="894a7-214">**新しい Web サービス拡張**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="894a7-214">In the **New Web Service Extension** dialog box, click **Add**.</span></span>  

   8. <span data-ttu-id="894a7-215">**ファイルの追加**ダイアログ ボックスで、をクリックして**参照**ファイルを選択 <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**、順にクリックします **[ok]**.</span><span class="sxs-lookup"><span data-stu-id="894a7-215">In the **Add file** dialog box, click **Browse** to select the file <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**, and then click **OK**.</span></span>  

   9. <span data-ttu-id="894a7-216">仮想ディレクトリの構成**ExpenseReport**ローカル パスを使用する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive</span><span class="sxs-lookup"><span data-stu-id="894a7-216">Configure the virtual directory **ExpenseReport** to use local path [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive</span></span>  

      <span data-ttu-id="894a7-217">詳細については、次を参照してください。 [IIS の HTTP 受信場所を構成する方法](../core/how-to-configure-iis-for-an-http-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="894a7-217">For more information, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  

## <a name="running-the-sample"></a><span data-ttu-id="894a7-218">サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="894a7-218">Running the Sample</span></span>  
 <span data-ttu-id="894a7-219">正しい経費報告書でサンプルを実行する前に、次の手順に従って、"エラーなし" のケース サンプルが正しく機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="894a7-219">Before running the sample with the correct expense report, use the following procedure to verify that the "no errors" case sample works correctly.</span></span>  

#### <a name="to-verify-that-the-no-errors-case-sample-works-correctly"></a><span data-ttu-id="894a7-220">"エラーなし" のケース サンプルが正しく機能することを確認するには</span><span class="sxs-lookup"><span data-stu-id="894a7-220">To verify that the "no errors" case sample works correctly</span></span>  

1. <span data-ttu-id="894a7-221">InfoPath フォームを開きます**Expense Report - John Doe.xml**します。</span><span class="sxs-lookup"><span data-stu-id="894a7-221">Open the InfoPath form **Expense Report - John Doe.xml**.</span></span> <span data-ttu-id="894a7-222">見て、**部門**フォーム内でフィールド。</span><span class="sxs-lookup"><span data-stu-id="894a7-222">Look at the **Department** field within the form.</span></span> <span data-ttu-id="894a7-223">このフィールドは "Marketing" に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="894a7-223">This field should be set to "Marketing".</span></span>  

2. <span data-ttu-id="894a7-224">InfoPath ウィンドウの左上隅にある次のようにクリックします。**送信** をクリックまたは**経費報告書**します。</span><span class="sxs-lookup"><span data-stu-id="894a7-224">In the upper-left corner of the InfoPath window, click **Submit** or click **Resubmit Expense Report**.</span></span> <span data-ttu-id="894a7-225">経費報告書が正常に送信されたことを示す確認ウィンドウが表示されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="894a7-225">Wait for a confirmation window that says the expense report was successfully submitted.</span></span>  

    <span data-ttu-id="894a7-226">-または-</span><span class="sxs-lookup"><span data-stu-id="894a7-226">-OR-</span></span>  

    <span data-ttu-id="894a7-227">このファイルをコピーして、 **ExpenseReportIn**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="894a7-227">Copy and paste this file into the **ExpenseReportIn** folder.</span></span>  

3. <span data-ttu-id="894a7-228">ドロップされた新しいファイルを表示する必要があります、 **ExpenseReportOut**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="894a7-228">You should see a new file dropped into the **ExpenseReportOut** folder.</span></span> <span data-ttu-id="894a7-229">このファイルは、前の手順で送信された経費報告書レポート フォームと同じです。</span><span class="sxs-lookup"><span data-stu-id="894a7-229">This file is the same expense report form that was submitted during previous steps.</span></span>  

   <span data-ttu-id="894a7-230">"エラーなし" ケースを確認した後、次の手順に従って、正しい経費報告書のサンプルを実行し、エラー処理機能をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="894a7-230">After you confirm the "no errors" case, use the following procedure to run the sample with an incorrect expense report to trigger error-handling functionality.</span></span>  

#### <a name="to-trigger-error-handling"></a><span data-ttu-id="894a7-231">エラー処理をトリガーするには</span><span class="sxs-lookup"><span data-stu-id="894a7-231">To trigger error handling</span></span>  

1. <span data-ttu-id="894a7-232">InfoPath フォームを開きます**Invalid Expense Report - John Doe.xml**します。</span><span class="sxs-lookup"><span data-stu-id="894a7-232">Open the InfoPath form **Invalid Expense Report - John Doe.xml**.</span></span> <span data-ttu-id="894a7-233">見て、**部門**フォーム内でフィールド。</span><span class="sxs-lookup"><span data-stu-id="894a7-233">Look at the **Department** field within the form.</span></span> <span data-ttu-id="894a7-234">このフィールドは、無効な値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="894a7-234">This field is set to some invalid value.</span></span>  

2. <span data-ttu-id="894a7-235">InfoPath ウィンドウの左上隅にある次のようにクリックします。**送信**します。</span><span class="sxs-lookup"><span data-stu-id="894a7-235">In the upper-left corner of the InfoPath window, click **Submit**.</span></span> <span data-ttu-id="894a7-236">経費報告書が正常に送信されたことを示す確認ウィンドウが表示されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="894a7-236">Wait for a confirmation window that says the expense report was successfully submitted.</span></span>  

    <span data-ttu-id="894a7-237">-または-</span><span class="sxs-lookup"><span data-stu-id="894a7-237">-OR-</span></span>  

    <span data-ttu-id="894a7-238">このファイルをコピーして、 **ExpenseReportIn**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="894a7-238">Copy and paste this file into the **ExpenseReportIn** folder.</span></span>  

3. <span data-ttu-id="894a7-239">という新しいファイルを表示する必要があります**ErrorReport_\<**<em>日付</em>_<em>時間</em>**\>.xml** にドロップ**ExpenseReportOut**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="894a7-239">You should see a new file called **ErrorReport_\<**<em>date</em>_<em>time</em>**\>.xml** dropped into the **ExpenseReportOut** folder.</span></span>  

    <span data-ttu-id="894a7-240">このファイルを開き、前の手順で送信された経費報告書の先頭にエラー情報が追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="894a7-240">Open this file and observe that this is the expense report submitted in the previous step but with the error information added at the beginning.</span></span>  

4. <span data-ttu-id="894a7-241">クリックして、誤った部門値を"Marketing"に置き換えます**送信**InfoPath ウィンドウの左上隅にあります。</span><span class="sxs-lookup"><span data-stu-id="894a7-241">Replace the erroneous department value with "Marketing", and then click **Submit** in the upper-left corner of the InfoPath window.</span></span>  

    <span data-ttu-id="894a7-242">-または-</span><span class="sxs-lookup"><span data-stu-id="894a7-242">-OR-</span></span>  

    <span data-ttu-id="894a7-243">このファイルをコピーして、 **ResubmittedReportIn**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="894a7-243">Copy and paste this file into the **ResubmittedReportIn** folder.</span></span>  

5. <span data-ttu-id="894a7-244">作成した新しいファイルを表示する必要があります、 **ExpenseReportOut**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="894a7-244">You should see a new file created in the **ExpenseReportOut** folder.</span></span> <span data-ttu-id="894a7-245">このファイルが、サーバーに再送信された修正済みの費用報告書です。</span><span class="sxs-lookup"><span data-stu-id="894a7-245">This file is the corrected expense report that was resubmitted into the server.</span></span>  

## <a name="see-also"></a><span data-ttu-id="894a7-246">参照</span><span class="sxs-lookup"><span data-stu-id="894a7-246">See Also</span></span>  
 <span data-ttu-id="894a7-247">[失敗したメッセージのルーティングを使用します。](../core/using-failed-message-routing.md) </span><span class="sxs-lookup"><span data-stu-id="894a7-247">[Using Failed Message Routing](../core/using-failed-message-routing.md) </span></span>  
 [<span data-ttu-id="894a7-248">Messaging (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="894a7-248">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)