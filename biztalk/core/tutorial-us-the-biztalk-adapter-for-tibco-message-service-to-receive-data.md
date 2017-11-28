---
title: "チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用してデータを受信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc5a63ec-1897-4c9b-b37f-cdcec151b1c9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd19ff62c4597cfa75762a1a89ae8e60409096f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-receive-data"></a><span data-ttu-id="924a6-102">チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用したデータの受信</span><span class="sxs-lookup"><span data-stu-id="924a6-102">Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Receive Data</span></span>
<span data-ttu-id="924a6-103">BizTalk Adapter for TIBCO Enterprise Message Service (EMS) を使用して TIBCO システムからデータを受信できます。</span><span class="sxs-lookup"><span data-stu-id="924a6-103">You can use the BizTalk Adapter for TIBCO Enterprise Message Service (EMS) to receive data from a TIBCO system.</span></span> <span data-ttu-id="924a6-104">このチュートリアルでは、これを示す SDK サンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="924a6-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="924a6-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="924a6-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="924a6-106">BizTalk Adapter for TIBCO Enterprise Message Service を使用するには、TIBCO EMS C# API の TIBCO.EMS.dll をグローバル アセンブリ キャッシュ (GAC) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="924a6-106">BizTalk Adapter for TIBCO Enterprise Message Service requires that you add the TIBCO EMS C# API, TIBCO.EMS.dll, to the global assembly cache (GAC).</span></span> <span data-ttu-id="924a6-107">アセンブリのインストールの詳細については、次を参照してください。 [TIBCO Enterprise Message Service の要件と制限事項](../core/tibco-enterprise-message-service-requirements-and-limitations.md)です。</span><span class="sxs-lookup"><span data-stu-id="924a6-107">For more information about installing the assembly, see [TIBCO Enterprise Message Service Requirements and Limitations](../core/tibco-enterprise-message-service-requirements-and-limitations.md).</span></span>  
  
-   <span data-ttu-id="924a6-108">このサンプルをビルドして展開するには、アダプターが実行されている [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="924a6-108">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="924a6-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="924a6-109">What This Sample Does</span></span>  
 <span data-ttu-id="924a6-110">このサンプルでは、フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for TIBCO Enterprise Message Service を使用して TIBCO システムからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="924a6-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Enterprise Message Service to retrieve data from a TIBCO system.</span></span> <span data-ttu-id="924a6-111">結果は、XML ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="924a6-111">The result is written to an XML file.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="924a6-112">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="924a6-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="924a6-113">このサンプルは、[!INCLUDE[vs2010](../includes/vs2010-md.md)] でデザインされ、BizTalk Adapter for TIBCO Enterprise Message Service を BizTalk オーケストレーションと組み合わせて使用する基本的な機能を紹介する目的で作成されました。</span><span class="sxs-lookup"><span data-stu-id="924a6-113">This sample, designed in [!INCLUDE[vs2010](../includes/vs2010-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="924a6-114">このサンプルでは、処理するアプリケーション用の TIBCO からメッセージを送信する方法を理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="924a6-114">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="924a6-115">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="924a6-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="924a6-116">このサンプルの既定の場所は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="924a6-116">The default location for the sample is</span></span>  
  
 <span data-ttu-id="924a6-117">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive</span><span class="sxs-lookup"><span data-stu-id="924a6-117">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive</span></span>  
  
 <span data-ttu-id="924a6-118">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="924a6-118">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="924a6-119">**ランタイム プロジェクト ファイル名**</span><span class="sxs-lookup"><span data-stu-id="924a6-119">**Runtime Project Filename**</span></span>|<span data-ttu-id="924a6-120">**ランタイム プロジェクト ファイルの説明**</span><span class="sxs-lookup"><span data-stu-id="924a6-120">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="924a6-121">OneWayReceive.btproj、</span><span class="sxs-lookup"><span data-stu-id="924a6-121">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="924a6-122">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="924a6-122">OneWayReceive.sln</span></span>|<span data-ttu-id="924a6-123">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="924a6-123">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="924a6-124">Schema.xsd、</span><span class="sxs-lookup"><span data-stu-id="924a6-124">Schema.xsd,</span></span>|<span data-ttu-id="924a6-125">アプリケーションのスキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="924a6-125">Schema file for the application.</span></span>|  
|<span data-ttu-id="924a6-126">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="924a6-126">Orchestration.odx</span></span>|<span data-ttu-id="924a6-127">アプリケーションが使用するオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="924a6-127">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="924a6-128">TIBCOEMSOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="924a6-128">TIBCOEMSOneWaySend.snk</span></span>|<span data-ttu-id="924a6-129">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="924a6-129">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="924a6-130">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="924a6-130">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a><span data-ttu-id="924a6-131">BizTalk Adapter for TIBCO EMS の新しいインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="924a6-131">Create a new instance of the BizTalk Adapter for TIBCO EMS</span></span>  
  
1.  <span data-ttu-id="924a6-132">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを起動します。</span><span class="sxs-lookup"><span data-stu-id="924a6-132">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="924a6-133">をクリックして**開始**、**プログラム**、 **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 **BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-133">Click **Start**, **Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="924a6-134">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**をクリックして**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-134">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="924a6-135">右クリック**アダプター**を指す**新規**、**アダプター**を表示する、**アダプターのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="924a6-135">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="924a6-136">値を入力して、**名前**フィールド、たとえば**TIBCO EMS**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-136">Enter a value for the **Name** field, for example **TIBCO EMS**.</span></span>  
  
5.  <span data-ttu-id="924a6-137">選択**TIBCO Enterprise Message System**で利用可能なアダプターの一覧から、**アダプター**ドロップダウン リスト をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-137">Select **TIBCO Enterprise Message System** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-port"></a><span data-ttu-id="924a6-138">BizTalk 受信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="924a6-138">Create a BizTalk Receive Port</span></span>  
  
1.  <span data-ttu-id="924a6-139">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="924a6-140">受信ポート フォルダーを右クリックし、をクリックして**新規**、**一方向の受信ポート**受信ポートのプロパティ ダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="924a6-140">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port** to display the Receive Port Properties dialog.</span></span>  
  
3.  <span data-ttu-id="924a6-141">値を入力、**名前**フィールド、たとえば**TIBCOEMSOneWayRP**、 をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-141">Enter a value for the **Name** field, for example **TIBCOEMSOneWayRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-location"></a><span data-ttu-id="924a6-142">BizTalk の受信場所を作成する</span><span class="sxs-lookup"><span data-stu-id="924a6-142">Create a BizTalk Receive Location</span></span>  
  
1.  <span data-ttu-id="924a6-143">右クリックし、新しい受信ポートをクリックし、**新規**、**受信場所の**を表示する、**受信場所のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="924a6-143">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  
  
2.  <span data-ttu-id="924a6-144">値を入力して、**名前**フィールド、たとえば**TIBCOEMSOneWayRL**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-144">Enter a value for the **Name** field, for example **TIBCOEMSOneWayRL**.</span></span>  
  
3.  <span data-ttu-id="924a6-145">使用可能なアダプターの一覧から TIBCO EMS アダプターを選択して、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートのプロパティ**ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="924a6-145">Select the TIBCO EMS adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="924a6-146">この値は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで TIBCO アダプターを作成したときに指定した名前です。</span><span class="sxs-lookup"><span data-stu-id="924a6-146">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="924a6-147">値を入力して、**サーバー接続の定義**:</span><span class="sxs-lookup"><span data-stu-id="924a6-147">Enter values for the **Server Connection definition**:</span></span>  
  
    |<span data-ttu-id="924a6-148">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="924a6-148">**Property**</span></span>|<span data-ttu-id="924a6-149">**値**</span><span class="sxs-lookup"><span data-stu-id="924a6-149">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="924a6-150">転送先</span><span class="sxs-lookup"><span data-stu-id="924a6-150">Destination</span></span>|<span data-ttu-id="924a6-151">サーバーの送信先キューまたはトピック名。</span><span class="sxs-lookup"><span data-stu-id="924a6-151">The server destination queue or topic name.</span></span>|  
    |<span data-ttu-id="924a6-152">[ポート番号]</span><span class="sxs-lookup"><span data-stu-id="924a6-152">Port number</span></span>|<span data-ttu-id="924a6-153">TIBCO サーバーが待ち受けしているポート。</span><span class="sxs-lookup"><span data-stu-id="924a6-153">The port on which the TIBCO server is listening.</span></span> <span data-ttu-id="924a6-154">既定値は 7222 です。</span><span class="sxs-lookup"><span data-stu-id="924a6-154">Default value is 7222.</span></span>|  
    |<span data-ttu-id="924a6-155">[サーバー名]</span><span class="sxs-lookup"><span data-stu-id="924a6-155">Server Name</span></span>|<span data-ttu-id="924a6-156">TIBCO EMS サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="924a6-156">The name of the TIBCO EMS server.</span></span>|  
  
5.  <span data-ttu-id="924a6-157">値を入力して、**ユーザーの資格情報**:</span><span class="sxs-lookup"><span data-stu-id="924a6-157">Enter values for the **User Credentials**:</span></span>  
  
    |<span data-ttu-id="924a6-158">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="924a6-158">**Property**</span></span>|<span data-ttu-id="924a6-159">**値**</span><span class="sxs-lookup"><span data-stu-id="924a6-159">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="924a6-160">Password</span><span class="sxs-lookup"><span data-stu-id="924a6-160">Password</span></span>|<span data-ttu-id="924a6-161">TIBCO EMS サーバーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="924a6-161">The password for the TIBCO EMS server.</span></span>|  
    |<span data-ttu-id="924a6-162">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="924a6-162">User name</span></span>|<span data-ttu-id="924a6-163">TIBCO EMS サーバーのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="924a6-163">The user name for the TIBCO EMS server.</span></span>|  
  
     <span data-ttu-id="924a6-164">プロパティの詳細については、次を参照してください。 [TIBCO Enterprise メッセージ サービス受信ハンドラーの作成](../core/creating-tibco-enterprise-message-service-receive-handlers.md)です。</span><span class="sxs-lookup"><span data-stu-id="924a6-164">For more information about the properties, see [Creating TIBCO Enterprise Message Service Receive Handlers](../core/creating-tibco-enterprise-message-service-receive-handlers.md).</span></span>  
  
6.  <span data-ttu-id="924a6-165">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924a6-165">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="924a6-166">選択**[xmlreceive]**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン リスト ボックスし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-166">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
8.  <span data-ttu-id="924a6-167">受信場所を右クリックし、をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-167">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="create-a-one-way-file-send-port"></a><span data-ttu-id="924a6-168">一方向 FILE 送信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="924a6-168">Create a one-way file send port</span></span>  
  
1.  <span data-ttu-id="924a6-169">送信ポートが使用する送信先フォルダー (たとえば、C:\FilesOut) を作成します。</span><span class="sxs-lookup"><span data-stu-id="924a6-169">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  
  
2.  <span data-ttu-id="924a6-170">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-170">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="924a6-171">右クリック**送信ポート**を指す**新規**、**静的な一方向送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="924a6-171">Right-click **Send Ports** and point to **New**, **Static One-way Send Port** to display the **Send Port Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="924a6-172">値を入力して、**名前**フィールド、たとえば**TIBCOEMSOneWayFileSP**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-172">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileSP**.</span></span>  
  
5.  <span data-ttu-id="924a6-173">選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="924a6-173">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
6.  <span data-ttu-id="924a6-174">**コピー先フォルダー**プロパティ、先ほど作成したフォルダーの場所を入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-174">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  
  
7.  <span data-ttu-id="924a6-175">選択、 **xmltransmit**パイプラインで使用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン リスト をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-175">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
8.  <span data-ttu-id="924a6-176">送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="924a6-176">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="924a6-177">プロジェクトのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="924a6-177">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="924a6-178">ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="924a6-178">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="924a6-179">クリックして、**展開**タブです。</span><span class="sxs-lookup"><span data-stu-id="924a6-179">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="924a6-180">適切な値を入力、**サーバー**プロパティおよび**構成データベース**プロパティの  **BizTalk グループ**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="924a6-180">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  
  
4.  <span data-ttu-id="924a6-181">ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**展開**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。</span><span class="sxs-lookup"><span data-stu-id="924a6-181">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="924a6-182">オーケストレーションをバインドして参加させる</span><span class="sxs-lookup"><span data-stu-id="924a6-182">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="924a6-183">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="924a6-183">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="924a6-184">をクリックして、**更新**ボタンをクリックして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール ツールバーまたはキーを押して、 **f5 キーを押して**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。</span><span class="sxs-lookup"><span data-stu-id="924a6-184">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="924a6-185">表示するオーケストレーションをダブルクリック、**オーケストレーションのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="924a6-185">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="924a6-186">をクリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左ペインでします。</span><span class="sxs-lookup"><span data-stu-id="924a6-186">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="924a6-187">バインド オプションに適切な値を指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="924a6-187">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="924a6-188">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="924a6-188">**Parameter**</span></span>|<span data-ttu-id="924a6-189">**値**</span><span class="sxs-lookup"><span data-stu-id="924a6-189">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="924a6-190">Host</span><span class="sxs-lookup"><span data-stu-id="924a6-190">Host</span></span>|<span data-ttu-id="924a6-191">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="924a6-191">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="924a6-192">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="924a6-192">FileSendPort</span></span>|<span data-ttu-id="924a6-193">TIBCOEMSOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="924a6-193">TIBCOEMSOneWayFileSP</span></span>|  
    |<span data-ttu-id="924a6-194">TibcoEMSOneWayReceiveOperation</span><span class="sxs-lookup"><span data-stu-id="924a6-194">TibcoEMSOneWayReceiveOperation</span></span>|<span data-ttu-id="924a6-195">TIBCOEMSOneWayRP</span><span class="sxs-lookup"><span data-stu-id="924a6-195">TIBCOEMSOneWayRP</span></span>|  
  
6.  <span data-ttu-id="924a6-196">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924a6-196">Click **OK**.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="924a6-197">オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="924a6-197">Start the orchestration</span></span>  
  
-   <span data-ttu-id="924a6-198">[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]管理コンソールでは、オーケストレーションを右クリックし、をクリックして**開始**を参加させて、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="924a6-198">In the [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="verify-that-the-application-receives-a-message"></a><span data-ttu-id="924a6-199">アプリケーションがメッセージを受信することの確認</span><span class="sxs-lookup"><span data-stu-id="924a6-199">Verify that the application receives a message</span></span>  
  
-   <span data-ttu-id="924a6-200">ファイル送信ポートの送信先として構成されているフォルダーを開いて、出力ドキュメントが生成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="924a6-200">Open the folder that the file send port is configured to send to and verify that an output document was generated.</span></span> <span data-ttu-id="924a6-201">このファイルには、BizTalk Adapter for TIBCO Enterprise Message Service によって処理されたクエリの結果が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="924a6-201">This file should contain the results of the query that was processed by the BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
 <span data-ttu-id="924a6-202">ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="924a6-202">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="924a6-203">TIBCO EMS アダプターが TIBCO システムからメッセージを取得し、BizTalk メッセージとしてメッセージ ボックスに公開します。</span><span class="sxs-lookup"><span data-stu-id="924a6-203">The TIBCO EMS adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="924a6-204">オーケストレーションがこの公開されたメッセージをサブスクライブします。これにより、BizTalk メッセージング エンジンがオーケストレーションのインスタンスをアクティブ化し、オーケストレーション インスタンスにメッセージを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="924a6-204">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="924a6-205">オーケストレーション インスタンスがメッセージ ボックスにメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="924a6-205">The orchestration instance publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="924a6-206">ファイル送信ポートがこのメッセージをサブスクライブし、BizTalk がメッセージをファイル アダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="924a6-206">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  
  
5.  <span data-ttu-id="924a6-207">ファイル アダプターが、結果セットを含むメッセージを指定の出力フォルダーに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="924a6-207">The File adapter writes the message containing the result set to the designated output folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="924a6-208">参照</span><span class="sxs-lookup"><span data-stu-id="924a6-208">See Also</span></span>  
 <span data-ttu-id="924a6-209">[チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用してデータを送信するには](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="924a6-209">[Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Send Data](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md) </span></span>  
 <span data-ttu-id="924a6-210">[チュートリアル: Microsoft BizTalk Adapter を使用して TIBCO Enterprise Message Service の](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span><span class="sxs-lookup"><span data-stu-id="924a6-210">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span></span>  
 [<span data-ttu-id="924a6-211">作業の開始</span><span class="sxs-lookup"><span data-stu-id="924a6-211">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)