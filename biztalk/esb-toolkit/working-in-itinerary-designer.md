---
title: Itinerary Designer での作業 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06742cb8-f6d6-46e2-adc0-6be9a3d6a447
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8efcc93d77f24b86a6a5ba8680f35afea815c5b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396343"
---
# <a name="working-in-itinerary-designer"></a><span data-ttu-id="9e01b-102">Itinerary Designer での作業</span><span class="sxs-lookup"><span data-stu-id="9e01b-102">Working in Itinerary Designer</span></span>
<span data-ttu-id="9e01b-103">Microsoft Visual c# プロジェクトを作成した後は、スケジュールの新しいモデルを作成し、プロジェクトに既存のスケジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-103">After you create a Microsoft Visual C# project, you can create new itinerary models and add existing itineraries to the project.</span></span> <span data-ttu-id="9e01b-104">次の手順では、新しいスケジュールを作成、スケジュールの既存のモデルを追加またはスケジュールの名前を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-104">The following steps describe how to create a new itinerary, add an existing itinerary model, or change the name of an itinerary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e01b-105">旅行プラン デザイナーを使用する前から Microsoft.Practices.ESB.CORE Windows インストーラー (.msi ファイル) をインストールする必要があります、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]フォルダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9e01b-105">Before working with the Itinerary Designer, you must install the Microsoft.Practices.ESB.CORE Windows Installer (.msi file) from the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] install folder.</span></span> <span data-ttu-id="9e01b-106">この手順では、グローバル アセンブリ キャッシュに必要なランタイムのアセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9e01b-106">This step installs the required run-time assemblies to the global assembly cache.</span></span>  
  
## <a name="basic-operations"></a><span data-ttu-id="9e01b-107">基本的な操作</span><span class="sxs-lookup"><span data-stu-id="9e01b-107">Basic Operations</span></span>  

#### <a name="create-an-itinerary"></a><span data-ttu-id="9e01b-108">スケジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-108">Create an itinerary</span></span>  
  
1.  <span data-ttu-id="9e01b-109">ソリューション エクスプ ローラーで、c# のプロジェクト名を右クリックして**追加**、 をクリックし、**新しい行程**。</span><span class="sxs-lookup"><span data-stu-id="9e01b-109">In Solution Explorer, right-click the C# project name, point to **Add**, and then click **New Itinerary**.</span></span>  
  
2.  <span data-ttu-id="9e01b-110">**名前** ダイアログ ボックスの下部にあるボックスで、スケジュールの名前を入力し、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-110">In the **Name** box at the bottom of the dialog box, type the name for the itinerary, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e01b-111">新しいスケジュールが作成され、旅行プランのデザイナーに表示されると、対応する .itinerary ファイルが作成され、ソリューション エクスプ ローラーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e01b-111">The new itinerary is created and displayed in Itinerary Designer, and a corresponding .itinerary file is created and displayed in Solution Explorer.</span></span>  
  
#### <a name="add-an-existing-itinerary-to-the-project"></a><span data-ttu-id="9e01b-112">既存のスケジュールをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-112">Add an existing itinerary to the project</span></span>
  
1.  <span data-ttu-id="9e01b-113">ソリューション エクスプ ローラーで右クリックで、c# のプロジェクト名をポイントして**追加**、 をクリックし、**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-113">In Solution explorer, right click the C# project name, point to **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="9e01b-114">**既存項目の追加** ダイアログ ボックスでは、旅行プランを itinerary、クリックを格納するディレクトリに移動し、順にクリックします**追加**します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-114">In the **Add Existing Item** dialog box, navigate to the directory that contains the itinerary, click the itinerary, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e01b-115">旅行プランは、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="9e01b-115">The itinerary is added to the project.</span></span>  
  
#### <a name="change-the-name-of-an-itinerary"></a><span data-ttu-id="9e01b-116">スケジュールの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-116">Change the name of an itinerary</span></span>  
  
1.  <span data-ttu-id="9e01b-117">ソリューション エクスプ ローラーでクリックして、名前を変更する .itinerary ファイルを右クリックして**の名前を変更**します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-117">In Solution Explorer, right-click the .itinerary file you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="9e01b-118">新しいファイル名を入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-118">Type the new file name, and then press ENTER.</span></span>  
  
#### <a name="save-an-itinerary"></a><span data-ttu-id="9e01b-119">スケジュールを保存します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-119">Save an itinerary</span></span>  
  
<span data-ttu-id="9e01b-120">**ファイル** メニューのをクリックして**保存\<itinerary 名前\>** します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-120">On the **File** menu, click **Save \<itinerary name\>**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e01b-121">スケジュール オンランプ ファイルは、対応する XML 形式で DSL モデルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="9e01b-121">Itinerary files are saved as DSL models in corresponding XML format.</span></span>  
  
#### <a name="set-itinerary-export-properties"></a><span data-ttu-id="9e01b-122">スケジュール オンランプ エクスポート プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-122">Set itinerary export properties</span></span>  
  
1. <span data-ttu-id="9e01b-123">プロパティ ウィンドウで、入力、**名前**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9e01b-123">In the Properties window, type a **Name** property.</span></span>  
  
2. <span data-ttu-id="9e01b-124">プロパティ ウィンドウで、入力、**バージョン**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9e01b-124">In the Properties window, type a **Version** property.</span></span>  
  
3. <span data-ttu-id="9e01b-125">プロパティ ウィンドウで、指定、**は要求の応答**プロパティのドロップダウン リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-125">In the Properties window, specify the **Is Request Response** property using the drop-down list.</span></span> <span data-ttu-id="9e01b-126">このプロパティを設定**true**場合、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]入り口とクライアント アプリケーションが通信する要求-応答メッセージ交換パターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-126">Set this property to **true** if the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] client application communicates with an on-ramp using request-response message exchange pattern.</span></span>  
  
4. <span data-ttu-id="9e01b-127">[プロパティ] ウィンドウで次のように設定します。、**エクスポート モード**プロパティを**既定**または**Strict**します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-127">In the Properties window, set the **Export Mode** property to **Default** or **Strict**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9e01b-128">作成するときに[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]日程、旅行プラン デザイナーを使用して、**エクスポート モード**サービスを実行する場所を定義するプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e01b-128">When creating [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itineraries using the Itinerary Designer, the **Export Mode** property can be used to define where the service will execute.</span></span> <span data-ttu-id="9e01b-129">設定、**エクスポート モード**プロパティを**Strict**旅行計画により、規定されたコンテナー内で実行されます XML 行程で各スケジュール サービスのステージのプロパティがここでは、を。サービスが実行されるパイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-129">Setting the **Export Mode** property to **Strict** ensures that the itinerary service executes in its prescribed container; in this case, each itinerary service in the XML itinerary has a stage property that specifies the pipeline in which the service executes.</span></span> <span data-ttu-id="9e01b-130">このプロパティ設定されている場合**既定**、指定されていない段階に、Microsoft ESB と互換性のあるスケジュールが作成され、規定されている順序で、必要なパイプラインのステージでは必ずしもスケジュール サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-130">If this property is set to **Default**, an itinerary compatible with Microsoft ESB is created, with no stage specified, and the itinerary service executes in the order prescribed, but not necessarily in the pipeline stage desired.</span></span>  
  
#### <a name="export-an-itinerary-to-a-file"></a><span data-ttu-id="9e01b-131">日程をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="9e01b-131">Export an itinerary to a file</span></span>  
  
1.  <span data-ttu-id="9e01b-132">[プロパティ] ウィンドウで次のようにクリックします。 **XML 行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="9e01b-132">In the Properties window, click **XML Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
2.  <span data-ttu-id="9e01b-133">[プロパティ] ウィンドウで次のように設定します。、**旅行プラン XML ファイル**プロパティを新しい値。</span><span class="sxs-lookup"><span data-stu-id="9e01b-133">In the Properties window, set the **Itinerary XML file** property to a new value.</span></span>  
  
#### <a name="export-an-itinerary-to-a-database"></a><span data-ttu-id="9e01b-134">日程をデータベースにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="9e01b-134">Export an itinerary to a database</span></span>  
  
1. <span data-ttu-id="9e01b-135">[プロパティ] ウィンドウで次のようにクリックします。**データベース行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="9e01b-135">In the Properties window, click **Database Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
2. <span data-ttu-id="9e01b-136">[プロパティ] ウィンドウで次のように設定します。、**行程データベース**行程データベースを指す接続文字列のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9e01b-136">In the Properties window, set the **Itinerary Database** property connection string to point to the itinerary database.</span></span>  
  
3. <span data-ttu-id="9e01b-137">[プロパティ] ウィンドウで次のように設定します。、**行程状態**プロパティを**Published**または**配置済み**。</span><span class="sxs-lookup"><span data-stu-id="9e01b-137">In the Properties window, set the **Itinerary Status** property to **Published** or **Deployed**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9e01b-138">データベースに、旅行プランをエクスポートするときに**行程状態**に設定**発行済み**、有効にならないスケジュールは、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] に、プロパティの設定後までの時間を実行**デプロイされた**します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-138">When an itinerary is exported to a database with **Itinerary Status** set to **Published**, the itinerary will not become effective for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] run time until after the property is set to **Deployed**.</span></span>  
  
## <a name="security-operations"></a><span data-ttu-id="9e01b-139">セキュリティの操作</span><span class="sxs-lookup"><span data-stu-id="9e01b-139">Security Operations</span></span>  
 <span data-ttu-id="9e01b-140">格納されているパスワードおよびその他の資格情報など、旅行プラン デザイナーを使用して、機密情報を保護することができます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] X.509 証明書を使用してこの情報を暗号化することで、スケジュールします。</span><span class="sxs-lookup"><span data-stu-id="9e01b-140">By using the Itinerary Designer, you can protect sensitive information, such as passwords and other credentials stored in a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary, by encrypting this information using X.509 certificates.</span></span>  
  
#### <a name="select-the-x509-certificate-for-an-itinerary"></a><span data-ttu-id="9e01b-141">スケジュールを X.509 証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-141">Select the X.509 certificate for an itinerary</span></span>  
  
1.  <span data-ttu-id="9e01b-142">旅行プラン デザイナーのプロパティ ウィンドウで、**暗号化証明書**プロパティ、およびクリック、**ストアの場所**ドロップダウン リスト、および選択、 **CurrentUser**または**LocalMachine**します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-142">In the Itinerary Designer Properties window, expand the **Encryption Certificate** property, and then click the **Store Location** drop-down list, and select the **CurrentUser** or **LocalMachine**.</span></span> <span data-ttu-id="9e01b-143">これにより、X.509 証明書ストアが、現在のユーザーまたはローカル コンピューターに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="9e01b-143">This associates the X.509 certificate store with the current user or the local computer.</span></span>  
  
2.  <span data-ttu-id="9e01b-144">[プロパティ] ウィンドウ、**ストア名**ドロップダウン リストと、証明書ストアに対応する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-144">In the Properties window, click the **Store Name** drop-down list and select the value which corresponds to your certificate store.</span></span>  
  
3.  <span data-ttu-id="9e01b-145">プロパティ ウィンドウで、暗号化証明書のプロパティの横にある省略記号ボタン (…) をクリックし、選択、 **X.509 証明書**で、**証明書の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9e01b-145">In the Properties window, click the ellipsis button (...) next to the Encryption Certificate property, and then select the **X.509 certificate** in the **Select Certificate** dialog box.</span></span>  
  
#### <a name="remove-the-x509-certificate-from-an-itinerary"></a><span data-ttu-id="9e01b-146">日程から X.509 証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-146">Remove the X.509 certificate from an itinerary</span></span>  
  
- <span data-ttu-id="9e01b-147">旅行プラン デザイナーのプロパティ ウィンドウで、**暗号化証明書**プロパティ、および設定して、**ストアの場所**プロパティを別の値。</span><span class="sxs-lookup"><span data-stu-id="9e01b-147">In the Itinerary Designer Properties window, expand the **Encryption Certificate** property, and then set the **Store Location** property to a different value.</span></span> <span data-ttu-id="9e01b-148">これで、古い証明書の関連付けを解除、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary モデル。</span><span class="sxs-lookup"><span data-stu-id="9e01b-148">This disassociates the old certificate with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary model.</span></span>  
  
#### <a name="disable-the-x509-certificate-validation"></a><span data-ttu-id="9e01b-149">X.509 証明書の検証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="9e01b-149">Disable the X.509 certificate validation</span></span>  
  
<span data-ttu-id="9e01b-150">レジストリ エディターでは、サブキーに移動**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**、し、設定、 **RequireX509Certificate**プロパティの値を**false**します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-150">In the Registry Editor, go to the subkey **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**, and then set the **RequireX509Certificate** property value to **false**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e01b-151">インストールした場合、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サブキーは、64 ビット サポートしているオペレーティング システムで**HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**します。</span><span class="sxs-lookup"><span data-stu-id="9e01b-151">If you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] on an operating system that has 64-bit support, the subkey is **HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**.</span></span>