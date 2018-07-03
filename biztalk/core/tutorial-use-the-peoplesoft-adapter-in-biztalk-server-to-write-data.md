---
title: 'チュートリアル: BizTalk Adapter for PeopleSoft Enterprise を使用してデータを PeopleSoft Enterprise に書き込む |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 837dd4db-576d-41c1-9fe8-e1e46861270b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9663512bf84fefc56b8db0050cbed7ffa3997780
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012307"
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-write-data-to-peoplesoft-enterprise"></a><span data-ttu-id="f3760-102">チュートリアル: BizTalk Adapter for PeopleSoft Enterprise を使用した PeopleSoft Enterprise へのデータの書き込み</span><span class="sxs-lookup"><span data-stu-id="f3760-102">Tutorial: Using the BizTalk Adapter for PeopleSoft Enterprise to Write Data to PeopleSoft Enterprise</span></span>
<span data-ttu-id="f3760-103">BizTalk Adapter for PeopleSoft Enterprise を使用して、取引先または内部アプリケーションから受信した情報に基づくデータを PeopleSoft システムに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="f3760-103">The BizTalk Adapter for PeopleSoft Enterprise can be used to write data to a PeopleSoft System with information received from a trading partner or internal application.</span></span> <span data-ttu-id="f3760-104">ここでは、この機能を示す SDK サンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f3760-104">This walkthrough describes an SDK sample that illustrates this functionality.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="f3760-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="f3760-105">Prerequisites</span></span>  

- <span data-ttu-id="f3760-106">BizTalk Adapter for PeopleSoft Enterprise を実行する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に、Java 2 Platform がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3760-106">The Java 2 Platform must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  

- <span data-ttu-id="f3760-107">PeopleSoft Java Object Adapter JAR ファイル、 **psjoa.jar**にアクセスできるフォルダーにコピーするか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で BizTalk Adapter for PeopleSoft Enterprise が実行されています。</span><span class="sxs-lookup"><span data-stu-id="f3760-107">The PeopleSoft Java Object Adapter JAR file, **psjoa.jar** should be copied to a folder that is accessible to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  

- <span data-ttu-id="f3760-108">サンプルをビルドして展開するには、BizTalk Adapter for PeopleSoft Enterprise を実行する [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3760-108">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on in order to build and deploy the sample.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="f3760-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="f3760-109">What This Sample Does</span></span>  
 <span data-ttu-id="f3760-110">このサンプルでは、フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for PeopleSoft Enterprise を使用して XML ファイルのデータから PeopleSoft システム内にレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3760-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for PeopleSoft Enterprise to create a record in the PeopleSoft system from the data in the XML file.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="f3760-111">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="f3760-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="f3760-112">このサンプルは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデザインされ、BizTalk Adapter for PeopleSoft Enterprise を BizTalk オーケストレーションと組み合わせて使用する基本的な機能を紹介する目的で作成されました。</span><span class="sxs-lookup"><span data-stu-id="f3760-112">This sample was designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and was created to illustrate basic functionality using the BizTalk Adapter for PeopleSoft Enterprise with a BizTalk orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="f3760-113">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="f3760-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="f3760-114">このサンプルは、次のフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="f3760-114">The sample is located in the following folder:</span></span>  

 <span data-ttu-id="f3760-115">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftOneWaySend</span><span class="sxs-lookup"><span data-stu-id="f3760-115">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftOneWaySend</span></span>  

 <span data-ttu-id="f3760-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="f3760-116">The following table shows the files in this sample and describes their purpose.</span></span>  


|                               <span data-ttu-id="f3760-117">**ランタイム プロジェクト ファイル名**</span><span class="sxs-lookup"><span data-stu-id="f3760-117">**Runtime Project Filename**</span></span>                                |                                                                                                                                                                           <span data-ttu-id="f3760-118">**ランタイム プロジェクト ファイルの説明**</span><span class="sxs-lookup"><span data-stu-id="f3760-118">**Runtime Project File Description**</span></span>                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                       <span data-ttu-id="f3760-119">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="f3760-119">OneWaySend.btproj,</span></span><br /><br /> <span data-ttu-id="f3760-120">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="f3760-120">OneWaySend.sln</span></span>                       |                                                                                                                                                                      <span data-ttu-id="f3760-121">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="f3760-121">Project and solution files for the application.</span></span>                                                                                                                                                                      |
| <span data-ttu-id="f3760-122">LOCATIONService.xsd、</span><span class="sxs-lookup"><span data-stu-id="f3760-122">LOCATIONService.xsd,</span></span><br /><br /> <span data-ttu-id="f3760-123">LOCATIONService_1.xsd、</span><span class="sxs-lookup"><span data-stu-id="f3760-123">LOCATIONService_1.xsd,</span></span><br /><br /> <span data-ttu-id="f3760-124">LOCATIONService_2.xsd</span><span class="sxs-lookup"><span data-stu-id="f3760-124">LOCATIONService_2.xsd</span></span> | <span data-ttu-id="f3760-125">アプリケーションのスキーマ ファイル。</span><span class="sxs-lookup"><span data-stu-id="f3760-125">Schema files for the application.</span></span> <span data-ttu-id="f3760-126">**注:** プロジェクトのアダプター スキーマ ファイルは、使用してもともと作成された、**アダプター メタデータの追加ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-126">**Note:**  The adapter schema files in the project were originally created using the **Add Adapter Metadata Wizard**.</span></span> <span data-ttu-id="f3760-127">アダプター メタデータの追加ウィザードの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] マニュアルの「アダプター メタデータを BizTalk プロジェクトに追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3760-127">For more information on the Add Adapter Metadata Wizard see the topic "How to Add Adapter Metadata to a BizTalk Project" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span> |
|                                 <span data-ttu-id="f3760-128">PeopleSoftOneWaySend.odx</span><span class="sxs-lookup"><span data-stu-id="f3760-128">PeopleSoftOneWaySend.odx</span></span>                                  |                                                                                                                                                                        <span data-ttu-id="f3760-129">アプリケーションが使用するオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="f3760-129">The orchestration used by the application.</span></span>                                                                                                                                                                         |
|                                 <span data-ttu-id="f3760-130">PeopleSoftOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="f3760-130">PeopleSoftOneWaySend.snk</span></span>                                  |                                                                                                                                                                                <span data-ttu-id="f3760-131">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="f3760-131">The strong naming key file.</span></span>                                                                                                                                                                                |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="f3760-132">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="f3760-132">How to Use This Sample</span></span>  

#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a><span data-ttu-id="f3760-133">PeopleSoft Enterprise アダプターの新しいインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="f3760-133">Create a new instance of the PeopleSoft Enterprise adapter</span></span>  

1. <span data-ttu-id="f3760-134">起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="f3760-134">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="f3760-135">クリックして**開始**、**すべてのプログラム**、 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-135">Click **Start**, **All Programs**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f3760-136">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**プラットフォームの設定**、 をクリックし、**アダプター**。</span><span class="sxs-lookup"><span data-stu-id="f3760-136">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3. <span data-ttu-id="f3760-137">右クリックして**アダプター**  をポイント**新規**、**アダプター.**</span><span class="sxs-lookup"><span data-stu-id="f3760-137">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="f3760-138">表示する、**アダプター プロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="f3760-138">to display the **Adapter Properties** dialog.</span></span>  

4. <span data-ttu-id="f3760-139">値を入力、**名前**フィールドに、たとえば**PeopleSoft**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-139">Enter a value for the **Name** field, for example **PeopleSoft**.</span></span>  

5. <span data-ttu-id="f3760-140">選択**PeopleSoft enterprise (r)** で利用可能なアダプターの一覧から、**アダプター**ドロップダウンをクリック **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="f3760-140">Select **PeopleSoft Enterprise(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="f3760-141">BizTalk 送信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="f3760-141">Create a BizTalk Send Port</span></span>  

1. <span data-ttu-id="f3760-142">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-142">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="f3760-143">右クリックして**送信ポート** をポイント**新規**、**静的な一方向送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="f3760-143">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port** to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="f3760-144">値を入力、**名前**フィールドに、たとえば**PeopleSoftOneWaySP**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-144">Enter a value for the **Name** field, for example **PeopleSoftOneWaySP**.</span></span>  

4. <span data-ttu-id="f3760-145">使用可能なアダプターの一覧から PeopleSoft アダプターを選択、**型**ドロップダウン ボックスし、をクリックして、**構成**アダプターを表示するボタン**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="f3760-145">Select the PeopleSoft adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f3760-146">この値は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで PeopleSoft Enterprise アダプターを作成したときに指定した名前です。</span><span class="sxs-lookup"><span data-stu-id="f3760-146">This value is the name that was specified when the PeopleSoft Enterprise adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

5. <span data-ttu-id="f3760-147">次の値を入力、**アダプターに必要なプロパティ**:</span><span class="sxs-lookup"><span data-stu-id="f3760-147">Enter the following values for the **Adapter Required Properties**:</span></span>  


   |       <span data-ttu-id="f3760-148">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f3760-148">**Property**</span></span>       |                                                                                                                                        <span data-ttu-id="f3760-149">**[値]**</span><span class="sxs-lookup"><span data-stu-id="f3760-149">**Value**</span></span>                                                                                                                                         |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="f3760-150">アプリケーション サーバーのパス</span><span class="sxs-lookup"><span data-stu-id="f3760-150">Application server path</span></span>  | <span data-ttu-id="f3760-151">PeopleSoft Server のコンピューターおよびポートの場所 (例: //PSServer:8888)。</span><span class="sxs-lookup"><span data-stu-id="f3760-151">PeopleSoft Server's machine and port location, for example //PSServer:8888.</span></span> <span data-ttu-id="f3760-152">**注:** する上記の例ででした入力ように//psserver 値、PeopleSoft サーバーは、既定のポート値 9000 を使用している場合、既定のポート 9000 が使用されるポート番号を指定しない場合。</span><span class="sxs-lookup"><span data-stu-id="f3760-152">**Note:**  If you do not specify a port number, the default port of 9000 is used so in the example above you could enter a value of //PSServer if the PeopleSoft Server uses the default port value of 9000.</span></span> |
   |        <span data-ttu-id="f3760-153">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="f3760-153">JAVA_HOME</span></span>         |                                                                                          <span data-ttu-id="f3760-154">Java 2 Platform SDK ファイルに関連付けられているホーム ディレクトリへのパス (例: C:\j2sdk1.4.2_08)。</span><span class="sxs-lookup"><span data-stu-id="f3760-154">Path to the home directory associated with the Java 2 Platform SDK files, for example C:\j2sdk1.4.2_08</span></span>                                                                                          |
   |         <span data-ttu-id="f3760-155">パスワード</span><span class="sxs-lookup"><span data-stu-id="f3760-155">Password</span></span>         |                                                                                                                 <span data-ttu-id="f3760-156">PeopleSoft システムへの接続時に使用するパスワード。</span><span class="sxs-lookup"><span data-stu-id="f3760-156">Password used when connecting to the PeopleSoft system.</span></span>                                                                                                                  |
   | <span data-ttu-id="f3760-157">PeopleSoft 8.x JAR ファイル</span><span class="sxs-lookup"><span data-stu-id="f3760-157">PeopleSoft 8.x JAR files</span></span> |                                                                                          <span data-ttu-id="f3760-158">PeopleSoft Java Object Adapter JAR ファイルの場所**psjoa.jar**、C:\JARS\psjoa.jar など。</span><span class="sxs-lookup"><span data-stu-id="f3760-158">Location of the PeopleSoft Java Object Adapter JAR file, **psjoa.jar**, for example C:\JARS\psjoa.jar.</span></span>                                                                                          |
   |        <span data-ttu-id="f3760-159">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="f3760-159">User name</span></span>         |                                                                                                                    <span data-ttu-id="f3760-160">PeopleSoft システムへの接続時に使用するユーザー名。</span><span class="sxs-lookup"><span data-stu-id="f3760-160">Username for connecting to the PeopleSoft system.</span></span>                                                                                                                     |


6. <span data-ttu-id="f3760-161">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3760-161">Click **OK**.</span></span>  

7. <span data-ttu-id="f3760-162">選択、 **XML Transmit**で利用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン をクリック**OK**。</span><span class="sxs-lookup"><span data-stu-id="f3760-162">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

8. <span data-ttu-id="f3760-163">送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="f3760-163">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-file-receive-port"></a><span data-ttu-id="f3760-164">ファイル受信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="f3760-164">Create a file receive port</span></span>  

1. <span data-ttu-id="f3760-165">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-165">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2. <span data-ttu-id="f3760-166">受信ポート フォルダーを右クリックし、をクリックし、**新規**、**一方向の受信ポート**受信ポートのプロパティ ダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3760-166">Right-click the Receive Ports folder and then click **New**, **One-way Receive Port** to display the Receive Port Properties dialog.</span></span>  

3. <span data-ttu-id="f3760-167">値を入力、**名前**フィールドに**PeopleSoftOneWayFileRP**、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-167">Enter a value for the **Name** field, for example **PeopleSoftOneWayFileRP**, and click **OK**.</span></span>  

#### <a name="create-a-file-receive-location"></a><span data-ttu-id="f3760-168">ファイル受信場所を作成する</span><span class="sxs-lookup"><span data-stu-id="f3760-168">Create a file receive location</span></span>  

1.  <span data-ttu-id="f3760-169">ファイル受信場所で監視されるフォルダー (C:\Filesource など) を作成します。</span><span class="sxs-lookup"><span data-stu-id="f3760-169">Create a folder to be monitored by the file receive location, for example C:\Filesource.</span></span>  

2.  <span data-ttu-id="f3760-170">右クリックし、新しい受信ポート をクリックし、**新規**、**受信場所**を表示する、**受信場所のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="f3760-170">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="f3760-171">値を入力、**名前**フィールドに、たとえば**PeopleSoftOneWayFileRL**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-171">Enter a value for the **Name** field, for example **PeopleSoftOneWayFileRL**.</span></span>  

4.  <span data-ttu-id="f3760-172">選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="f3760-172">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="f3760-173">先ほど作成したフォルダーの場所を入力、**受信フォルダー**プロパティをクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-173">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="f3760-174">選択**XMLReceive**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン ボックスし、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="f3760-174">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="f3760-175">受信場所を右クリックし、をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-175">Right-click the receive location and click **Enable**.</span></span>  

#### <a name="modify-the-adapter-schema-target-namespace-property"></a><span data-ttu-id="f3760-176">アダプター スキーマのターゲットの名前空間プロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="f3760-176">Modify the Adapter schema target namespace property</span></span>  

1. <span data-ttu-id="f3760-177">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を起動し、OneWaySend.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="f3760-177">Launch [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and open OneWaySend.sln.</span></span> <span data-ttu-id="f3760-178">クリックして**ファイル**、**オープン**、**プロジェクト/ソリューション.**</span><span class="sxs-lookup"><span data-stu-id="f3760-178">Click **File**, **Open**, **Project/Solution…**</span></span> <span data-ttu-id="f3760-179">表示する、**プロジェクトを開く**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="f3760-179">to display the **Open Project** dialog.</span></span>  

2. <span data-ttu-id="f3760-180">OneWaySend.sln ファイルへの参照をクリックし、このファイルを選択し、をクリックして**開く**サンプル プロジェクトを含むソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="f3760-180">Browse to the OneWaySend.sln file, click to select this file and click **Open** to open the solution that contains the sample project.</span></span>  

3. <span data-ttu-id="f3760-181">をクリックして、**ビュー**メニュー選択し、**ソリューション エクスプ ローラー**ソリューション エクスプ ローラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3760-181">Click the **View** menu and select **Solution Explorer** to display the Solution Explorer.</span></span>  

4. <span data-ttu-id="f3760-182">ソリューション エクスプローラーで、LOCATIONService_1.xsd ファイルをダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="f3760-182">Double-click the LOCATIONService_1.xsd file in the Solution Explorer to open it.</span></span>  

5. <span data-ttu-id="f3760-183">右クリックし、**スキーマ**LOCATIONService_1.xsd のノード、**プロパティ**スキーマのプロパティを表示するメニュー オプション。</span><span class="sxs-lookup"><span data-stu-id="f3760-183">Right-click the **Schema** node of LOCATIONService_1.xsd and select the **Properties** menu option to display the properties for the schema.</span></span>  

6. <span data-ttu-id="f3760-184">編集、 **Target Namespace**など、アダプター名の適切な値を使用するプロパティ、 **Target Namespace**プロパティを次のように読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3760-184">Edit the **Target Namespace** property to use the appropriate values for the adapter name, for example the **Target Namespace** property should read as follows:</span></span>  

   ```  
   http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
   ```  

    <span data-ttu-id="f3760-185">場所*PeopleSoft*は BizTalk 管理コンソールで表示される PeopleSoft アダプターの名前。</span><span class="sxs-lookup"><span data-stu-id="f3760-185">Where *PeopleSoft* is the name of the PeopleSoft adapter as viewed in the BizTalk Administration Console.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="f3760-186">場合設定値を**Target Namespace**によって入力ドキュメント インスタンスが処理されると、ルーティングの障害が発生し、入力ドキュメント インスタンスで指定された名前空間と一致しません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f3760-186">If the configured value for **Target Namespace** does not match the namespace specified in the input document instance then a routing failure will occur when the input document instance is processed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="f3760-187">アダプター スキーマからドキュメント インスタンスを生成する</span><span class="sxs-lookup"><span data-stu-id="f3760-187">Generate a document instance from the Adapter schema</span></span>  

1.  <span data-ttu-id="f3760-188">ダブルクリック**LOCATIONService_1.xsd**スキーマ エディターでファイルを開き、ソリューション エクスプ ローラーでします。</span><span class="sxs-lookup"><span data-stu-id="f3760-188">Double-click **LOCATIONService_1.xsd** in the Solution Explorer to open the file in the Schema Editor.</span></span>  

2.  <span data-ttu-id="f3760-189">右クリックし、 **\<スキーマ\>** ノードのスキーマ エディターをクリックします**プロパティ**ノードのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3760-189">Right-click the **\<Schema\>** node in the Schema Editor, and click **Properties** to display the properties for the node.</span></span>  

3.  <span data-ttu-id="f3760-190">選択**CreateEx**で使用可能なノードの一覧から、**ルート参照**ドロップダウン ボックス。</span><span class="sxs-lookup"><span data-stu-id="f3760-190">Select **CreateEx** from the list of available nodes in the **Root Reference** dropdown box.</span></span> <span data-ttu-id="f3760-191">生成されるサンプルのドキュメント インスタンスを生成するときにようにこれ行う必要があります、 **CreateEx**スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="f3760-191">This should be done so that when you generate a sample document instance it will be generated from the **CreateEx** node of the schema.</span></span>  

4.  <span data-ttu-id="f3760-192">ソリューション エクスプ ローラーで LOCATIONService_1.xsd を右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-192">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Properties**.</span></span>  

5.  <span data-ttu-id="f3760-193">プロパティ ウィンドウでクリックして選択、**出力インスタンス ファイル名**オプションで 、**全般**セクション。</span><span class="sxs-lookup"><span data-stu-id="f3760-193">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  

6.  <span data-ttu-id="f3760-194">表示するには、省略記号ボタン (...) をクリックして、**出力ファイルの選択**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="f3760-194">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

7.  <span data-ttu-id="f3760-195">たとえば、フォルダーと出力ファイル インスタンスの名前を指定**C:\instance.xml**  をクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-195">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="f3760-196">ファイル受信場所に指定したフォルダーの場所は、ここに指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="f3760-196">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

8.  <span data-ttu-id="f3760-197">ソリューション エクスプ ローラーで LOCATIONService_1.xsd を右クリックし、をクリックして**インスタンスの生成**指定された場所にドキュメント インスタンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="f3760-197">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

9. <span data-ttu-id="f3760-198">右クリックし、 **\<スキーマ\>** ノードのスキーマ エディターをクリックします**プロパティ**ノードのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3760-198">Right-click the **\<Schema\>** node in the Schema Editor, and click **Properties** to display the properties for the node.</span></span>  

10. <span data-ttu-id="f3760-199">選択 (**既定)** で使用可能なノードの一覧から、**ルート参照**ドロップダウン ボックス。</span><span class="sxs-lookup"><span data-stu-id="f3760-199">Select (**Default)** from the list of available nodes in the **Root Reference** dropdown box.</span></span>  

#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="f3760-200">生成されたドキュメント インスタンスを変更する</span><span class="sxs-lookup"><span data-stu-id="f3760-200">Modify the generated document instance</span></span>  

1.  <span data-ttu-id="f3760-201">生成されたドキュメント インスタンスをメモ帳などのテキスト エディターで開き、ドキュメント インスタンスの内容を編集して、これらのフィールドのデータによって PeopleSoft システムで一意のレコードが生成されるようにします。たとえば、次の XML ファイルには、場所を定義するレコードのフィールドが記述されています。</span><span class="sxs-lookup"><span data-stu-id="f3760-201">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data in these fields will generate a unique record in the PeopleSoft system, for example the XML file below describes the fields in a record that define a location:</span></span>  

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
    >  <span data-ttu-id="f3760-202">上記の例で*PeopleSoft*アダプターの実際の名前のプレース ホルダーは、BizTalk 管理コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="f3760-202">In the example above, *PeopleSoft* is a placeholder for the actual name of the adapter as viewed in the BizTalk Administration Console.</span></span>  

2.  <span data-ttu-id="f3760-203">変更したドキュメント インスタンスを保存します。</span><span class="sxs-lookup"><span data-stu-id="f3760-203">Save the modified document instance.</span></span>  

#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="f3760-204">プロジェクトのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="f3760-204">Build and deploy the project</span></span>  

1. <span data-ttu-id="f3760-205">ソリューション エクスプ ローラーで OneWaySend プロジェクトを右クリックし、をクリックして**プロパティ**をプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="f3760-205">Right-click the OneWaySend project in Solution Explorer and click **Properties** to launch the Project Designer.</span></span>  

2. <span data-ttu-id="f3760-206">をクリックして、**展開**タブ。</span><span class="sxs-lookup"><span data-stu-id="f3760-206">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="f3760-207">適切な値を入力、 **Server**プロパティと**構成データベース**のプロパティの  **BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-207">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  

4. <span data-ttu-id="f3760-208">ソリューション エクスプ ローラーで OneWaySend プロジェクトを右クリックし、をクリックして**デプロイ**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。</span><span class="sxs-lookup"><span data-stu-id="f3760-208">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="f3760-209">オーケストレーションをバインドして参加させる</span><span class="sxs-lookup"><span data-stu-id="f3760-209">Bind and Enlist the orchestration</span></span>  

1. <span data-ttu-id="f3760-210">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="f3760-210">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="f3760-211">をクリックして、**更新**MMC ツールバーまたはキーを押してボタン、 **F5**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。</span><span class="sxs-lookup"><span data-stu-id="f3760-211">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console view.</span></span>  

3. <span data-ttu-id="f3760-212">表示するオーケストレーションをダブルクリックして、**オーケストレーションのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="f3760-212">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="f3760-213">クリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="f3760-213">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="f3760-214">バインド オプションに適切な値を指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f3760-214">Specify the appropriate values for the binding options, for example:</span></span>  


   |      <span data-ttu-id="f3760-215">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f3760-215">**Parameter**</span></span>       |        <span data-ttu-id="f3760-216">**[値]**</span><span class="sxs-lookup"><span data-stu-id="f3760-216">**Value**</span></span>         |
   |--------------------------|--------------------------|
   |           <span data-ttu-id="f3760-217">ホスト</span><span class="sxs-lookup"><span data-stu-id="f3760-217">Host</span></span>           | <span data-ttu-id="f3760-218">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="f3760-218">BizTalkServerApplication</span></span> |
   |     <span data-ttu-id="f3760-219">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="f3760-219">FileReceivePort</span></span>      |  <span data-ttu-id="f3760-220">PeopleSoftOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="f3760-220">PeopleSoftOneWayFileRP</span></span>  |
   | <span data-ttu-id="f3760-221">PeopleSoftOneWaySendPort</span><span class="sxs-lookup"><span data-stu-id="f3760-221">PeopleSoftOneWaySendPort</span></span> |    <span data-ttu-id="f3760-222">PeopleSoftOneWaySP</span><span class="sxs-lookup"><span data-stu-id="f3760-222">PeopleSoftOneWaySP</span></span>    |


6. <span data-ttu-id="f3760-223">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3760-223">Click OK.</span></span>  

#### <a name="start-the-orchestration"></a><span data-ttu-id="f3760-224">オーケストレーションを開始します</span><span class="sxs-lookup"><span data-stu-id="f3760-224">Start the orchestration</span></span>  

- <span data-ttu-id="f3760-225">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、オーケストレーションを右クリックし、クリックして**開始**を参加させて、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="f3760-225">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="f3760-226">ファイル受信場所の監視対象フォルダーにドキュメント インスタンスをドロップする</span><span class="sxs-lookup"><span data-stu-id="f3760-226">Drop a document instance into the folder monitored by the file receive location</span></span>  

-   <span data-ttu-id="f3760-227">先ほど作成したドキュメント インスタンスを、ファイル受信場所の監視対象として構成されているフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f3760-227">Copy the document instance that was created earlier to the folder that the file receive location is configured to monitor.</span></span>  

#### <a name="verify-that-the-peoplesoft-system-is-updated"></a><span data-ttu-id="f3760-228">PeopleSoft システムが更新されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="f3760-228">Verify that the PeopleSoft system is updated</span></span>  

- <span data-ttu-id="f3760-229">PeopleSoft Web インターフェイスを使用して、XML ファイルのデータからレコードが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3760-229">Use the PeopleSoft web interface to verify that the record was created from the data in the XML file.</span></span>  

  <span data-ttu-id="f3760-230">ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="f3760-230">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="f3760-231">ファイル アダプターがフォルダーからファイルを取得し、メッセージボックスに BizTalk メッセージとして公開します。</span><span class="sxs-lookup"><span data-stu-id="f3760-231">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="f3760-232">この公開されたメッセージをオーケストレーションがサブスクライブします。その結果、BizTalk メッセージング エンジンによってオーケストレーションのインスタンスがアクティブ化され、メッセージがオーケストレーション インスタンスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f3760-232">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="f3760-233">オーケストレーション インスタンスがオーケストレーションで指定されたロジックを使用してメッセージを処理し、メッセージ ボックスにメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="f3760-233">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="f3760-234">PeopleSoft 送信ポートがこの公開されたメッセージをサブスクライブし、BizTalk メッセージング エンジンがメッセージを PeopleSoft 送信ポートに送信します。</span><span class="sxs-lookup"><span data-stu-id="f3760-234">The PeopleSoft send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the PeopleSoft send port.</span></span>  

5.  <span data-ttu-id="f3760-235">送信ポートがメッセージを BizTalk Adapter for PeopleSoft Enterprise に渡します。</span><span class="sxs-lookup"><span data-stu-id="f3760-235">The send port hands the message to the BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

6.  <span data-ttu-id="f3760-236">BizTalk Adapter for PeopleSoft Enterprise が CreateEx メソッドを呼び出して、XML ファイルのデータを使用してレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3760-236">The BizTalk Adapter for PeopleSoft Enterprise invokes the CreateEx method to create a record using the data in the XML file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f3760-237">参照</span><span class="sxs-lookup"><span data-stu-id="f3760-237">See Also</span></span>  
 [<span data-ttu-id="f3760-238">チュートリアル: BizTalk Adapter for PeopleSoft Enterprise の使用</span><span class="sxs-lookup"><span data-stu-id="f3760-238">Tutorials: Using BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)