---
title: "JD Edwards OneWorld サンプル クエリを実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b060d383-a2df-472f-90cc-e79078b0bcfd
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4e15310442d12c0b2604eb0d22b071ff6c57212
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="execute-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="cb5da-102">JD Edwards OneWorld サンプル クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-102">Execute a JD Edwards OneWorld Sample Query</span></span>
<span data-ttu-id="cb5da-103">JD Edwards OneWorld (JDEOW) システムに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムからアクセスするには、JD Edwards OneWorld アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-103">The JD Edwards OneWorld (JDEOW) system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="cb5da-104">このアダプターは、付属[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-104">This adapter is included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>
  
 <span data-ttu-id="cb5da-105">これは、JD Edwards OneWorld ラボ作業の 2 つめのパートです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-105">This is the second part of the JD Edwards OneWorld lab work.</span></span> <span data-ttu-id="cb5da-106">最初のパート (ラボ 1) では、JD Edwards OneWorld システムのデータに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] などの Microsoft テクノロジーを使用せずに手動でアクセスしました。</span><span class="sxs-lookup"><span data-stu-id="cb5da-106">In the first part (Lab 1), you manually accessed data on the JD Edwards OneWorld system without the assistance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or other Microsoft technologies.</span></span> <span data-ttu-id="cb5da-107">このパート (ラボ 2) では、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトの一部として、BizTalk オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-107">In this part (Lab 2), you will create a BizTalk orchestration as part of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project.</span></span> <span data-ttu-id="cb5da-108">JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムからデータを取得するように、このオーケストレーションのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-108">You will configure ports on this orchestration to use the JD Edwards OneWorld adapter to get data from a JD Edwards OneWorld system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cb5da-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="cb5da-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="cb5da-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb5da-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>
  
-   <span data-ttu-id="cb5da-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb5da-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="cb5da-112">JD Edwards OneWorld クライアント ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="cb5da-112">JD Edwards OneWorld Client software</span></span>  
  
-   <span data-ttu-id="cb5da-113">別のサーバー上にある JD Edwards OneWorld システムへのネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="cb5da-113">Network connectivity to a JD Edwards OneWorld system on another server</span></span>  
  
-   <span data-ttu-id="cb5da-114">Microsoft BizTalk Adapters for Enterprise Applications</span><span class="sxs-lookup"><span data-stu-id="cb5da-114">Microsoft BizTalk Adapters for Enterprise Applications</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb5da-115">参照してください[をインストールし、エンタープライズ アプリケーション用のアダプターを構成](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)JD Edwards、PeopleSoft、および TIBCO アダプターのキーの構成についてはします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-115">See [Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) for key configuration information for the JD Edwards, PeopleSoft, and TIBCO adapters.</span></span>  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="cb5da-116">ラボ 2 - JD Edwards OneWorld サンプル クエリの実行</span><span class="sxs-lookup"><span data-stu-id="cb5da-116">Lab 2 - Executing a JD Edwards OneWorld Sample Query</span></span>  
 <span data-ttu-id="cb5da-117">このラボでは、実行、**取得**JD Edwards OneWorld システムに対して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-117">In this lab, you will execute a **Get** operation against the JD Edwards OneWorld system.</span></span> <span data-ttu-id="cb5da-118">具体的には、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-118">Specifically you will perform the following tasks:</span></span>  
  
-   <span data-ttu-id="cb5da-119">JD Edwards OneWorld の前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-119">Verify the JD Edwards OneWorld prerequisites</span></span>  
  
-   <span data-ttu-id="cb5da-120">JD Edwards OneWorld 送信ポートを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でセットアップ</span><span class="sxs-lookup"><span data-stu-id="cb5da-120">Set up a JD Edwards OneWorld send port in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="cb5da-121">BizTalk オーケストレーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="cb5da-121">Create a BizTalk orchestration project</span></span>  
  
-   <span data-ttu-id="cb5da-122">プロジェクトのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="cb5da-122">Build and deploy the project</span></span>  
  
-   <span data-ttu-id="cb5da-123">アプリケーションのテストと XML 出力の表示</span><span class="sxs-lookup"><span data-stu-id="cb5da-123">Test the application and view the XML output</span></span>  
  
 <span data-ttu-id="cb5da-124">JD Edwards OneWorld アダプターを使用して、JD Edwards OneWorld システム上のデータに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-124">You will use the JD Edwards OneWorld adapter to access data on the JD Edwards OneWorld system from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cb5da-125">このアダプターを使用すると、オーケストレーションによって実行される要求と応答を使用して JD Edwards OneWorld のオブジェクトの処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-125">This adapter enables the processing of JD Edwards OneWorld objects by using requests and responses executed by an orchestration.</span></span> <span data-ttu-id="cb5da-126">1 つのスキーマ オブジェクトに対して使用可能なメソッドは多数あります。</span><span class="sxs-lookup"><span data-stu-id="cb5da-126">Many methods are available for a schema object.</span></span> <span data-ttu-id="cb5da-127">このラボを使用する方法を示しています、 **Address Book MBF**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-127">This lab demonstrates how to use the **Address Book MBF** method.</span></span>  
  
 <span data-ttu-id="cb5da-128">サービス要求を実行する前に、対象の JD Edwards OneWorld オブジェクトに対するサービス要求と応答のスキーマを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb5da-128">Before running a service request, you must create service request and response schemas for the specific JD Edwards OneWorld object.</span></span> <span data-ttu-id="cb5da-129">これらのスキーマは、生成した項目の追加/アダプターの追加ウィザードによって、JD Edwards OneWorld 内のサポート メタデータ オブジェクトに直接問い合わせることによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-129">The Add Generated Items/Add Adapter Wizard creates these schemas by directly interrogating the supporting metadata object in JD Edwards OneWorld.</span></span> <span data-ttu-id="cb5da-130">このラボ用スキーマの作成に必要な手順を示しています、 **Address Book MBF**メソッドとクエリを処理します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-130">This lab illustrates the steps required to create schemas for the **Address Book MBF** method and to process a query.</span></span>  
  
## <a name="step-1-verify-the-jd-edwards-oneworld-prerequisites"></a><span data-ttu-id="cb5da-131">手順 1: JD Edwards OneWorld の前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-131">Step 1: Verify the JD Edwards OneWorld prerequisites</span></span>  
 <span data-ttu-id="cb5da-132">JD Edwards OneWorld アダプターと共に使用する BizTalk プロジェクトの作成を開始する前に、JD Edwards OneWorld システムにアクセスできるように適切にファイルとアダプターがセットアップされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb5da-132">Before you start creating a BizTalk project for use with the JD Edwards OneWorld adapter, you need to be sure the files and the adapter are set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="cb5da-133">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上の JD Edwards OneWorld アダプターと JD Edwards OneWorld システムとの通信には、Java インターフェイスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-133">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, the JD Edwards OneWorld adapter communicates with the JD Edwards OneWorld system by using the Java interface.</span></span>    

1. <span data-ttu-id="cb5da-134">JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムに適切にアクセスするには、Connector.jar、Kernel.jar、BTSLIBinterop.jar、JDEJAccess.jar の 4 つのファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-134">Four files are necessary for proper interface access to a JD Edwards OneWorld system using the JD Edwards OneWorld adapter: Connector.jar, Kernel.jar, BTSLIBinterop.jar, and JDEJAccess.jar.</span></span>  
  
    -   <span data-ttu-id="cb5da-135">Connector.jar と Kernel.jar は、JD Edwards OneWorld システムに付属しています。JD Edwards OneWorld 管理者から入手してください。</span><span class="sxs-lookup"><span data-stu-id="cb5da-135">The Connector.jar and Kernel.jar files come with the JD Edwards OneWorld system and are obtained from a JD Edwards OneWorld administrator.</span></span> <span data-ttu-id="cb5da-136">これらのファイルの場所は、C:\JDEOWJars フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-136">These files are located in the C:\JDEOWJars folder.</span></span>  
  
    -   <span data-ttu-id="cb5da-137">BTSLIBinterop.jar ファイルは、アダプターのインストール ガイドに記載されている手順に従って JD Edwards OneWorld システムによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-137">The BTSLIBinterop.jar file is generated by the JD Edwards OneWorld system by following the instructions included in the Installation Guide for the adapters.</span></span> <span data-ttu-id="cb5da-138">このファイルの場所は、C:\JDEOWJars フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-138">This file is located in the C:\JDEOWJars folder.</span></span>  
  
    -   <span data-ttu-id="cb5da-139">JDEJAccess.jar ファイルは JDEOW アダプターの一部であり、アダプターのインストール時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-139">The JDEJAccess.jar file is a part of the JDEOW adapter and is included with the installation of the adapter.</span></span> <span data-ttu-id="cb5da-140">既定にある、C:\Program files \microsoft BizTalk Adapters Enterprise applications \j.d. 用です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-140">By default, it is located in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="cb5da-141">Edwards OneWorld® \Classes フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-141">Edwards OneWorld®\Classes folder.</span></span>  
  
2. <span data-ttu-id="cb5da-142">Connector.jar、Kernel.jar、ことを確認し、BTSLIBinterop.jar ファイル上に存在、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] C:\JDEOWJars フォルダー内のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="cb5da-142">Confirm the Connector.jar, Kernel.jar, and BTSLIBinterop.jar files exist on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\JDEOWJars folder.</span></span>  
  
3. <span data-ttu-id="cb5da-143">JDEJAccess.jar ファイル上に存在することを確認、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] C:\Program files \microsoft BizTalk Adapters for Enterprise applications \j.d. 内のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="cb5da-143">Confirm the JDEJAccess.jar file exists on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="cb5da-144">Edwards OneWorld\Classes フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-144">Edwards OneWorld\Classes folder.</span></span>  
  
## <a name="step-2-configure-biztalk-send-ports"></a><span data-ttu-id="cb5da-145">手順 2: BizTalk 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-145">Step 2: Configure BizTalk send ports</span></span>  
<span data-ttu-id="cb5da-146">次に、いることを確認、JD Edwards OneWorld アダプターがインストールされている送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-146">Next, verify that the JD Edwards OneWorld adapter is installed, and create the send port.</span></span>  

1.  <span data-ttu-id="cb5da-147">開いている**BizTalk Server 管理コンソール**、展開**コンソール ルート**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**の順に展開および**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-147">Open **BizTalk Server Administration**, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
    <span data-ttu-id="cb5da-148">確認、 **JDE_OneWorld**アダプターが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-148">Confirm the **JDE_OneWorld** adapter is listed.</span></span> <span data-ttu-id="cb5da-149">JD Edwards OneWorld アダプターがインストールされていない場合は、BizTalk Adapters for Enterprise Applications をインストールしてください (前の「前提条件」の項を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="cb5da-149">If the JD Edwards OneWorld adapter is not installed, install the BizTalk Adapters for Enterprise Applications (see the earlier "Prerequisites" section).</span></span> <span data-ttu-id="cb5da-150">アダプターをインストールしたらを右クリックし**アダプター**  をクリックし、 **New - Adapter** JD Edwards OneWorld アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-150">After the adapters are installed, right-click **Adapters** and then click **New - Adapter** to install the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="cb5da-151">これを有効にするホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-151">Restart the host instance for this to take effect.</span></span>  
  
2. <span data-ttu-id="cb5da-152">展開**アプリケーション**の順に展開および**BizTalk アプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-152">Expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="cb5da-153">右クリック**送信ポート**をクリックして**新規**、順にクリック**静的な送信請求-応答送信ポート**です。これらのフィールドに、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-153">Right-click **Send Ports**, click **New**, and then click **Static Solicit-Response Send Port**.Enter the following values for these fields:</span></span>  
  
    1.  <span data-ttu-id="cb5da-154">**[名前]:**  `JDE_OneWorldPort`</span><span class="sxs-lookup"><span data-stu-id="cb5da-154">**Name:**  `JDE_OneWorldPort`</span></span>  
  
    2.  <span data-ttu-id="cb5da-155">**型:**  `JDE_OneWorld`</span><span class="sxs-lookup"><span data-stu-id="cb5da-155">**Type:**  `JDE_OneWorld`</span></span>  
  
    3.  <span data-ttu-id="cb5da-156">**送信ハンドラー。**  `BizTalkServerApplication`</span><span class="sxs-lookup"><span data-stu-id="cb5da-156">**Send handler:**  `BizTalkServerApplication`</span></span>  
  
    4.  <span data-ttu-id="cb5da-157">**送信パイプライン。**  `XMLTransmit`</span><span class="sxs-lookup"><span data-stu-id="cb5da-157">**Send pipeline:**  `XMLTransmit`</span></span>  
  
    5.  <span data-ttu-id="cb5da-158">**受信パイプライン。**  `XMLReceive`</span><span class="sxs-lookup"><span data-stu-id="cb5da-158">**Receive pipeline:**  `XMLReceive`</span></span>  
  
4.  <span data-ttu-id="cb5da-159">**[構成]**をクリックし、次のプロパティ値を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-159">Click **Configure**, and then enter the following property values:</span></span>  
  
    1.  <span data-ttu-id="cb5da-160">**ホスト:** \<JDEOW ホスト名を入力してください\></span><span class="sxs-lookup"><span data-stu-id="cb5da-160">**Host:** \<enter your JDEOW host name\></span></span>  
  
    2.  <span data-ttu-id="cb5da-161">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="cb5da-161">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
    3.  <span data-ttu-id="cb5da-162">**JDEdwards 環境:** \<JDEOW 環境を入力してください\></span><span class="sxs-lookup"><span data-stu-id="cb5da-162">**JDEdwards Environment:** \<enter your JDEOW environment\></span></span>  
  
    4.  <span data-ttu-id="cb5da-163">**JDEdwards JAR ファイル:** \<JAR ファイルの完全なパスを入力してください\></span><span class="sxs-lookup"><span data-stu-id="cb5da-163">**JDEdwards JAR files:** \<enter full path of JAR files\></span></span>  
  
         `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
    5.  <span data-ttu-id="cb5da-164">**パスワード:**ドロップダウン リストを使用して、JD Edwards OneWorld パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-164">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
    6.  <span data-ttu-id="cb5da-165">**ポート:**  `6009`</span><span class="sxs-lookup"><span data-stu-id="cb5da-165">**Port:**  `6009`</span></span>  
  
    7.  <span data-ttu-id="cb5da-166">**ユーザー名:** \<JD Edwards のユーザー名を入力\></span><span class="sxs-lookup"><span data-stu-id="cb5da-166">**User Name:** \<enter your JD Edwards User Name\></span></span>  
  
     <span data-ttu-id="cb5da-167">![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")</span><span class="sxs-lookup"><span data-stu-id="cb5da-167">![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")</span></span>  
  
5.  <span data-ttu-id="cb5da-168">選択**OK**を閉じる、**送信ポートのプロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-168">Select **OK** to close the **Send Port Properties**.</span></span>  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a><span data-ttu-id="cb5da-169">手順 3: BizTalk オーケストレーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-169">Step 3: Create a BizTalk Orchestration Project</span></span>  
<span data-ttu-id="cb5da-170">次に、BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、間の通信を処理するプロジェクトで、オーケストレーションを構成して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と JD Edwards OneWorld システムです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-170">Next, create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and configure an orchestration in the project to handle communication between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the JD Edwards OneWorld system.</span></span> <span data-ttu-id="cb5da-171">送信と受信のポートを追加し、プロジェクトをビルドしてから、プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-171">You will add send and receive ports, build the project, and then deploy the project.</span></span>  

  
1.  <span data-ttu-id="cb5da-172">開いている[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、C:\LABS フォルダーに新しい BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-172">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and create a new BizTalk project in the C:\LABS folder.</span></span> <span data-ttu-id="cb5da-173">**[ファイル]** メニューの **[新規作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-173">On the **File** menu, click **New**.</span></span> <span data-ttu-id="cb5da-174">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-174">The **New Project** dialog box appears.</span></span> <span data-ttu-id="cb5da-175">**[テンプレート]** セクションで **[空の BizTalk Server プロジェクト]**</span><span class="sxs-lookup"><span data-stu-id="cb5da-175">In the **Templates** section, select **Empty BizTalk Server project.**</span></span> <span data-ttu-id="cb5da-176">入力`JDE_OW_Test`クリックして一意のプロジェクト名として**OK**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-176">Enter `JDE_OW_Test` as the unique project name, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="cb5da-177">ソリューション エクスプローラーでプロジェクト名を右クリックし、 **[追加]**をクリックし、 **[生成した項目の追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-177">In Solution Explorer, right-click the project, click **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="cb5da-178">[カテゴリ] ウィンドウで、次のように選択します。**アダプター メタデータの追加**、[テンプレート] ペインで選択**アダプター メタデータの追加**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-178">In the Categories pane, select **Add Adapter Metadata**, in the Templates pane, select **Add Adapter Metadata**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="cb5da-179">アダプターの追加ウィザードで選択、 **JD Edwards OneWorld**アダプター、select、 **[jde_oneworldport]** 、前の手順で作成したポートを送信し、をクリックして**次**.</span><span class="sxs-lookup"><span data-stu-id="cb5da-179">In the Add Adapter Wizard, select the **JD Edwards OneWorld** adapter, select the **JDE_OneWorldPort** send port that you created in the preceding procedure, and then click **Next**.</span></span>  
  
     <span data-ttu-id="cb5da-180">![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")</span><span class="sxs-lookup"><span data-stu-id="cb5da-180">![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")</span></span>  
  
4.  <span data-ttu-id="cb5da-181">**[インポートするサービス**] ページで、開いている**JD Edwards OneWorld**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-181">On the **Select Services to Import** page, open **JD Edwards OneWorld**.</span></span> <span data-ttu-id="cb5da-182">JDEOW システムへのアダプター経由でのアクセスには、BrowsingAgent プログラムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-182">The JDEOW system is contacted through the adapter by using the BrowsingAgent program.</span></span> <span data-ttu-id="cb5da-183">この BrowsingAgent からは、次に示すサービスが返されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-183">The BrowsingAgent returns the following services.</span></span>  
  
     <span data-ttu-id="cb5da-184">![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")</span><span class="sxs-lookup"><span data-stu-id="cb5da-184">![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")</span></span>  
  
5.  <span data-ttu-id="cb5da-185">展開**CALLBSFN**まで下にスクロール**N0100041 - Address Book MBF**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-185">Expand **CALLBSFN** and scroll down to **N0100041 - Address Book MBF**.</span></span> <span data-ttu-id="cb5da-186">N0100041 を選択し、クリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-186">Select N0100041 and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="cb5da-187">ソリューション エクスプローラーに、新しい BizTalk オーケストレーションと、2 つの新しい関連スキーマ ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-187">In Solution Explorer, there is a new BizTalk orchestration with two new associated schema files.</span></span> <span data-ttu-id="cb5da-188">これらのファイルはアダプターの追加ウィザードによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-188">These files are created by the Add Adapter Wizard.</span></span> <span data-ttu-id="cb5da-189">**BizTalk Orchestration.odx** ファイルをダブルクリックし、オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-189">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
     <span data-ttu-id="cb5da-190">![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")</span><span class="sxs-lookup"><span data-stu-id="cb5da-190">![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")</span></span>  
  
 <span data-ttu-id="cb5da-191">このオーケストレーションは、JD Edwards OneWorld システムに合わせてフォーマットされた XML ファイルをファイル アダプターから受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cb5da-191">This orchestration accepts as input from the File adapter an XML file formatted for the JD Edwards OneWorld system.</span></span> <span data-ttu-id="cb5da-192">この XML ファイルは、JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムに送信されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-192">The orchestration uses the JD Edwards OneWorld adapter to send the XML file to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="cb5da-193">JD Edwards OneWorld は、クエリを処理して、結果が格納された出力 XML ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-193">JD Edwards OneWorld processes the query and generates an output XML file containing the results.</span></span> <span data-ttu-id="cb5da-194">この XML ファイルは、JD Edwards OneWorld アダプターを介してオーケストレーションに返され、ファイル アダプターによってディスク上の出力場所に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-194">This XML file returns to the orchestration through the JD Edwards OneWorld adapter, and the File adapter writes the XML file to the output location on disk.</span></span>  
  
 <span data-ttu-id="cb5da-195">オーケストレーションを完成させるには、XML の送信と受信のためのポートを作成および構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb5da-195">To complete the orchestration, you need to create and configure ports to receive and send the XML files.</span></span> <span data-ttu-id="cb5da-196">初めに、受信ポートを構成します。これは、ファイル アダプターがディスクから読み取った XML ファイルをオーケストレーションに渡すのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-196">First, configure a receive port to be used by the File adapter to input the XML containing the query into the orchestration from disk.</span></span>  
  
#### <a name="configure-a-receive-port-to-accept-the-input-xml-file"></a><span data-ttu-id="cb5da-197">入力 XML ファイルをそのまま使用する受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-197">Configure a receive port to accept the input XML file</span></span>  
  
1.  <span data-ttu-id="cb5da-198">**BizTalk Orchestration.odx** ファイルをダブルクリックし、オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-198">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
2.  <span data-ttu-id="cb5da-199">BizTalk Orchestration.odx ファイルで、左ポート画面を右クリックし、をクリックして**新しい構成済みポート**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-199">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="cb5da-200">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-200">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="cb5da-201">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-201">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="cb5da-202">**ポートのプロパティ** ページで、入力`JDE_File_In`の**名前**、クリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-202">On the **Port Properties** page, enter `JDE_File_In` for **Name**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="cb5da-203">**[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]**を選択し、次のプロパティ値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-203">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="cb5da-204">**ポートの種類名**:`JDE_FileIn_Port`</span><span class="sxs-lookup"><span data-stu-id="cb5da-204">**Port Type Name**: `JDE_FileIn_Port`</span></span>  
  
     <span data-ttu-id="cb5da-205">**[通信方式]**: **一方向**</span><span class="sxs-lookup"><span data-stu-id="cb5da-205">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="cb5da-206">**[アクセスの制限]**: **[内部 - このプロジェクト限定]**</span><span class="sxs-lookup"><span data-stu-id="cb5da-206">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
5.  <span data-ttu-id="cb5da-207">**[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-207">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="cb5da-208">**[ポートの通信方向]**: **常にこのポートでメッセージを受信する**</span><span class="sxs-lookup"><span data-stu-id="cb5da-208">**Port direction of communication**: **I'll always be receiving messages on this port**</span></span>  
  
     <span data-ttu-id="cb5da-209">**[ポートのバインド]**: **[後で指定する]**</span><span class="sxs-lookup"><span data-stu-id="cb5da-209">**Port binding**: **Specify later**</span></span>  
  
6.  <span data-ttu-id="cb5da-210">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-210">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="cb5da-211">次に、送信/受信ポートを作成します。これは、クエリが格納された最初の XML 入力ファイルを JD Edwards OneWorld システムに送信するためのものです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-211">Next, create a send/receive port to send the initial XML input file containing the query to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="cb5da-212">このポートは、クエリの結果が格納された出力 XML ファイルを JD Edwards OneWorld システムから受信するのにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-212">This port will also receive an output XML file containing the query results from the call to the JD Edwards OneWorld system.</span></span>  
  
#### <a name="configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a><span data-ttu-id="cb5da-213">JD Edwards OneWorld とインターフェイスへの送信/受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-213">Configure a send/receive port to interface with JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="cb5da-214">BizTalk Orchestration.odx ファイルで右ポート画面を右クリックし、をクリックして**新しい構成済みポート**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-214">In the BizTalk Orchestration.odx file, right-click the right port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="cb5da-215">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-215">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="cb5da-216">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-216">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="cb5da-217">**[ポートの種類の選択]** ページで、 **[既存のポートの種類を使用する]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-217">On the **Select a Port Type** page, select **Use an existing Port Type**.</span></span> <span data-ttu-id="cb5da-218">**使用可能なポートの種類** **JD_OW_Test.N0100041**、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-218">Under **Available Port Types**, select **JD_OW_Test.N0100041**,and then click **Next**.</span></span>  
  
     <span data-ttu-id="cb5da-219">![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")</span><span class="sxs-lookup"><span data-stu-id="cb5da-219">![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")</span></span>  
  
3.  <span data-ttu-id="cb5da-220">プロパティ値を次のとおりに選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-220">Select the following property values:</span></span>  
  
     <span data-ttu-id="cb5da-221">**ポートの通信方向**:**要求の送信と応答の受信を行います**</span><span class="sxs-lookup"><span data-stu-id="cb5da-221">**Port direction of communication**: **I'll be sending a request and receiving a response**</span></span>  
  
     <span data-ttu-id="cb5da-222">**[ポートのバインド]**: **[後で指定する]**</span><span class="sxs-lookup"><span data-stu-id="cb5da-222">**Port binding**: **Specify later**</span></span>  
  
4.  <span data-ttu-id="cb5da-223">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-223">Click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="cb5da-224">ポート画面に、ポートと使用可能なメソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-224">On the port surface you will see the port and the available methods.</span></span>  
  
 <span data-ttu-id="cb5da-225">最後に、送信ポートを構成します。これは、クエリの結果を格納した XML ファイルをファイル アダプターがディスクに出力するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-225">Finally, configure a send port to be used by the File adapter to output the XML containing the query results to disk.</span></span>  
  
#### <a name="configure-a-send-port-to-output-the-xml-file-to-disk"></a><span data-ttu-id="cb5da-226">XML ファイルをディスクに出力する送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-226">Configure a send port to output the XML file to disk</span></span>  
  
1.  <span data-ttu-id="cb5da-227">BizTalk Orchestration.odx ファイルで、左ポート画面を右クリックし、をクリックして**新しい構成済みポート**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-227">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="cb5da-228">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-228">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="cb5da-229">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-229">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="cb5da-230">**ポートのプロパティ** ページで、入力`JDE_FileOut`の**名前**、クリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-230">On the **Port Properties** page, enter `JDE_FileOut` for **Name**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="cb5da-231">**[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]**を選択し、次のプロパティ値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-231">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="cb5da-232">**ポートの種類名**:`JDE_FileOut_Port`</span><span class="sxs-lookup"><span data-stu-id="cb5da-232">**Port Type Name**: `JDE_FileOut_Port`</span></span>  
  
     <span data-ttu-id="cb5da-233">**[通信方式]**: **一方向**</span><span class="sxs-lookup"><span data-stu-id="cb5da-233">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="cb5da-234">**[アクセスの制限]**: **[内部 - このプロジェクト限定]**</span><span class="sxs-lookup"><span data-stu-id="cb5da-234">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4.  <span data-ttu-id="cb5da-235">**[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-235">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="cb5da-236">**[ポートの通信方向]**: **[常にこのポートでメッセージを送信する]**</span><span class="sxs-lookup"><span data-stu-id="cb5da-236">**Port direction of communication**: **I'll always be sending messages on this port**</span></span>  
  
     <span data-ttu-id="cb5da-237">**[ポートのバインド]**: **[後で指定する]**</span><span class="sxs-lookup"><span data-stu-id="cb5da-237">**Port binding**: **Specify later**</span></span>  
  
5.  <span data-ttu-id="cb5da-238">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-238">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="cb5da-239">ポート画面に、JD Edwards OneWorld のサービスのための新しいポートと使用できるメソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-239">Displayed on the port surface are the new ports and the available methods for the JD Edwards OneWorld services.</span></span> <span data-ttu-id="cb5da-240">JD Edwards OneWorld システムとの間でファイルを送受信するように JD Edwards OneWorld アダプターを設定する作業は、後で行います。</span><span class="sxs-lookup"><span data-stu-id="cb5da-240">Later you will specify the JD Edwards OneWorld adapter to send and receive files from the JD Edwards OneWorld system.</span></span>  
  
 <span data-ttu-id="cb5da-241">**JDE_File_In**と**JDE_File_Out**必要性を作成したポートには、メッセージの種類が関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="cb5da-241">The **JDE_File_In** and **JDE_File_Out** ports you just created need associated message types.</span></span>  
  
#### <a name="assign-message-types-to-the-ports"></a><span data-ttu-id="cb5da-242">ポートにメッセージの種類を割り当てる</span><span class="sxs-lookup"><span data-stu-id="cb5da-242">Assign message types to the ports</span></span>  
  
1.  <span data-ttu-id="cb5da-243">左のポート画面上で、 **JDE_File_In**ポートでは、をクリックして**要求**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-243">On the left port surface, on the **JDE_File_In** port, click **Request**.</span></span> <span data-ttu-id="cb5da-244">プロパティ ウィンドウで **メッセージの種類**、展開**マルチパート メッセージ**、順にクリック**jde_ow_testaddressbookmastermbf**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-244">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBF**.</span></span>  
  
2.  <span data-ttu-id="cb5da-245">左のポート画面上で、 **JDE_File_Out**ポートでは、をクリックして**要求**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-245">On the left port surface, on the **JDE_File_Out** port, click **Request**.</span></span> <span data-ttu-id="cb5da-246">プロパティ ウィンドウで **メッセージの種類**、展開**マルチパート メッセージ**、順にクリック**jde_ow_testaddressbookmastermbfresponse**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-246">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBFResponse**.</span></span>  
  
 <span data-ttu-id="cb5da-247">2 つの挿入**送信**図形と 2 つ**受信**図形をオーケストレーションにポートにリンクします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-247">Insert two **Send** shapes and two **Receive** shapes into the orchestration to link to the ports.</span></span>  
  
#### <a name="add-send-and-receive-shapes"></a><span data-ttu-id="cb5da-248">追加の送信と受信図形</span><span class="sxs-lookup"><span data-stu-id="cb5da-248">Add Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="cb5da-249">ツールボックスから **受信** コンポーネントをドラッグし、オーケストレーション (緑色の円) の先頭の真下にドロップします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-249">Drag a **Receive** component from the Toolbox and drop it immediately below the start of the orchestration (the green circle).</span></span> <span data-ttu-id="cb5da-250">をクリックして、**受信**図形、および [プロパティ] ウィンドウで次のように入力します。`Get_File`の、**名前**、設定と**Activate**に`true`です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-250">Click the **Receive** shape, and in the Properties window, enter `Get_File` for the **Name**, and set **Activate** to `true`.</span></span> <span data-ttu-id="cb5da-251">このように設定すると、この受信ポートでドキュメントを受信したときにオーケストレーションがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="cb5da-251">Doing so will activate the orchestration when an incoming document is received on this receive port.</span></span>  
  
2.  <span data-ttu-id="cb5da-252">ドラッグ、**送信**コンポーネントをツールボックスからすぐ下にドロップし、 **GetFileReceive**図形です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-252">Drag a **Send** component from the Toolbox and drop it immediately below the **GetFileReceive** shape.</span></span> <span data-ttu-id="cb5da-253">クリックして、新しい**送信**図形、および [プロパティ] ウィンドウで次のように入力します。`SendToJDEOW`の、**名**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-253">Click the new **Send** shape, and in the Properties window, enter `SendToJDEOW` for the **Name**.</span></span>  
  
3.  <span data-ttu-id="cb5da-254">ドラッグ、**受信**コンポーネントをツールボックスからすぐ下にドロップし、 **SendToJDEOWSend**図形です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-254">Drag a **Receive** component from the Toolbox and drop it immediately below the **SendToJDEOWSend** shape.</span></span> <span data-ttu-id="cb5da-255">クリックして、**受信**図形、および [プロパティ] ウィンドウで次のように入力します。`JDEOW_Resp`の、**名前**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-255">Click the **Receive** shape, and in the Properties window, enter `JDEOW_Resp` for the **Name**.</span></span>  
  
4.  <span data-ttu-id="cb5da-256">ドラッグ、**送信**コンポーネントをツールボックスからすぐ下にドロップし、 **JDEOW_RespReceive**図形です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-256">Drag a **Send** component from the Toolbox and drop it immediately below the **JDEOW_RespReceive** shape.</span></span> <span data-ttu-id="cb5da-257">クリックして、新しい**送信**図形、および [プロパティ] ウィンドウで次のように入力します。`FileToDisk`の、**名**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-257">Click the new **Send** shape, and in the Properties window, enter `FileToDisk` for the **Name**.</span></span>  
  
     <span data-ttu-id="cb5da-258">![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")</span><span class="sxs-lookup"><span data-stu-id="cb5da-258">![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")</span></span>  
  
5.  <span data-ttu-id="cb5da-259">接続、 **JDE_FileIn**ポートを**GetFileReceive**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-259">Connect the **JDE_FileIn** port to the **GetFileReceive** component.</span></span>  
  
6.  <span data-ttu-id="cb5da-260">接続、 **JDE_FileOut**ポートを**FileToDiskReceive**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-260">Connect the **JDE_FileOut** port to the **FileToDiskReceive** component.</span></span>  
  
7.  <span data-ttu-id="cb5da-261">移動して**オーケストレーション ビュー**展開**メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-261">Go to **Orchestration View** and expand **Messages**.</span></span> <span data-ttu-id="cb5da-262">識別子を変更**Message_1**に`MsgToJDEOW`、および**Message_2**に`JDEOW_Resp.`</span><span class="sxs-lookup"><span data-stu-id="cb5da-262">Change the identifier for **Message_1** to `MsgToJDEOW`, and for **Message_2** to `JDEOW_Resp.`</span></span>  
  
8.  <span data-ttu-id="cb5da-263">強調表示、 **SendToJDEOWSend**コンポーネントで、設定、**メッセージ**プロパティを**MsgToJDEOW**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-263">Highlight the **SendToJDEOWSend** component and set its **Message** property to **MsgToJDEOW**.</span></span>  
  
9. <span data-ttu-id="cb5da-264">強調表示、 **JDEOW_RespReceive**コンポーネントで、設定、**メッセージ**プロパティを**JDEOW_Resp**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-264">Highlight the **JDEOW_RespReceive** component and set its **Message** property to **JDEOW_Resp**.</span></span>  
  
10. <span data-ttu-id="cb5da-265">接続**SendToJDEOW**を**要求**の部分、 **JDE_OW_Port**ポートです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-265">Connect **SendToJDEOW** to the **Request** portion of the **JDE_OW_Port** port.</span></span>  
  
11. <span data-ttu-id="cb5da-266">接続**JDEOW_Resp**を**応答**の部分、 **JDE_OW_Port**ポートです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-266">Connect **JDEOW_Resp** to the **Response** portion of the **JDE_OW_Port** port.</span></span>  
  
     <span data-ttu-id="cb5da-267">![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")</span><span class="sxs-lookup"><span data-stu-id="cb5da-267">![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")</span></span>  
  
## <a name="step-4-build-and-deploy-the-project"></a><span data-ttu-id="cb5da-268">手順 4: ビルドし、プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="cb5da-268">Step 4: Build and deploy the project</span></span>  
 <span data-ttu-id="cb5da-269">BizTalk プロジェクトが完成したので、ビルドし、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に展開できます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-269">Now the BizTalk project is complete and you can build and deploy it in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="cb5da-270">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-270">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="cb5da-271">プロジェクトをビルドするには、厳密な名前のキー ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-271">To build the project, you need a strong name key file.</span></span> <span data-ttu-id="cb5da-272">コマンド プロンプトで、次のとおりに入力して厳密な名前のキー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-272">At the command prompt, enter the following to create a strong name key file:</span></span>  
  
     <span data-ttu-id="cb5da-273">**sn-k labs.snk**</span><span class="sxs-lookup"><span data-stu-id="cb5da-273">**sn -k labs.snk**</span></span>  
  
3.  <span data-ttu-id="cb5da-274">ソリューション エクスプ ローラーで右クリックし、 **[jd_ow_test]**プロジェクトをクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-274">In Solution Explorer, right-click the **JD_OW_Test** project, and then click **Properties** to launch the Project Designer for the project.</span></span>  
  
4.  <span data-ttu-id="cb5da-275">**[署名]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-275">Click the **Signing** tab.</span></span>  
  
5.  <span data-ttu-id="cb5da-276">**[アセンブリの署名]** オプションを選択し、 **[厳密な名前のキー ファイルを選択してください]** オプションのドロップダウン リストをクリックして、 **[参照]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-276">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
6.  <span data-ttu-id="cb5da-277">キー ファイル **labs.snk**を一覧から選択して **[開く]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-277">Browse to select the key file: **labs.snk**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="cb5da-278">プロジェクト デザイナーの **[展開]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-278">Click **Deployment** tab in the Project Designer.</span></span>  
  
8.  <span data-ttu-id="cb5da-279">設定、**アプリケーション名**に`JDE_OW_Test`です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-279">Set the **Application Name** to `JDE_OW_Test`.</span></span>  
  
9. <span data-ttu-id="cb5da-280">ソリューション エクスプ ローラーで右クリックし、 **JDE_OW_Test**プロジェクトをクリックして**を構築します。**</span><span class="sxs-lookup"><span data-stu-id="cb5da-280">In Solution Explorer, right-click the **JDE_OW_Test** project, and then click **Build.**</span></span>  
  
     <span data-ttu-id="cb5da-281">![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")</span><span class="sxs-lookup"><span data-stu-id="cb5da-281">![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")</span></span>  
  
10. <span data-ttu-id="cb5da-282">ビルドが完了したらを右クリックし、 **[XX_JD Edwards oneworldquery]**プロジェクトをクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-282">After the build completes successfully, right-click the **XX_JD Edwards OneWorldQuery** project, and then click **Deploy**.</span></span> <span data-ttu-id="cb5da-283">出力ウィンドウに、次のように出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-283">In the output window the following output will be displayed:</span></span>  
  
     <span data-ttu-id="cb5da-284">![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")</span><span class="sxs-lookup"><span data-stu-id="cb5da-284">![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")</span></span>  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a><span data-ttu-id="cb5da-285">手順 5: テスト アプリケーションと XML 出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-285">Step 5: Test the Application and Viewing the XML Output</span></span>  
 <span data-ttu-id="cb5da-286">次に、作成して展開したアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-286">Now you will test the application that you have created and deployed.</span></span> <span data-ttu-id="cb5da-287">初めに、オーケストレーション プロセスを開始する XML ファイルを作成します。次に、アプリケーション内で XML ファイルを送受信するためのフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-287">You will create the XML file that starts the orchestration process, and then you will configure folders to receive and send XML files within the application.</span></span> <span data-ttu-id="cb5da-288">アプリケーションの構成後は、アプリケーションを実行し、オーケストレーションが返す XML ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-288">After you have configured the application, you will run it and view the XML files that the orchestration returns.</span></span>  
  
#### <a name="generate-the-xml-file-for-the-query"></a><span data-ttu-id="cb5da-289">クエリの XML ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-289">Generate the XML file for the query</span></span>  
  
1.  <span data-ttu-id="cb5da-290">ソリューション エクスプ ローラーで、 **N0100041Service_N0100041.xsd**ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-290">In Solution Explorer, double-click **N0100041Service_N0100041.xsd** to open the file.</span></span>  
  
2.  <span data-ttu-id="cb5da-291">右クリック**N0100041Service_N0100041.xsd**  をクリックし、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-291">Right-click **N0100041Service_N0100041.xsd** and then click **Properties**.</span></span> <span data-ttu-id="cb5da-292">**[出力インスタンス ファイル名]** に、サンプル XML のパスとファイル名を次のとおりに入力します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-292">For the **Output Instance Filename** enter the following path and file name for the sample XML:</span></span>  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  <span data-ttu-id="cb5da-293">クリックして **OK.**</span><span class="sxs-lookup"><span data-stu-id="cb5da-293">Click **OK.**</span></span> <span data-ttu-id="cb5da-294">[プロパティ] ウィンドウで選択**\<スキーマ\>**設定と**ルート参照:**に`AddressBookMasterMBF`です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-294">In the Properties window, select **\<Schema\>** and set **Root Reference:** to `AddressBookMasterMBF`.</span></span> <span data-ttu-id="cb5da-295">これにより、生成された XML のみを含む、**クエリ**xml です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-295">This will cause the generated XML to include only the **Query** xml.</span></span>  
  
     <span data-ttu-id="cb5da-296">![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")</span><span class="sxs-lookup"><span data-stu-id="cb5da-296">![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")</span></span>  
  
4.  <span data-ttu-id="cb5da-297">右クリック**N0100041Service_N0100041.xsd**  をクリックし、**インスタンスの生成**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-297">Right-click **N0100041Service_N0100041.xsd** and then click **Generate Instance**.</span></span> <span data-ttu-id="cb5da-298">これにより生成、 **Sample.xml**ファイル。</span><span class="sxs-lookup"><span data-stu-id="cb5da-298">This generates the **Sample.xml** file.</span></span> <span data-ttu-id="cb5da-299">このファイルは、オーケストレーション プロセスを開始するアダプターに対する入力として、受信場所にドロップされます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-299">This file will be dropped in the receive location as input to the adapter to start the orchestration process.</span></span>  
  
#### <a name="configure-and-start-the-biztalk-application"></a><span data-ttu-id="cb5da-300">構成および BizTalk アプリケーションの開始</span><span class="sxs-lookup"><span data-stu-id="cb5da-300">Configure and start the BizTalk application</span></span>  
  
1.  <span data-ttu-id="cb5da-301">入力ファイルの受信と送出ファイルの送信のフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-301">Configure folders for receiving the incoming files and sending the outgoing files.</span></span> <span data-ttu-id="cb5da-302">移動して**C:\LABS\JDE_OW_Test**という 2 つの新しいサブフォルダーを作成および`FileIn`と`FileOut`です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-302">Go to **C:\LABS\JDE_OW_Test** and create two new subfolders named `FileIn` and `FileOut`.</span></span>  
  
2.  <span data-ttu-id="cb5da-303">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**コンソール ルート**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**を展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-303">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,expand **Console Root**, expand**BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="cb5da-304">右クリック**JDE_OW_Test**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-304">Right-click **JDE_OW_Test**, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="cb5da-305">![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")</span><span class="sxs-lookup"><span data-stu-id="cb5da-305">![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")</span></span>  
  
4.  <span data-ttu-id="cb5da-306">**[Orchestration_1]** を選択し、 **[ホスト]** ドロップダウン ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-306">Select **Orchestration_1** and click the **Host** drop-down box.</span></span> <span data-ttu-id="cb5da-307">**[BizTalkServerApplication]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-307">Select **BizTalkServerApplication**.</span></span>  
  
5.  <span data-ttu-id="cb5da-308">**受信ポート**をクリックして **\<None\>**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-308">Under **Receive Ports**, click **\<None\>**.</span></span> <span data-ttu-id="cb5da-309">ドロップダウン リストの **[新しい受信ポート]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-309">In the drop-down list, select **New Receive Port**.</span></span>  
  
6.  <span data-ttu-id="cb5da-310">**名前**、型`JDE_FileIn_Port`、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-310">For **Name**, type `JDE_FileIn_Port`, and then click **OK**.</span></span> <span data-ttu-id="cb5da-311">受信場所を指定する必要があるというメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-311">A message box appears stating that you need to designate a receive location.</span></span> <span data-ttu-id="cb5da-312">**[OK]**をクリックし、 **[新規作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-312">Click **OK**, and then click **New**.</span></span>  
  
     <span data-ttu-id="cb5da-313">![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")</span><span class="sxs-lookup"><span data-stu-id="cb5da-313">![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")</span></span>  
  
7.  <span data-ttu-id="cb5da-314">プロパティに次の値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-314">Type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="cb5da-315">**名前**: JDE_`FileInLoc`</span><span class="sxs-lookup"><span data-stu-id="cb5da-315">**Name**: JDE_`FileInLoc`</span></span>  
  
     <span data-ttu-id="cb5da-316">**種類**: **ファイル**</span><span class="sxs-lookup"><span data-stu-id="cb5da-316">**Type**: **File**</span></span>  
  
     <span data-ttu-id="cb5da-317">**受信ハンドラー**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="cb5da-317">**Receive Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="cb5da-318">**受信パイプライン**: **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="cb5da-318">**Receive Pipeline**: **XMLReceive**</span></span>  
  
     <span data-ttu-id="cb5da-319">![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")</span><span class="sxs-lookup"><span data-stu-id="cb5da-319">![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")</span></span>  
  
8.  <span data-ttu-id="cb5da-320">をクリックして**構成**、型`C:\LABS\JDE_OW_Test\FileIn`の**受信フォルダー**、クリックして**[ok]** 3 回です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-320">Click **Configure**, type `C:\LABS\JDE_OW_Test\FileIn` for **Receive Folder**, and then click **OK** three times.</span></span>  
  
     <span data-ttu-id="cb5da-321">![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")</span><span class="sxs-lookup"><span data-stu-id="cb5da-321">![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")</span></span>  
  
9. <span data-ttu-id="cb5da-322">をクリックして **\<None\>** の**JDE_OW_Port**ドロップダウン リストでします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-322">Click **\<None\>** for **JDE_OW_Port** in the drop-down list.</span></span>  
  
10. <span data-ttu-id="cb5da-323">選択**新しい送信ポートを**を選択するか、プロパティに次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-323">Select **New Send Port** and then select or type the following values for the properties:</span></span>  
  
     <span data-ttu-id="cb5da-324">**名前**:`JDE_OW_Port`</span><span class="sxs-lookup"><span data-stu-id="cb5da-324">**Name**: `JDE_OW_Port`</span></span>  
  
     <span data-ttu-id="cb5da-325">**型**: **JDE_OneWorld**</span><span class="sxs-lookup"><span data-stu-id="cb5da-325">**Type**: **JDE_OneWorld**</span></span>  
  
     <span data-ttu-id="cb5da-326">**[送信ハンドラー]**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="cb5da-326">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="cb5da-327">**[パイプライン]**: **XMLTransmit** および **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="cb5da-327">**Pipelines**: **XMLTransmit** and **XMLReceive**</span></span>  
  
11. <span data-ttu-id="cb5da-328">**[構成]**をクリックし、次のプロパティ値を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-328">Click **Configure**, and then enter the following property values:</span></span>  
  
     <span data-ttu-id="cb5da-329">**ホスト:** \<JDEOW ホスト名を入力してください\></span><span class="sxs-lookup"><span data-stu-id="cb5da-329">**Host:** \<enter your JDEOW host name\></span></span>  
  
     <span data-ttu-id="cb5da-330">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="cb5da-330">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
     <span data-ttu-id="cb5da-331">**JDEdwards 環境:** \<JDEOW 環境を入力してください\></span><span class="sxs-lookup"><span data-stu-id="cb5da-331">**JDEdwards Environment:** \<enter your JDEOW environment\></span></span>  
  
     <span data-ttu-id="cb5da-332">**JDEdwards JAR ファイル:**<enter full path of JAR files></span><span class="sxs-lookup"><span data-stu-id="cb5da-332">**JDEdwards JAR files:** <enter full path of JAR files></span></span>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     <span data-ttu-id="cb5da-333">**パスワード:**ドロップダウン リストを使用して、JD Edwards OneWorld パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-333">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
     <span data-ttu-id="cb5da-334">**ポート:**  `6009`</span><span class="sxs-lookup"><span data-stu-id="cb5da-334">**Port:**  `6009`</span></span>  
  
     <span data-ttu-id="cb5da-335">**ユーザー名:**<enter your JD Edwards User Name></span><span class="sxs-lookup"><span data-stu-id="cb5da-335">**User Name:** <enter your JD Edwards User Name></span></span>  
  
     <span data-ttu-id="cb5da-336">![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")</span><span class="sxs-lookup"><span data-stu-id="cb5da-336">![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")</span></span>  
  
12. <span data-ttu-id="cb5da-337">**[OK]** を 2 回クリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-337">Click **OK** twice to close the dialog boxes.</span></span>  
  
13. <span data-ttu-id="cb5da-338">構成 Applicationwindow、クリックして **\<None\>** の**JDE_FileOut**ドロップダウン リストでします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-338">In the Configure Applicationwindow, click **\<None\>** for **JDE_FileOut** in the drop-down list.</span></span>  
  
14. <span data-ttu-id="cb5da-339">**[新しい送信ポート]** を選択し、プロパティの値を次のとおりに入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-339">Select **New Send Port** and type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="cb5da-340">**名前**:`FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="cb5da-340">**Name**: `FileOutPort`</span></span>  
  
     <span data-ttu-id="cb5da-341">**種類**: **ファイル**</span><span class="sxs-lookup"><span data-stu-id="cb5da-341">**Type**: **File**</span></span>  
  
     <span data-ttu-id="cb5da-342">**[送信ハンドラー]**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="cb5da-342">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="cb5da-343">**送信パイプライン**: **XMLTransmit**</span><span class="sxs-lookup"><span data-stu-id="cb5da-343">**Send Pipeline**: **XMLTransmit**</span></span>  
  
15. <span data-ttu-id="cb5da-344">をクリックして**構成**および種類`C:\Labs\JDE_OW_Test\FileOut`の**先のフォルダーです。**</span><span class="sxs-lookup"><span data-stu-id="cb5da-344">Click **Configure** and type`C:\Labs\JDE_OW_Test\FileOut` for **Destination Folder.**</span></span> <span data-ttu-id="cb5da-345">」と入力します。 **[ファイル名]** に「 **%MessageID%.xml** because this results in a unique file に「 each message.</span><span class="sxs-lookup"><span data-stu-id="cb5da-345">Keep **%MessageID%.xml** for **File Name** because this results in a unique file for each message.</span></span>  
  
     <span data-ttu-id="cb5da-346">![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")</span><span class="sxs-lookup"><span data-stu-id="cb5da-346">![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")</span></span>  
  
16. <span data-ttu-id="cb5da-347">**[OK]** を 3 回クリックして、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-347">Click **OK** three times to close the dialog boxes.</span></span>  
  
17. <span data-ttu-id="cb5da-348">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして、 **JDE_OW_Test**アプリケーション、およびクリック**開始**です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-348">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,right-click the **JDE_OW_Test** application, and then click **Start**.</span></span>  
  
#### <a name="test-the-orchestration"></a><span data-ttu-id="cb5da-349">オーケストレーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="cb5da-349">Test the orchestration</span></span>  
  
1.  <span data-ttu-id="cb5da-350">**C:\Labs\JDE_OW_Test**ディレクトリ、 **Sample.xml**ファイルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb5da-350">In the **C:\Labs\JDE_OW_Test** directory the **Sample.xml** file will appear as:</span></span>  
  
     <span data-ttu-id="cb5da-351">![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")</span><span class="sxs-lookup"><span data-stu-id="cb5da-351">![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")</span></span>  
  
2.  <span data-ttu-id="cb5da-352">編集、 **Sample.xml**を除くすべての項目を削除するファイル、 **cActionCode**と**mnAddressBookNumber**要素。</span><span class="sxs-lookup"><span data-stu-id="cb5da-352">Edit the **Sample.xml** file to remove everything except the **cActionCode** and **mnAddressBookNumber** elements.</span></span>  
  
     <span data-ttu-id="cb5da-353">![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")</span><span class="sxs-lookup"><span data-stu-id="cb5da-353">![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")</span></span>  
  
3.  <span data-ttu-id="cb5da-354">**CActionCode**要素は、文字を挿入`i`です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-354">For the **cActionCode** element insert the letter `i`.</span></span>  
  
4.  <span data-ttu-id="cb5da-355">**MnAddressBookNumber**数を挿入する`500`です。</span><span class="sxs-lookup"><span data-stu-id="cb5da-355">For **mnAddressBookNumber** insert the number `500`.</span></span>  
  
5.  <span data-ttu-id="cb5da-356">変更を保存し、ファイルのコピー、 **C:\Labs\JDE_OW_Test\FileIn**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-356">Save the changes and copy the file to the **C:\Labs\JDE_OW_Test\FileIn** folder.</span></span> <span data-ttu-id="cb5da-357">これが受信場所であり、ここからオーケストレーション プロセスが開始します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-357">This is the receive location that starts the orchestration process.</span></span>  
  
6.  <span data-ttu-id="cb5da-358">表示する必要があります XML ファイル、数秒で、 **C:\Labs\JDE_OW_Test\FileOut**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="cb5da-358">In a few seconds, an XML file should appear in the **C:\Labs\JDE_OW_Test\FileOut** folder.</span></span> <span data-ttu-id="cb5da-359">このファイルには、アドレスが 500 であるすべてのレコードが格納されています。</span><span class="sxs-lookup"><span data-stu-id="cb5da-359">This should contain the all the records where the address is 500.</span></span>  
  
     <span data-ttu-id="cb5da-360">![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")</span><span class="sxs-lookup"><span data-stu-id="cb5da-360">![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")</span></span>  
  
     <span data-ttu-id="cb5da-361">この返されたレコード データは、ラボ 1 で JD Edwards OneWorld システムに対してクエリによって返されるデータと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb5da-361">This returned record data should match the data returned by the query against the JD Edwards OneWorld system in Lab 1.</span></span> <span data-ttu-id="cb5da-362">ラボ 1 で取得したレコードを比較すると、できることを確認する、**取得**メソッドが正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="cb5da-362">By comparing the records you obtained in Lab 1, you can verify that the **Get** method worked properly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="cb5da-363">概要</span><span class="sxs-lookup"><span data-stu-id="cb5da-363">Summary</span></span>  
 <span data-ttu-id="cb5da-364">このラボでは、初めに、JD Edwards OneWorld システムにアクセスするための前提条件が適切にセットアップされていることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="cb5da-364">In this lab, you first verified that the prerequisites were set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="cb5da-365">次に、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、オーケストレーションが含まれる新しい BizTalk プロジェクトを作成しました。</span><span class="sxs-lookup"><span data-stu-id="cb5da-365">Then you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project containing an orchestration.</span></span> <span data-ttu-id="cb5da-366">JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムからデータを取得するように、この BizTalk オーケストレーションを構成しました。</span><span class="sxs-lookup"><span data-stu-id="cb5da-366">You configured the BizTalk orchestration to use the JD Edwards OneWorld adapter to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="cb5da-367">オーケストレーションを構成するために、送信ポート、受信ポート、および送信/受信ポートを作成しました。</span><span class="sxs-lookup"><span data-stu-id="cb5da-367">To configure the orchestration, you created send, receive, and send/receive ports.</span></span> <span data-ttu-id="cb5da-368">これらのポートを JD Edwards OneWorld アダプターにバインドし、メッセージを該当するポートに割り当てました。</span><span class="sxs-lookup"><span data-stu-id="cb5da-368">You bound these ports to the JD Edwards OneWorld adapter, and assigned messages to the appropriate ports.</span></span>  
  
 <span data-ttu-id="cb5da-369">BizTalk プロジェクトの作成後、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してプロジェクトをビルドして展開しました。</span><span class="sxs-lookup"><span data-stu-id="cb5da-369">After you completed the BizTalk project, you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build and deploy it.</span></span> <span data-ttu-id="cb5da-370">次に、新しいアプリケーションを構成して実行し、JD Edwards OneWorld システムからデータを取得しました。</span><span class="sxs-lookup"><span data-stu-id="cb5da-370">You then configured your new application and ran it to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="cb5da-371">アプリケーションが正しく動作したことを確認するために、出力 XML ファイルを、ラボ 1 で JD Edwards OneWorld システムから受信したファイルと比較しました。</span><span class="sxs-lookup"><span data-stu-id="cb5da-371">To verify that the application worked correctly, you compared its output XML file to the file that you received from the JD Edwards OneWorld system in Lab 1.</span></span>