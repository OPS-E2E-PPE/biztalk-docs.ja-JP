---
title: "Itinerary Designer での作業 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06742cb8-f6d6-46e2-adc0-6be9a3d6a447
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d54d742b883ec843d56610b25fdfb91371dbe4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="working-in-itinerary-designer"></a><span data-ttu-id="b0c68-102">Itinerary Designer での作業</span><span class="sxs-lookup"><span data-stu-id="b0c68-102">Working in Itinerary Designer</span></span>
<span data-ttu-id="b0c68-103">Microsoft Visual c# プロジェクトを作成した後は、新しい itinerary モデルを作成し、既存の日程をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-103">After you create a Microsoft Visual C# project, you can create new itinerary models and add existing itineraries to the project.</span></span> <span data-ttu-id="b0c68-104">次の手順では、新しい旅程を作成、既存の itinerary モデルを追加または日程の名前を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-104">The following steps describe how to create a new itinerary, add an existing itinerary model, or change the name of an itinerary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0c68-105">行程デザイナーを使用する前から Microsoft.Practices.ESB.CORE Windows インストーラー (.msi ファイル) をインストールする必要があります、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]フォルダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b0c68-105">Before working with the Itinerary Designer, you must install the Microsoft.Practices.ESB.CORE Windows Installer (.msi file) from the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] install folder.</span></span> <span data-ttu-id="b0c68-106">このステップでは、グローバル アセンブリ キャッシュに必要なランタイムのアセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b0c68-106">This step installs the required run-time assemblies to the global assembly cache.</span></span>  
  
## <a name="basic-operations"></a><span data-ttu-id="b0c68-107">基本的な操作</span><span class="sxs-lookup"><span data-stu-id="b0c68-107">Basic Operations</span></span>  

#### <a name="create-an-itinerary"></a><span data-ttu-id="b0c68-108">日程を作成します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-108">Create an itinerary</span></span>  
  
1.  <span data-ttu-id="b0c68-109">ソリューション エクスプ ローラーで、c# プロジェクトの名前を右クリックし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-109">In Solution Explorer, right-click the C# project name, point to **Add**, and then click **New Itinerary**.</span></span>  
  
2.  <span data-ttu-id="b0c68-110">**名前** ダイアログ ボックスの下部にあるボックスで、旅行計画の名前を入力し、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-110">In the **Name** box at the bottom of the dialog box, type the name for the itinerary, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0c68-111">新しい行程作成されて行程デザイナーに表示され、対応する .itinerary ファイルが作成され、ソリューション エクスプ ローラーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0c68-111">The new itinerary is created and displayed in Itinerary Designer, and a corresponding .itinerary file is created and displayed in Solution Explorer.</span></span>  
  
#### <a name="add-an-existing-itinerary-to-the-project"></a><span data-ttu-id="b0c68-112">既存の日程をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-112">Add an existing itinerary to the project</span></span>
  
1.  <span data-ttu-id="b0c68-113">ソリューション エクスプ ローラーで右クリックし、c# のプロジェクト名、 をポイント**追加**、クリックして**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-113">In Solution explorer, right click the C# project name, point to **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="b0c68-114">**既存項目の追加** ダイアログ ボックスが、itinerary を itinerary、クリックを含むディレクトリに移動し、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-114">In the **Add Existing Item** dialog box, navigate to the directory that contains the itinerary, click the itinerary, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0c68-115">旅行計画は、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b0c68-115">The itinerary is added to the project.</span></span>  
  
#### <a name="change-the-name-of-an-itinerary"></a><span data-ttu-id="b0c68-116">日程の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-116">Change the name of an itinerary</span></span>  
  
1.  <span data-ttu-id="b0c68-117">ソリューション エクスプ ローラーでファイルを右クリック、.itinerary、名前を変更し、をクリックする**の名前を変更**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-117">In Solution Explorer, right-click the .itinerary file you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="b0c68-118">新しいファイル名を入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-118">Type the new file name, and then press ENTER.</span></span>  
  
#### <a name="save-an-itinerary"></a><span data-ttu-id="b0c68-119">日程を保存します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-119">Save an itinerary</span></span>  
  
<span data-ttu-id="b0c68-120">**ファイル** メニューのをクリックして**保存\<itinerary 名 >**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-120">On the **File** menu, click **Save \<itinerary name>**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0c68-121">Itinerary ファイルは、対応する XML 形式での DSL モデルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="b0c68-121">Itinerary files are saved as DSL models in corresponding XML format.</span></span>  
  
#### <a name="set-itinerary-export-properties"></a><span data-ttu-id="b0c68-122">Itinerary エクスポート プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-122">Set itinerary export properties</span></span>  
  
1.  <span data-ttu-id="b0c68-123">[プロパティ] ウィンドウで次のように入力します。、**名前**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="b0c68-123">In the Properties window, type a **Name** property.</span></span>  
  
2.  <span data-ttu-id="b0c68-124">[プロパティ] ウィンドウで次のように入力します。、**バージョン**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="b0c68-124">In the Properties window, type a **Version** property.</span></span>  
  
3.  <span data-ttu-id="b0c68-125">プロパティ ウィンドウで、指定、**は要求の応答**プロパティのドロップダウン リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-125">In the Properties window, specify the **Is Request Response** property using the drop-down list.</span></span> <span data-ttu-id="b0c68-126">このプロパティを設定**true**場合、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]入り口と通信するクライアント アプリケーション要求-応答メッセージ交換パターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-126">Set this property to **true** if the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] client application communicates with an on-ramp using request-response message exchange pattern.</span></span>  
  
4.  <span data-ttu-id="b0c68-127">[プロパティ] ウィンドウで、設定、**エクスポート モード**プロパティを**既定**または**Strict**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-127">In the Properties window, set the **Export Mode** property to **Default** or **Strict**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0c68-128">作成するときに[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]旅程行程デザイナーを使用して、**エクスポート モード**サービスが実行されますを定義するプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0c68-128">When creating [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itineraries using the Itinerary Designer, the **Export Mode** property can be used to define where the service will execute.</span></span> <span data-ttu-id="b0c68-129">設定、**エクスポート モード**プロパティを**Strict** itinerary により指定されたコンテナー内で実行されます; XML 行程内の各 itinerary サービスのステージのプロパティがここをサービスを実行するパイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-129">Setting the **Export Mode** property to **Strict** ensures that the itinerary service executes in its prescribed container; in this case, each itinerary service in the XML itinerary has a stage property that specifies the pipeline in which the service executes.</span></span> <span data-ttu-id="b0c68-130">このプロパティ設定されている場合**既定**ありません段階を指定すると、日程 Microsoft ESB と互換性が作成、および itinerary サービスが、設定されている順番では必ずしも必要なパイプラインのステージでを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-130">If this property is set to **Default**, an itinerary compatible with Microsoft ESB is created, with no stage specified, and the itinerary service executes in the order prescribed, but not necessarily in the pipeline stage desired.</span></span>  
  
#### <a name="export-an-itinerary-to-a-file"></a><span data-ttu-id="b0c68-131">日程をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b0c68-131">Export an itinerary to a file</span></span>  
  
1.  <span data-ttu-id="b0c68-132">[プロパティ] ウィンドウでをクリックして**XML 行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="b0c68-132">In the Properties window, click **XML Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
2.  <span data-ttu-id="b0c68-133">[プロパティ] ウィンドウで、設定、**行程 XML ファイル**プロパティを新しい値にします。</span><span class="sxs-lookup"><span data-stu-id="b0c68-133">In the Properties window, set the **Itinerary XML file** property to a new value.</span></span>  
  
#### <a name="export-an-itinerary-to-a-database"></a><span data-ttu-id="b0c68-134">データベースに日程をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b0c68-134">Export an itinerary to a database</span></span>  
  
1.  <span data-ttu-id="b0c68-135">[プロパティ] ウィンドウでをクリックして**データベース行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="b0c68-135">In the Properties window, click **Database Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
2.  <span data-ttu-id="b0c68-136">[プロパティ] ウィンドウで、設定、**行程データベース**行程データベースを指す接続文字列のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="b0c68-136">In the Properties window, set the **Itinerary Database** property connection string to point to the itinerary database.</span></span>  
  
3.  <span data-ttu-id="b0c68-137">[プロパティ] ウィンドウで、設定、**行程ステータス**プロパティを**公開済み**または**配置済み**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-137">In the Properties window, set the **Itinerary Status** property to **Published** or **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0c68-138">日程を持つデータベースにエクスポートするときに**行程ステータス**に設定**Published**、itinerary を有効になりませんが、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] にプロパティを設定した後にするまでの時間を実行**展開**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-138">When an itinerary is exported to a database with **Itinerary Status** set to **Published**, the itinerary will not become effective for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] run time until after the property is set to **Deployed**.</span></span>  
  
## <a name="security-operations"></a><span data-ttu-id="b0c68-139">セキュリティの操作</span><span class="sxs-lookup"><span data-stu-id="b0c68-139">Security Operations</span></span>  
 <span data-ttu-id="b0c68-140">行程デザイナーを使用すると、パスワードおよびその他の資格情報に格納されているなど、機密性の高い情報を保護できます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary、X.509 証明書を使用してこの情報を暗号化することによりします。</span><span class="sxs-lookup"><span data-stu-id="b0c68-140">By using the Itinerary Designer, you can protect sensitive information, such as passwords and other credentials stored in a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary, by encrypting this information using X.509 certificates.</span></span>  
  
#### <a name="select-the-x509-certificate-for-an-itinerary"></a><span data-ttu-id="b0c68-141">日程の X.509 証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-141">Select the X.509 certificate for an itinerary</span></span>  
  
1.  <span data-ttu-id="b0c68-142">行程デザイナーのプロパティ ウィンドウで、展開、**暗号化証明書**プロパティをクリックして、**ストアの場所**ドロップダウン リストから、 **CurrentUser**または**LocalMachine**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-142">In the Itinerary Designer Properties window, expand the **Encryption Certificate** property, and then click the **Store Location** drop-down list, and select the **CurrentUser** or **LocalMachine**.</span></span> <span data-ttu-id="b0c68-143">これにより、X.509 証明書ストアが現在のユーザーまたはローカル コンピューターに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="b0c68-143">This associates the X.509 certificate store with the current user or the local computer.</span></span>  
  
2.  <span data-ttu-id="b0c68-144">[プロパティ] ウィンドウ、**ストア名**ドロップダウン リストと、証明書ストアに対応する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-144">In the Properties window, click the **Store Name** drop-down list and select the value which corresponds to your certificate store.</span></span>  
  
3.  <span data-ttu-id="b0c68-145">プロパティ ウィンドウで、暗号化証明書プロパティの横にある省略記号ボタン (...) をクリックし、選択、 **X.509 証明書**で、**証明書の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b0c68-145">In the Properties window, click the ellipsis button (...) next to the Encryption Certificate property, and then select the **X.509 certificate** in the **Select Certificate** dialog box.</span></span>  
  
#### <a name="remove-the-x509-certificate-from-an-itinerary"></a><span data-ttu-id="b0c68-146">日程から X.509 証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="b0c68-146">Remove the X.509 certificate from an itinerary</span></span>  
  
-   <span data-ttu-id="b0c68-147">行程デザイナーのプロパティ ウィンドウで、展開、**暗号化証明書**プロパティ、および設定、**ストアの場所**プロパティを別の値。</span><span class="sxs-lookup"><span data-stu-id="b0c68-147">In the Itinerary Designer Properties window, expand the **Encryption Certificate** property, and then set the **Store Location** property to a different value.</span></span> <span data-ttu-id="b0c68-148">これで、古い証明書の関連付けを解除、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary モデル。</span><span class="sxs-lookup"><span data-stu-id="b0c68-148">This disassociates the old certificate with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary model.</span></span>  
  
#### <a name="disable-the-x509-certificate-validation"></a><span data-ttu-id="b0c68-149">X.509 証明書の検証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b0c68-149">Disable the X.509 certificate validation</span></span>  
  
<span data-ttu-id="b0c68-150">レジストリ エディターでは、サブキーに移動**hkey_local_machine ESB Toolkit\2.0\Designer**、し、設定、 **RequireX509Certificate**プロパティの値を**false**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-150">In the Registry Editor, go to the subkey **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**, and then set the **RequireX509Certificate** property value to **false**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0c68-151">インストールした場合、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サブキーは、64 ビット サポートしているオペレーティング システムで**HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**です。</span><span class="sxs-lookup"><span data-stu-id="b0c68-151">If you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] on an operating system that has 64-bit support, the subkey is **HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**.</span></span>