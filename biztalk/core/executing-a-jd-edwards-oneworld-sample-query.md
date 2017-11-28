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
ms.openlocfilehash: 58e06eb1b606217aea6fe5e40ac645a2eaf623c2
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
---
# <a name="execute-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="51d9c-102">JD Edwards OneWorld サンプル クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-102">Execute a JD Edwards OneWorld Sample Query</span></span>
<span data-ttu-id="51d9c-103">JD Edwards OneWorld (JDEOW) システムに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムからアクセスするには、JD Edwards OneWorld アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-103">The JD Edwards OneWorld (JDEOW) system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="51d9c-104">このアダプターは、付属[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-104">This adapter is included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>
  
 <span data-ttu-id="51d9c-105">これは、JD Edwards OneWorld ラボ作業の 2 つめのパートです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-105">This is the second part of the JD Edwards OneWorld lab work.</span></span> <span data-ttu-id="51d9c-106">最初のパート (ラボ 1) では、JD Edwards OneWorld システムのデータに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] などの Microsoft テクノロジーを使用せずに手動でアクセスしました。</span><span class="sxs-lookup"><span data-stu-id="51d9c-106">In the first part (Lab 1), you manually accessed data on the JD Edwards OneWorld system without the assistance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or other Microsoft technologies.</span></span> <span data-ttu-id="51d9c-107">このパート (ラボ 2) では、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトの一部として、BizTalk オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-107">In this part (Lab 2), you will create a BizTalk orchestration as part of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project.</span></span> <span data-ttu-id="51d9c-108">JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムからデータを取得するように、このオーケストレーションのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-108">You will configure ports on this orchestration to use the JD Edwards OneWorld adapter to get data from a JD Edwards OneWorld system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51d9c-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="51d9c-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="51d9c-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51d9c-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>
  
-   <span data-ttu-id="51d9c-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51d9c-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="51d9c-112">JD Edwards OneWorld クライアント ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="51d9c-112">JD Edwards OneWorld Client software</span></span>  
  
-   <span data-ttu-id="51d9c-113">別のサーバー上にある JD Edwards OneWorld システムへのネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="51d9c-113">Network connectivity to a JD Edwards OneWorld system on another server</span></span>  
  
-   <span data-ttu-id="51d9c-114">Microsoft BizTalk Adapters for Enterprise Applications</span><span class="sxs-lookup"><span data-stu-id="51d9c-114">Microsoft BizTalk Adapters for Enterprise Applications</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51d9c-115">参照してください[をインストールし、エンタープライズ アプリケーション用のアダプターを構成](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)JD Edwards、PeopleSoft、および TIBCO アダプターのキーの構成についてはします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-115">See [Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) for key configuration information for the JD Edwards, PeopleSoft, and TIBCO adapters.</span></span>  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="51d9c-116">ラボ 2 - JD Edwards OneWorld サンプル クエリの実行</span><span class="sxs-lookup"><span data-stu-id="51d9c-116">Lab 2 - Executing a JD Edwards OneWorld Sample Query</span></span>  
 <span data-ttu-id="51d9c-117">このラボでは、実行、**取得**JD Edwards OneWorld システムに対して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-117">In this lab, you will execute a **Get** operation against the JD Edwards OneWorld system.</span></span> <span data-ttu-id="51d9c-118">具体的には、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-118">Specifically you will perform the following tasks:</span></span>  
  
-   <span data-ttu-id="51d9c-119">JD Edwards OneWorld の前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-119">Verify the JD Edwards OneWorld prerequisites</span></span>  
  
-   <span data-ttu-id="51d9c-120">JD Edwards OneWorld 送信ポートを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でセットアップ</span><span class="sxs-lookup"><span data-stu-id="51d9c-120">Set up a JD Edwards OneWorld send port in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="51d9c-121">BizTalk オーケストレーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="51d9c-121">Create a BizTalk orchestration project</span></span>  
  
-   <span data-ttu-id="51d9c-122">プロジェクトのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="51d9c-122">Build and deploy the project</span></span>  
  
-   <span data-ttu-id="51d9c-123">アプリケーションのテストと XML 出力の表示</span><span class="sxs-lookup"><span data-stu-id="51d9c-123">Test the application and view the XML output</span></span>  
  
 <span data-ttu-id="51d9c-124">JD Edwards OneWorld アダプターを使用して、JD Edwards OneWorld システム上のデータに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からアクセスします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-124">You will use the JD Edwards OneWorld adapter to access data on the JD Edwards OneWorld system from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="51d9c-125">このアダプターを使用すると、オーケストレーションによって実行される要求と応答を使用して JD Edwards OneWorld のオブジェクトの処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-125">This adapter enables the processing of JD Edwards OneWorld objects by using requests and responses executed by an orchestration.</span></span> <span data-ttu-id="51d9c-126">1 つのスキーマ オブジェクトに対して使用可能なメソッドは多数あります。</span><span class="sxs-lookup"><span data-stu-id="51d9c-126">Many methods are available for a schema object.</span></span> <span data-ttu-id="51d9c-127">このラボを使用する方法を示しています、 **Address Book MBF**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-127">This lab demonstrates how to use the **Address Book MBF** method.</span></span>  
  
 <span data-ttu-id="51d9c-128">サービス要求を実行する前に、対象の JD Edwards OneWorld オブジェクトに対するサービス要求と応答のスキーマを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51d9c-128">Before running a service request, you must create service request and response schemas for the specific JD Edwards OneWorld object.</span></span> <span data-ttu-id="51d9c-129">これらのスキーマは、生成した項目の追加/アダプターの追加ウィザードによって、JD Edwards OneWorld 内のサポート メタデータ オブジェクトに直接問い合わせることによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-129">The Add Generated Items/Add Adapter Wizard creates these schemas by directly interrogating the supporting metadata object in JD Edwards OneWorld.</span></span> <span data-ttu-id="51d9c-130">このラボ用スキーマの作成に必要な手順を示しています、 **Address Book MBF**メソッドとクエリを処理します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-130">This lab illustrates the steps required to create schemas for the **Address Book MBF** method and to process a query.</span></span>  
  
## <a name="step-1-verify-the-jd-edwards-oneworld-prerequisites"></a><span data-ttu-id="51d9c-131">手順 1: JD Edwards OneWorld の前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-131">Step 1: Verify the JD Edwards OneWorld prerequisites</span></span>  
 <span data-ttu-id="51d9c-132">JD Edwards OneWorld アダプターと共に使用する BizTalk プロジェクトの作成を開始する前に、JD Edwards OneWorld システムにアクセスできるように適切にファイルとアダプターがセットアップされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51d9c-132">Before you start creating a BizTalk project for use with the JD Edwards OneWorld adapter, you need to be sure the files and the adapter are set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="51d9c-133">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上の JD Edwards OneWorld アダプターと JD Edwards OneWorld システムとの通信には、Java インターフェイスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-133">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, the JD Edwards OneWorld adapter communicates with the JD Edwards OneWorld system by using the Java interface.</span></span>    

1. <span data-ttu-id="51d9c-134">JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムに適切にアクセスするには、Connector.jar、Kernel.jar、BTSLIBinterop.jar、JDEJAccess.jar の 4 つのファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-134">Four files are necessary for proper interface access to a JD Edwards OneWorld system using the JD Edwards OneWorld adapter: Connector.jar, Kernel.jar, BTSLIBinterop.jar, and JDEJAccess.jar.</span></span>  
  
    -   <span data-ttu-id="51d9c-135">Connector.jar と Kernel.jar は、JD Edwards OneWorld システムに付属しています。JD Edwards OneWorld 管理者から入手してください。</span><span class="sxs-lookup"><span data-stu-id="51d9c-135">The Connector.jar and Kernel.jar files come with the JD Edwards OneWorld system and are obtained from a JD Edwards OneWorld administrator.</span></span> <span data-ttu-id="51d9c-136">これらのファイルの場所は、C:\JDEOWJars フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-136">These files are located in the C:\JDEOWJars folder.</span></span>  
  
    -   <span data-ttu-id="51d9c-137">BTSLIBinterop.jar ファイルは、アダプターのインストール ガイドに記載されている手順に従って JD Edwards OneWorld システムによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-137">The BTSLIBinterop.jar file is generated by the JD Edwards OneWorld system by following the instructions included in the Installation Guide for the adapters.</span></span> <span data-ttu-id="51d9c-138">このファイルの場所は、C:\JDEOWJars フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-138">This file is located in the C:\JDEOWJars folder.</span></span>  
  
    -   <span data-ttu-id="51d9c-139">JDEJAccess.jar ファイルは JDEOW アダプターの一部であり、アダプターのインストール時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-139">The JDEJAccess.jar file is a part of the JDEOW adapter and is included with the installation of the adapter.</span></span> <span data-ttu-id="51d9c-140">既定にある、C:\Program files \microsoft BizTalk Adapters Enterprise applications \j.d. 用です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-140">By default, it is located in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="51d9c-141">Edwards OneWorld® \Classes フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-141">Edwards OneWorld®\Classes folder.</span></span>  
  
2. <span data-ttu-id="51d9c-142">Connector.jar、Kernel.jar、ことを確認し、BTSLIBinterop.jar ファイル上に存在、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] C:\JDEOWJars フォルダー内のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="51d9c-142">Confirm the Connector.jar, Kernel.jar, and BTSLIBinterop.jar files exist on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\JDEOWJars folder.</span></span>  
  
3. <span data-ttu-id="51d9c-143">JDEJAccess.jar ファイル上に存在することを確認、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] C:\Program files \microsoft BizTalk Adapters for Enterprise applications \j.d. 内のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="51d9c-143">Confirm the JDEJAccess.jar file exists on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="51d9c-144">Edwards OneWorld\Classes フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-144">Edwards OneWorld\Classes folder.</span></span>  
  
## <a name="step-2-configure-biztalk-send-ports"></a><span data-ttu-id="51d9c-145">手順 2: BizTalk 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-145">Step 2: Configure BizTalk send ports</span></span>  
<span data-ttu-id="51d9c-146">次に、いることを確認、JD Edwards OneWorld アダプターがインストールされている送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-146">Next, verify that the JD Edwards OneWorld adapter is installed, and create the send port.</span></span>  

1.  <span data-ttu-id="51d9c-147">開いている**BizTalk Server 管理コンソール**、展開**コンソール ルート**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**の順に展開および**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-147">Open **BizTalk Server Administration**, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
    <span data-ttu-id="51d9c-148">確認、 **JDE_OneWorld**アダプターが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-148">Confirm the **JDE_OneWorld** adapter is listed.</span></span> <span data-ttu-id="51d9c-149">JD Edwards OneWorld アダプターがインストールされていない場合は、BizTalk Adapters for Enterprise Applications をインストールしてください (前の「前提条件」の項を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="51d9c-149">If the JD Edwards OneWorld adapter is not installed, install the BizTalk Adapters for Enterprise Applications (see the earlier "Prerequisites" section).</span></span> <span data-ttu-id="51d9c-150">アダプターをインストールしたらを右クリックし**アダプター** をクリックし、 **New - Adapter** JD Edwards OneWorld アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-150">After the adapters are installed, right-click **Adapters** and then click **New - Adapter** to install the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="51d9c-151">これを有効にするホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-151">Restart the host instance for this to take effect.</span></span>  
  
2. <span data-ttu-id="51d9c-152">展開**アプリケーション**の順に展開および**BizTalk アプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-152">Expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="51d9c-153">右クリック**送信ポート**をクリックして**新規**、順にクリック**静的な送信請求-応答送信ポート**です。これらのフィールドに、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-153">Right-click **Send Ports**, click **New**, and then click **Static Solicit-Response Send Port**.Enter the following values for these fields:</span></span>  
  
    1.  <span data-ttu-id="51d9c-154">**[名前]:**  `JDE_OneWorldPort`</span><span class="sxs-lookup"><span data-stu-id="51d9c-154">**Name:**  `JDE_OneWorldPort`</span></span>  
  
    2.  <span data-ttu-id="51d9c-155">**型:**  `JDE_OneWorld`</span><span class="sxs-lookup"><span data-stu-id="51d9c-155">**Type:**  `JDE_OneWorld`</span></span>  
  
    3.  <span data-ttu-id="51d9c-156">**送信ハンドラー。**  `BizTalkServerApplication`</span><span class="sxs-lookup"><span data-stu-id="51d9c-156">**Send handler:**  `BizTalkServerApplication`</span></span>  
  
    4.  <span data-ttu-id="51d9c-157">**送信パイプライン。**  `XMLTransmit`</span><span class="sxs-lookup"><span data-stu-id="51d9c-157">**Send pipeline:**  `XMLTransmit`</span></span>  
  
    5.  <span data-ttu-id="51d9c-158">**受信パイプライン。**  `XMLReceive`</span><span class="sxs-lookup"><span data-stu-id="51d9c-158">**Receive pipeline:**  `XMLReceive`</span></span>  
  
4.  <span data-ttu-id="51d9c-159">**[構成]**をクリックし、次のプロパティ値を入力します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-159">Click **Configure**, and then enter the following property values:</span></span>  
  
    1.  <span data-ttu-id="51d9c-160">**ホスト:** \<JDEOW ホスト名を入力 ></span><span class="sxs-lookup"><span data-stu-id="51d9c-160">**Host:** \<enter your JDEOW host name></span></span>  
  
    2.  <span data-ttu-id="51d9c-161">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="51d9c-161">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
    3.  <span data-ttu-id="51d9c-162">**JDEdwards 環境:** \<JDEOW 環境を入力 ></span><span class="sxs-lookup"><span data-stu-id="51d9c-162">**JDEdwards Environment:** \<enter your JDEOW environment></span></span>  
  
    4.  <span data-ttu-id="51d9c-163">**JDEdwards JAR ファイル:** \<JAR ファイルの完全なパスを入力 ></span><span class="sxs-lookup"><span data-stu-id="51d9c-163">**JDEdwards JAR files:** \<enter full path of JAR files></span></span>  
  
         `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
    5.  <span data-ttu-id="51d9c-164">**パスワード:**ドロップダウン リストを使用して、JD Edwards OneWorld パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-164">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
    6.  <span data-ttu-id="51d9c-165">**ポート:**  `6009`</span><span class="sxs-lookup"><span data-stu-id="51d9c-165">**Port:**  `6009`</span></span>  
  
    7.  <span data-ttu-id="51d9c-166">**ユーザー名:** \<JD Edwards のユーザー名を入力 ></span><span class="sxs-lookup"><span data-stu-id="51d9c-166">**User Name:** \<enter your JD Edwards User Name></span></span>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")  
  
5.  <span data-ttu-id="51d9c-167">選択**OK**を閉じる、**送信ポートのプロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-167">Select **OK** to close the **Send Port Properties**.</span></span>  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a><span data-ttu-id="51d9c-168">手順 3: BizTalk オーケストレーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-168">Step 3: Create a BizTalk Orchestration Project</span></span>  
<span data-ttu-id="51d9c-169">次に、BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、間の通信を処理するプロジェクトで、オーケストレーションを構成して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と JD Edwards OneWorld システムです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-169">Next, create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and configure an orchestration in the project to handle communication between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the JD Edwards OneWorld system.</span></span> <span data-ttu-id="51d9c-170">送信と受信のポートを追加し、プロジェクトをビルドしてから、プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-170">You will add send and receive ports, build the project, and then deploy the project.</span></span>  

  
1.  <span data-ttu-id="51d9c-171">開いている[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、C:\LABS フォルダーに新しい BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-171">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and create a new BizTalk project in the C:\LABS folder.</span></span> <span data-ttu-id="51d9c-172">**[ファイル]** メニューの **[新規作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-172">On the **File** menu, click **New**.</span></span> <span data-ttu-id="51d9c-173">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-173">The **New Project** dialog box appears.</span></span> <span data-ttu-id="51d9c-174">**[テンプレート]** セクションで **[空の BizTalk Server プロジェクト]**</span><span class="sxs-lookup"><span data-stu-id="51d9c-174">In the **Templates** section, select **Empty BizTalk Server project.**</span></span> <span data-ttu-id="51d9c-175">入力`JDE_OW_Test`クリックして一意のプロジェクト名として**OK**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-175">Enter `JDE_OW_Test` as the unique project name, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="51d9c-176">ソリューション エクスプローラーでプロジェクト名を右クリックし、 **[追加]**をクリックし、 **[生成した項目の追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-176">In Solution Explorer, right-click the project, click **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="51d9c-177">[カテゴリ] ウィンドウで、次のように選択します。**アダプター メタデータの追加**、[テンプレート] ペインで選択**アダプター メタデータの追加**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-177">In the Categories pane, select **Add Adapter Metadata**, in the Templates pane, select **Add Adapter Metadata**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="51d9c-178">アダプターの追加ウィザードで選択、 **JD Edwards OneWorld**アダプター、select、 **[jde_oneworldport]** 、前の手順で作成したポートを送信し、をクリックして**次**.</span><span class="sxs-lookup"><span data-stu-id="51d9c-178">In the Add Adapter Wizard, select the **JD Edwards OneWorld** adapter, select the **JDE_OneWorldPort** send port that you created in the preceding procedure, and then click **Next**.</span></span>  
  
     ![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")  
  
4.  <span data-ttu-id="51d9c-179">**[インポートするサービス**] ページで、開いている**JD Edwards OneWorld**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-179">On the **Select Services to Import** page, open **JD Edwards OneWorld**.</span></span> <span data-ttu-id="51d9c-180">JDEOW システムへのアダプター経由でのアクセスには、BrowsingAgent プログラムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-180">The JDEOW system is contacted through the adapter by using the BrowsingAgent program.</span></span> <span data-ttu-id="51d9c-181">この BrowsingAgent からは、次に示すサービスが返されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-181">The BrowsingAgent returns the following services.</span></span>  
  
     ![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")  
  
5.  <span data-ttu-id="51d9c-182">展開**CALLBSFN**まで下にスクロール**N0100041 - Address Book MBF**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-182">Expand **CALLBSFN** and scroll down to **N0100041 - Address Book MBF**.</span></span> <span data-ttu-id="51d9c-183">N0100041 を選択し、クリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-183">Select N0100041 and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="51d9c-184">ソリューション エクスプローラーに、新しい BizTalk オーケストレーションと、2 つの新しい関連スキーマ ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-184">In Solution Explorer, there is a new BizTalk orchestration with two new associated schema files.</span></span> <span data-ttu-id="51d9c-185">これらのファイルはアダプターの追加ウィザードによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-185">These files are created by the Add Adapter Wizard.</span></span> <span data-ttu-id="51d9c-186">**BizTalk Orchestration.odx** ファイルをダブルクリックし、オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-186">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
     ![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")  
  
 <span data-ttu-id="51d9c-187">このオーケストレーションは、JD Edwards OneWorld システムに合わせてフォーマットされた XML ファイルをファイル アダプターから受け取ります。</span><span class="sxs-lookup"><span data-stu-id="51d9c-187">This orchestration accepts as input from the File adapter an XML file formatted for the JD Edwards OneWorld system.</span></span> <span data-ttu-id="51d9c-188">この XML ファイルは、JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムに送信されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-188">The orchestration uses the JD Edwards OneWorld adapter to send the XML file to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="51d9c-189">JD Edwards OneWorld は、クエリを処理して、結果が格納された出力 XML ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-189">JD Edwards OneWorld processes the query and generates an output XML file containing the results.</span></span> <span data-ttu-id="51d9c-190">この XML ファイルは、JD Edwards OneWorld アダプターを介してオーケストレーションに返され、ファイル アダプターによってディスク上の出力場所に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-190">This XML file returns to the orchestration through the JD Edwards OneWorld adapter, and the File adapter writes the XML file to the output location on disk.</span></span>  
  
 <span data-ttu-id="51d9c-191">オーケストレーションを完成させるには、XML の送信と受信のためのポートを作成および構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51d9c-191">To complete the orchestration, you need to create and configure ports to receive and send the XML files.</span></span> <span data-ttu-id="51d9c-192">初めに、受信ポートを構成します。これは、ファイル アダプターがディスクから読み取った XML ファイルをオーケストレーションに渡すのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-192">First, configure a receive port to be used by the File adapter to input the XML containing the query into the orchestration from disk.</span></span>  
  
#### <a name="configure-a-receive-port-to-accept-the-input-xml-file"></a><span data-ttu-id="51d9c-193">入力 XML ファイルをそのまま使用する受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-193">Configure a receive port to accept the input XML file</span></span>  
  
1.  <span data-ttu-id="51d9c-194">**BizTalk Orchestration.odx** ファイルをダブルクリックし、オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-194">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
2.  <span data-ttu-id="51d9c-195">BizTalk Orchestration.odx ファイルで、左ポート画面を右クリックし、をクリックして**新しい構成済みポート**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-195">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="51d9c-196">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-196">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="51d9c-197">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-197">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="51d9c-198">**ポートのプロパティ** ページで、入力`JDE_File_In`の**名前**、クリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-198">On the **Port Properties** page, enter `JDE_File_In` for **Name**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="51d9c-199">**[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]**を選択し、次のプロパティ値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-199">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="51d9c-200">**ポートの種類名**:`JDE_FileIn_Port`</span><span class="sxs-lookup"><span data-stu-id="51d9c-200">**Port Type Name**: `JDE_FileIn_Port`</span></span>  
  
     <span data-ttu-id="51d9c-201">**[通信方式]**: **一方向**</span><span class="sxs-lookup"><span data-stu-id="51d9c-201">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="51d9c-202">**[アクセスの制限]**: **[内部 - このプロジェクト限定]**</span><span class="sxs-lookup"><span data-stu-id="51d9c-202">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
5.  <span data-ttu-id="51d9c-203">**[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-203">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="51d9c-204">**[ポートの通信方向]**: **常にこのポートでメッセージを受信する**</span><span class="sxs-lookup"><span data-stu-id="51d9c-204">**Port direction of communication**: **I'll always be receiving messages on this port**</span></span>  
  
     <span data-ttu-id="51d9c-205">**[ポートのバインド]**: **[後で指定する]**</span><span class="sxs-lookup"><span data-stu-id="51d9c-205">**Port binding**: **Specify later**</span></span>  
  
6.  <span data-ttu-id="51d9c-206">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-206">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="51d9c-207">次に、送信/受信ポートを作成します。これは、クエリが格納された最初の XML 入力ファイルを JD Edwards OneWorld システムに送信するためのものです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-207">Next, create a send/receive port to send the initial XML input file containing the query to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="51d9c-208">このポートは、クエリの結果が格納された出力 XML ファイルを JD Edwards OneWorld システムから受信するのにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-208">This port will also receive an output XML file containing the query results from the call to the JD Edwards OneWorld system.</span></span>  
  
#### <a name="configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a><span data-ttu-id="51d9c-209">JD Edwards OneWorld とインターフェイスへの送信/受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-209">Configure a send/receive port to interface with JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="51d9c-210">BizTalk Orchestration.odx ファイルで右ポート画面を右クリックし、をクリックして**新しい構成済みポート**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-210">In the BizTalk Orchestration.odx file, right-click the right port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="51d9c-211">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-211">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="51d9c-212">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-212">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="51d9c-213">**[ポートの種類の選択]** ページで、 **[既存のポートの種類を使用する]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-213">On the **Select a Port Type** page, select **Use an existing Port Type**.</span></span> <span data-ttu-id="51d9c-214">**使用可能なポートの種類** **JD_OW_Test.N0100041**、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-214">Under **Available Port Types**, select **JD_OW_Test.N0100041**,and then click **Next**.</span></span>  
  
     ![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")  
  
3.  <span data-ttu-id="51d9c-215">プロパティ値を次のとおりに選択します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-215">Select the following property values:</span></span>  
  
     <span data-ttu-id="51d9c-216">**ポートの通信方向**:**要求の送信と応答の受信を行います**</span><span class="sxs-lookup"><span data-stu-id="51d9c-216">**Port direction of communication**: **I'll be sending a request and receiving a response**</span></span>  
  
     <span data-ttu-id="51d9c-217">**[ポートのバインド]**: **[後で指定する]**</span><span class="sxs-lookup"><span data-stu-id="51d9c-217">**Port binding**: **Specify later**</span></span>  
  
4.  <span data-ttu-id="51d9c-218">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-218">Click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="51d9c-219">ポート画面に、ポートと使用可能なメソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-219">On the port surface you will see the port and the available methods.</span></span>  
  
 <span data-ttu-id="51d9c-220">最後に、送信ポートを構成します。これは、クエリの結果を格納した XML ファイルをファイル アダプターがディスクに出力するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-220">Finally, configure a send port to be used by the File adapter to output the XML containing the query results to disk.</span></span>  
  
#### <a name="configure-a-send-port-to-output-the-xml-file-to-disk"></a><span data-ttu-id="51d9c-221">XML ファイルをディスクに出力する送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-221">Configure a send port to output the XML file to disk</span></span>  
  
1.  <span data-ttu-id="51d9c-222">BizTalk Orchestration.odx ファイルで、左ポート画面を右クリックし、をクリックして**新しい構成済みポート**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-222">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="51d9c-223">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-223">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="51d9c-224">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-224">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="51d9c-225">**ポートのプロパティ** ページで、入力`JDE_FileOut`の**名前**、クリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-225">On the **Port Properties** page, enter `JDE_FileOut` for **Name**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="51d9c-226">**[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]**を選択し、次のプロパティ値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-226">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="51d9c-227">**ポートの種類名**:`JDE_FileOut_Port`</span><span class="sxs-lookup"><span data-stu-id="51d9c-227">**Port Type Name**: `JDE_FileOut_Port`</span></span>  
  
     <span data-ttu-id="51d9c-228">**[通信方式]**: **一方向**</span><span class="sxs-lookup"><span data-stu-id="51d9c-228">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="51d9c-229">**[アクセスの制限]**: **[内部 - このプロジェクト限定]**</span><span class="sxs-lookup"><span data-stu-id="51d9c-229">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4.  <span data-ttu-id="51d9c-230">**[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-230">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="51d9c-231">**[ポートの通信方向]**: **[常にこのポートでメッセージを送信する]**</span><span class="sxs-lookup"><span data-stu-id="51d9c-231">**Port direction of communication**: **I'll always be sending messages on this port**</span></span>  
  
     <span data-ttu-id="51d9c-232">**[ポートのバインド]**: **[後で指定する]**</span><span class="sxs-lookup"><span data-stu-id="51d9c-232">**Port binding**: **Specify later**</span></span>  
  
5.  <span data-ttu-id="51d9c-233">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-233">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="51d9c-234">ポート画面に、JD Edwards OneWorld のサービスのための新しいポートと使用できるメソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-234">Displayed on the port surface are the new ports and the available methods for the JD Edwards OneWorld services.</span></span> <span data-ttu-id="51d9c-235">JD Edwards OneWorld システムとの間でファイルを送受信するように JD Edwards OneWorld アダプターを設定する作業は、後で行います。</span><span class="sxs-lookup"><span data-stu-id="51d9c-235">Later you will specify the JD Edwards OneWorld adapter to send and receive files from the JD Edwards OneWorld system.</span></span>  
  
 <span data-ttu-id="51d9c-236">**JDE_File_In**と**JDE_File_Out**必要性を作成したポートには、メッセージの種類が関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="51d9c-236">The **JDE_File_In** and **JDE_File_Out** ports you just created need associated message types.</span></span>  
  
#### <a name="assign-message-types-to-the-ports"></a><span data-ttu-id="51d9c-237">ポートにメッセージの種類を割り当てる</span><span class="sxs-lookup"><span data-stu-id="51d9c-237">Assign message types to the ports</span></span>  
  
1.  <span data-ttu-id="51d9c-238">左のポート画面上で、 **JDE_File_In**ポートでは、をクリックして**要求**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-238">On the left port surface, on the **JDE_File_In** port, click **Request**.</span></span> <span data-ttu-id="51d9c-239">プロパティ ウィンドウで **メッセージの種類**、展開**マルチパート メッセージ**、順にクリック**jde_ow_testaddressbookmastermbf**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-239">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBF**.</span></span>  
  
2.  <span data-ttu-id="51d9c-240">左のポート画面上で、 **JDE_File_Out**ポートでは、をクリックして**要求**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-240">On the left port surface, on the **JDE_File_Out** port, click **Request**.</span></span> <span data-ttu-id="51d9c-241">プロパティ ウィンドウで **メッセージの種類**、展開**マルチパート メッセージ**、順にクリック**jde_ow_testaddressbookmastermbfresponse**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-241">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBFResponse**.</span></span>  
  
 <span data-ttu-id="51d9c-242">2 つの挿入**送信**図形と 2 つ**受信**図形をオーケストレーションにポートにリンクします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-242">Insert two **Send** shapes and two **Receive** shapes into the orchestration to link to the ports.</span></span>  
  
#### <a name="add-send-and-receive-shapes"></a><span data-ttu-id="51d9c-243">追加の送信と受信図形</span><span class="sxs-lookup"><span data-stu-id="51d9c-243">Add Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="51d9c-244">ツールボックスから **受信** コンポーネントをドラッグし、オーケストレーション (緑色の円) の先頭の真下にドロップします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-244">Drag a **Receive** component from the Toolbox and drop it immediately below the start of the orchestration (the green circle).</span></span> <span data-ttu-id="51d9c-245">をクリックして、**受信**図形、および [プロパティ] ウィンドウで次のように入力します。`Get_File`の、**名前**、設定と**Activate**に`true`です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-245">Click the **Receive** shape, and in the Properties window, enter `Get_File` for the **Name**, and set **Activate** to `true`.</span></span> <span data-ttu-id="51d9c-246">このように設定すると、この受信ポートでドキュメントを受信したときにオーケストレーションがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="51d9c-246">Doing so will activate the orchestration when an incoming document is received on this receive port.</span></span>  
  
2.  <span data-ttu-id="51d9c-247">ドラッグ、**送信**コンポーネントをツールボックスからすぐ下にドロップし、 **GetFileReceive**図形です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-247">Drag a **Send** component from the Toolbox and drop it immediately below the **GetFileReceive** shape.</span></span> <span data-ttu-id="51d9c-248">クリックして、新しい**送信**図形、および [プロパティ] ウィンドウで次のように入力します。`SendToJDEOW`の、**名**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-248">Click the new **Send** shape, and in the Properties window, enter `SendToJDEOW` for the **Name**.</span></span>  
  
3.  <span data-ttu-id="51d9c-249">ドラッグ、**受信**コンポーネントをツールボックスからすぐ下にドロップし、 **SendToJDEOWSend**図形です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-249">Drag a **Receive** component from the Toolbox and drop it immediately below the **SendToJDEOWSend** shape.</span></span> <span data-ttu-id="51d9c-250">クリックして、**受信**図形、および [プロパティ] ウィンドウで次のように入力します。`JDEOW_Resp`の、**名前**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-250">Click the **Receive** shape, and in the Properties window, enter `JDEOW_Resp` for the **Name**.</span></span>  
  
4.  <span data-ttu-id="51d9c-251">ドラッグ、**送信**コンポーネントをツールボックスからすぐ下にドロップし、 **JDEOW_RespReceive**図形です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-251">Drag a **Send** component from the Toolbox and drop it immediately below the **JDEOW_RespReceive** shape.</span></span> <span data-ttu-id="51d9c-252">クリックして、新しい**送信**図形、および [プロパティ] ウィンドウで次のように入力します。`FileToDisk`の、**名**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-252">Click the new **Send** shape, and in the Properties window, enter `FileToDisk` for the **Name**.</span></span>  
  
     ![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")  
  
5.  <span data-ttu-id="51d9c-253">接続、 **JDE_FileIn**ポートを**GetFileReceive**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-253">Connect the **JDE_FileIn** port to the **GetFileReceive** component.</span></span>  
  
6.  <span data-ttu-id="51d9c-254">接続、 **JDE_FileOut**ポートを**FileToDiskReceive**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-254">Connect the **JDE_FileOut** port to the **FileToDiskReceive** component.</span></span>  
  
7.  <span data-ttu-id="51d9c-255">移動して**オーケストレーション ビュー**展開**メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-255">Go to **Orchestration View** and expand **Messages**.</span></span> <span data-ttu-id="51d9c-256">識別子を変更**Message_1**に`MsgToJDEOW`、および**Message_2**に`JDEOW_Resp.`</span><span class="sxs-lookup"><span data-stu-id="51d9c-256">Change the identifier for **Message_1** to `MsgToJDEOW`, and for **Message_2** to `JDEOW_Resp.`</span></span>  
  
8.  <span data-ttu-id="51d9c-257">強調表示、 **SendToJDEOWSend**コンポーネントで、設定、**メッセージ**プロパティを**MsgToJDEOW**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-257">Highlight the **SendToJDEOWSend** component and set its **Message** property to **MsgToJDEOW**.</span></span>  
  
9. <span data-ttu-id="51d9c-258">強調表示、 **JDEOW_RespReceive**コンポーネントで、設定、**メッセージ**プロパティを**JDEOW_Resp**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-258">Highlight the **JDEOW_RespReceive** component and set its **Message** property to **JDEOW_Resp**.</span></span>  
  
10. <span data-ttu-id="51d9c-259">接続**SendToJDEOW**を**要求**の部分、 **JDE_OW_Port**ポートです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-259">Connect **SendToJDEOW** to the **Request** portion of the **JDE_OW_Port** port.</span></span>  
  
11. <span data-ttu-id="51d9c-260">接続**JDEOW_Resp**を**応答**の部分、 **JDE_OW_Port**ポートです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-260">Connect **JDEOW_Resp** to the **Response** portion of the **JDE_OW_Port** port.</span></span>  
  
     ![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")  
  
## <a name="step-4-build-and-deploy-the-project"></a><span data-ttu-id="51d9c-261">手順 4: ビルドし、プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="51d9c-261">Step 4: Build and deploy the project</span></span>  
 <span data-ttu-id="51d9c-262">BizTalk プロジェクトが完成したので、ビルドし、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に展開できます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-262">Now the BizTalk project is complete and you can build and deploy it in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="51d9c-263">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-263">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="51d9c-264">プロジェクトをビルドするには、厳密な名前のキー ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-264">To build the project, you need a strong name key file.</span></span> <span data-ttu-id="51d9c-265">コマンド プロンプトで、次のとおりに入力して厳密な名前のキー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-265">At the command prompt, enter the following to create a strong name key file:</span></span>  
  
     <span data-ttu-id="51d9c-266">**sn-k labs.snk**</span><span class="sxs-lookup"><span data-stu-id="51d9c-266">**sn -k labs.snk**</span></span>  
  
3.  <span data-ttu-id="51d9c-267">ソリューション エクスプ ローラーで右クリックし、 **[jd_ow_test]**プロジェクトをクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-267">In Solution Explorer, right-click the **JD_OW_Test** project, and then click **Properties** to launch the Project Designer for the project.</span></span>  
  
4.  <span data-ttu-id="51d9c-268">**[署名]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-268">Click the **Signing** tab.</span></span>  
  
5.  <span data-ttu-id="51d9c-269">**[アセンブリの署名]** オプションを選択し、 **[厳密な名前のキー ファイルを選択してください]** オプションのドロップダウン リストをクリックして、 **[参照]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-269">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
6.  <span data-ttu-id="51d9c-270">キー ファイル **labs.snk**を一覧から選択して **[開く]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-270">Browse to select the key file: **labs.snk**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="51d9c-271">プロジェクト デザイナーの **[展開]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-271">Click **Deployment** tab in the Project Designer.</span></span>  
  
8.  <span data-ttu-id="51d9c-272">設定、**アプリケーション名**に`JDE_OW_Test`です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-272">Set the **Application Name** to `JDE_OW_Test`.</span></span>  
  
9. <span data-ttu-id="51d9c-273">ソリューション エクスプ ローラーで右クリックし、 **JDE_OW_Test**プロジェクトをクリックして**を構築します。**</span><span class="sxs-lookup"><span data-stu-id="51d9c-273">In Solution Explorer, right-click the **JDE_OW_Test** project, and then click **Build.**</span></span>  
  
     ![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")  
  
10. <span data-ttu-id="51d9c-274">ビルドが完了したらを右クリックし、 **[XX_JD Edwards oneworldquery]**プロジェクトをクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-274">After the build completes successfully, right-click the **XX_JD Edwards OneWorldQuery** project, and then click **Deploy**.</span></span> <span data-ttu-id="51d9c-275">出力ウィンドウに、次のように出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-275">In the output window the following output will be displayed:</span></span>  
  
     ![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a><span data-ttu-id="51d9c-276">手順 5: テスト アプリケーションと XML 出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-276">Step 5: Test the Application and Viewing the XML Output</span></span>  
 <span data-ttu-id="51d9c-277">次に、作成して展開したアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-277">Now you will test the application that you have created and deployed.</span></span> <span data-ttu-id="51d9c-278">初めに、オーケストレーション プロセスを開始する XML ファイルを作成します。次に、アプリケーション内で XML ファイルを送受信するためのフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-278">You will create the XML file that starts the orchestration process, and then you will configure folders to receive and send XML files within the application.</span></span> <span data-ttu-id="51d9c-279">アプリケーションの構成後は、アプリケーションを実行し、オーケストレーションが返す XML ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-279">After you have configured the application, you will run it and view the XML files that the orchestration returns.</span></span>  
  
#### <a name="generate-the-xml-file-for-the-query"></a><span data-ttu-id="51d9c-280">クエリの XML ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-280">Generate the XML file for the query</span></span>  
  
1.  <span data-ttu-id="51d9c-281">ソリューション エクスプ ローラーで、 **N0100041Service_N0100041.xsd**ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-281">In Solution Explorer, double-click **N0100041Service_N0100041.xsd** to open the file.</span></span>  
  
2.  <span data-ttu-id="51d9c-282">右クリック**N0100041Service_N0100041.xsd** をクリックし、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-282">Right-click **N0100041Service_N0100041.xsd** and then click **Properties**.</span></span> <span data-ttu-id="51d9c-283">**[出力インスタンス ファイル名]** に、サンプル XML のパスとファイル名を次のとおりに入力します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-283">For the **Output Instance Filename** enter the following path and file name for the sample XML:</span></span>  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  <span data-ttu-id="51d9c-284">クリックして **OK.**</span><span class="sxs-lookup"><span data-stu-id="51d9c-284">Click **OK.**</span></span> <span data-ttu-id="51d9c-285">[プロパティ] ウィンドウで選択**\<スキーマ >**設定と**ルート参照:**に`AddressBookMasterMBF`です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-285">In the Properties window, select **\<Schema>** and set **Root Reference:** to `AddressBookMasterMBF`.</span></span> <span data-ttu-id="51d9c-286">これにより、生成された XML のみを含む、**クエリ**xml です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-286">This will cause the generated XML to include only the **Query** xml.</span></span>  
  
     ![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")  
  
4.  <span data-ttu-id="51d9c-287">右クリック**N0100041Service_N0100041.xsd** をクリックし、**インスタンスの生成**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-287">Right-click **N0100041Service_N0100041.xsd** and then click **Generate Instance**.</span></span> <span data-ttu-id="51d9c-288">これにより生成、 **Sample.xml**ファイル。</span><span class="sxs-lookup"><span data-stu-id="51d9c-288">This generates the **Sample.xml** file.</span></span> <span data-ttu-id="51d9c-289">このファイルは、オーケストレーション プロセスを開始するアダプターに対する入力として、受信場所にドロップされます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-289">This file will be dropped in the receive location as input to the adapter to start the orchestration process.</span></span>  
  
#### <a name="configure-and-start-the-biztalk-application"></a><span data-ttu-id="51d9c-290">構成および BizTalk アプリケーションの開始</span><span class="sxs-lookup"><span data-stu-id="51d9c-290">Configure and start the BizTalk application</span></span>  
  
1.  <span data-ttu-id="51d9c-291">入力ファイルの受信と送出ファイルの送信のフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-291">Configure folders for receiving the incoming files and sending the outgoing files.</span></span> <span data-ttu-id="51d9c-292">移動して**C:\LABS\JDE_OW_Test**という 2 つの新しいサブフォルダーを作成および`FileIn`と`FileOut`です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-292">Go to **C:\LABS\JDE_OW_Test** and create two new subfolders named `FileIn` and `FileOut`.</span></span>  
  
2.  <span data-ttu-id="51d9c-293">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**コンソール ルート**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**を展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-293">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,expand **Console Root**, expand**BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="51d9c-294">右クリック**JDE_OW_Test**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-294">Right-click **JDE_OW_Test**, and then click **Configure**.</span></span>  
  
     ![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")  
  
4.  <span data-ttu-id="51d9c-295">**[Orchestration_1]** を選択し、 **[ホスト]** ドロップダウン ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-295">Select **Orchestration_1** and click the **Host** drop-down box.</span></span> <span data-ttu-id="51d9c-296">[ **BizTalkServerApplication**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-296">Select **BizTalkServerApplication**.</span></span>  
  
5.  <span data-ttu-id="51d9c-297">**受信ポート**をクリックして**\<なし >**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-297">Under **Receive Ports**, click **\<None>**.</span></span> <span data-ttu-id="51d9c-298">ドロップダウン リストの **[新しい受信ポート]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-298">In the drop-down list, select **New Receive Port**.</span></span>  
  
6.  <span data-ttu-id="51d9c-299">**名前**、型`JDE_FileIn_Port`、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-299">For **Name**, type `JDE_FileIn_Port`, and then click **OK**.</span></span> <span data-ttu-id="51d9c-300">受信場所を指定する必要があるというメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-300">A message box appears stating that you need to designate a receive location.</span></span> <span data-ttu-id="51d9c-301">**[OK]**をクリックし、 **[新規作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-301">Click **OK**, and then click **New**.</span></span>  
  
     ![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")  
  
7.  <span data-ttu-id="51d9c-302">プロパティに次の値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-302">Type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="51d9c-303">**名前**: JDE_`FileInLoc`</span><span class="sxs-lookup"><span data-stu-id="51d9c-303">**Name**: JDE_`FileInLoc`</span></span>  
  
     <span data-ttu-id="51d9c-304">**種類**: **ファイル**</span><span class="sxs-lookup"><span data-stu-id="51d9c-304">**Type**: **File**</span></span>  
  
     <span data-ttu-id="51d9c-305">**受信ハンドラー**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="51d9c-305">**Receive Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="51d9c-306">**受信パイプライン**: **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="51d9c-306">**Receive Pipeline**: **XMLReceive**</span></span>  
  
     ![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")  
  
8.  <span data-ttu-id="51d9c-307">をクリックして**構成**、型`C:\LABS\JDE_OW_Test\FileIn`の**受信フォルダー**、クリックして**[ok]** 3 回です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-307">Click **Configure**, type `C:\LABS\JDE_OW_Test\FileIn` for **Receive Folder**, and then click **OK** three times.</span></span>  
  
     ![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")  
  
9. <span data-ttu-id="51d9c-308">をクリックして**\<なし >**の**JDE_OW_Port**ドロップダウン リストでします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-308">Click **\<None>** for **JDE_OW_Port** in the drop-down list.</span></span>  
  
10. <span data-ttu-id="51d9c-309">選択**新しい送信ポートを**を選択するか、プロパティに次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-309">Select **New Send Port** and then select or type the following values for the properties:</span></span>  
  
     <span data-ttu-id="51d9c-310">**名前**:`JDE_OW_Port`</span><span class="sxs-lookup"><span data-stu-id="51d9c-310">**Name**: `JDE_OW_Port`</span></span>  
  
     <span data-ttu-id="51d9c-311">**型**: **JDE_OneWorld**</span><span class="sxs-lookup"><span data-stu-id="51d9c-311">**Type**: **JDE_OneWorld**</span></span>  
  
     <span data-ttu-id="51d9c-312">**[送信ハンドラー]**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="51d9c-312">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="51d9c-313">**[パイプライン]**: **XMLTransmit** および **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="51d9c-313">**Pipelines**: **XMLTransmit** and **XMLReceive**</span></span>  
  
11. <span data-ttu-id="51d9c-314">**[構成]**をクリックし、次のプロパティ値を入力します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-314">Click **Configure**, and then enter the following property values:</span></span>  
  
     <span data-ttu-id="51d9c-315">**ホスト:** \<JDEOW ホスト名を入力 ></span><span class="sxs-lookup"><span data-stu-id="51d9c-315">**Host:** \<enter your JDEOW host name></span></span>  
  
     <span data-ttu-id="51d9c-316">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="51d9c-316">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
     <span data-ttu-id="51d9c-317">**JDEdwards 環境:** \<JDEOW 環境を入力 ></span><span class="sxs-lookup"><span data-stu-id="51d9c-317">**JDEdwards Environment:** \<enter your JDEOW environment></span></span>  
  
     <span data-ttu-id="51d9c-318">**JDEdwards JAR ファイル:**<enter full path of JAR files></span><span class="sxs-lookup"><span data-stu-id="51d9c-318">**JDEdwards JAR files:** <enter full path of JAR files></span></span>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     <span data-ttu-id="51d9c-319">**パスワード:**ドロップダウン リストを使用して、JD Edwards OneWorld パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-319">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
     <span data-ttu-id="51d9c-320">**ポート:**  `6009`</span><span class="sxs-lookup"><span data-stu-id="51d9c-320">**Port:**  `6009`</span></span>  
  
     <span data-ttu-id="51d9c-321">**ユーザー名:**<enter your JD Edwards User Name></span><span class="sxs-lookup"><span data-stu-id="51d9c-321">**User Name:** <enter your JD Edwards User Name></span></span>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")  
  
12. <span data-ttu-id="51d9c-322">**[OK]** を 2 回クリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-322">Click **OK** twice to close the dialog boxes.</span></span>  
  
13. <span data-ttu-id="51d9c-323">構成 Applicationwindow、クリックして**\<なし >**の**JDE_FileOut**ドロップダウン リストでします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-323">In the Configure Applicationwindow, click **\<None>** for **JDE_FileOut** in the drop-down list.</span></span>  
  
14. <span data-ttu-id="51d9c-324">**[新しい送信ポート]** を選択し、プロパティの値を次のとおりに入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-324">Select **New Send Port** and type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="51d9c-325">**名前**:`FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="51d9c-325">**Name**: `FileOutPort`</span></span>  
  
     <span data-ttu-id="51d9c-326">**種類**: **ファイル**</span><span class="sxs-lookup"><span data-stu-id="51d9c-326">**Type**: **File**</span></span>  
  
     <span data-ttu-id="51d9c-327">**[送信ハンドラー]**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="51d9c-327">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="51d9c-328">**送信パイプライン**: **XMLTransmit**</span><span class="sxs-lookup"><span data-stu-id="51d9c-328">**Send Pipeline**: **XMLTransmit**</span></span>  
  
15. <span data-ttu-id="51d9c-329">をクリックして**構成**および種類`C:\Labs\JDE_OW_Test\FileOut`の**先のフォルダーです。**</span><span class="sxs-lookup"><span data-stu-id="51d9c-329">Click **Configure** and type`C:\Labs\JDE_OW_Test\FileOut` for **Destination Folder.**</span></span> <span data-ttu-id="51d9c-330">」と入力します。 **[ファイル名]** に「 **%MessageID%.xml** because this results in a unique file に「 each message.</span><span class="sxs-lookup"><span data-stu-id="51d9c-330">Keep **%MessageID%.xml** for **File Name** because this results in a unique file for each message.</span></span>  
  
     ![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")  
  
16. <span data-ttu-id="51d9c-331">**[OK]** を 3 回クリックして、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-331">Click **OK** three times to close the dialog boxes.</span></span>  
  
17. <span data-ttu-id="51d9c-332">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして、 **JDE_OW_Test**アプリケーション、およびクリック**開始**です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-332">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,right-click the **JDE_OW_Test** application, and then click **Start**.</span></span>  
  
#### <a name="test-the-orchestration"></a><span data-ttu-id="51d9c-333">オーケストレーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="51d9c-333">Test the orchestration</span></span>  
  
1.  <span data-ttu-id="51d9c-334">**C:\Labs\JDE_OW_Test**ディレクトリ、 **Sample.xml**ファイルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d9c-334">In the **C:\Labs\JDE_OW_Test** directory the **Sample.xml** file will appear as:</span></span>  
  
     ![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")  
  
2.  <span data-ttu-id="51d9c-335">編集、 **Sample.xml**を除くすべての項目を削除するファイル、 **cActionCode**と**mnAddressBookNumber**要素。</span><span class="sxs-lookup"><span data-stu-id="51d9c-335">Edit the **Sample.xml** file to remove everything except the **cActionCode** and **mnAddressBookNumber** elements.</span></span>  
  
     ![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")  
  
3.  <span data-ttu-id="51d9c-336">**CActionCode**要素は、文字を挿入`i`です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-336">For the **cActionCode** element insert the letter `i`.</span></span>  
  
4.  <span data-ttu-id="51d9c-337">**MnAddressBookNumber**数を挿入する`500`です。</span><span class="sxs-lookup"><span data-stu-id="51d9c-337">For **mnAddressBookNumber** insert the number `500`.</span></span>  
  
5.  <span data-ttu-id="51d9c-338">変更を保存し、ファイルのコピー、 **C:\Labs\JDE_OW_Test\FileIn**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-338">Save the changes and copy the file to the **C:\Labs\JDE_OW_Test\FileIn** folder.</span></span> <span data-ttu-id="51d9c-339">これが受信場所であり、ここからオーケストレーション プロセスが開始します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-339">This is the receive location that starts the orchestration process.</span></span>  
  
6.  <span data-ttu-id="51d9c-340">表示する必要があります XML ファイル、数秒で、 **C:\Labs\JDE_OW_Test\FileOut**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="51d9c-340">In a few seconds, an XML file should appear in the **C:\Labs\JDE_OW_Test\FileOut** folder.</span></span> <span data-ttu-id="51d9c-341">このファイルには、アドレスが 500 であるすべてのレコードが格納されています。</span><span class="sxs-lookup"><span data-stu-id="51d9c-341">This should contain the all the records where the address is 500.</span></span>  
  
     ![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")  
  
     <span data-ttu-id="51d9c-342">この返されたレコード データは、ラボ 1 で JD Edwards OneWorld システムに対してクエリによって返されるデータと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51d9c-342">This returned record data should match the data returned by the query against the JD Edwards OneWorld system in Lab 1.</span></span> <span data-ttu-id="51d9c-343">ラボ 1 で取得したレコードを比較すると、できることを確認する、**取得**メソッドが正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="51d9c-343">By comparing the records you obtained in Lab 1, you can verify that the **Get** method worked properly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="51d9c-344">概要</span><span class="sxs-lookup"><span data-stu-id="51d9c-344">Summary</span></span>  
 <span data-ttu-id="51d9c-345">このラボでは、初めに、JD Edwards OneWorld システムにアクセスするための前提条件が適切にセットアップされていることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="51d9c-345">In this lab, you first verified that the prerequisites were set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="51d9c-346">次に、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、オーケストレーションが含まれる新しい BizTalk プロジェクトを作成しました。</span><span class="sxs-lookup"><span data-stu-id="51d9c-346">Then you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project containing an orchestration.</span></span> <span data-ttu-id="51d9c-347">JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムからデータを取得するように、この BizTalk オーケストレーションを構成しました。</span><span class="sxs-lookup"><span data-stu-id="51d9c-347">You configured the BizTalk orchestration to use the JD Edwards OneWorld adapter to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="51d9c-348">オーケストレーションを構成するために、送信ポート、受信ポート、および送信/受信ポートを作成しました。</span><span class="sxs-lookup"><span data-stu-id="51d9c-348">To configure the orchestration, you created send, receive, and send/receive ports.</span></span> <span data-ttu-id="51d9c-349">これらのポートを JD Edwards OneWorld アダプターにバインドし、メッセージを該当するポートに割り当てました。</span><span class="sxs-lookup"><span data-stu-id="51d9c-349">You bound these ports to the JD Edwards OneWorld adapter, and assigned messages to the appropriate ports.</span></span>  
  
 <span data-ttu-id="51d9c-350">BizTalk プロジェクトの作成後、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してプロジェクトをビルドして展開しました。</span><span class="sxs-lookup"><span data-stu-id="51d9c-350">After you completed the BizTalk project, you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build and deploy it.</span></span> <span data-ttu-id="51d9c-351">次に、新しいアプリケーションを構成して実行し、JD Edwards OneWorld システムからデータを取得しました。</span><span class="sxs-lookup"><span data-stu-id="51d9c-351">You then configured your new application and ran it to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="51d9c-352">アプリケーションが正しく動作したことを確認するために、出力 XML ファイルを、ラボ 1 で JD Edwards OneWorld システムから受信したファイルと比較しました。</span><span class="sxs-lookup"><span data-stu-id="51d9c-352">To verify that the application worked correctly, you compared its output XML file to the file that you received from the JD Edwards OneWorld system in Lab 1.</span></span>