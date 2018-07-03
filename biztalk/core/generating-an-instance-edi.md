---
title: インスタンスの生成 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 362b9803-4d4a-4d17-9ad6-439ec4c7d8aa
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82674b175ad1c408b6ddb9f7823427a550288e96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999299"
---
# <a name="generating-an-instance-edi"></a><span data-ttu-id="14f22-102">インスタンスの生成 (EDI)</span><span class="sxs-lookup"><span data-stu-id="14f22-102">Generating an Instance (EDI)</span></span>
<span data-ttu-id="14f22-103">デザイン時に、EDI スキーマからメッセージ インスタンスを生成できます。</span><span class="sxs-lookup"><span data-stu-id="14f22-103">You can generate a message instance from an EDI schema at design time.</span></span> <span data-ttu-id="14f22-104">それには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の XML ツール拡張を使用します。</span><span class="sxs-lookup"><span data-stu-id="14f22-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span>  
  
 <span data-ttu-id="14f22-105">完全なバッチ化されたインターチェンジ (インターチェンジ ヘッダーとグループ ヘッダーを含む) を生成することも、トランザクション セット (インターチェンジ ヘッダーとグループ ヘッダーを含まない) を生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="14f22-105">You can generate either a complete batched interchange (with interchange and group headers) or a transaction set (without interchange and group headers).</span></span> <span data-ttu-id="14f22-106">完全なインターチェンジを生成する操作を実行すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、1 つのインターチェンジ ヘッダー、スキーマごとに 1 つのグループ、および各スキーマのグループごとに 3 つの同一なトランザクション セットを含むファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="14f22-106">If you execute the operation to generate a complete interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a file with one interchange header, a group for each schema, and three identical transaction sets per group for each schema.</span></span> <span data-ttu-id="14f22-107">トランザクション セットを生成する操作を実行すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、1 つのトランザクション セットだけを含むファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="14f22-107">If you execute the operation to generate a transaction set, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a file with a single transaction set.</span></span>  
  
 <span data-ttu-id="14f22-108">完全なバッチ化されたインターチェンジを生成するには、バッチ スキーマに対してインスタンス生成コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="14f22-108">To generate a complete batched interchange, you execute the generate-instance command on the batch schema.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="14f22-109"> によってプロジェクト内のメッセージ スキーマが検出され、それらのスキーマに対するトランザクション セットが自動的に含められます。</span><span class="sxs-lookup"><span data-stu-id="14f22-109"> will detect the message schemas in the project, and will automatically include transaction sets for those schemas.</span></span>  
  
 <span data-ttu-id="14f22-110">1 つのトランザクション セットを生成するには、メッセージ スキーマに対してインスタンス生成コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="14f22-110">To generate a single transaction set, you execute the generate-instance command on a message schema.</span></span> <span data-ttu-id="14f22-111">その場合、バッチ スキーマをプロジェクトに追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14f22-111">In this case, the batch schema does not need to be added to the project.</span></span> <span data-ttu-id="14f22-112">生成されたインスタンスにはインターチェンジ ヘッダーおよびグループ ヘッダーが含まれないので、機能 EDI インターチェンジを作成する場合はそれらを手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f22-112">The generated instance will not include an interchange or group header, however, so you will have to add those manually to have a functional EDI interchange.</span></span>  
  
 <span data-ttu-id="14f22-113">インスタンスを生成する際には、そのインスタンスで使用する構成 (区切り記号や構文識別子など) を指定するためのダイアログ ボックスが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に表示されます。</span><span class="sxs-lookup"><span data-stu-id="14f22-113">When you generate an instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] displays a dialog box in which you specify the configuration used in that instance, including separators and the syntax identifier.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="14f22-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="14f22-114">Prerequisites</span></span>  
 <span data-ttu-id="14f22-115">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f22-115">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-generate-an-instance-of-a-batched-interchange"></a><span data-ttu-id="14f22-116">バッチ化されたインターチェンジのインスタンスを生成するには</span><span class="sxs-lookup"><span data-stu-id="14f22-116">To generate an instance of a batched interchange</span></span>  
  
1. <span data-ttu-id="14f22-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="14f22-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="14f22-118">ソリューション エクスプローラーで、プロジェクトに、メッセージ インスタンスに含めるトランザクション セットの種類ごとに 1 つのメッセージ スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="14f22-118">Add a message schema to the project in Solution Explorer for each type of transaction set that you want in the message instance.</span></span> <span data-ttu-id="14f22-119">エンコードの種類に応じたバッチ スキーマ (Edifact_BatchSchema.xsd または X12_BatchSchema.xsd) をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="14f22-119">Add the batch schema for the type of encoding to the project: either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="14f22-120">バッチ スキーマは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="14f22-120">The batch schemas are located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="14f22-121">インスタンスを生成する際にプロジェクトをビルドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14f22-121">You do not have to build the project to generate an instance.</span></span>  
  
2. <span data-ttu-id="14f22-122">ソリューション エクスプ ローラーで、バッチ スキーマを右クリックし、をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="14f22-122">Right-click the batch schema in Solution Explorer, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="14f22-123">**プロパティ**ウィンドウで、設定**インスタンスの出力の種類の生成**に**ネイティブ**または**XML**します。</span><span class="sxs-lookup"><span data-stu-id="14f22-123">In the **Properties** window, set **Generate Instance Output Type** to **Native** or **XML**.</span></span> <span data-ttu-id="14f22-124">選択**ネイティブ**.txt 拡張子を持つフラット ファイルの生成を求められます。</span><span class="sxs-lookup"><span data-stu-id="14f22-124">Selecting **Native** will prompt generation of a flat file with a .txt extension.</span></span> <span data-ttu-id="14f22-125">選択**XML** XML ファイルの生成を求められます。</span><span class="sxs-lookup"><span data-stu-id="14f22-125">Selecting **XML** will prompt generation of an XML file.</span></span>  
  
4. <span data-ttu-id="14f22-126">**出力インスタンス ファイル名**名前を入力、またはファイルを参照し、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="14f22-126">For **Output Instance Filename**, enter a name or browse to a file and select the file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="14f22-127">出力インスタンス ファイル名の値を入力しない場合、ファイル名が自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="14f22-127">If you do not enter a value for the output instance filename, one will be chosen for you.</span></span> <span data-ttu-id="14f22-128">ファイル名は [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の [出力] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="14f22-128">The filename will be displayed in the Output window of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="14f22-129">既存のファイルを選択した場合、既存のファイルの内容が、この操作によって生成された内容で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="14f22-129">If you select an existing file, the contents of the existing file will be replaced with the content generated by this operation.</span></span>  
  
5. <span data-ttu-id="14f22-130">バッチ スキーマを右クリックし、をクリックし、**インスタンスの生成**します。</span><span class="sxs-lookup"><span data-stu-id="14f22-130">Right-click the batch schema and then click **Generate Instance**.</span></span>  
  
6. <span data-ttu-id="14f22-131">**EDI インスタンスのプロパティ**ダイアログ ボックスで、クリックして、そのインスタンスで使用する区切り記号、識別子、およびその他の構成のオプション、選択**OK**します。</span><span class="sxs-lookup"><span data-stu-id="14f22-131">In the **EDI Instance Properties** dialog box, select the separators, identifiers, and other configuration options to be used in that instance, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="14f22-132">操作が成功したことを確認、**出力**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="14f22-132">Verify that the operation worked in the **Output** window.</span></span>  
  
8. <span data-ttu-id="14f22-133">ファイルを表示するには、キーを押して**コントロール**のリンクをクリックし、**出力**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="14f22-133">To view the file, press **Control** and click the link in the **Output** window.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="14f22-134"> の [BizTalk エディター] ウィンドウにファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14f22-134"> will display the contents of the file in the BizTalk Editor window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="14f22-135">837I、837D、または 837P を含むインスタンスを生成すると、GS08 の値は誤って 00401 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="14f22-135">When generating an instance that contains an 837I, 837D, or 837P, the value of GS08 will be incorrectly set to 00401.</span></span> <span data-ttu-id="14f22-136">詳細については、次を参照してください。 [EDI ソリューションで XML ツールの使用に関する既知の問題](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)します。</span><span class="sxs-lookup"><span data-stu-id="14f22-136">For more information, see [Known Issues with XML Tools Used with EDI Solutions](../core/known-issues-with-xml-tools-used-with-edi-solutions.md).</span></span>  
  
### <a name="to-generate-an-instance-of-a-transaction-set"></a><span data-ttu-id="14f22-137">トランザクション セットのインスタンスを生成するには</span><span class="sxs-lookup"><span data-stu-id="14f22-137">To generate an instance of a transaction set</span></span>  
  
1. <span data-ttu-id="14f22-138">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="14f22-138">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="14f22-139">インスタンスを生成するトランザクション セットの種類に応じたスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="14f22-139">Add the schema for the type of transaction set that you want to generate an instance for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="14f22-140">トランザクション セットのインスタンスを生成する際に、プロジェクトにバッチ スキーマを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14f22-140">You do not have to add the batch schema to the project to generate an instance of a transaction set.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="14f22-141">インスタンスを生成する際にプロジェクトをビルドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14f22-141">You do not have to build the project to generate an instance.</span></span>  
  
2. <span data-ttu-id="14f22-142">ソリューション エクスプ ローラーで、メッセージ スキーマを右クリックし、をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="14f22-142">Right-click the message schema in Solution Explorer, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="14f22-143">[プロパティ] ウィンドウで次のように設定します。**インスタンスの出力の種類の生成**に**ネイティブ**または**XML**します。</span><span class="sxs-lookup"><span data-stu-id="14f22-143">In the Properties window, set **Generate Instance Output Type** to **Native** or **XML**.</span></span> <span data-ttu-id="14f22-144">選択**ネイティブ**.txt 拡張子を持つフラット ファイルの生成を求められます。</span><span class="sxs-lookup"><span data-stu-id="14f22-144">Selecting **Native** will prompt generation of a flat file with a .txt extension.</span></span> <span data-ttu-id="14f22-145">選択**XML** XML ファイルの生成を求められます。</span><span class="sxs-lookup"><span data-stu-id="14f22-145">Selecting **XML** will prompt generation of an XML file.</span></span>  
  
4. <span data-ttu-id="14f22-146">**出力インスタンス ファイル名**名前を入力、またはファイルを参照し、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="14f22-146">For **Output Instance Filename**, enter a name or browse to a file and select the file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="14f22-147">出力インスタンス ファイル名の値を入力しない場合、ファイル名が自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="14f22-147">If you do not enter a value for the output instance filename, one will be chosen for you.</span></span> <span data-ttu-id="14f22-148">ファイル名が表示されます、**出力**のウィンドウ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="14f22-148">The filename will be displayed in the **Output** window of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="14f22-149">既存のファイルを選択した場合、既存のファイルの内容が、この操作によって生成された内容で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="14f22-149">If you select an existing file, the contents of the existing file will be replaced with the content generated by this operation.</span></span>  
  
5. <span data-ttu-id="14f22-150">メッセージ スキーマを右クリックし、をクリックし、**インスタンスの生成**します。</span><span class="sxs-lookup"><span data-stu-id="14f22-150">Right-click the message schema and then click **Generate Instance**.</span></span>  
  
6. <span data-ttu-id="14f22-151">**EDI インスタンスのプロパティ**ダイアログ ボックスで、構成オプションをクリックしたこと、選択**OK**します。</span><span class="sxs-lookup"><span data-stu-id="14f22-151">In the **EDI Instance Properties** dialog box, select the configuration options that you want, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="14f22-152">内のメッセージがあることを確認、**出力**操作が成功したことを示すウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="14f22-152">Verify that there is a message in the **Output** window indicating that the operation succeeded.</span></span>  
  
8. <span data-ttu-id="14f22-153">ファイルを表示するには、キーを押して**コントロール**出力ウィンドウ内のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="14f22-153">To view the file, press **Control** and click the link in the Output window.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="14f22-154"> の [BizTalk エディター] ウィンドウにファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14f22-154"> will display the contents of the file in the BizTalk Editor window.</span></span>  
  
9. <span data-ttu-id="14f22-155">機能 EDI メッセージを作成する場合は、テキスト エディターで、メッセージにインターチェンジ ヘッダーとグループ ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="14f22-155">To make a functional EDI message, add the interchange and group headers to the message in a text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f22-156">参照</span><span class="sxs-lookup"><span data-stu-id="14f22-156">See Also</span></span>  
 <span data-ttu-id="14f22-157">[デザイン時 XML ツールを使用します。](../core/using-design-time-xml-tools.md) </span><span class="sxs-lookup"><span data-stu-id="14f22-157">[Using Design-Time XML Tools](../core/using-design-time-xml-tools.md) </span></span>  
 [<span data-ttu-id="14f22-158">インスタンスの検証 (EDI)</span><span class="sxs-lookup"><span data-stu-id="14f22-158">Validating an Instance (EDI)</span></span>](../core/validating-an-instance-edi.md)