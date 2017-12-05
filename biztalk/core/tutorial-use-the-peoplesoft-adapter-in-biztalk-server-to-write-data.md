---
title: "チュートリアル: BizTalk Adapter for PeopleSoft Enterprise を使用してデータを PeopleSoft Enterprise に書き込む |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 837dd4db-576d-41c1-9fe8-e1e46861270b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b38c1f5a0bd442404e832274d13ace2b0660c2e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-write-data-to-peoplesoft-enterprise"></a><span data-ttu-id="eee2d-102">チュートリアル: BizTalk Adapter for PeopleSoft Enterprise を使用した PeopleSoft Enterprise へのデータの書き込み</span><span class="sxs-lookup"><span data-stu-id="eee2d-102">Tutorial: Using the BizTalk Adapter for PeopleSoft Enterprise to Write Data to PeopleSoft Enterprise</span></span>
<span data-ttu-id="eee2d-103">BizTalk Adapter for PeopleSoft Enterprise を使用して、取引先または内部アプリケーションから受信した情報に基づくデータを PeopleSoft システムに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="eee2d-103">The BizTalk Adapter for PeopleSoft Enterprise can be used to write data to a PeopleSoft System with information received from a trading partner or internal application.</span></span> <span data-ttu-id="eee2d-104">ここでは、この機能を示す SDK サンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-104">This walkthrough describes an SDK sample that illustrates this functionality.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eee2d-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="eee2d-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="eee2d-106">BizTalk Adapter for PeopleSoft Enterprise を実行する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に、Java 2 Platform がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eee2d-106">The Java 2 Platform must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  
  
-   <span data-ttu-id="eee2d-107">PeopleSoft Java Object Adapter JAR ファイル**psjoa.jar**にアクセスできるフォルダーにコピーするか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で BizTalk Adapter for PeopleSoft Enterprise が実行されています。</span><span class="sxs-lookup"><span data-stu-id="eee2d-107">The PeopleSoft Java Object Adapter JAR file, **psjoa.jar** should be copied to a folder that is accessible to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  
  
-   <span data-ttu-id="eee2d-108">サンプルをビルドして展開するには、BizTalk Adapter for PeopleSoft Enterprise を実行する [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eee2d-108">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on in order to build and deploy the sample.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="eee2d-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="eee2d-109">What This Sample Does</span></span>  
 <span data-ttu-id="eee2d-110">このサンプルでは、フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for PeopleSoft Enterprise を使用して XML ファイルのデータから PeopleSoft システム内にレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for PeopleSoft Enterprise to create a record in the PeopleSoft system from the data in the XML file.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="eee2d-111">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="eee2d-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="eee2d-112">このサンプルは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデザインされ、BizTalk Adapter for PeopleSoft Enterprise を BizTalk オーケストレーションと組み合わせて使用する基本的な機能を紹介する目的で作成されました。</span><span class="sxs-lookup"><span data-stu-id="eee2d-112">This sample was designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and was created to illustrate basic functionality using the BizTalk Adapter for PeopleSoft Enterprise with a BizTalk orchestration.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="eee2d-113">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="eee2d-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="eee2d-114">このサンプルは、次のフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="eee2d-114">The sample is located in the following folder:</span></span>  
  
 <span data-ttu-id="eee2d-115">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftOneWaySend</span><span class="sxs-lookup"><span data-stu-id="eee2d-115">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftOneWaySend</span></span>  
  
 <span data-ttu-id="eee2d-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="eee2d-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="eee2d-117">**ランタイム プロジェクト ファイル名**</span><span class="sxs-lookup"><span data-stu-id="eee2d-117">**Runtime Project Filename**</span></span>|<span data-ttu-id="eee2d-118">**ランタイム プロジェクト ファイルの説明**</span><span class="sxs-lookup"><span data-stu-id="eee2d-118">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="eee2d-119">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="eee2d-119">OneWaySend.btproj,</span></span><br /><br /> <span data-ttu-id="eee2d-120">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="eee2d-120">OneWaySend.sln</span></span>|<span data-ttu-id="eee2d-121">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="eee2d-121">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="eee2d-122">LOCATIONService.xsd、</span><span class="sxs-lookup"><span data-stu-id="eee2d-122">LOCATIONService.xsd,</span></span><br /><br /> <span data-ttu-id="eee2d-123">LOCATIONService_1.xsd、</span><span class="sxs-lookup"><span data-stu-id="eee2d-123">LOCATIONService_1.xsd,</span></span><br /><br /> <span data-ttu-id="eee2d-124">LOCATIONService_2.xsd</span><span class="sxs-lookup"><span data-stu-id="eee2d-124">LOCATIONService_2.xsd</span></span>|<span data-ttu-id="eee2d-125">アプリケーションのスキーマ ファイル。</span><span class="sxs-lookup"><span data-stu-id="eee2d-125">Schema files for the application.</span></span> <span data-ttu-id="eee2d-126">**注:**アダプター スキーマ ファイルは、プロジェクトでは、使用してもともと作成された、**アダプター メタデータの追加ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-126">**Note:**  The adapter schema files in the project were originally created using the **Add Adapter Metadata Wizard**.</span></span> <span data-ttu-id="eee2d-127">アダプター メタデータの追加ウィザードの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] マニュアルの「アダプター メタデータを BizTalk プロジェクトに追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eee2d-127">For more information on the Add Adapter Metadata Wizard see the topic "How to Add Adapter Metadata to a BizTalk Project" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>|  
|<span data-ttu-id="eee2d-128">PeopleSoftOneWaySend.odx</span><span class="sxs-lookup"><span data-stu-id="eee2d-128">PeopleSoftOneWaySend.odx</span></span>|<span data-ttu-id="eee2d-129">アプリケーションが使用するオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="eee2d-129">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="eee2d-130">PeopleSoftOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="eee2d-130">PeopleSoftOneWaySend.snk</span></span>|<span data-ttu-id="eee2d-131">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="eee2d-131">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="eee2d-132">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="eee2d-132">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a><span data-ttu-id="eee2d-133">PeopleSoft Enterprise アダプターの新しいインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="eee2d-133">Create a new instance of the PeopleSoft Enterprise adapter</span></span>  
  
1.  <span data-ttu-id="eee2d-134">起動して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="eee2d-134">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="eee2d-135">をクリックして**開始**、**すべてのプログラム**、 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 **BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-135">Click **Start**, **All Programs**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="eee2d-136">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**プラットフォームの設定**、順にクリック**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-136">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="eee2d-137">右クリック**アダプター**を指す**新規**、**アダプターしています.**</span><span class="sxs-lookup"><span data-stu-id="eee2d-137">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="eee2d-138">表示する、**アダプター プロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="eee2d-138">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="eee2d-139">値を入力して、**名前**フィールド、たとえば**PeopleSoft**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-139">Enter a value for the **Name** field, for example **PeopleSoft**.</span></span>  
  
5.  <span data-ttu-id="eee2d-140">選択**PeopleSoft enterprise (r)**で利用可能なアダプターの一覧から、**アダプター**ドロップダウン リスト をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-140">Select **PeopleSoft Enterprise(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="eee2d-141">BizTalk 送信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="eee2d-141">Create a BizTalk Send Port</span></span>  
  
1.  <span data-ttu-id="eee2d-142">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、 をクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-142">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="eee2d-143">右クリック**送信ポート**を指す**新規**、**静的な一方向送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="eee2d-143">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port** to display the **Send Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="eee2d-144">値を入力して、**名前**フィールド、たとえば**PeopleSoftOneWaySP**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-144">Enter a value for the **Name** field, for example **PeopleSoftOneWaySP**.</span></span>  
  
4.  <span data-ttu-id="eee2d-145">使用可能なアダプターの一覧から PeopleSoft アダプターを選択、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="eee2d-145">Select the PeopleSoft adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eee2d-146">この値は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで PeopleSoft Enterprise アダプターを作成したときに指定した名前です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-146">This value is the name that was specified when the PeopleSoft Enterprise adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
5.  <span data-ttu-id="eee2d-147">次の値を入力、**アダプターに必要なプロパティ**:</span><span class="sxs-lookup"><span data-stu-id="eee2d-147">Enter the following values for the **Adapter Required Properties**:</span></span>  
  
    |<span data-ttu-id="eee2d-148">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="eee2d-148">**Property**</span></span>|<span data-ttu-id="eee2d-149">**値**</span><span class="sxs-lookup"><span data-stu-id="eee2d-149">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="eee2d-150">アプリケーション サーバーのパス</span><span class="sxs-lookup"><span data-stu-id="eee2d-150">Application server path</span></span>|<span data-ttu-id="eee2d-151">PeopleSoft Server のコンピューターおよびポートの場所 (例: //PSServer:8888)。</span><span class="sxs-lookup"><span data-stu-id="eee2d-151">PeopleSoft Server's machine and port location, for example //PSServer:8888.</span></span> <span data-ttu-id="eee2d-152">**注:**する上記の例ででした入力ように//PSServer の値、PeopleSoft サーバーは、既定のポート値 9000 を使用している場合、9000 の既定のポートが使用されるポート番号を指定しない場合。</span><span class="sxs-lookup"><span data-stu-id="eee2d-152">**Note:**  If you do not specify a port number, the default port of 9000 is used so in the example above you could enter a value of //PSServer if the PeopleSoft Server uses the default port value of 9000.</span></span>|  
    |<span data-ttu-id="eee2d-153">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="eee2d-153">JAVA_HOME</span></span>|<span data-ttu-id="eee2d-154">Java 2 Platform SDK ファイルに関連付けられているホーム ディレクトリへのパス (例: C:\j2sdk1.4.2_08)。</span><span class="sxs-lookup"><span data-stu-id="eee2d-154">Path to the home directory associated with the Java 2 Platform SDK files, for example C:\j2sdk1.4.2_08</span></span>|  
    |<span data-ttu-id="eee2d-155">Password</span><span class="sxs-lookup"><span data-stu-id="eee2d-155">Password</span></span>|<span data-ttu-id="eee2d-156">PeopleSoft システムへの接続時に使用するパスワード。</span><span class="sxs-lookup"><span data-stu-id="eee2d-156">Password used when connecting to the PeopleSoft system.</span></span>|  
    |<span data-ttu-id="eee2d-157">PeopleSoft 8.x JAR ファイル</span><span class="sxs-lookup"><span data-stu-id="eee2d-157">PeopleSoft 8.x JAR files</span></span>|<span data-ttu-id="eee2d-158">PeopleSoft Java Object Adapter JAR ファイルの場所**psjoa.jar**C:\JARS\psjoa.jar 例を示します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-158">Location of the PeopleSoft Java Object Adapter JAR file, **psjoa.jar**, for example C:\JARS\psjoa.jar.</span></span>|  
    |<span data-ttu-id="eee2d-159">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="eee2d-159">User name</span></span>|<span data-ttu-id="eee2d-160">PeopleSoft システムへの接続時に使用するユーザー名。</span><span class="sxs-lookup"><span data-stu-id="eee2d-160">Username for connecting to the PeopleSoft system.</span></span>|  
  
6.  <span data-ttu-id="eee2d-161">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eee2d-161">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="eee2d-162">選択、 **XML Transmit**パイプラインで使用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン リスト をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-162">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
8.  <span data-ttu-id="eee2d-163">送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-163">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="create-a-file-receive-port"></a><span data-ttu-id="eee2d-164">ファイル受信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="eee2d-164">Create a file receive port</span></span>  
  
1.  <span data-ttu-id="eee2d-165">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、 をクリック**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-165">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="eee2d-166">受信ポート フォルダーを右クリックし、をクリックして**新規**、**一方向の受信ポート**受信ポートのプロパティ ダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-166">Right-click the Receive Ports folder and then click **New**, **One-way Receive Port** to display the Receive Port Properties dialog.</span></span>  
  
3.  <span data-ttu-id="eee2d-167">値を入力、**名前**フィールド、たとえば**PeopleSoftOneWayFileRP**、 をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-167">Enter a value for the **Name** field, for example **PeopleSoftOneWayFileRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-file-receive-location"></a><span data-ttu-id="eee2d-168">ファイル受信場所を作成する</span><span class="sxs-lookup"><span data-stu-id="eee2d-168">Create a file receive location</span></span>  
  
1.  <span data-ttu-id="eee2d-169">ファイル受信場所で監視されるフォルダー (C:\Filesource など) を作成します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-169">Create a folder to be monitored by the file receive location, for example C:\Filesource.</span></span>  
  
2.  <span data-ttu-id="eee2d-170">右クリックし、新しい受信ポートをクリックし、**新規**、**受信場所の**を表示する、**受信場所のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="eee2d-170">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="eee2d-171">値を入力して、**名前**フィールド、たとえば**PeopleSoftOneWayFileRL**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-171">Enter a value for the **Name** field, for example **PeopleSoftOneWayFileRL**.</span></span>  
  
4.  <span data-ttu-id="eee2d-172">選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="eee2d-172">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="eee2d-173">用に作成したフォルダーの場所を入力、**受信フォルダー**プロパティをクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-173">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  
  
6.  <span data-ttu-id="eee2d-174">選択**[xmlreceive]**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン リスト ボックスし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-174">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="eee2d-175">受信場所を右クリックし、をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-175">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="modify-the-adapter-schema-target-namespace-property"></a><span data-ttu-id="eee2d-176">アダプター スキーマのターゲットの名前空間プロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="eee2d-176">Modify the Adapter schema target namespace property</span></span>  
  
1.  <span data-ttu-id="eee2d-177">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を起動し、OneWaySend.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="eee2d-177">Launch [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and open OneWaySend.sln.</span></span> <span data-ttu-id="eee2d-178">をクリックして**ファイル**、**開く**、**プロジェクト/ソリューションしています.**</span><span class="sxs-lookup"><span data-stu-id="eee2d-178">Click **File**, **Open**, **Project/Solution…**</span></span> <span data-ttu-id="eee2d-179">表示する、**プロジェクトを開く**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="eee2d-179">to display the **Open Project** dialog.</span></span>  
  
2.  <span data-ttu-id="eee2d-180">OneWaySend.sln ファイルを [参照] をクリックし、このファイルを選択し、をクリックして**開く**サンプル プロジェクトを含むソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="eee2d-180">Browse to the OneWaySend.sln file, click to select this file and click **Open** to open the solution that contains the sample project.</span></span>  
  
3.  <span data-ttu-id="eee2d-181">をクリックして、**ビュー**メニュー**ソリューション エクスプ ローラー**ソリューション エクスプ ローラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-181">Click the **View** menu and select **Solution Explorer** to display the Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="eee2d-182">ソリューション エクスプローラーで、LOCATIONService_1.xsd ファイルをダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="eee2d-182">Double-click the LOCATIONService_1.xsd file in the Solution Explorer to open it.</span></span>  
  
5.  <span data-ttu-id="eee2d-183">右クリックし、**スキーマ**LOCATIONService_1.xsd と選択のノード、**プロパティ**スキーマのプロパティを表示するメニュー オプション。</span><span class="sxs-lookup"><span data-stu-id="eee2d-183">Right-click the **Schema** node of LOCATIONService_1.xsd and select the **Properties** menu option to display the properties for the schema.</span></span>  
  
6.  <span data-ttu-id="eee2d-184">編集、 **Target Namespace**アダプター名はたとえば、適切な値を使用するプロパティ、 **Target Namespace**プロパティを次のように読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="eee2d-184">Edit the **Target Namespace** property to use the appropriate values for the adapter name, for example the **Target Namespace** property should read as follows:</span></span>  
  
    ```  
    http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
    ```  
  
     <span data-ttu-id="eee2d-185">ここで*PeopleSoft*は BizTalk 管理コンソールに表示される PeopleSoft アダプターの名前。</span><span class="sxs-lookup"><span data-stu-id="eee2d-185">Where *PeopleSoft* is the name of the PeopleSoft adapter as viewed in the BizTalk Administration Console.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="eee2d-186">場合設定値を**Target Namespace**によって入力ドキュメント インスタンスが処理されるときに、ルーティングの障害が発生し、入力ドキュメント インスタンスで指定された名前空間と一致しません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-186">If the configured value for **Target Namespace** does not match the namespace specified in the input document instance then a routing failure will occur when the input document instance is processed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="eee2d-187">アダプター スキーマからドキュメント インスタンスを生成する</span><span class="sxs-lookup"><span data-stu-id="eee2d-187">Generate a document instance from the Adapter schema</span></span>  
  
1.  <span data-ttu-id="eee2d-188">ダブルクリックして**LOCATIONService_1.xsd**ソリューション エクスプ ローラーで、スキーマ エディターでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="eee2d-188">Double-click **LOCATIONService_1.xsd** in the Solution Explorer to open the file in the Schema Editor.</span></span>  
  
2.  <span data-ttu-id="eee2d-189">右クリックし、 **\<スキーマ\>**スキーマ エディターでノード**プロパティ**ノードのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-189">Right-click the **\<Schema\>** node in the Schema Editor, and click **Properties** to display the properties for the node.</span></span>  
  
3.  <span data-ttu-id="eee2d-190">選択**CreateEx**で利用可能なノードの一覧から、**ルート参照**ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-190">Select **CreateEx** from the list of available nodes in the **Root Reference** dropdown box.</span></span> <span data-ttu-id="eee2d-191">これから生成されるサンプルのドキュメント インスタンスを生成するときにそのように実行する、 **CreateEx**スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="eee2d-191">This should be done so that when you generate a sample document instance it will be generated from the **CreateEx** node of the schema.</span></span>  
  
4.  <span data-ttu-id="eee2d-192">ソリューション エクスプ ローラーで LOCATIONService_1.xsd を右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-192">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="eee2d-193">プロパティ ウィンドウでクリックして選択、**出力インスタンス ファイル名**オプションで 、**全般**セクションです。</span><span class="sxs-lookup"><span data-stu-id="eee2d-193">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  
  
6.  <span data-ttu-id="eee2d-194">表示するには、省略記号ボタン (...) をクリックして、 **出力ファイルの**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="eee2d-194">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  
  
7.  <span data-ttu-id="eee2d-195">たとえば、フォルダーと出力ファイル インスタンスの名前を指定**C:\instance.xml**  をクリック**保存**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-195">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eee2d-196">ファイル受信場所に指定したフォルダーの場所は、ここに指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="eee2d-196">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  
  
8.  <span data-ttu-id="eee2d-197">ソリューション エクスプ ローラーで LOCATIONService_1.xsd を右クリックし、をクリックして**インスタンスの生成**を指定した場所にドキュメント インスタンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-197">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  
  
9. <span data-ttu-id="eee2d-198">右クリックし、 **\<スキーマ\>**スキーマ エディターでノード**プロパティ**ノードのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-198">Right-click the **\<Schema\>** node in the Schema Editor, and click **Properties** to display the properties for the node.</span></span>  
  
10. <span data-ttu-id="eee2d-199">選択 (**既定)**で利用可能なノードの一覧から、**ルート参照**ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-199">Select (**Default)** from the list of available nodes in the **Root Reference** dropdown box.</span></span>  
  
#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="eee2d-200">生成されたドキュメント インスタンスを変更する</span><span class="sxs-lookup"><span data-stu-id="eee2d-200">Modify the generated document instance</span></span>  
  
1.  <span data-ttu-id="eee2d-201">生成されたドキュメント インスタンスをメモ帳などのテキスト エディターで開き、ドキュメント インスタンスの内容を編集して、これらのフィールドのデータによって PeopleSoft システムで一意のレコードが生成されるようにします。たとえば、次の XML ファイルには、場所を定義するレコードのフィールドが記述されています。</span><span class="sxs-lookup"><span data-stu-id="eee2d-201">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data in these fields will generate a unique record in the PeopleSoft system, for example the XML file below describes the fields in a record that define a location:</span></span>  
  
    ```  
    <ns0:CreateEx xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
      <ns0:SETID>SHARE</ns0:SETID>  
      <ns0:LOCATION>9991</ns0:LOCATION>  
      <ns0:interactiveMode>true</ns0:interactiveMode>  
       <ns0:properties>  
        <ns0:LOCATION_TBL_sequence>  
          <ns0:LOCATION_TBL>  
            <ns0:COUNTRY>USA</ns0:COUNTRY>  
            <ns0:DESCR>Adapter Test</ns0:DESCR>  
            <ns0:EFFDT>2006-05-31</ns0:EFFDT>  
            <ns0:EFF_STATUS>A</ns0:EFF_STATUS>  
            <ns0:SETID>SHARE</ns0:SETID>  
          </ns0:LOCATION_TBL>  
        </ns0:LOCATION_TBL_sequence>  
      </ns0:properties>  
    </ns0:CreateEx>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="eee2d-202">上記の例で*PeopleSoft*アダプターの実際の名前を表すプレース ホルダーは、BizTalk 管理コンソールで表示します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-202">In the example above, *PeopleSoft* is a placeholder for the actual name of the adapter as viewed in the BizTalk Administration Console.</span></span>  
  
2.  <span data-ttu-id="eee2d-203">変更したドキュメント インスタンスを保存します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-203">Save the modified document instance.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="eee2d-204">プロジェクトのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="eee2d-204">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="eee2d-205">ソリューション エクスプ ローラーで OneWaySend プロジェクトを右クリックし、をクリックして**プロパティ**プロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-205">Right-click the OneWaySend project in Solution Explorer and click **Properties** to launch the Project Designer.</span></span>  
  
2.  <span data-ttu-id="eee2d-206">クリックして、**展開**タブです。</span><span class="sxs-lookup"><span data-stu-id="eee2d-206">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="eee2d-207">適切な値を入力、**サーバー**プロパティおよび**構成データベース**プロパティの  **BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-207">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  
  
4.  <span data-ttu-id="eee2d-208">ソリューション エクスプ ローラーで OneWaySend プロジェクトを右クリックし、をクリックして**展開**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。</span><span class="sxs-lookup"><span data-stu-id="eee2d-208">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="eee2d-209">オーケストレーションをバインドして参加させる</span><span class="sxs-lookup"><span data-stu-id="eee2d-209">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="eee2d-210">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、 をクリック**オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="eee2d-210">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="eee2d-211">クリックして、**更新**MMC ツールバーまたはキーを押してボタン、 **f5 キーを押して**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。</span><span class="sxs-lookup"><span data-stu-id="eee2d-211">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console view.</span></span>  
  
3.  <span data-ttu-id="eee2d-212">表示するオーケストレーションをダブルクリック、**オーケストレーションのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="eee2d-212">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="eee2d-213">をクリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左ペインでします。</span><span class="sxs-lookup"><span data-stu-id="eee2d-213">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="eee2d-214">バインド オプションに適切な値を指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-214">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="eee2d-215">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="eee2d-215">**Parameter**</span></span>|<span data-ttu-id="eee2d-216">**値**</span><span class="sxs-lookup"><span data-stu-id="eee2d-216">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="eee2d-217">Host</span><span class="sxs-lookup"><span data-stu-id="eee2d-217">Host</span></span>|<span data-ttu-id="eee2d-218">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="eee2d-218">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="eee2d-219">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="eee2d-219">FileReceivePort</span></span>|<span data-ttu-id="eee2d-220">PeopleSoftOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="eee2d-220">PeopleSoftOneWayFileRP</span></span>|  
    |<span data-ttu-id="eee2d-221">PeopleSoftOneWaySendPort</span><span class="sxs-lookup"><span data-stu-id="eee2d-221">PeopleSoftOneWaySendPort</span></span>|<span data-ttu-id="eee2d-222">PeopleSoftOneWaySP</span><span class="sxs-lookup"><span data-stu-id="eee2d-222">PeopleSoftOneWaySP</span></span>|  
  
6.  <span data-ttu-id="eee2d-223">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eee2d-223">Click OK.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="eee2d-224">オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-224">Start the orchestration</span></span>  
  
-   <span data-ttu-id="eee2d-225">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、オーケストレーションを右クリックし、をクリックして**開始**を参加させて、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-225">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="eee2d-226">ファイル受信場所の監視対象フォルダーにドキュメント インスタンスをドロップする</span><span class="sxs-lookup"><span data-stu-id="eee2d-226">Drop a document instance into the folder monitored by the file receive location</span></span>  
  
-   <span data-ttu-id="eee2d-227">先ほど作成したドキュメント インスタンスを、ファイル受信場所の監視対象として構成されているフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="eee2d-227">Copy the document instance that was created earlier to the folder that the file receive location is configured to monitor.</span></span>  
  
#### <a name="verify-that-the-peoplesoft-system-is-updated"></a><span data-ttu-id="eee2d-228">PeopleSoft システムが更新されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="eee2d-228">Verify that the PeopleSoft system is updated</span></span>  
  
-   <span data-ttu-id="eee2d-229">PeopleSoft Web インターフェイスを使用して、XML ファイルのデータからレコードが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-229">Use the PeopleSoft web interface to verify that the record was created from the data in the XML file.</span></span>  
  
 <span data-ttu-id="eee2d-230">ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-230">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="eee2d-231">ファイル アダプターがフォルダーからファイルを取得し、メッセージボックスに BizTalk メッセージとして公開します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-231">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="eee2d-232">この公開されたメッセージをオーケストレーションがサブスクライブします。その結果、BizTalk メッセージング エンジンによってオーケストレーションのインスタンスがアクティブ化され、メッセージがオーケストレーション インスタンスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="eee2d-232">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="eee2d-233">オーケストレーション インスタンスがオーケストレーションで指定されたロジックを使用してメッセージを処理し、メッセージ ボックスにメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-233">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="eee2d-234">PeopleSoft 送信ポートがこの公開されたメッセージをサブスクライブし、BizTalk メッセージング エンジンがメッセージを PeopleSoft 送信ポートに送信します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-234">The PeopleSoft send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the PeopleSoft send port.</span></span>  
  
5.  <span data-ttu-id="eee2d-235">送信ポートがメッセージを BizTalk Adapter for PeopleSoft Enterprise に渡します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-235">The send port hands the message to the BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
6.  <span data-ttu-id="eee2d-236">BizTalk Adapter for PeopleSoft Enterprise が CreateEx メソッドを呼び出して、XML ファイルのデータを使用してレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="eee2d-236">The BizTalk Adapter for PeopleSoft Enterprise invokes the CreateEx method to create a record using the data in the XML file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee2d-237">参照</span><span class="sxs-lookup"><span data-stu-id="eee2d-237">See Also</span></span>  
 [<span data-ttu-id="eee2d-238">チュートリアル: BizTalk Adapter for PeopleSoft Enterprise の使用</span><span class="sxs-lookup"><span data-stu-id="eee2d-238">Tutorials: Using BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)