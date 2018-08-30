---
title: 'チュートリアル: フラット ファイル逆アセンブリのヘッダーとトレーラーを使用して |Microsoft Docs'
description: フラット ファイル スキーマ ウィザードを使用してヘッダー スキーマ、トレーラー スキーマ、および本文のスキーマを作成し、BizTalk Server でのフラット ファイル逆アセンブル
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715af9cc-d718-483d-b593-64462aa5a58b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a39361e4da6dec9acf023911466f07572a3de13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983915"
---
# <a name="walkthrough-flat-file-disassembly-using-a-header-and-trailer"></a><span data-ttu-id="b096c-103">ヘッダーとトレーラーを使用してチュートリアル: フラット ファイル逆アセンブリ</span><span class="sxs-lookup"><span data-stu-id="b096c-103">Walkthrough: Flat File Disassembly Using a Header and Trailer</span></span>

## <a name="overview"></a><span data-ttu-id="b096c-104">概要</span><span class="sxs-lookup"><span data-stu-id="b096c-104">Overview</span></span>
<span data-ttu-id="b096c-105">このチュートリアルでは、フラット ファイル スキーマ ウィザードによって作成されたスキーマを使用して、ヘッダー、トレーラー、および繰り返しのメッセージ ボディを含んでいるファイルのフラット ファイル逆アセンブリを実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="b096c-105">This walkthrough demonstrates the use of schemas created by the Flat File Schema Wizard to perform flat file disassembly of a file containing a header, a trailer, and a repeating message body.</span></span> <span data-ttu-id="b096c-106">このチュートリアルでは、次の要件を満たす架空のエラー追跡システムの一部を開発します。</span><span class="sxs-lookup"><span data-stu-id="b096c-106">In this walkthrough, you develop part of a fictitious error-tracking system that meets the following requirements:</span></span>  
  
- <span data-ttu-id="b096c-107">エラー メッセージは社内のさまざまな物理的な場所でログに記録され、集中管理された場所に送信されて、さまざまなバックエンド システムに振り分けられます。</span><span class="sxs-lookup"><span data-stu-id="b096c-107">Error messages are logged at various physical sites within the company and sent to a central location for processing into various back-end systems.</span></span>  
  
- <span data-ttu-id="b096c-108">エラー メッセージは、場所を示すヘッダー、1 つ以上のエラー メッセージを含むボディ、およびバッチ数を示すトレーラーを含んだフラット ファイル形式で書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b096c-108">Error messages are written into a flat file format that contains a header indicating location, a body containing one or more error messages, and a trailer indicating the batch number.</span></span>  
  
- <span data-ttu-id="b096c-109">メッセージは、ヘッダー、ボディ、トレーラーを含んでいない場合、無効と見なされます。</span><span class="sxs-lookup"><span data-stu-id="b096c-109">Messages are considered invalid if they do not have a header, body, and trailer.</span></span>  
  
  <span data-ttu-id="b096c-110">このチュートリアルを完了すると、フラット ファイルを処理し、バックエンド システムで処理するために XML として出力する BizTalk Server アプリケーションが完成します。</span><span class="sxs-lookup"><span data-stu-id="b096c-110">When the walkthrough is completed you will have a BizTalk Server application that processes flat files and writes them out as XML for processing by a back-end system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b096c-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="b096c-111">Prerequisites</span></span>  
 <span data-ttu-id="b096c-112">この例では、BizTalk Server プロジェクトの作成、アセンブリへの署名、および BizTalk Server 管理コンソールでのアプリケーションとポートの表示に慣れている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b096c-112">For this example you need to be comfortable with creating BizTalk Server projects, signing an assembly, and using the BizTalk Server Administration console to view applications and ports.</span></span> <span data-ttu-id="b096c-113">またはずで紹介したアイデアに[チュートリアル: 基本的な BizTalk アプリケーションの展開](../core/walkthrough-deploying-a-basic-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="b096c-113">You should also be comfortable with the ideas presented in [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span> <span data-ttu-id="b096c-114">フラット ファイル スキーマ ウィザードの基礎知識は役立ちますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="b096c-114">Basic familiarity with the Flat File Schema Wizard is also helpful but not required.</span></span>  
  
## <a name="what-this-example-does"></a><span data-ttu-id="b096c-115">この例の処理</span><span class="sxs-lookup"><span data-stu-id="b096c-115">What This Example Does</span></span>  
 <span data-ttu-id="b096c-116">この例では、受信フラット ファイルをカスタム パイプラインとフラット ファイル逆アセンブラー コンポーネントを使用して処理します。</span><span class="sxs-lookup"><span data-stu-id="b096c-116">This example processes inbound flat file messages using a custom pipeline and the Flat File Disassembler component.</span></span> <span data-ttu-id="b096c-117">ヘッダー スキーマ、トレーラー スキーマ、およびボディ スキーマを使用してメッセージを解析した後、バックエンドで処理するためにそれらのメッセージを送信場所に出力します。</span><span class="sxs-lookup"><span data-stu-id="b096c-117">Messages are parsed using header, trailer, and body schemas and then written out to a send location for back-end processing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b096c-118">例</span><span class="sxs-lookup"><span data-stu-id="b096c-118">Example</span></span>  
 <span data-ttu-id="b096c-119">この例を作成するには、以下で概要を説明している手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b096c-119">To create the example, follow the steps outlined in the following sections.</span></span>  
  
### <a name="create-a-new-biztalk-project"></a><span data-ttu-id="b096c-120">新しい BizTalk プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="b096c-120">Create a New BizTalk Project</span></span>  
 <span data-ttu-id="b096c-121">BizTalk プロジェクトを作成する必要があるソリューションをビルドする前に、ソリューションに厳密な名前が付いていることを確認し、アプリケーション名をそのソリューションに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b096c-121">Before building a solution you need to create a BizTalk project, ensure that it is strongly named, and assign it an application name.</span></span> <span data-ttu-id="b096c-122">アプリケーション名を割り当てると、そのソリューションが BizTalk Server によって既定の BizTalk アプリケーションに配置されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="b096c-122">Assigning an application name prevents BizTalk Server from deploying the solution into the default BizTalk application.</span></span>  
  
1. <span data-ttu-id="b096c-123">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して新しい BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b096c-123">Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project.</span></span> <span data-ttu-id="b096c-124">プロジェクトを呼び出す **[ffdisassemblerwalkthrough]** します。</span><span class="sxs-lookup"><span data-stu-id="b096c-124">Call the project **FFDisassemblerWalkthrough**.</span></span>  
  
2. <span data-ttu-id="b096c-125">キー ファイルを作成してプロジェクトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b096c-125">Generate a key file and assign it to the project.</span></span> <span data-ttu-id="b096c-126">このタスクの詳細については、次を参照してください。[署名 Page, Project Designer](http://go.microsoft.com/fwlink/?LinkId=125876)します。</span><span class="sxs-lookup"><span data-stu-id="b096c-126">For more information about this task, see [Signing Page, Project Designer](http://go.microsoft.com/fwlink/?LinkId=125876).</span></span>  
  
3. <span data-ttu-id="b096c-127">プロジェクトの配置プロパティで、次のように設定します。**アプリケーション名**を"FlatFileExample"に設定し**ホスト インスタンスを再起動**に`True`します。</span><span class="sxs-lookup"><span data-stu-id="b096c-127">In the deployment properties for the project, set **Application Name** to “FlatFileExample” and set **Restart Host Instances** to `True`.</span></span> <span data-ttu-id="b096c-128">このフラグを設定すると、キャッシュされたアセンブリのインスタンスを消去するようにホストに通知されます。</span><span class="sxs-lookup"><span data-stu-id="b096c-128">Setting this flag tells the host to clear any cached instances of the assembly.</span></span>  
  
### <a name="create-the-sample-data-file"></a><span data-ttu-id="b096c-129">サンプル データ ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="b096c-129">Create the Sample Data File</span></span>  
<span data-ttu-id="b096c-130">スキーマを生成する前に、テスト ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b096c-130">Before generating schemas, you need to create a test file.</span></span>   
  
1.  <span data-ttu-id="b096c-131">メモ帳または任意のテキスト エディターを起動します。</span><span class="sxs-lookup"><span data-stu-id="b096c-131">Start Notepad or another text editor.</span></span>  
  
2.  <span data-ttu-id="b096c-132">サンプル テスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b096c-132">Create a sample test file.</span></span> <span data-ttu-id="b096c-133">このファイルは、エラーの報告元の場所を示すヘッダー、バッチの ID を含んだトレーラー、および 1 つ以上のエラー レコードで構成されたボディで構成されています。</span><span class="sxs-lookup"><span data-stu-id="b096c-133">The file consists of a header indicating the location reporting the error(s), a trailer with a batch ID for this batch, and a body consisting of one or more error records.</span></span> <span data-ttu-id="b096c-134">ファイルの形式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b096c-134">The format of the file is as follows:</span></span>  
  
    ```  
    Location  
    ERRORid|type|priority|description|errorDateTime  
    …additional error records   
    BatchID  
    ```  
  
    <span data-ttu-id="b096c-135">エラー レコードのタグが付いたテキスト"ERROR"と区切り、"&#124;"文字 (位置指定)。</span><span class="sxs-lookup"><span data-stu-id="b096c-135">The ERROR record is tagged with the text “ERROR” and delimited with the “&#124;” character (versus positional).</span></span> <span data-ttu-id="b096c-136">この ERROR レコードのデータ要素を次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="b096c-136">The data elements of the ERROR record are described in the following table.</span></span>  
  
    |<span data-ttu-id="b096c-137">要素</span><span class="sxs-lookup"><span data-stu-id="b096c-137">Element</span></span>|<span data-ttu-id="b096c-138">データ型</span><span class="sxs-lookup"><span data-stu-id="b096c-138">Data type</span></span>|<span data-ttu-id="b096c-139">説明</span><span class="sxs-lookup"><span data-stu-id="b096c-139">Description</span></span>|  
    |---|---|---|  
    |<span data-ttu-id="b096c-140">ID</span><span class="sxs-lookup"><span data-stu-id="b096c-140">ID</span></span>|<span data-ttu-id="b096c-141">整数 (integer)</span><span class="sxs-lookup"><span data-stu-id="b096c-141">integer</span></span>|<span data-ttu-id="b096c-142">このエラーの ID。</span><span class="sxs-lookup"><span data-stu-id="b096c-142">ID for this error.</span></span>|  
    |<span data-ttu-id="b096c-143">型</span><span class="sxs-lookup"><span data-stu-id="b096c-143">Type</span></span>|<span data-ttu-id="b096c-144">整数 (integer)</span><span class="sxs-lookup"><span data-stu-id="b096c-144">integer</span></span>|<span data-ttu-id="b096c-145">エラーの種類。</span><span class="sxs-lookup"><span data-stu-id="b096c-145">Type of error.</span></span>|  
    |<span data-ttu-id="b096c-146">[Priority]</span><span class="sxs-lookup"><span data-stu-id="b096c-146">Priority</span></span>|<span data-ttu-id="b096c-147">string</span><span class="sxs-lookup"><span data-stu-id="b096c-147">string</span></span>|<span data-ttu-id="b096c-148">優先度インジケーター: Low、Medium、または High。</span><span class="sxs-lookup"><span data-stu-id="b096c-148">Priority indicator: Low, Medium, or High.</span></span>|  
    |<span data-ttu-id="b096c-149">説明</span><span class="sxs-lookup"><span data-stu-id="b096c-149">Description</span></span>|<span data-ttu-id="b096c-150">string</span><span class="sxs-lookup"><span data-stu-id="b096c-150">string</span></span>|<span data-ttu-id="b096c-151">エラーの説明。</span><span class="sxs-lookup"><span data-stu-id="b096c-151">Description of the error.</span></span>|  
    |<span data-ttu-id="b096c-152">ErrorDateTime</span><span class="sxs-lookup"><span data-stu-id="b096c-152">ErrorDateTime</span></span>|<span data-ttu-id="b096c-153">DateTime</span><span class="sxs-lookup"><span data-stu-id="b096c-153">DateTime</span></span>|<span data-ttu-id="b096c-154">エラーが発生した日時です。</span><span class="sxs-lookup"><span data-stu-id="b096c-154">Date and time that the error occurred.</span></span>|  
  
    <span data-ttu-id="b096c-155">ファイルには、1 つ以上の ERROR レコードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b096c-155">The file can have one or more ERROR records.</span></span>  
  
     <span data-ttu-id="b096c-156">* * - または-- * *</span><span class="sxs-lookup"><span data-stu-id="b096c-156">**-- OR --  **</span></span>
  
     <span data-ttu-id="b096c-157">新しいファイルに次のサンプル データをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b096c-157">Copy the following sample data into the new file.</span></span> <span data-ttu-id="b096c-158">最後の行には、ラインフィードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b096c-158">The last line contains a trailing linefeed:</span></span>
  
    ```  
    East Coast Facility  
    ERROR102|0|High|Sprocket query fails.|1999-05-31T13:20:00.000-05:00  
    ERROR16502|2|Low|Time threshold exceeded.|1999-05-31T13:20:00.000-05:00  
    8675309  
  
    ```  
  
3.  <span data-ttu-id="b096c-159">新しいサンプル ファイルをプロジェクト ディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="b096c-159">Save the new sample file in the project directory.</span></span> <span data-ttu-id="b096c-160">簡単に見つけられるように、"ErrorFile.txt" などのわかりやすい名前を付けてください。</span><span class="sxs-lookup"><span data-stu-id="b096c-160">Use a descriptive name like "ErrorFile.txt" so it can be located easily.</span></span>  
  
### <a name="create-and-test-the-header-trailer-and-body-schemas"></a><span data-ttu-id="b096c-161">ヘッダー スキーマ、トレーラー スキーマ、およびボディ スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="b096c-161">Create and Test the Header, Trailer, and Body Schemas</span></span>  
 <span data-ttu-id="b096c-162">サンプル データ ファイルを作成したら、ヘッダー スキーマ、トレーラー スキーマ、およびボディ スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="b096c-162">After the sample data file is created, the next step is to create the header, trailer, and body schemas.</span></span> <span data-ttu-id="b096c-163">これらのスキーマは、受信したメッセージを処理するためにフラット ファイル逆アセンブラー受信パイプライン コンポーネントで使用されます。</span><span class="sxs-lookup"><span data-stu-id="b096c-163">These schemas are used with the Flat File Disassembler receive pipeline component to process received messages.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-header-schema"></a><span data-ttu-id="b096c-164">フラット ファイル スキーマ ウィザードを使用して、ヘッダー スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="b096c-164">Use the Flat File Schema Wizard to create the header schema</span></span>  
  
1.  <span data-ttu-id="b096c-165">新しいスキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b096c-165">Add a new schema to the project.</span></span> <span data-ttu-id="b096c-166">ソリューション エクスプ ローラーで右クリック**ffdisassemblerwalkthrough**、 をポイント**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-166">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="b096c-167">**新しい項目の追加**ダイアログ ボックスで、をクリックして**スキーマ ファイル**選択と**フラット ファイル スキーマ ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-167">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="b096c-168">新しいスキーマ"Header.xsd"という名前をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-168">Name the new schema "Header.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="b096c-169">**BizTalk フラット ファイル スキーマ ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-169">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="b096c-170">**フラット ファイル スキーマ情報**] ページで [**参照**前に作成したサンプル データ ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="b096c-170">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="b096c-171">変更、**レコード名**"Header"に、コード ページを確認し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-171">Change the **Record Name** to "Header", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b096c-172">サンプル ファイルを Unicode 形式で保存した場合、コード ページはリトル エンディアン UTF16 (1200) になります。</span><span class="sxs-lookup"><span data-stu-id="b096c-172">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="b096c-173">これは、この例に影響しません。</span><span class="sxs-lookup"><span data-stu-id="b096c-173">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="b096c-174">次に、ドキュメント データを選択します。</span><span class="sxs-lookup"><span data-stu-id="b096c-174">Next select the document data.</span></span> <span data-ttu-id="b096c-175">**ドキュメント データを選択** ページで、改行文字 {CR} を含むデータの最初の行を強調表示と {LF} よう。</span><span class="sxs-lookup"><span data-stu-id="b096c-175">On the **Select Document Data** page, highlight the first line of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="b096c-176">![ヘッダー スキーマ用に選択されたデータ](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="b096c-176">![Data selected for header schema](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")</span></span>  
  
     <span data-ttu-id="b096c-177">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b096c-177">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="b096c-178">**レコード書式を** ページで  **次へ**既定値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="b096c-178">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="b096c-179">データ ファイルでは相対位置を使用していないので、既定の "区切り記号" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b096c-179">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="b096c-180">**区切られたレコード**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-180">On the **Delimited Record** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="b096c-181">次に子要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="b096c-181">Now you specify child elements.</span></span> <span data-ttu-id="b096c-182">次に示すように、ヘッダーには、"Location" という要素が 1 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="b096c-182">The header contains one element named "Location":</span></span>  
  
     <span data-ttu-id="b096c-183">![ヘッダーに定義された場所ノード](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")</span><span class="sxs-lookup"><span data-stu-id="b096c-183">![Location node defined for header](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")</span></span>  
  
     <span data-ttu-id="b096c-184">**[次へ]** をクリックして次に進みます。</span><span class="sxs-lookup"><span data-stu-id="b096c-184">Click **Next** to continue.</span></span>  
  
9. <span data-ttu-id="b096c-185">**スキーマ ビュー**ページで、スキーマを確認します。</span><span class="sxs-lookup"><span data-stu-id="b096c-185">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="b096c-186">![スキーマ ビューの表示が完了したヘッダー スキーマ](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")</span><span class="sxs-lookup"><span data-stu-id="b096c-186">![Schema view showing completed Header schema](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")</span></span>  
  
     <span data-ttu-id="b096c-187">問題がなければ、 をクリックして**完了**ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="b096c-187">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
10. <span data-ttu-id="b096c-188">をクリックして、 **\<スキーマ\>** ヘッダー スキーマ ペインでノード。</span><span class="sxs-lookup"><span data-stu-id="b096c-188">Click the **\<Schema\>** node in the Header schema pane.</span></span> <span data-ttu-id="b096c-189">プロパティ ペインで次のように変更します。 **Element FormDefault**に**Qualified**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-189">In the Properties pane, change **Element FormDefault** to **Qualified**.</span></span> <span data-ttu-id="b096c-190">これは、ローカルに宣言された要素を、ターゲットの名前空間を使用してインスタンス ドキュメント内で修飾する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="b096c-190">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-trailer-schema"></a><span data-ttu-id="b096c-191">フラット ファイル スキーマ ウィザードを使用して、トレーラー スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="b096c-191">Use the Flat File Schema Wizard to create the trailer schema</span></span>  
  
1.  <span data-ttu-id="b096c-192">新しいスキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b096c-192">Add a new schema to the project.</span></span> <span data-ttu-id="b096c-193">ソリューション エクスプ ローラーで右クリック**ffdisassemblerwalkthrough**、 をポイント**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-193">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add** , and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="b096c-194">**新しい項目の追加**ダイアログ ボックスで、をクリックして**スキーマ ファイル**選択と**フラット ファイル スキーマ ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-194">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="b096c-195">新しいスキーマ"Trailer.xsd"という名前をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-195">Name the new schema "Trailer.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="b096c-196">**BizTalk フラット ファイル スキーマ ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-196">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="b096c-197">**フラット ファイル スキーマ情報**] ページで [**参照**前に作成したサンプル データ ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="b096c-197">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="b096c-198">変更、**レコード名**を"Trailer"、コード ページを確認し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-198">Change the **Record Name** to "Trailer", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b096c-199">サンプル ファイルを Unicode 形式で保存した場合、コード ページはリトル エンディアン UTF16 (1200) になります。</span><span class="sxs-lookup"><span data-stu-id="b096c-199">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="b096c-200">これは、この例に影響しません。</span><span class="sxs-lookup"><span data-stu-id="b096c-200">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="b096c-201">次に、ドキュメント データを選択します。</span><span class="sxs-lookup"><span data-stu-id="b096c-201">Next select the document data.</span></span> <span data-ttu-id="b096c-202">**ドキュメント データを選択** ページで、改行文字 {CR} を含むデータの最後の行を強調表示と {LF} よう。</span><span class="sxs-lookup"><span data-stu-id="b096c-202">On the **Select Document Data** page, highlight the last line of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="b096c-203">![トレーラー スキーマ用に選択されたデータ](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="b096c-203">![Data selected for trailer schema](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")</span></span>  
  
     <span data-ttu-id="b096c-204">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b096c-204">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="b096c-205">**レコード書式を** ページで  **次へ**既定値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="b096c-205">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="b096c-206">データ ファイルでは相対位置を使用していないので、既定の "区切り記号" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b096c-206">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="b096c-207">**区切られたレコード**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-207">On the **Delimited Record** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="b096c-208">次に子要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="b096c-208">Now you specify child elements.</span></span> <span data-ttu-id="b096c-209">次に示すように、ヘッダーには、"BatchID" という要素が 1 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="b096c-209">The header contains one element named "BatchID":</span></span>  
  
     <span data-ttu-id="b096c-210">![トレーラー用に定義された場所ノード](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")</span><span class="sxs-lookup"><span data-stu-id="b096c-210">![Location node defined for trailer](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")</span></span>  
  
     <span data-ttu-id="b096c-211">**[次へ]** をクリックして次に進みます。</span><span class="sxs-lookup"><span data-stu-id="b096c-211">Click **Next** to continue.</span></span>  
  
9. <span data-ttu-id="b096c-212">**スキーマ ビュー**ページで、スキーマを確認します。</span><span class="sxs-lookup"><span data-stu-id="b096c-212">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="b096c-213">![スキーマ ビュー表示が完了したトレーラー スキーマ](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")</span><span class="sxs-lookup"><span data-stu-id="b096c-213">![Schema view showing completed Trailer schema](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")</span></span>  
  
     <span data-ttu-id="b096c-214">問題がなければ、 をクリックして**完了**ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="b096c-214">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
10. <span data-ttu-id="b096c-215">をクリックして、 **\<スキーマ\>** トレーラー スキーマ ペイン内のノード。</span><span class="sxs-lookup"><span data-stu-id="b096c-215">Click the **\<Schema\>** node in the Trailer schema pane.</span></span> <span data-ttu-id="b096c-216">プロパティ ペインで次のように変更します。 **elementFormDefault**に**Qualified**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-216">In the Properties pane, change **elementFormDefault** to **Qualified**.</span></span> <span data-ttu-id="b096c-217">これは、ローカルに宣言された要素を、ターゲットの名前空間を使用してインスタンス ドキュメント内で修飾する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="b096c-217">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-body-schema"></a><span data-ttu-id="b096c-218">フラット ファイル スキーマ ウィザードを使用して、本文のスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="b096c-218">Use the Flat File Schema Wizard to create the body schema</span></span>  
  
1.  <span data-ttu-id="b096c-219">新しいスキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b096c-219">Add a new schema to the project.</span></span> <span data-ttu-id="b096c-220">ソリューション エクスプ ローラーで右クリック**ffdisassemblerwalkthrough**、 をポイント**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-220">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="b096c-221">**新しい項目の追加**ダイアログ ボックスで、をクリックして**スキーマ ファイル**選択と**フラット ファイル スキーマ ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-221">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="b096c-222">新しいスキーマ"Body.xsd"という名前をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-222">Name the new schema "Body.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="b096c-223">**BizTalk フラット ファイル スキーマ ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-223">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="b096c-224">**フラット ファイル スキーマ情報**] ページで [**参照**前に作成したサンプル データ ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="b096c-224">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="b096c-225">変更、**レコード名**"Body"に、コード ページを確認し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-225">Change the **Record Name** to "Body", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b096c-226">サンプル ファイルを Unicode 形式で保存した場合、コード ページはリトル エンディアン UTF16 (1200) になります。</span><span class="sxs-lookup"><span data-stu-id="b096c-226">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="b096c-227">これは、この例に影響しません。</span><span class="sxs-lookup"><span data-stu-id="b096c-227">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="b096c-228">次に、ドキュメント データを選択します。</span><span class="sxs-lookup"><span data-stu-id="b096c-228">Next select the document data.</span></span> <span data-ttu-id="b096c-229">**ドキュメント データを選択** ページで、改行文字 {CR} を含む、データの 2 と 3 つの行を強調表示と {LF} よう。</span><span class="sxs-lookup"><span data-stu-id="b096c-229">On the **Select Document Data** page, highlight lines two and three of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="b096c-230">![ボディ スキーマ用に選択されたデータ](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="b096c-230">![Data selected for body schema](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")</span></span>  
  
     <span data-ttu-id="b096c-231">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b096c-231">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="b096c-232">**レコード書式を** ページで  **次へ**既定値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="b096c-232">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="b096c-233">データ ファイルでは相対位置を使用していないので、既定の "区切り記号" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b096c-233">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="b096c-234">**区切られたレコード**] ページで、[**次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-234">On the **Delimited Record** page, select **Next**.</span></span>  
  
8.  <span data-ttu-id="b096c-235">ここでは、子要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="b096c-235">Next define the child elements.</span></span> <span data-ttu-id="b096c-236">変更**Body_Child1**に**エラー**に要素の型を設定および**繰り返しレコード**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-236">Change **Body_Child1** to **Error**and set its element type to **Repeating record**.</span></span> <span data-ttu-id="b096c-237">設定、 **Body_Child2**要素レコードの種類を**無視**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-237">Set the **Body_Child2** element record type to **Ignore**.</span></span>  
  
9. <span data-ttu-id="b096c-238">**スキーマ ビュー** ] ページで [**次**エラー レコードの子要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="b096c-238">On the **Schema View** page, click **Next** to define the child elements of the Error record.</span></span>  
  
10. <span data-ttu-id="b096c-239">**ドキュメント データを選択**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-239">On the **Select Document Data** page, click **Next**.</span></span> <span data-ttu-id="b096c-240">ウィザードによって、レコード定義データが適切に選択されます。</span><span class="sxs-lookup"><span data-stu-id="b096c-240">The wizard chooses the record-defining data correctly.</span></span>  
  
11. <span data-ttu-id="b096c-241">**レコード書式を** ページで **次**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-241">On the **Select Record Format** page, click **Next**.</span></span> <span data-ttu-id="b096c-242">データは、区切り記号で書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="b096c-242">The data is formatted by delimiter symbol.</span></span>  
  
12. <span data-ttu-id="b096c-243">**区切られたレコード**] ページで、[ **&#124;** の**子区切り記号**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-243">On the **Delimited Record** page, select **&#124;** for the **Child delimiter**.</span></span> <span data-ttu-id="b096c-244">次に、選択、**レコードにタグ識別子** チェック ボックス**エラー**タグ値にします。</span><span class="sxs-lookup"><span data-stu-id="b096c-244">Next, select the **Record has a tag identifier** check box and type **ERROR** for the tag value.</span></span>  
  
     <span data-ttu-id="b096c-245">![構成で区切られたレコードのタグ識別子](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")</span><span class="sxs-lookup"><span data-stu-id="b096c-245">![Configuring delimited record with tag identifier](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")</span></span>  
  
     <span data-ttu-id="b096c-246">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b096c-246">Click **Next**.</span></span>  
  
13. <span data-ttu-id="b096c-247">ここでは、Error レコードの子要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="b096c-247">Now define the child elements of the Error record.</span></span>  
  
     <span data-ttu-id="b096c-248">![5 つの要素で定義されたエラー レコード](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")</span><span class="sxs-lookup"><span data-stu-id="b096c-248">![Error record defined with five elements](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")</span></span>  
  
     <span data-ttu-id="b096c-249">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b096c-249">Click **Next**.</span></span>  
  
14. <span data-ttu-id="b096c-250">**スキーマ ビュー**ページで、スキーマを確認します。</span><span class="sxs-lookup"><span data-stu-id="b096c-250">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="b096c-251">![スキーマ ビュー表示が完了したボディ スキーマ](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")</span><span class="sxs-lookup"><span data-stu-id="b096c-251">![Schema view showing completed Body schema](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")</span></span>  
  
     <span data-ttu-id="b096c-252">誤りを加えた場合にクリックします**戻る**し、必要に応じて修正します。</span><span class="sxs-lookup"><span data-stu-id="b096c-252">If you have made any mistakes, click **Back** and make the necessary corrections.</span></span> <span data-ttu-id="b096c-253">問題がなければ、 をクリックして**完了**ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="b096c-253">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
15. <span data-ttu-id="b096c-254">をクリックして、 **\<スキーマ\>** Body スキーマ ペイン内のノード。</span><span class="sxs-lookup"><span data-stu-id="b096c-254">Click the **\<Schema\>** node in the Body schema pane.</span></span> <span data-ttu-id="b096c-255">プロパティ ペインで次のように変更します。 **Element FormDefault**に**Qualified**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-255">In the Properties pane, change **Element FormDefault** to **Qualified**.</span></span> <span data-ttu-id="b096c-256">これは、ローカルに宣言された要素を、ターゲットの名前空間を使用してインスタンス ドキュメント内で修飾する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="b096c-256">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
16. <span data-ttu-id="b096c-257">をクリックして、 **\<エラー\>**  Body スキーマ ペイン上のノード。</span><span class="sxs-lookup"><span data-stu-id="b096c-257">Click the **\<Error\>** node on the Body schema pane.</span></span> <span data-ttu-id="b096c-258">プロパティ ペインで次のように変更します。 **Max Occurs**に**1**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-258">In the Properties pane, change **Max Occurs** to **1**.</span></span> <span data-ttu-id="b096c-259">これにより、フラット ファイル逆アセンブラーによって各エラーがそれぞれのメッセージに分割されます。</span><span class="sxs-lookup"><span data-stu-id="b096c-259">This causes the Flat File Disassembler to split each error into its own message.</span></span>  
  
##### <a name="test-the-schemas-using-ffdasm"></a><span data-ttu-id="b096c-260">FFDasm を使用してスキーマをテストします。</span><span class="sxs-lookup"><span data-stu-id="b096c-260">Test the schemas using FFDasm</span></span>  
  
1.  <span data-ttu-id="b096c-261">コマンド プロンプトを開き、ディレクトリをプロジェクト ディレクトリに変更します。</span><span class="sxs-lookup"><span data-stu-id="b096c-261">Open a command prompt and change the directory to your project directory.</span></span>  
  
2.  <span data-ttu-id="b096c-262">コマンド プロンプトから、次に示すように FFDasm.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="b096c-262">From the command prompt, run FFDasm.exe as shown below.</span></span>  
  
    ```  
    <Samples Path>\SDK\Utilities\PipelineTools\FFDasm ErrorFile.txt  -hs header.xsd -bs body.xsd -ts Trailer.xsd  
    ```  
  
     <span data-ttu-id="b096c-263">これと他のパイプライン ツールの場所については、次を参照してください。[パイプライン ツール](../core/pipeline-tools.md)します。</span><span class="sxs-lookup"><span data-stu-id="b096c-263">For information about the location of this and other pipeline tools, see [Pipeline Tools](../core/pipeline-tools.md).</span></span>  
  
3.  <span data-ttu-id="b096c-264">FFDasm.exe によって、テスト ファイル内の各 ERROR レコードに対応した {GUID}.xml という名前の出力ファイルが 2 つ生成されます。</span><span class="sxs-lookup"><span data-stu-id="b096c-264">FFDasm.exe should produce two output files named {GUID}.xml, one for each ERROR record in the test file.</span></span> <span data-ttu-id="b096c-265">優先度の高いエラー レコードは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b096c-265">The high-priority error record looks like the following:</span></span>  
  
    ```  
    <Body xmlns="http://FFDisassemblerWalkthrough.Body">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <DateTime>1999-05-31T13:20:00.000-05:00</DateTime>  
      </Error>  
    </Body>  
    ```  
  
### <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="b096c-266">カスタム受信パイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="b096c-266">Create a Custom Receive Pipeline</span></span>  
 <span data-ttu-id="b096c-267">フラット ファイル スキーマを定義したので、次はフラット ファイル逆アセンブラー コンポーネントを使用するカスタム パイプラインを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b096c-267">Now that the flat file schemas are defined, you need to create a custom pipeline that uses the Flat File Disassembler component.</span></span> <span data-ttu-id="b096c-268">その後で、フラット ファイル逆アセンブラー コンポーネントを、ヘッダー スキーマ、ボディ スキーマ、およびトレーラー スキーマを使用するように構成して、メッセージを分割できます。</span><span class="sxs-lookup"><span data-stu-id="b096c-268">The Flat File Disassembler component can then be configured to use the header, body, and trailer schemas to break up messages.</span></span>    
 
1.  <span data-ttu-id="b096c-269">新しい受信パイプラインをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b096c-269">Add a new receive pipeline to the project.</span></span> <span data-ttu-id="b096c-270">ソリューション エクスプ ローラーで右クリックし、 **ffdisassemblerwalkthrough**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。</span><span class="sxs-lookup"><span data-stu-id="b096c-270">In Solution Explorer, right-click the **FFDisassemblerWalkthrough** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="b096c-271">**新しい項目の追加** ダイアログ ボックスで、 をポイント**パイプライン ファイル** をクリックし、**受信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-271">In the **Add New Item** dialog box, point to **Pipeline Files** and then click **Receive Pipeline**.</span></span> <span data-ttu-id="b096c-272">新しいパイプライン"FFReceivePipeline"という名前をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-272">Name the new pipeline "FFReceivePipeline" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="b096c-273">フラット ファイル逆アセンブラー コンポーネントを、[ツールボックス] ペインから逆アセンブル ステップへドラッグして新しいパイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="b096c-273">Configure the new pipeline by dragging the Flat File Disassembler component from the Toolbox pane to the Disassemble step.</span></span>  
  
4.  <span data-ttu-id="b096c-274">プロパティ ウィンドウで、設定、**ドキュメント スキーマ**に**FFDisassemblerWalkthrough.Body**、**ヘッダー スキーマ**に**FFDisassemblerWalkthrough.Header**と**トレーラー スキーマ**に**FFDisassemblerWalkthrough.Trailer**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-274">In the Properties pane, set the **Document schema** to **FFDisassemblerWalkthrough.Body**, the **Header schema** to **FFDisassemblerWalkthrough.Header** and the **Trailer schema** to **FFDisassemblerWalkthrough.Trailer**.</span></span>  
  
### <a name="deploy-the-application-and-configure-the-send-and-receive-ports"></a><span data-ttu-id="b096c-275">アプリケーションの展開および送信ポートと受信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="b096c-275">Deploy the Application and Configure the Send and Receive Ports</span></span>  
 <span data-ttu-id="b096c-276">スキーマとカスタム受信パイプラインを作成したら、次はプロジェクトをコンパイルして配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b096c-276">With the schemas and custom receive pipeline created, you need to compile and deploy the project.</span></span> <span data-ttu-id="b096c-277">プロジェクトを配置すると、BizTalk Server 管理コンソールを使用して、送信ポートと受信ポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b096c-277">After it is deployed, you can use the BizTalk Server Administration console to configure the send and receive ports.</span></span>  

##### <a name="deploy"></a><span data-ttu-id="b096c-278">配置</span><span class="sxs-lookup"><span data-stu-id="b096c-278">Deploy</span></span>  
1. <span data-ttu-id="b096c-279">内から[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、プロジェクトを右クリックし、をクリックして、ソリューションを配置**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-279">From within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], deploy the solution by right-clicking on the project and then clicking **Deploy**.</span></span>  
  
2. <span data-ttu-id="b096c-280">展開し、BizTalk Server 管理コンソールを使用して、**アプリケーション**ことを確認するグループ **[flatfileexample]** がカスタム アプリケーションとして存在します。</span><span class="sxs-lookup"><span data-stu-id="b096c-280">Using the BizTalk Server Administration console, expand the **Applications** group to verify that **FlatFileExample** is present as a custom application.</span></span>  
  
##### <a name="configure-the-receive-port"></a><span data-ttu-id="b096c-281">受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b096c-281">Configure the receive port</span></span>  
  
1.  <span data-ttu-id="b096c-282">下の"Receive"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **[ffdisassemblerwalkthrough]** プロジェクト ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="b096c-282">Use Windows Explorer to create a directory named "Receive" under the **FFDisassemblerWalkthrough** project directory.</span></span>  
  
2.  <span data-ttu-id="b096c-283">BizTalk Server 管理コンソールで、 **flatfileexample**アプリケーションを右クリックして**受信ポート**、 をポイント**新規**順にクリックします**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-283">In the BizTalk Server Administration console, expand the **FlatFileExample** application, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="b096c-284">**受信ポートのプロパティ** ダイアログ ボックスで、ポートを"ReceiveError"の名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="b096c-284">In the **Receive Port Properties** dialog box, set the name of the port to "ReceiveError".</span></span>  
  
4.  <span data-ttu-id="b096c-285">クリックして**受信場所**、 をクリックし、**新規**受信場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="b096c-285">Click **Receive Locations**, and then click **New** to add a receive location.</span></span> <span data-ttu-id="b096c-286">新しい受信場所に "ReceiveErrorLocation" という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="b096c-286">Name the new receive location "ReceiveErrorLocation".</span></span> <span data-ttu-id="b096c-287">設定、**受信パイプライン**に**FFReceivePipeline**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-287">Set the **Receive Pipeline** to **FFReceivePipeline**.</span></span> <span data-ttu-id="b096c-288">**トランスポートの種類**を選択します**ファイル**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-288">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="b096c-289">設定し、作成した受信ディレクトリを選択、\*\*ファイル マスク\*\*\*.txt にします。</span><span class="sxs-lookup"><span data-stu-id="b096c-289">Select the receive directory you created, and then set the **File mask** to \*.txt.</span></span>  
  
5.  <span data-ttu-id="b096c-290">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b096c-290">Click **OK**.</span></span> <span data-ttu-id="b096c-291">受信ポートが正しく構成されます。</span><span class="sxs-lookup"><span data-stu-id="b096c-291">Your receive port should now be configured.</span></span> <span data-ttu-id="b096c-292">クリックして**OK**を閉じます。</span><span class="sxs-lookup"><span data-stu-id="b096c-292">Click **OK** to close.</span></span>  
  
##### <a name="configure-the-send-port"></a><span data-ttu-id="b096c-293">送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b096c-293">Configure the send port</span></span>  
  
1.  <span data-ttu-id="b096c-294">下の"Send"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **[ffdisassemblerwalkthrough]** プロジェクト ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="b096c-294">Use Windows Explorer to create a directory named "Send" under the **FFDisassemblerWalkthrough** project directory.</span></span>  
  
2.  <span data-ttu-id="b096c-295">BizTalk Server 管理コンソールで、 **[flatfileexample]** 、アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポートしています**。</span><span class="sxs-lookup"><span data-stu-id="b096c-295">In the BizTalk Server Administration console, expand the **FlatFileExample** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way  Send Port…**.</span></span>  
  
3.  <span data-ttu-id="b096c-296">**送信ポートのプロパティ** ダイアログ ボックスで、「送信」をポートの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="b096c-296">In the **Send Port Properties** dialog box, set the name of the port to "Send".</span></span>  
  
4.  <span data-ttu-id="b096c-297">トランスポートの種類を選択**ファイル**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-297">For transport type, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="b096c-298">送信先のフォルダーを、先ほど作成した送信ディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="b096c-298">Set the destination folder to the send directory you created earlier.</span></span>  
  
5.  <span data-ttu-id="b096c-299">次は、フィルターを構成します。</span><span class="sxs-lookup"><span data-stu-id="b096c-299">Now configure the filter.</span></span> <span data-ttu-id="b096c-300">クリックして**フィルター**し、1 つの式を追加します。</span><span class="sxs-lookup"><span data-stu-id="b096c-300">Click **Filters** and add one expression:</span></span>  
  
    -   <span data-ttu-id="b096c-301">BTS.MessageType == **http://FFDisassemblerWalkthrough.Body#Body**</span><span class="sxs-lookup"><span data-stu-id="b096c-301">BTS.MessageType == **http://FFDisassemblerWalkthrough.Body#Body**</span></span>  
  
6.  <span data-ttu-id="b096c-302">クリックして**OK**送信ポートの構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="b096c-302">Click **OK** to complete the send port configuration.</span></span> <span data-ttu-id="b096c-303">送信ポートが正しく構成されます。</span><span class="sxs-lookup"><span data-stu-id="b096c-303">Your send port should be configured.</span></span>  
  
### <a name="run-the-example"></a><span data-ttu-id="b096c-304">例の実行</span><span class="sxs-lookup"><span data-stu-id="b096c-304">Run the Example</span></span>  
 <span data-ttu-id="b096c-305">次に、例を実行します。</span><span class="sxs-lookup"><span data-stu-id="b096c-305">It is now time to run the example.</span></span> <span data-ttu-id="b096c-306">BizTalk Server 管理コンソールを使用すると、アプリケーションを起動、受信場所に、テスト ファイルをコピーし、送信場所に生成される内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="b096c-306">After using the BizTalk Server Management console to start the application, copy the test files to the receive location and observe what is produced in the send location.</span></span>  
  
1.  <span data-ttu-id="b096c-307">右クリックし、BizTalk Server 管理コンソールで、 **[flatfileexample]** アプリケーション、およびクリック**開始**します。</span><span class="sxs-lookup"><span data-stu-id="b096c-307">In the BizTalk Server Administration console, right-click the **FlatFileExample** application, and then click **Start**.</span></span> <span data-ttu-id="b096c-308">送信を開始し、および受信ポートこれを参加させます。</span><span class="sxs-lookup"><span data-stu-id="b096c-308">This enlists and starts the send and receive ports.</span></span>  
  
2.  <span data-ttu-id="b096c-309">サンプルの Errorfile.txt のコピーを受信ディレクトリに置きます。</span><span class="sxs-lookup"><span data-stu-id="b096c-309">Drop the copy of the sample Errorfile.txt into the receive directory.</span></span> <span data-ttu-id="b096c-310">2 つの出力ファイルが送信ディレクトリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b096c-310">Two output files should be written to the send directory.</span></span>  
  
