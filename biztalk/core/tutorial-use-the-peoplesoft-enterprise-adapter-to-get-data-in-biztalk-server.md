---
title: チュートリアル:BizTalk Adapter for PeopleSoft Enterprise を使用して、PeopleSoft Enterprise からデータを取得する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c173fa4c-911e-4fa3-813f-e8f36b0049a5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 447e447dd261ad49f4dd5588bf602512f45768fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395411"
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-retrieve-data-from-peoplesoft-enterprise"></a><span data-ttu-id="7a9c7-102">チュートリアル:BizTalk Adapter for PeopleSoft Enterprise を使用して、PeopleSoft Enterprise からデータを取得するには</span><span class="sxs-lookup"><span data-stu-id="7a9c7-102">Tutorial: Using the BizTalk Adapter for PeopleSoft Enterprise to Retrieve Data from PeopleSoft Enterprise</span></span>
<span data-ttu-id="7a9c7-103">PeopleSoft システムに対してクエリを実行し、クエリの結果を返すには、BizTalk Adapter for PeopleSoft Enterprise を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-103">The BizTalk Adapter for PeopleSoft Enterprise can be used to execute a query against a PeopleSoft system and return the results of the query.</span></span> <span data-ttu-id="7a9c7-104">このチュートリアルでは、この機能を示す SDK サンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-104">This walkthrough describes an SDK sample that illustrates this functionality.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="7a9c7-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="7a9c7-105">Prerequisites</span></span>  

- <span data-ttu-id="7a9c7-106">Java 2 Platform をインストールする必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を BizTalk Adapter for PeopleSoft Enterprise の Geis で実行されています。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-106">The Java 2 Platform must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise Geis running on.</span></span>  

- <span data-ttu-id="7a9c7-107">PeopleSoft Java Object Adapter JAR ファイル、 **psjoa.jar**にアクセスできるフォルダーにコピーするか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で BizTalk Adapter for PeopleSoft Enterprise が実行されています。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-107">The PeopleSoft Java Object Adapter JAR file, **psjoa.jar** should be copied to a folder that is accessible to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  

- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="7a9c7-108">インストールする必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の構築し、サンプルをデプロイするには、BizTalk Adapter for PeopleSoft Enterprise が実行されていること。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-108">must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on in order to build and deploy the sample.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="7a9c7-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="7a9c7-109">What This Sample Does</span></span>  
 <span data-ttu-id="7a9c7-110">このサンプルは、フォルダーから XML ファイルを取得するには、ファイルをオーケストレーションに送信およびし、BizTalk Adapter for PeopleSoft Enterprise を使用して PeopleSoft システムに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for PeopleSoft Enterprise to execute a query against a PeopleSoft system.</span></span> <span data-ttu-id="7a9c7-111">クエリの結果は、XML ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-111">The result of the query is written to an XML file.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="7a9c7-112">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="7a9c7-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="7a9c7-113">このサンプルでデザインした[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]for PeopleSoft Enterprise を BizTalk オーケストレーションと BizTalk アダプターを使用した基本機能を説明するために作成されました。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-113">This sample was designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and was created to illustrate basic functionality using the BizTalk Adapter for PeopleSoft Enterprise with a BizTalk orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="7a9c7-114">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="7a9c7-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="7a9c7-115">サンプルは、次のフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-115">The sample is located in the following folder:</span></span>  

 <span data-ttu-id="7a9c7-116">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftTwoWaySend</span><span class="sxs-lookup"><span data-stu-id="7a9c7-116">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftTwoWaySend</span></span>  

 <span data-ttu-id="7a9c7-117">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-117">The following table shows the files in this sample and describes their purpose.</span></span>  


|                               <span data-ttu-id="7a9c7-118">**ランタイム プロジェクト ファイル名**</span><span class="sxs-lookup"><span data-stu-id="7a9c7-118">**Runtime Project Filename**</span></span>                                |                                                                                                                                                                           <span data-ttu-id="7a9c7-119">**ランタイム プロジェクト ファイルの説明**</span><span class="sxs-lookup"><span data-stu-id="7a9c7-119">**Runtime Project File Description**</span></span>                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                       <span data-ttu-id="7a9c7-120">TwoWaySend.btproj,</span><span class="sxs-lookup"><span data-stu-id="7a9c7-120">TwoWaySend.btproj,</span></span><br /><br /> <span data-ttu-id="7a9c7-121">TwoWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="7a9c7-121">TwoWaySend.sln</span></span>                       |                                                                                                                                                                      <span data-ttu-id="7a9c7-122">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-122">Project and solution files for the application.</span></span>                                                                                                                                                                      |
| <span data-ttu-id="7a9c7-123">LOCATIONService.xsd,</span><span class="sxs-lookup"><span data-stu-id="7a9c7-123">LOCATIONService.xsd,</span></span><br /><br /> <span data-ttu-id="7a9c7-124">LOCATIONService_1.xsd,</span><span class="sxs-lookup"><span data-stu-id="7a9c7-124">LOCATIONService_1.xsd,</span></span><br /><br /> <span data-ttu-id="7a9c7-125">LOCATIONService_2.xsd</span><span class="sxs-lookup"><span data-stu-id="7a9c7-125">LOCATIONService_2.xsd</span></span> | <span data-ttu-id="7a9c7-126">アプリケーションのスキーマ ファイル。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-126">Schema files for the application.</span></span> <span data-ttu-id="7a9c7-127">**注:** プロジェクトのアダプター スキーマ ファイルは、使用してもともと作成された、**アダプター メタデータの追加ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-127">**Note:**  The adapter schema files in the project were originally created using the **Add Adapter Metadata Wizard**.</span></span> <span data-ttu-id="7a9c7-128">アダプター メタデータの追加ウィザードの詳細については、トピック「する方法を追加アダプター メタデータを BizTalk プロジェクトに」を参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-128">For more information on the Add Adapter Metadata Wizard see the topic "How to Add Adapter Metadata to a BizTalk Project" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span> |
|                                 <span data-ttu-id="7a9c7-129">PeopleSoftTwoWaySend.odx</span><span class="sxs-lookup"><span data-stu-id="7a9c7-129">PeopleSoftTwoWaySend.odx</span></span>                                  |                                                                                                                                                                        <span data-ttu-id="7a9c7-130">アプリケーションが使用するオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-130">The orchestration used by the application.</span></span>                                                                                                                                                                         |
|                                 <span data-ttu-id="7a9c7-131">PeopleSoftTwoWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="7a9c7-131">PeopleSoftTwoWaySend.snk</span></span>                                  |                                                                                                                                                                                <span data-ttu-id="7a9c7-132">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-132">The strong naming key file.</span></span>                                                                                                                                                                                |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="7a9c7-133">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="7a9c7-133">How to Use This Sample</span></span>  

#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a><span data-ttu-id="7a9c7-134">PeopleSoft Enterprise アダプターの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-134">Create a new instance of the PeopleSoft Enterprise adapter</span></span>  

1. <span data-ttu-id="7a9c7-135">起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-135">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="7a9c7-136">クリックして**開始**、**プログラム**、 **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-136">Click **Start**, **Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="7a9c7-137">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順にクリックします**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-137">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3. <span data-ttu-id="7a9c7-138">右クリック**アダプター**  をポイント**新規**、**アダプター**を表示する、**アダプター プロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-138">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  

4. <span data-ttu-id="7a9c7-139">値を入力、**名前**フィールドに、たとえば**PeopleSoft**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-139">Enter a value for the **Name** field, for example **PeopleSoft**.</span></span>  

5. <span data-ttu-id="7a9c7-140">選択**PeopleSoft enterprise (r)** で利用可能なアダプターの一覧から、**アダプター**ドロップダウンをクリック **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-140">Select **PeopleSoft Enterprise(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

#### <a name="create-a-solicit-response-biztalk-send-port"></a><span data-ttu-id="7a9c7-141">送信請求-応答の BizTalk 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-141">Create a Solicit-Response BizTalk Send Port</span></span>  

1. <span data-ttu-id="7a9c7-142">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-142">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="7a9c7-143">右クリックして**送信ポート** をポイント**新規**、**静的な送信請求-応答送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-143">Right-click **Send Ports** and point to **New**, **Static Solicit-Response Send Port** to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="7a9c7-144">値を入力、**名前**フィールドに、たとえば**PeopleSoftTwoWaySP**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-144">Enter a value for the **Name** field, for example **PeopleSoftTwoWaySP**.</span></span>  

4. <span data-ttu-id="7a9c7-145">使用可能なアダプターの一覧から PeopleSoft アダプターを選択、**型**ドロップダウン ボックスし、をクリックして、**構成**アダプターを表示するボタン**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-145">Select the PeopleSoft adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="7a9c7-146">この値は、管理コンソールで PeopleSoft Enterprise アダプターの作成時に指定された名前です。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-146">This value is the name that was specified when the PeopleSoft Enterprise adapter was created in the Administration Console.</span></span>  

5. <span data-ttu-id="7a9c7-147">次の値を入力、**アダプターに必要なプロパティ**:</span><span class="sxs-lookup"><span data-stu-id="7a9c7-147">Enter the following values for the **Adapter Required Properties**:</span></span>  


   |       <span data-ttu-id="7a9c7-148">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="7a9c7-148">**Property**</span></span>       |                                                                                                                                        <span data-ttu-id="7a9c7-149">**[値]**</span><span class="sxs-lookup"><span data-stu-id="7a9c7-149">**Value**</span></span>                                                                                                                                         |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="7a9c7-150">アプリケーション サーバーのパス</span><span class="sxs-lookup"><span data-stu-id="7a9c7-150">Application server path</span></span>  | <span data-ttu-id="7a9c7-151">PeopleSoft Server のコンピューターおよびポートの場所、たとえば//PSServer:8888 します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-151">PeopleSoft Server's machine and port location, for example //PSServer:8888.</span></span> <span data-ttu-id="7a9c7-152">**注:** ポート番号を指定しない場合、これにより上記の例ででした入力//psserver 値、PeopleSoft サーバーは、既定のポート値 9000 を使用している場合に既定のポート 9000 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-152">**Note:**  If you do not specify a port number, the default port of 9000 is used so in the example above you could enter a value of //PSServer if the PeopleSoft Server uses the default port value of 9000.</span></span> |
   |        <span data-ttu-id="7a9c7-153">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="7a9c7-153">JAVA_HOME</span></span>         |                                                                                          <span data-ttu-id="7a9c7-154">Java 2 Platform SDK のファイル、たとえば C:\j2sdk1.4.2_08 に関連付けられているホーム ディレクトリへのパス</span><span class="sxs-lookup"><span data-stu-id="7a9c7-154">Path to the home directory associated with the Java 2 Platform SDK files, for example C:\j2sdk1.4.2_08</span></span>                                                                                          |
   |         <span data-ttu-id="7a9c7-155">パスワード</span><span class="sxs-lookup"><span data-stu-id="7a9c7-155">Password</span></span>         |                                                                                                                 <span data-ttu-id="7a9c7-156">PeopleSoft システムに接続するときに使用するパスワード。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-156">Password used when connecting to the PeopleSoft system.</span></span>                                                                                                                  |
   | <span data-ttu-id="7a9c7-157">PeopleSoft 8.x JAR ファイル</span><span class="sxs-lookup"><span data-stu-id="7a9c7-157">PeopleSoft 8.x JAR files</span></span> |                                                                                          <span data-ttu-id="7a9c7-158">PeopleSoft Java Object Adapter JAR ファイルの場所**psjoa.jar**、C:\JARS\psjoa.jar など。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-158">Location of the PeopleSoft Java Object Adapter JAR file, **psjoa.jar**, for example C:\JARS\psjoa.jar.</span></span>                                                                                          |
   |        <span data-ttu-id="7a9c7-159">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="7a9c7-159">User name</span></span>         |                                                                                                                    <span data-ttu-id="7a9c7-160">PeopleSoft システムに接続するためのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-160">Username for connecting to the PeopleSoft system.</span></span>                                                                                                                     |


6. <span data-ttu-id="7a9c7-161">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-161">Click **OK**.</span></span>  

7. <span data-ttu-id="7a9c7-162">選択、 **XMLTransmit**で利用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウンします。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-162">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown.</span></span>  

8. <span data-ttu-id="7a9c7-163">選択、 **XMLReceive**で利用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン をクリック**ok**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-163">Select the **XMLReceive** pipeline from the list of pipelines available in the **Receive pipeline** dropdown and click **OK**.</span></span>  

9. <span data-ttu-id="7a9c7-164">送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-164">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-one-way-biztalk-send-port"></a><span data-ttu-id="7a9c7-165">一方向 BizTalk 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-165">Create a One-Way BizTalk Send Port</span></span>  

1. <span data-ttu-id="7a9c7-166">たとえば C:\Files\Out、送信ポートで使用するターゲット フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-166">Create a target folder to be used by the send port, for example C:\Files\Out.</span></span>  

2. <span data-ttu-id="7a9c7-167">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-167">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

3. <span data-ttu-id="7a9c7-168">右クリックして**送信ポート** をポイント**新規**、**静的な一方向送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-168">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port** to display the **Send Port Properties** dialog.</span></span>  

4. <span data-ttu-id="7a9c7-169">値を入力、**名前**フィールドに、たとえば**PeopleSoftTwoWayFileSP**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-169">Enter a value for the **Name** field, for example **PeopleSoftTwoWayFileSP**.</span></span>  

5. <span data-ttu-id="7a9c7-170">選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-170">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

6. <span data-ttu-id="7a9c7-171">先ほど作成したフォルダーの場所を入力、**先フォルダー**プロパティをクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-171">Enter the location of the folder that you created earlier for the **Destination Folder** property and click **OK**.</span></span>  

7. <span data-ttu-id="7a9c7-172">選択、 **XMLTransmit**で利用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン をクリック**ok**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-172">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

8. <span data-ttu-id="7a9c7-173">送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-173">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-file-receive-port"></a><span data-ttu-id="7a9c7-174">ファイル受信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="7a9c7-174">Create a file receive port</span></span>  

1. <span data-ttu-id="7a9c7-175">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-175">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2. <span data-ttu-id="7a9c7-176">受信ポート フォルダーを右クリックし、をクリックし、**新規**、**一方向の受信ポート**受信ポートのプロパティ ダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-176">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port** to display the Receive Port Properties dialog.</span></span>  

3. <span data-ttu-id="7a9c7-177">値を入力、**名前**フィールドに**PeopleSoftTwoWayFileRP**、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-177">Enter a value for the **Name** field, for example **PeopleSoftTwoWayFileRP**, and click **OK**.</span></span>  

#### <a name="create-a-file-receive-location"></a><span data-ttu-id="7a9c7-178">ファイル受信場所を作成する</span><span class="sxs-lookup"><span data-stu-id="7a9c7-178">Create a file receive location</span></span>  

1.  <span data-ttu-id="7a9c7-179">フォルダーを作成して、ファイルによって監視される受信場所、C:\Files\In など。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-179">Create a folder to be monitored by the file receive location, for example C:\Files\In.</span></span>  

2.  <span data-ttu-id="7a9c7-180">右クリックし、新しい受信ポート をクリックし、**新規**、**受信場所**を表示する、**受信場所のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-180">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="7a9c7-181">値を入力、**名前**フィールドに、たとえば**PeopleSoftTwoWayFileRL**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-181">Enter a value for the **Name** field, for example **PeopleSoftTwoWayFileRL**.</span></span>  

4.  <span data-ttu-id="7a9c7-182">選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-182">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="7a9c7-183">先ほど作成したフォルダーの場所を入力、**受信フォルダー**プロパティをクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-183">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="7a9c7-184">選択**XMLReceive**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン ボックスし、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-184">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="7a9c7-185">受信場所を右クリックし、をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-185">Right-click the receive location and click **Enable**.</span></span>  

#### <a name="modify-the-adapter-schema-target-namespace-property"></a><span data-ttu-id="7a9c7-186">アダプター スキーマのターゲット名前空間のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-186">Modify the Adapter schema target namespace property</span></span>  

1. <span data-ttu-id="7a9c7-187">起動[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]TwoWaySend.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-187">Launch [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and open TwoWaySend.sln.</span></span> <span data-ttu-id="7a9c7-188">クリックして**ファイル**、**オープン**、**プロジェクト/ソリューション**を表示する、**プロジェクトを開く**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-188">Click **File**, **Open**, **Project/Solution** to display the **Open Project** dialog.</span></span>  

2. <span data-ttu-id="7a9c7-189">TwoWaySend.sln ファイルを [参照] をクリックし、このファイルを選択し、をクリックして**開く**サンプル プロジェクトを含むソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-189">Browse to the TwoWaySend.sln file, click to select this file and click **Open** to open the solution that contains the sample project.</span></span>  

3. <span data-ttu-id="7a9c7-190">をクリックして、**ビュー**メニュー選択し、**ソリューション エクスプ ローラー**ソリューション エクスプ ローラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-190">Click the **View** menu and select **Solution Explorer** to display the Solution Explorer.</span></span>  

4. <span data-ttu-id="7a9c7-191">ソリューション エクスプ ローラーを開くことで、LOCATIONService_1.xsd ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-191">Double-click the LOCATIONService_1.xsd file in the Solution Explorer to open it.</span></span>  

5. <span data-ttu-id="7a9c7-192">右クリックし、**スキーマ**LOCATIONService_1.xsd のノード、**プロパティ**スキーマのプロパティを表示するメニュー オプション。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-192">Right-click the **Schema** node of LOCATIONService_1.xsd and select the **Properties** menu option to display the properties for the schema.</span></span>  

6. <span data-ttu-id="7a9c7-193">編集、 **Target Namespace**など、アダプター名の適切な値を使用するプロパティ、 **Target Namespace**プロパティを次のように読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-193">Edit the **Target Namespace** property to use the appropriate values for the adapter name, for example the **Target Namespace** property should read as follows:</span></span>  

   ```  
   http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
   ```  

    <span data-ttu-id="7a9c7-194">場所*PeopleSoft*はで表示される PeopleSoft アダプターの名前、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-194">Where *PeopleSoft* is the name of the PeopleSoft adapter as viewed in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="7a9c7-195">場合設定値を**Target Namespace**によって入力ドキュメント インスタンスが処理されると、ルーティングの障害が発生し、入力ドキュメント インスタンスで指定された名前空間と一致しません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-195">If the configured value for **Target Namespace** does not match the namespace specified in the input document instance then a routing failure will occur when the input document instance is processed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="7a9c7-196">アダプター スキーマからドキュメント インスタンスを生成する</span><span class="sxs-lookup"><span data-stu-id="7a9c7-196">Generate a document instance from the Adapter schema</span></span>  

1.  <span data-ttu-id="7a9c7-197">ダブルクリック**LOCATIONService_1.xsd**をスキーマ エディターでファイルを開き、ソリューション エクスプ ローラーでします。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-197">Double-click **LOCATIONService_1.xsd** in Solution Explorer to open the file in Schema Editor.</span></span>  

2.  <span data-ttu-id="7a9c7-198">右クリックし、 **\<スキーマ\>** スキーマ エディターでノード**プロパティ**ノードのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-198">Right-click the **\<Schema\>** node in Schema Editor and click **Properties** to display properties for the node.</span></span>  

3.  <span data-ttu-id="7a9c7-199">選択**取得**で使用可能なノードの一覧から、**ルート参照**ドロップダウン ボックス。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-199">Select **Get** from the list of available nodes in the **Root Reference** dropdown box.</span></span> <span data-ttu-id="7a9c7-200">生成されるサンプルのドキュメント インスタンスを生成するときにようにこれ行う必要があります、**取得**スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-200">This should be done so that when you generate a sample document instance it will be generated from the **Get** node of the schema.</span></span>  

4.  <span data-ttu-id="7a9c7-201">右クリックして**LOCATIONService_1.xsd**ソリューション エクスプ ローラーをクリックします**プロパティ**プロパティ ウィンドウでプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-201">Right-click **LOCATIONService_1.xsd** in Solution Explorer and click **Properties** to display properties in the Properties window.</span></span>  

5.  <span data-ttu-id="7a9c7-202">[プロパティ] ウィンドウでクリックして選択、**出力インスタンス ファイル名**オプション。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-202">In the Properties window, click to select the **Output Instance Filename** option.</span></span>  

6.  <span data-ttu-id="7a9c7-203">表示するには、省略記号ボタン (...) をクリックして、**出力ファイルの選択**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-203">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

7.  <span data-ttu-id="7a9c7-204">たとえば、フォルダーと出力ファイル インスタンスの名前を指定**C:\instance.xml**  をクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-204">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="7a9c7-205">ファイル受信場所に指定したフォルダーの場所は、ここに指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-205">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

8.  <span data-ttu-id="7a9c7-206">ソリューション エクスプ ローラーで LOCATIONService_1.xsd を右クリックし、をクリックして**インスタンスの生成**指定された場所にドキュメント インスタンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-206">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

9. <span data-ttu-id="7a9c7-207">右クリックし、 **\<スキーマ\>** スキーマ エディターでノード**プロパティ**ノードのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-207">Right-click the **\<Schema\>** node in Schema Editor and click **Properties** to display the properties for the node.</span></span>  

10. <span data-ttu-id="7a9c7-208">選択 (**既定)** で使用可能なノードの一覧から、**ルート参照**ドロップダウン ボックス。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-208">Select (**Default)** from the list of available nodes in the **Root Reference** dropdown box.</span></span>  

#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="7a9c7-209">生成されたドキュメント インスタンスを変更する</span><span class="sxs-lookup"><span data-stu-id="7a9c7-209">Modify the generated document instance</span></span>  

1.  <span data-ttu-id="7a9c7-210">メモ帳などのテキスト エディターで生成されたドキュメント インスタンスを開き、これらのフィールドのデータが既存のレコードを返すことを確認するドキュメント インスタンスの内容を編集します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-210">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data in these fields will return an existing record:</span></span>  

    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
    <ns0:SETID>SHARE</ns0:SETID>  
    <ns0:LOCATION>WFKLOC</ns0:LOCATION>  
    <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  

    > [!NOTE]
    >  <span data-ttu-id="7a9c7-211">上記の例で*PeopleSoft*アダプターの実際の名前のプレース ホルダーは、BizTalk 管理コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-211">In the example above, *PeopleSoft* is a placeholder for the actual name of the adapter as viewed in the BizTalk Administration Console.</span></span> <span data-ttu-id="7a9c7-212">*共有*と*WFKLOC* PeopleSoft システムの特定のレコードを識別するために使用される値のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-212">*SHARE* and *WFKLOC* are placeholders for values used to identify a particular record in the PeopleSoft system.</span></span>  

2.  <span data-ttu-id="7a9c7-213">変更したドキュメント インスタンスを保存します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-213">Save the modified document instance.</span></span>  

#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="7a9c7-214">プロジェクトのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="7a9c7-214">Build and deploy the project</span></span>  

1. <span data-ttu-id="7a9c7-215">ソリューション エクスプ ローラーで TwoWaySend プロジェクトを右クリックし、をクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-215">Right-click the TwoWaySend project in Solution Explorer and click **Properties** to display the Project Designer for the project.</span></span>  

2. <span data-ttu-id="7a9c7-216">をクリックして、**展開**プロジェクト デザイナー タブ。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-216">Click the **Deployment** tab in the Project Designer.</span></span>  

3. <span data-ttu-id="7a9c7-217">適切な値を入力、 **Server**プロパティと**構成データベース**のプロパティの  **BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-217">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  

4. <span data-ttu-id="7a9c7-218">ソリューション エクスプ ローラーで TwoWaySend プロジェクトを右クリックし、をクリックして**デプロイ**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-218">Right-click the TwoWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="7a9c7-219">オーケストレーションをバインドして参加させる</span><span class="sxs-lookup"><span data-stu-id="7a9c7-219">Bind and Enlist the orchestration</span></span>  

1. <span data-ttu-id="7a9c7-220">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-220">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="7a9c7-221">をクリックして、**更新**ボタン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールのツールバーまたはキーを押して、 **F5**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-221">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console view.</span></span>  

3. <span data-ttu-id="7a9c7-222">表示するオーケストレーションをダブルクリックして、**オーケストレーションのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-222">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="7a9c7-223">クリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-223">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="7a9c7-224">バインド オプションに適切な値を指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-224">Specify the appropriate values for the binding options, for example:</span></span>  


   |      <span data-ttu-id="7a9c7-225">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="7a9c7-225">**Parameter**</span></span>      |        <span data-ttu-id="7a9c7-226">**[値]**</span><span class="sxs-lookup"><span data-stu-id="7a9c7-226">**Value**</span></span>         |
   |-------------------------|--------------------------|
   |          <span data-ttu-id="7a9c7-227">ホスト</span><span class="sxs-lookup"><span data-stu-id="7a9c7-227">Host</span></span>           | <span data-ttu-id="7a9c7-228">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="7a9c7-228">BizTalkServerApplication</span></span> |
   |     <span data-ttu-id="7a9c7-229">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="7a9c7-229">FileReceivePort</span></span>     |  <span data-ttu-id="7a9c7-230">PeopleSoftTwoWayFileRP</span><span class="sxs-lookup"><span data-stu-id="7a9c7-230">PeopleSoftTwoWayFileRP</span></span>  |
   | <span data-ttu-id="7a9c7-231">PeopleSoftTwoWaySend678</span><span class="sxs-lookup"><span data-stu-id="7a9c7-231">PeopleSoftTwoWaySend678</span></span> |    <span data-ttu-id="7a9c7-232">PeopleSoftTwoWaySP</span><span class="sxs-lookup"><span data-stu-id="7a9c7-232">PeopleSoftTwoWaySP</span></span>    |
   |      <span data-ttu-id="7a9c7-233">ResponsePort</span><span class="sxs-lookup"><span data-stu-id="7a9c7-233">ResponsePort</span></span>       |  <span data-ttu-id="7a9c7-234">PeopleSoftTwoWayFileSP</span><span class="sxs-lookup"><span data-stu-id="7a9c7-234">PeopleSoftTwoWayFileSP</span></span>  |


6. <span data-ttu-id="7a9c7-235">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-235">Click OK.</span></span>  

#### <a name="start-the-orchestration"></a><span data-ttu-id="7a9c7-236">オーケストレーションを開始します</span><span class="sxs-lookup"><span data-stu-id="7a9c7-236">Start the orchestration</span></span>  

- <span data-ttu-id="7a9c7-237">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、オーケストレーションを右クリックし、クリックして**開始**を参加させて、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-237">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="7a9c7-238">ファイル受信場所の監視対象フォルダーにドキュメント インスタンスをドロップする</span><span class="sxs-lookup"><span data-stu-id="7a9c7-238">Drop a document instance into the folder monitored by the file receive location</span></span>  

-   <span data-ttu-id="7a9c7-239">ファイルの受信場所のフォルダーに作成したドキュメント インスタンスが監視するよう構成をコピーします。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-239">Copy the document instance that was created earlier to the folder that the file receive location is configured to monitor.</span></span>  

#### <a name="verify-that-the-document-instance-was-processed-by-the-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="7a9c7-240">ドキュメント インスタンスは、PeopleSoft Enterprise の BizTalk アダプターによって処理されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-240">Verify that the document instance was processed by the BizTalk Adapter for PeopleSoft Enterprise</span></span>  

- <span data-ttu-id="7a9c7-241">ファイル送信ポートの送信先として構成されているフォルダーを開いて、出力ドキュメントが生成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-241">Open the folder that the file send port is configured to send to and verify that an output document was generated.</span></span> <span data-ttu-id="7a9c7-242">このファイルで BizTalk Adapter for PeopleSoft Enterprise の処理されたクエリの結果を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-242">This file should contain the results of the query that was processed by the BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

  <span data-ttu-id="7a9c7-243">ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-243">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="7a9c7-244">ファイル アダプターがフォルダーからファイルを取得し、メッセージボックスに BizTalk メッセージとして公開します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-244">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="7a9c7-245">オーケストレーションがこの公開されたメッセージをサブスクライブします。これにより、BizTalk メッセージング エンジンがオーケストレーションのインスタンスをアクティブ化し、オーケストレーション インスタンスにメッセージを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-245">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="7a9c7-246">オーケストレーション インスタンスがメッセージ ボックスにメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-246">The orchestration instance publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="7a9c7-247">送信請求-応答の送信ポートは、BizTalk メッセージング エンジンは、PeopleSoft 送信ポートにメッセージを送信するために、この公開されたメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-247">The solicit-response send port subscribes to this published message so the BizTalk Messaging Engine sends the message to the PeopleSoft send port.</span></span>  

5.  <span data-ttu-id="7a9c7-248">送信ポートを BizTalk Adapter for PeopleSoft Enterprise のメッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-248">The send port hands the message to the BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

6.  <span data-ttu-id="7a9c7-249">BizTalk Adapter for PeopleSoft Enterprise は、入力ファイルで定義されているパラメーターを使用して PeopleSoft システムに対して Get ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-249">The BizTalk Adapter for PeopleSoft Enterprise executes a Get statement against the PeopleSoft system using the parameters defined in the input file.</span></span>  

7.  <span data-ttu-id="7a9c7-250">BizTalk Adapter for PeopleSoft Enterprise では、オーケストレーションの送信請求-応答ポートの応答メッセージとして Get ステートメントの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-250">The BizTalk Adapter for PeopleSoft Enterprise returns the results of the Get statement as the response message for the solicit-response port in the orchestration.</span></span>  

8.  <span data-ttu-id="7a9c7-251">オーケストレーションでは、メッセージ ボックスに結果セットを公開します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-251">The orchestration publishes the result set to the MessageBox.</span></span>  

9. <span data-ttu-id="7a9c7-252">ファイル送信ポートがこのメッセージをサブスクライブし、BizTalk がメッセージをファイル アダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-252">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  

10. <span data-ttu-id="7a9c7-253">ファイル アダプターが、結果セットを含むメッセージを指定の出力フォルダーに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7a9c7-253">The File adapter writes the message containing the result set to the designated output folder.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7a9c7-254">参照</span><span class="sxs-lookup"><span data-stu-id="7a9c7-254">See Also</span></span>  
 [<span data-ttu-id="7a9c7-255">チュートリアル:BizTalk Adapter for PeopleSoft Enterprise の使用</span><span class="sxs-lookup"><span data-stu-id="7a9c7-255">Tutorials: Using BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)