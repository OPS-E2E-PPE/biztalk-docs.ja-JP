---
title: 'チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用してデータを送信する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1912d594-3839-4e04-bc40-93bd7cc0b309
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19cf0dee6bfc4535e627b6cfccfb0c0babaee909
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975387"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-send-data"></a><span data-ttu-id="8fc60-102">チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用したデータの送信</span><span class="sxs-lookup"><span data-stu-id="8fc60-102">Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Send Data</span></span>
<span data-ttu-id="8fc60-103">BizTalk Adapter for TIBCO Enterprise Message Service (EMS) を使用して TIBCO システムにデータを送信できます。</span><span class="sxs-lookup"><span data-stu-id="8fc60-103">You can use the BizTalk Adapter for TIBCO Enterprise Message Service (EMS) to send data to a TIBCO system.</span></span> <span data-ttu-id="8fc60-104">このチュートリアルでは、これを示す SDK サンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="8fc60-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="8fc60-105">Prerequisites</span></span>  

- <span data-ttu-id="8fc60-106">BizTalk Adapter for TIBCO EMS を使用するには、TIBCO EMS C# API の TIBCO.EMS.dll をグローバル アセンブリ キャッシュ (GAC) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc60-106">BizTalk Adapter for TIBCO EMS requires that you add the TIBCO EMS C# API, TIBCO.EMS.dll, to the global assembly cache (GAC).</span></span> <span data-ttu-id="8fc60-107">アセンブリのインストールの詳細については、次を参照してください。 [TIBCO Enterprise Message Service の要件と制限事項](../core/tibco-enterprise-message-service-requirements-and-limitations.md)します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-107">For more information about installing the assembly, see [TIBCO Enterprise Message Service Requirements and Limitations](../core/tibco-enterprise-message-service-requirements-and-limitations.md).</span></span>  

- <span data-ttu-id="8fc60-108">このサンプルをビルドして展開するには、アダプターが実行されている [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="8fc60-108">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="8fc60-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="8fc60-109">What This Sample Does</span></span>  
 <span data-ttu-id="8fc60-110">このサンプルでは、ファイル フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for TIBCO Enterprise Message Service を使用して TIBCO システム内にレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-110">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Enterprise Message Service to create a record in the TIBCO system.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="8fc60-111">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="8fc60-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="8fc60-112">このサンプルは、Visual Studio でデザインでは、BizTalk オーケストレーションで TIBCO Enterprise Message Service の BizTalk アダプターを使用した基本機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="8fc60-112">This sample, designed in Visual Studio, illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="8fc60-113">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="8fc60-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="8fc60-114">このサンプルの既定の場所は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8fc60-114">The default location for the sample is</span></span>  

 <span data-ttu-id="8fc60-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWaySend</span><span class="sxs-lookup"><span data-stu-id="8fc60-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWaySend</span></span>  

 <span data-ttu-id="8fc60-116">次の表に、サンプル内のファイルとその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-116">The following table lists and describes the files in the sample.</span></span>  

|<span data-ttu-id="8fc60-117">**ランタイム プロジェクト ファイル名**</span><span class="sxs-lookup"><span data-stu-id="8fc60-117">**Runtime Project Filename**</span></span>|<span data-ttu-id="8fc60-118">**ランタイム プロジェクト ファイルの説明**</span><span class="sxs-lookup"><span data-stu-id="8fc60-118">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="8fc60-119">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="8fc60-119">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="8fc60-120">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="8fc60-120">OneWaySend.sln</span></span>|<span data-ttu-id="8fc60-121">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="8fc60-121">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="8fc60-122">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="8fc60-122">Schema.xsd</span></span>|<span data-ttu-id="8fc60-123">アプリケーションのスキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="8fc60-123">Schema file for the application.</span></span>|  
|<span data-ttu-id="8fc60-124">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="8fc60-124">Orchestration.odx</span></span>|<span data-ttu-id="8fc60-125">アプリケーションが使用するオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="8fc60-125">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="8fc60-126">TIBCOEMSOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="8fc60-126">TIBCOEMSOneWaySend.snk</span></span>|<span data-ttu-id="8fc60-127">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="8fc60-127">The strong naming key file.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="8fc60-128">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="8fc60-128">How to Use This Sample</span></span>  

#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a><span data-ttu-id="8fc60-129">BizTalk Adapter for TIBCO EMS の新しいインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="8fc60-129">Create a new instance of the BizTalk Adapter for TIBCO EMS</span></span>  

1. <span data-ttu-id="8fc60-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを起動します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-130">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="8fc60-131">クリックして**開始**、**すべてのプログラム**、 **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-131">Click **Start**, **All Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="8fc60-132">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順にクリックします**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-132">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3. <span data-ttu-id="8fc60-133">右クリック**アダプター**  をポイント**新規**、**アダプター**を表示する、**アダプター プロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="8fc60-133">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  

4. <span data-ttu-id="8fc60-134">値を入力、**名前**フィールドに、たとえば**TIBCO EMS**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-134">Enter a value for the **Name** field, for example **TIBCO EMS**.</span></span>  

5. <span data-ttu-id="8fc60-135">選択**TIBCO Enterprise Message System**で利用可能なアダプターの一覧から、**アダプター**ドロップダウンをクリック **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="8fc60-135">Select **TIBCO Enterprise Message System** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="8fc60-136">BizTalk 送信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="8fc60-136">Create a BizTalk Send Port</span></span>  

1. <span data-ttu-id="8fc60-137">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、] をクリック**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-137">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="8fc60-138">右クリックして**送信ポート** をポイント**新規**、**静的な一方向送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="8fc60-138">Right-click **Send Ports** and point to **New**, **Static One-way Send Port** to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="8fc60-139">値を入力、**名前**フィールドに、たとえば**TIBCOEMSOneWaySP**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-139">Enter a value for the **Name** field, for example **TIBCOEMSOneWaySP**.</span></span>  

4. <span data-ttu-id="8fc60-140">使用可能なアダプターの一覧から TIBCO EMS アダプターを選択、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートのプロパティ**ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8fc60-140">Select the TIBCO EMS adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="8fc60-141">この値は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで TIBCO Enterprise Message System アダプターを作成したときに指定された名前です。</span><span class="sxs-lookup"><span data-stu-id="8fc60-141">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

5. <span data-ttu-id="8fc60-142">値を入力、**サーバー接続の定義**:</span><span class="sxs-lookup"><span data-stu-id="8fc60-142">Enter values for the **Server Connection definition**:</span></span>  


   | <span data-ttu-id="8fc60-143">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="8fc60-143">**Property**</span></span> |                                <span data-ttu-id="8fc60-144">**[値]**</span><span class="sxs-lookup"><span data-stu-id="8fc60-144">**Value**</span></span>                                |
   |--------------|-------------------------------------------------------------------------|
   | <span data-ttu-id="8fc60-145">[Destination]</span><span class="sxs-lookup"><span data-stu-id="8fc60-145">Destination</span></span>  |               <span data-ttu-id="8fc60-146">サーバーの送信先キューまたはトピック名。</span><span class="sxs-lookup"><span data-stu-id="8fc60-146">The server destination queue or topic name.</span></span>               |
   | <span data-ttu-id="8fc60-147">[ポート番号]</span><span class="sxs-lookup"><span data-stu-id="8fc60-147">Port number</span></span>  | <span data-ttu-id="8fc60-148">TIBCO サーバーが待ち受けしているポート。</span><span class="sxs-lookup"><span data-stu-id="8fc60-148">The port on which the TIBCO server is listening.</span></span> <span data-ttu-id="8fc60-149">既定値は 7222 です。</span><span class="sxs-lookup"><span data-stu-id="8fc60-149">Default value is 7222.</span></span> |
   | <span data-ttu-id="8fc60-150">[サーバー名]</span><span class="sxs-lookup"><span data-stu-id="8fc60-150">Server Name</span></span>  |                    <span data-ttu-id="8fc60-151">TIBCO EMS サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="8fc60-151">The name of the TIBCO EMS server.</span></span>                    |


6. <span data-ttu-id="8fc60-152">値を入力、**ユーザーの資格情報**:</span><span class="sxs-lookup"><span data-stu-id="8fc60-152">Enter values for the **User Credentials**:</span></span>  

   |<span data-ttu-id="8fc60-153">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="8fc60-153">**Property**</span></span>|<span data-ttu-id="8fc60-154">**[値]**</span><span class="sxs-lookup"><span data-stu-id="8fc60-154">**Value**</span></span>|  
   |------------------|---------------|  
   |<span data-ttu-id="8fc60-155">パスワード</span><span class="sxs-lookup"><span data-stu-id="8fc60-155">Password</span></span>|<span data-ttu-id="8fc60-156">TIBCO EMS サーバーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="8fc60-156">The password for the TIBCO EMS server.</span></span>|  
   |<span data-ttu-id="8fc60-157">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="8fc60-157">User name</span></span>|<span data-ttu-id="8fc60-158">TIBCO EMS サーバーのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="8fc60-158">The user name for the TIBCO EMS server.</span></span>|  

    <span data-ttu-id="8fc60-159">プロパティの詳細については、次を参照してください。[作成 TIBCO Enterprise Message Service 送信ハンドラー](../core/creating-tibco-enterprise-message-service-send-handlers.md)します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-159">For more information about the properties, see [Creating  TIBCO Enterprise Message Service Send Handlers](../core/creating-tibco-enterprise-message-service-send-handlers.md).</span></span>  

7. <span data-ttu-id="8fc60-160">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fc60-160">Click **OK**.</span></span>  

8. <span data-ttu-id="8fc60-161">選択、 **XML Transmit**で利用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン をクリック**OK**。</span><span class="sxs-lookup"><span data-stu-id="8fc60-161">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

9. <span data-ttu-id="8fc60-162">送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-162">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-file-receive-port"></a><span data-ttu-id="8fc60-163">ファイル受信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="8fc60-163">Create a file receive port</span></span>  

1. <span data-ttu-id="8fc60-164">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、] をクリック**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-164">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2. <span data-ttu-id="8fc60-165">受信ポート フォルダーを右クリックし、をクリックし、**新規**、**一方向の受信ポート**受信ポートのプロパティ ダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-165">Right-click the Receive Ports folder and then click **New**, **One-way Receive Port** to display the Receive Port Properties dialog.</span></span>  

3. <span data-ttu-id="8fc60-166">値を入力、**名前**フィールドに**TIBCOEMSOneWayFileRP**、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-166">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileRP**, and click **OK**.</span></span>  

#### <a name="create-a-file-receive-location"></a><span data-ttu-id="8fc60-167">ファイル受信場所を作成する</span><span class="sxs-lookup"><span data-stu-id="8fc60-167">Create a file receive location</span></span>  

1.  <span data-ttu-id="8fc60-168">監視対象のファイル受信場所となるフォルダー (たとえば C:\Filesource) を作成します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-168">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  

2.  <span data-ttu-id="8fc60-169">右クリックし、新しい受信ポート をクリックし、**新規**、**受信場所**を表示する、**受信場所のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="8fc60-169">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="8fc60-170">値を入力、**名前**フィールドに、たとえば**TIBCOEMSOneWayFileRL**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-170">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileRL**.</span></span>  

4.  <span data-ttu-id="8fc60-171">選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8fc60-171">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="8fc60-172">先ほど作成したフォルダーの場所を入力、**受信フォルダー**プロパティをクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-172">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="8fc60-173">選択**XMLReceive**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン ボックスし、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="8fc60-173">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="8fc60-174">受信場所を右クリックし、をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-174">Right-click the receive location and click **Enable**.</span></span>  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="8fc60-175">アダプター スキーマからドキュメント インスタンスを生成する</span><span class="sxs-lookup"><span data-stu-id="8fc60-175">Generate a document instance from the Adapter schema</span></span>  

1.  <span data-ttu-id="8fc60-176">ソリューション エクスプ ローラーで、Schema.xsd を右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-176">Right-click Schema.xsd in Solution Explorer and click **Properties**.</span></span>  

2.  <span data-ttu-id="8fc60-177">プロパティ ウィンドウでクリックして選択、**出力インスタンス ファイル名**オプションで 、**全般**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="8fc60-177">In the Properties window, click to select the **Output Instance Filename** option under the **General** category.</span></span>  

3.  <span data-ttu-id="8fc60-178">表示するには、省略記号ボタン (...) をクリックして、**出力ファイルの選択**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="8fc60-178">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

4.  <span data-ttu-id="8fc60-179">たとえば、フォルダーと出力ファイル インスタンスの名前を指定**C:\instance.xml**  をクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-179">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="8fc60-180">ファイル受信場所に指定したフォルダーの場所は、ここに指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="8fc60-180">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

5.  <span data-ttu-id="8fc60-181">ソリューション エクスプ ローラーで、Schema.xsd を右クリックし、をクリックして**インスタンスの生成**指定された場所にドキュメント インスタンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-181">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="8fc60-182">生成されたドキュメント インスタンスを変更する</span><span class="sxs-lookup"><span data-stu-id="8fc60-182">Modify the generated document instance</span></span>  

1.  <span data-ttu-id="8fc60-183">生成されたドキュメント インスタンスをメモ帳などのテキスト エディターで開き、ドキュメント インスタンスの内容を編集して、データによって TIBCO システムで一意のレコードが生成されるようにします。</span><span class="sxs-lookup"><span data-stu-id="8fc60-183">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="8fc60-184">データ ファイルの最初の部分を例として次に示します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-184">For example the code below shows the first part of the data file:</span></span>  

    ```  
    <ns0:Root xmlns:ns0="http://TibcoEMSOne_WaySend.TibcoEMSOneWaySendSchema">  
      <Name>Punya Palit</Name>  
      <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  

2.  <span data-ttu-id="8fc60-185">変更したドキュメント インスタンスを保存します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-185">Save the modified document instance.</span></span>  

#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="8fc60-186">プロジェクトのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="8fc60-186">Build and deploy the project</span></span>  

1. <span data-ttu-id="8fc60-187">ソリューション エクスプ ローラーで OneWaySend プロジェクトを右クリックし、をクリックして**プロパティ**をプロジェクトのプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-187">Right-click the OneWaySend project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  

2. <span data-ttu-id="8fc60-188">をクリックして、**展開**タブ。</span><span class="sxs-lookup"><span data-stu-id="8fc60-188">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="8fc60-189">適切な値を入力、 **Server**プロパティおよび**構成データベース**のプロパティの  **BizTalk グループ**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="8fc60-189">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  

4. <span data-ttu-id="8fc60-190">ソリューション エクスプ ローラーで OneWaySend プロジェクトを右クリックし、をクリックして**デプロイ**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。</span><span class="sxs-lookup"><span data-stu-id="8fc60-190">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="8fc60-191">オーケストレーションをバインドして参加させる</span><span class="sxs-lookup"><span data-stu-id="8fc60-191">Bind and Enlist the orchestration</span></span>  

1. <span data-ttu-id="8fc60-192">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、] をクリック**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-192">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="8fc60-193">をクリックして、**更新**MMC ツールバーまたはキーを押してボタン、 **F5**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。</span><span class="sxs-lookup"><span data-stu-id="8fc60-193">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  

3. <span data-ttu-id="8fc60-194">表示するオーケストレーションをダブルクリックして、**オーケストレーションのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="8fc60-194">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="8fc60-195">クリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="8fc60-195">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="8fc60-196">バインド オプションに適切な値を指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-196">Specify the appropriate values for the binding options, for example:</span></span>  


   |     <span data-ttu-id="8fc60-197">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="8fc60-197">**Parameter**</span></span>      |        <span data-ttu-id="8fc60-198">**[値]**</span><span class="sxs-lookup"><span data-stu-id="8fc60-198">**Value**</span></span>         |
   |------------------------|--------------------------|
   |          <span data-ttu-id="8fc60-199">ホスト</span><span class="sxs-lookup"><span data-stu-id="8fc60-199">Host</span></span>          | <span data-ttu-id="8fc60-200">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="8fc60-200">BizTalkServerApplication</span></span> |
   |    <span data-ttu-id="8fc60-201">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="8fc60-201">FileReceivePort</span></span>     |   <span data-ttu-id="8fc60-202">TIBCOEMSOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="8fc60-202">TIBCOEMSOneWayFileRP</span></span>   |
   | <span data-ttu-id="8fc60-203">TibcoEMSOneWaySendPort</span><span class="sxs-lookup"><span data-stu-id="8fc60-203">TibcoEMSOneWaySendPort</span></span> |     <span data-ttu-id="8fc60-204">TIBCOEMSOneWaySP</span><span class="sxs-lookup"><span data-stu-id="8fc60-204">TIBCOEMSOneWaySP</span></span>     |


6. <span data-ttu-id="8fc60-205">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fc60-205">Click OK.</span></span>  

#### <a name="start-the-orchestration"></a><span data-ttu-id="8fc60-206">オーケストレーションを開始します</span><span class="sxs-lookup"><span data-stu-id="8fc60-206">Start the orchestration</span></span>  

- <span data-ttu-id="8fc60-207">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、オーケストレーションを右クリックし、クリックして**開始**を参加させて、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-207">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="8fc60-208">ファイル受信場所の監視対象フォルダーにドキュメント インスタンスをドロップする</span><span class="sxs-lookup"><span data-stu-id="8fc60-208">Drop a document instance into the folder monitored by the file receive location</span></span>  

-   <span data-ttu-id="8fc60-209">先ほど作成したドキュメント インスタンスを、アプリケーションが監視するファイル受信フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="8fc60-209">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  

#### <a name="verify-that-the-tibco-system-is-updated"></a><span data-ttu-id="8fc60-210">TIBCO システムが更新されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="8fc60-210">Verify that the TIBCO system is updated</span></span>  

- <span data-ttu-id="8fc60-211">TIBCO Web インターフェイスを使用して、XML ファイルのデータからレコードが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-211">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  

  <span data-ttu-id="8fc60-212">ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-212">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="8fc60-213">ファイル アダプターがフォルダーからファイルを取得し、メッセージボックスに BizTalk メッセージとして公開します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-213">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="8fc60-214">この公開されたメッセージをオーケストレーションがサブスクライブします。その結果、BizTalk メッセージング エンジンによってオーケストレーションのインスタンスがアクティブ化され、メッセージがオーケストレーション インスタンスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="8fc60-214">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="8fc60-215">オーケストレーション インスタンスがオーケストレーションで指定されたロジックを使用してメッセージを処理し、メッセージ ボックスにメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-215">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="8fc60-216">この公開されたメッセージを TIBCO 送信ポートがサブスクライブします。その結果、BizTalk メッセージング エンジンによってこのメッセージが TIBCO 送信ポートに送信されます。</span><span class="sxs-lookup"><span data-stu-id="8fc60-216">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  

5.  <span data-ttu-id="8fc60-217">送信ポートがメッセージを BizTalk Adapter for TIBCO Enterprise Message Service. に渡します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-217">The send port hands the message to the BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  

6.  <span data-ttu-id="8fc60-218">BizTalk Adapter for TIBCO Enterprise Message Service がメッセージを TIBCO システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="8fc60-218">The BizTalk Adapter for TIBCO Enterprise Message Service sends the message to the TIBCO system.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8fc60-219">参照</span><span class="sxs-lookup"><span data-stu-id="8fc60-219">See Also</span></span>  
 <span data-ttu-id="8fc60-220">[チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用してデータを受信するには](../core/tutorial-us-the-biztalk-adapter-for-tibco-message-service-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="8fc60-220">[Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Receive Data](../core/tutorial-us-the-biztalk-adapter-for-tibco-message-service-to-receive-data.md) </span></span>  
 <span data-ttu-id="8fc60-221">[チュートリアル: TIBCO Enterprise Message Service 用の Microsoft BizTalk Adapter の使用](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span><span class="sxs-lookup"><span data-stu-id="8fc60-221">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span></span>  
 [<span data-ttu-id="8fc60-222">作業の開始</span><span class="sxs-lookup"><span data-stu-id="8fc60-222">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)