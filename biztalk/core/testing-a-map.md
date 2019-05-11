---
title: マップのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 265afd62-3c1d-4b9a-9f51-176b9b079241
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a40963bffc97fa2b1057331a3adda3e846b039e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299296"
---
# <a name="testing-a-map"></a><span data-ttu-id="b660f-102">マップのテスト</span><span class="sxs-lookup"><span data-stu-id="b660f-102">Testing a Map</span></span>
<span data-ttu-id="b660f-103">デザイン時に EDI プロジェクトのマップをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="b660f-103">You can test a map in an EDI project at design time.</span></span> <span data-ttu-id="b660f-104">それには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の XML ツール拡張を使用します。</span><span class="sxs-lookup"><span data-stu-id="b660f-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="b660f-105">このトピックでは、設定して使用する方法を説明します、**マップのテスト**XML ツール拡張の機能です。</span><span class="sxs-lookup"><span data-stu-id="b660f-105">This topic describes how to set up and use the **Test Map** feature of the XML Tool extension.</span></span>  
  
 <span data-ttu-id="b660f-106">ソース ドキュメントを指定して、フォルダーを指定することでマップのテスト場所[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](架空のデータを生成したインスタンスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="b660f-106">You test a map by specifying a source document and specifying a folder where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will save a generated instance (with fictitious data).</span></span> <span data-ttu-id="b660f-107">区切り記号を設定する必要があるを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソース ドキュメントを処理し、EDI スキーマに従って送信先ドキュメントの生成に使用します。</span><span class="sxs-lookup"><span data-stu-id="b660f-107">You need to set the delimiters that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to process the source document and generate the destination document according to EDI schemas.</span></span> <span data-ttu-id="b660f-108">これは、すべての値は true、 **TestMap**入力プロパティのマップのプロパティ ページ。**インスタンスの生成**、 **XML**、または**ネイティブ**します。</span><span class="sxs-lookup"><span data-stu-id="b660f-108">This is true for all values of the **TestMap** input property in the map's property pages: **Generate Instance**, **XML**, or **Native**.</span></span> <span data-ttu-id="b660f-109">True に設定**インスタンスの生成**ため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にどのような区切り記号を使用して、インスタンスを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b660f-109">It is true for **Generate Instance** because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] needs to know what delimiters to use to generate the instance.</span></span> <span data-ttu-id="b660f-110">True に設定**XML**または**ネイティブ**ため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ネイティブのフラット ファイルまたは XML ファイルを解釈する方法を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b660f-110">It is true for **XML** or **Native** because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] needs to know how to interpret the native flat file or the XML file.</span></span> <span data-ttu-id="b660f-111">区切り記号を設定する必要がありますを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]出力ファイルを生成するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b660f-111">You also need to set the delimiters that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use when generating the output file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b660f-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="b660f-112">Prerequisites</span></span>  
 <span data-ttu-id="b660f-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b660f-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-test-a-map"></a><span data-ttu-id="b660f-114">マップをテストします。</span><span class="sxs-lookup"><span data-stu-id="b660f-114">To test a map</span></span>  
  
1. <span data-ttu-id="b660f-115">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトにテストするマップを追加して、そのマップの元と送信先スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b660f-115">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], add the map that you want to test to a project, and add the source and destination schemas for that map to the project.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b660f-116">マップをテストするプロジェクトをビルドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b660f-116">You do not have to build the project to test the map.</span></span>  
  
2. <span data-ttu-id="b660f-117">マップを右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="b660f-117">Right-click the map and click **Properties**.</span></span>  
  
3. <span data-ttu-id="b660f-118">**プロパティ**ウィンドウで、設定**TestMap 入力の検証**に**True**送信元スキーマに対して入力ファイルを検証する場合。</span><span class="sxs-lookup"><span data-stu-id="b660f-118">In the **Properties** window, set **Validate TestMap Input** to **True** if you want to validate the input file against the source schema.</span></span> <span data-ttu-id="b660f-119">設定**TestMap 出力の検証**に**True**送信先スキーマを出力ファイルを検証する場合。</span><span class="sxs-lookup"><span data-stu-id="b660f-119">Set **Validate TestMap Output** to **True** if you want to validate the output file against the destination schema.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b660f-120">使用してマップをテストする場合、 **TestMap の入力**プロパティに設定**ネイティブ**と**TestMap 入力の検証**と**TestMap 出力の検証**プロパティを設定**False**検証は実行されます。</span><span class="sxs-lookup"><span data-stu-id="b660f-120">If you test a map with the **TestMap Input** property set to **Native** and the **Validate TestMap Input** and **Validate TestMap Output** properties set to **False**, validation will still be performed.</span></span> <span data-ttu-id="b660f-121">これは、ネイティブ形式の入力ファイルは、XML 形式に変換するために発生し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマに対して XML を検証します。</span><span class="sxs-lookup"><span data-stu-id="b660f-121">This occurs because the native-formatted input file will be converted into XML format, and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will validate the XML against the schema.</span></span> <span data-ttu-id="b660f-122">検証メカニズムによってエラーが通知される場合でも入力インスタンスに検証の問題がある場合、 **TestMap 入力の検証**と**TestMap 出力の検証**にプロパティが設定されて**False**します。</span><span class="sxs-lookup"><span data-stu-id="b660f-122">If there are validation issues in the input instance, the validation mechanism will post errors, even though the **Validate TestMap Input** and **Validate TestMap Output** properties are set to **False**.</span></span>  
  
4. <span data-ttu-id="b660f-123">設定**TestMap の入力**に**ネイティブ**.edi 拡張子を持つ入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="b660f-123">Set **TestMap Input** to **Native** for an input file that has an .edi extension.</span></span> <span data-ttu-id="b660f-124">設定**XML** .xml 拡張子がある場合。</span><span class="sxs-lookup"><span data-stu-id="b660f-124">Set it to **XML** if it has an .xml extension.</span></span> <span data-ttu-id="b660f-125">設定**TestMap の入力**に**インスタンスの生成**が[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]入力インスタンスを手動で指定することではなく、入力のインスタンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="b660f-125">Set **TestMap Input** to **Generate Instance** to have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generate an input instance, rather than you designating an input instance manually.</span></span>  
  
5. <span data-ttu-id="b660f-126">設定**TestMap 出力**に**ネイティブ**.edi 拡張子を持つ出力ファイル。</span><span class="sxs-lookup"><span data-stu-id="b660f-126">Set **TestMap Output** to **Native** for an output file that has an .edi extension.</span></span> <span data-ttu-id="b660f-127">設定**XML** .xml 拡張子がある場合。</span><span class="sxs-lookup"><span data-stu-id="b660f-127">Set it to **XML** if it has an .xml extension.</span></span>  
  
6. <span data-ttu-id="b660f-128">**TestMap の入力インスタンス**、マップをテストして、それを選択するために使用する入力インスタンスに移動し、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="b660f-128">For **TestMap Input Instance**, browse to the input instance that you want to be used to test the map, select it, and then **Open**.</span></span> <span data-ttu-id="b660f-129">このプロパティを空白のままにする場合は、設定**TestMap の入力**に**インスタンスの生成**します。</span><span class="sxs-lookup"><span data-stu-id="b660f-129">If you want to leave this property blank, set **TestMap Input** to **Generate Instance**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b660f-130">いずれかの入力インスタンスを指定する必要が**TestMap の入力インスタンス**設定または**TestMap の入力**に**インスタンスの生成**します。</span><span class="sxs-lookup"><span data-stu-id="b660f-130">You have to either designate an input instance for **TestMap Input Instance** or set **TestMap Input** to **Generate Instance**.</span></span> <span data-ttu-id="b660f-131">ない場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b660f-131">If not, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate an error.</span></span>  
  
7. <span data-ttu-id="b660f-132">**TestMap 出力インスタンス**、参照を保存する出力インスタンスの出力インスタンスの名前を入力し、をクリックする場所に**保存**します。</span><span class="sxs-lookup"><span data-stu-id="b660f-132">For **TestMap Output Instance**, browse to the location you want to save the output instance at, enter a name for the output instance, and then click **Save**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b660f-133">出力インスタンスを指定しない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は出力ファイルを作成、フォルダーに出力ファイルを配置およびファイル名とパスを示します。</span><span class="sxs-lookup"><span data-stu-id="b660f-133">If you do not designate an output instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will create an output file, place the output file into a folder, and indicate the file name and path.</span></span>  
  
8. <span data-ttu-id="b660f-134">テストをクリックしたマップを右クリックして**マップのテスト**します。</span><span class="sxs-lookup"><span data-stu-id="b660f-134">Right-click the map you are testing, and then click **Test Map**.</span></span>  
  
9. <span data-ttu-id="b660f-135">X12 で**EDI インスタンスのプロパティ** ダイアログ ボックスで、すべてのプロパティが入力と出力インスタンスの設定に整合性があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b660f-135">In the X12 **EDI Instance Properties** dialog box, make sure that all properties are consistent with the settings for the input and output instances.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b660f-136">表示されます、 **EDI インスタンスのプロパティ**TestMap プロセス中に 2 回のダイアログ ボックス: 入力メッセージ インスタンスの解釈で 1 回は出力メッセージ インスタンスを生成するためです。</span><span class="sxs-lookup"><span data-stu-id="b660f-136">will display the **EDI Instance Properties** dialog box twice during the TestMap process: once for interpreting the input message instance and once for generating the output message instance.</span></span> <span data-ttu-id="b660f-137">ただし、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 3 回以上、ダイアログ ボックスを表示し、EDI スキーマ以外のダイアログ ボックスを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="b660f-137">However, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may display the dialog box more than just twice and may display the dialog box for non-EDI schema.</span></span> <span data-ttu-id="b660f-138">そうである場合にクリックします**OK**ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b660f-138">If so, click **OK** to close the dialog box.</span></span>  
  
10. <span data-ttu-id="b660f-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b660f-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b660f-140">参照</span><span class="sxs-lookup"><span data-stu-id="b660f-140">See Also</span></span>  
 [<span data-ttu-id="b660f-141">デザイン時 XML ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="b660f-141">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)