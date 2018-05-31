---
title: PeopleSoft Enterprise Sample Get の実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb54f14c-3fce-44d6-91bb-cb1ca38a20da
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29cf6bba03e6a43bb3fdedf0742741e48ac22dd6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25975296"
---
# <a name="execute-a-peoplesoft-enterprise-sample-get"></a><span data-ttu-id="b0f17-102">PeopleSoft Enterprise Sample Get を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-102">Execute a PeopleSoft Enterprise Sample Get</span></span>
<span data-ttu-id="b0f17-103">PeopleSoft システムは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムから PeopleSoft アダプターを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-103">The PeopleSoft system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="b0f17-104">このアダプターは、付属[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-104">This adapter is included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>
  
 <span data-ttu-id="b0f17-105">これは PeopleSoft ラボ作業の 2 パート目です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-105">This is the second part of the PeopleSoft lab work.</span></span> <span data-ttu-id="b0f17-106">1 パート目 (ラボ 1) では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] またはその他の Microsoft テクノロジを使用せずに、PeopleSoft システムに手動でアクセスし、データを変更しました。</span><span class="sxs-lookup"><span data-stu-id="b0f17-106">In the first part (Lab 1), you manually accessed and modified data on the PeopleSoft system without the assistance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or other Microsoft technologies.</span></span> <span data-ttu-id="b0f17-107">このパート (ラボ 2) では、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトの一部として、BizTalk オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-107">In this part (Lab 2), you will create a BizTalk orchestration as part of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project.</span></span> <span data-ttu-id="b0f17-108">PeopleSoft アダプターを使用して PeopleSoft システムのデータを取得するために、このオーケストレーションのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-108">You will configure ports on this orchestration to use the PeopleSoft adapter to get data from a PeopleSoft system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b0f17-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="b0f17-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="b0f17-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0f17-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>
  
-   <span data-ttu-id="b0f17-111">Microsoft BizTalk Adapters for Enterprise Applications</span><span class="sxs-lookup"><span data-stu-id="b0f17-111">Microsoft BizTalk Adapters for Enterprise Applications</span></span>  
  
-   <span data-ttu-id="b0f17-112">Microsoft Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0f17-112">Microsoft Visual Studio</span></span>  
  
-   <span data-ttu-id="b0f17-113">Sun Systems Java Development Kit (JDK) バージョン 1.4 以降</span><span class="sxs-lookup"><span data-stu-id="b0f17-113">Sun Systems Java Development Kit (JDK) version 1.4 or higher</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0f17-114">参照してください[をインストールし、エンタープライズ アプリケーション用のアダプターを構成](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)JD Edwards、PeopleSoft、および TIBCO アダプターのキーの構成についてはします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-114">See [Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) for key configuration information for the JD Edwards, PeopleSoft, and TIBCO adapters.</span></span>  
  
## <a name="lab-2---executing-a-peoplesoft-sample-get"></a><span data-ttu-id="b0f17-115">ラボ 2 - PeopleSoft Sample Get の実行</span><span class="sxs-lookup"><span data-stu-id="b0f17-115">Lab 2 - Executing a PeopleSoft Sample Get</span></span>  
 <span data-ttu-id="b0f17-116">このラボでは、PeopleSoft システムに対して **Get** 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-116">In this lab, you will execute a **Get** operation against the PeopleSoft system.</span></span> <span data-ttu-id="b0f17-117">具体的には、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-117">Specifically you will perform the following tasks:</span></span>  
  
-   <span data-ttu-id="b0f17-118">PeopleSoft の前提条件の確認</span><span class="sxs-lookup"><span data-stu-id="b0f17-118">Verify the PeopleSoft prerequisites</span></span>  
  
-   <span data-ttu-id="b0f17-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] での PeopleSoft 送信ポートのセットアップ</span><span class="sxs-lookup"><span data-stu-id="b0f17-119">Set up a PeopleSoft send port in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="b0f17-120">BizTalk オーケストレーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="b0f17-120">Create a BizTalk orchestration project</span></span>  
  
-   <span data-ttu-id="b0f17-121">プロジェクトのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="b0f17-121">Build and deploy the project</span></span>  
  
-   <span data-ttu-id="b0f17-122">アプリケーションのテストと XML 出力の表示</span><span class="sxs-lookup"><span data-stu-id="b0f17-122">Test the application and view the XML output</span></span>  
  
## <a name="procedures-for-lab-2--executing-a-peoplesoft-sample-get"></a><span data-ttu-id="b0f17-123">ラボ 2 の手順 - PeopleSoft Sample Get の実行</span><span class="sxs-lookup"><span data-stu-id="b0f17-123">Procedures for Lab 2- Executing a PeopleSoft Sample Get</span></span>  
 <span data-ttu-id="b0f17-124">PeopleSoft システムへのインターフェイス アクセスには、PSJOA.JAR および GET_CI_INFO.PC。</span><span class="sxs-lookup"><span data-stu-id="b0f17-124">Two files are necessary for proper interface access to a PeopleSoft system: PSJOA.JAR and GET_CI_INFO.PC.</span></span> <span data-ttu-id="b0f17-125">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターで、PeopleSoft アダプターは PeopleSoft Java インターフェイスを使用して PeopleSoft システムとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-125">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, the PeopleSoft adapter communicates with the PeopleSoft system by using the PeopleSoft Java interface.</span></span> <span data-ttu-id="b0f17-126">このインターフェイスは PSJOA.JAR ファイルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-126">This interface is supplied by the PSJOA.JAR file.</span></span> <span data-ttu-id="b0f17-127">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に配置されているこのファイルのコピーは、通常、アクセス先の PeopleSoft サーバー システムの管理者から送信されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-127">A copy of this file placed onto the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] typically comes from the administrator of the PeopleSoft server system that is being accessed.</span></span> <span data-ttu-id="b0f17-128">このラボでは、PSJOA.JAR のコピーは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の C:\PSJars\Ver841\ フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-128">In this lab, a copy of PSJOA.JAR exists in the C:\PSJars\Ver841\ folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b0f17-129">このファイルの場所は、PeopleSoft アダプター構成プロパティで指定されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-129">The location of this file is specified in the PeopleSoft adapter configuration properties.</span></span>  
  
 <span data-ttu-id="b0f17-130">PeopleSoft システムには、カスタム コンポーネント インターフェイス (CI) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-130">On the PeopleSoft system itself, a custom component interface (CI) must be installed.</span></span> <span data-ttu-id="b0f17-131">インストールすると、アダプターの構成時にアダプターから PeopleSoft オブジェクトを参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-131">This allows the adapter to browse PeopleSoft objects during adapter configuration.</span></span> <span data-ttu-id="b0f17-132">アクセス可能な PeopleSoft オブジェクトのリストを取得するために、カスタム コンポーネント インターフェイスを呼び出します ([生成した項目の追加] 手順から)。</span><span class="sxs-lookup"><span data-stu-id="b0f17-132">The custom component interface is called (from within the Add Generated Items step) to get a list of accessible PeopleSoft objects.</span></span> <span data-ttu-id="b0f17-133">これらのオブジェクトで、クライアント システムから使用できる PeopleSoft の公開機能が決まります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-133">These objects determine exposed PeopleSoft functionality available to the client system.</span></span>  
  
 <span data-ttu-id="b0f17-134">具体的には、初期セットアップ時に、カスタム コンポーネント GET_CI_INFO を PeopleSoft システムにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-134">Specifically the custom component, GET_CI_INFO, must be installed on the PeopleSoft system once during initial setup.</span></span> <span data-ttu-id="b0f17-135">このファイルを変更して、GET_CI_INFO で公開する内容を制限できます (既定では、PeopleSoft システムのすべてのコンポーネント インターフェイスが公開されます)。</span><span class="sxs-lookup"><span data-stu-id="b0f17-135">This file can be modified to limit what the GET_CI_INFO exposes (by default it exposes all component interfaces within the PeopleSoft system).</span></span> <span data-ttu-id="b0f17-136">ソースは既定で次の場所にある GET_CI_INFO テキスト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-136">Its source is found in the GET_CI_INFO.PC text file at the following default location:</span></span>  
  
 <span data-ttu-id="b0f17-137">**Enterprise Applications\PeopleSoft Enterprise(r) \Config の C:\Program files \microsoft BizTalk アダプター**</span><span class="sxs-lookup"><span data-stu-id="b0f17-137">**C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Config**</span></span>  
  
 <span data-ttu-id="b0f17-138">GET_CI_INFO コンポーネント インターフェイスを PeopleSoft にインストールに関する一般的な手順についてで提供される[をインストールし、エンタープライズ アプリケーション用のアダプターを構成](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-138">General instructions about installing the GET_CI_INFO component interface into PeopleSoft are provided in [Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md).</span></span> <span data-ttu-id="b0f17-139">これらのガイドは、PeopleSoft の操作に慣れた管理者向きです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-139">These instructions are for an experienced PeopleSoft administrator.</span></span>  
  
## <a name="step-1-confirm-the-peoplesoft-rerequisites"></a><span data-ttu-id="b0f17-140">手順 1: PeopleSoft rerequisites を確認します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-140">Step 1: Confirm the PeopleSoft rerequisites</span></span>  
 <span data-ttu-id="b0f17-141">PeopleSoft アダプターに使用する BizTalk プロジェクトの作成を開始する前に、PeopleSoft へのアクセスに必要な条件がすべてセットアップされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-141">Before you start creating a BizTalk project for use with the PeopleSoft adapter, you need to be sure that everything is set up correctly to access PeopleSoft.</span></span>  
  
1.  <span data-ttu-id="b0f17-142">いることを確認、PSJOA です。JAR ファイルに存在する、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] C:\psjars\ver841 フォルダー内のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="b0f17-142">Confirm that the PSJOA.JAR file exists on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\psjars\ver841 folder.</span></span> <span data-ttu-id="b0f17-143">(このファイルは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上では異なる場所にある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-143">(This file can exist at a different location on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b0f17-144">以下の構成では、ファイルがこの場所にあると想定しています)。</span><span class="sxs-lookup"><span data-stu-id="b0f17-144">In the configuration given below, it is assumed the file is at this location.)</span></span>  
  
2.  <span data-ttu-id="b0f17-145">C:\Program files \microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r) \Config フォルダーに get_ci_info.pc ファイルが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-145">Confirm that the get_ci_info.pc file exists in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Config folder.</span></span>  
  
3.  <span data-ttu-id="b0f17-146">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**の順に展開および**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-146">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Console Root**, expand [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span> <span data-ttu-id="b0f17-147">PeopleSoft アダプターがインストールされ、一覧に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-147">Ensure that the PeopleSoft adapter is installed and on the list.</span></span>  
  
     <span data-ttu-id="b0f17-148">PeopleSoft アダプターがインストールされていない場合、BizTalk Adapters for Enterprise Applications をインストールします (前述の「前提条件」の項を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b0f17-148">If the PeopleSoft adapter is not installed, install the BizTalk Adapters for Enterprise Applications (see the earlier "Prerequisites" section).</span></span> <span data-ttu-id="b0f17-149">アダプターのインストール後、 **[アダプター]** を右クリックし、 **[新規作成 - アダプター]** をクリックして PeopleSoft アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-149">After the adapters are installed, right-click **Adapters** and then click **New - Adapter** to install the PeopleSoft adapter.</span></span> <span data-ttu-id="b0f17-150">これを有効にするホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-150">Restart the host instance for this to take effect.</span></span>  
  
## <a name="step-2-create-a-send-port-for-peoplesoft"></a><span data-ttu-id="b0f17-151">手順 2: PeopleSoft の送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-151">Step 2: Create a Send Port for PeopleSoft</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b0f17-152"> には、PeopleSoft システムとの通信に使用する送信ポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-152"> needs to have a send port to use for communicating with the PeopleSoft system.</span></span> <span data-ttu-id="b0f17-153">この送信ポートは、最終的にオーケストレーションの論理ポートにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-153">This send port will eventually be bound to the orchestration's logical ports.</span></span>  
  
1.  <span data-ttu-id="b0f17-154">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**コンソール ルート**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開および**BizTalk.EnterpriseApplication です。**</span><span class="sxs-lookup"><span data-stu-id="b0f17-154">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk.EnterpriseApplication.**</span></span>  
  
2.  <span data-ttu-id="b0f17-155">**[送信ポート]** を右クリックし、 **[新規作成]** をクリックして、 **[静的な送信請求 - 応答の送信ポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-155">Right-click **Send Ports**, click **New**, and then select **Static Solicit-Response Send Port**.</span></span> <span data-ttu-id="b0f17-156">**[送信ポートのプロパティ]** ダイアログ ボックスで、プロパティの次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-156">In the **Send Port Properties** dialog box, enter the following values for the properties:</span></span>  
  
    1.  <span data-ttu-id="b0f17-157">**[名前]:**  `PeopleSoftSamplePort`</span><span class="sxs-lookup"><span data-stu-id="b0f17-157">**Name:**  `PeopleSoftSamplePort`</span></span>  
  
    2.  <span data-ttu-id="b0f17-158">**型:**  `PeopleSoft`</span><span class="sxs-lookup"><span data-stu-id="b0f17-158">**Type:**  `PeopleSoft`</span></span>  
  
    3.  <span data-ttu-id="b0f17-159">**送信ハンドラー。**  `BizTalkServerApplication`</span><span class="sxs-lookup"><span data-stu-id="b0f17-159">**Send handler:**  `BizTalkServerApplication`</span></span>  
  
    4.  <span data-ttu-id="b0f17-160">**送信パイプライン。**  `XMLTransmit`</span><span class="sxs-lookup"><span data-stu-id="b0f17-160">**Send pipeline:**  `XMLTransmit`</span></span>  
  
    5.  <span data-ttu-id="b0f17-161">**受信パイプライン。**  `XMLReceive`</span><span class="sxs-lookup"><span data-stu-id="b0f17-161">**Receive pipeline:**  `XMLReceive`</span></span>  
  
3.  <span data-ttu-id="b0f17-162">**[構成]** をクリックし、次のプロパティ値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-162">Click **Configure**, and then enter the following property values:</span></span>  
  
    1.  <span data-ttu-id="b0f17-163">**[アプリケーション サーバーのパス]**: **//Servername:9000**</span><span class="sxs-lookup"><span data-stu-id="b0f17-163">**Application server path**: **//Servername:9000**</span></span>  
  
         <span data-ttu-id="b0f17-164">Servername には、使用しているアプリケーション サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-164">Servername is your application server.</span></span> <span data-ttu-id="b0f17-165">これは、この PeopleSoft システムの固有のサーバー名または IP アドレスとポート番号です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-165">This is the specific server name or IP address and port number for this PeopleSoft system.</span></span>  
  
    2.  <span data-ttu-id="b0f17-166">**[JAVA_HOME]**: **C:\J2SDK1.4.2_08**</span><span class="sxs-lookup"><span data-stu-id="b0f17-166">**JAVA_HOME**: **C:\J2SDK1.4.2_08**</span></span>  
  
         <span data-ttu-id="b0f17-167">このパスは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の Java SDK インストールに固有のパスです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-167">This path is specific to the Java SDK installation on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    3.  <span data-ttu-id="b0f17-168">**パスワード**: \<PeopleSoft パスワードを入力してください\></span><span class="sxs-lookup"><span data-stu-id="b0f17-168">**Password**: \<enter your PeopleSoft password\></span></span>  
  
    4.  <span data-ttu-id="b0f17-169">**[PeopleSoft 8.x JAR ファイル]**: **C:\PSJARS\VER841\PSJOA.JAR**</span><span class="sxs-lookup"><span data-stu-id="b0f17-169">**PeopleSoft 8.x JAR files**: **C:\PSJARS\VER841\PSJOA.JAR**</span></span>  
  
    5.  <span data-ttu-id="b0f17-170">**ユーザー名:** \<PeopleSoft UserID を入力してください\></span><span class="sxs-lookup"><span data-stu-id="b0f17-170">**User name:** \<enter your PeopleSoft UserID\></span></span>  
  
     <span data-ttu-id="b0f17-171">![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")</span><span class="sxs-lookup"><span data-stu-id="b0f17-171">![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")</span></span>  
  
4.  <span data-ttu-id="b0f17-172">**[OK]** を 2 回クリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-172">Click **OK** twice to close the dialog boxes.</span></span>  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a><span data-ttu-id="b0f17-173">手順 3: BizTalk オーケストレーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-173">Step 3: Create a BizTalk Orchestration Project</span></span>  
 <span data-ttu-id="b0f17-174">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で BizTalk プロジェクトを作成し、プロジェクトのオーケストレーションを構成して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と PeopleSoft システム間の通信を処理します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-174">Now you will create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and configure an orchestration in the project to handle communication between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the PeopleSoft system.</span></span> <span data-ttu-id="b0f17-175">送信と受信のポートを追加し、プロジェクトをビルドしてから、プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-175">You will add send and receive ports, build the project, and then deploy the project.</span></span>  
  
1.  <span data-ttu-id="b0f17-176">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を開き、C:\LABS フォルダーに新しい BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-176">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and create a new BizTalk project in the C:\LABS folder.</span></span> <span data-ttu-id="b0f17-177">**[ファイル]** メニューの **[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-177">On the **File** menu, click **New**.</span></span> <span data-ttu-id="b0f17-178">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-178">The **New Project** dialog box appears.</span></span> <span data-ttu-id="b0f17-179">**[テンプレート]** セクションで **[空の BizTalk Server プロジェクト]**</span><span class="sxs-lookup"><span data-stu-id="b0f17-179">In the **Templates** section, select **Empty BizTalk Server project.**</span></span> <span data-ttu-id="b0f17-180">を選択します。一意なプロジェクト名として「 `PS_Test` 」と入力し、 **[OK]** 用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-180">Enter `PS_Test` as the unique project name, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="b0f17-181">ソリューション エクスプローラーでプロジェクト名を右クリックし、 **[追加]** をクリックし、 **[生成した項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-181">In Solution Explorer, right-click the project, click **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="b0f17-182">**[カテゴリ]** ペインの **[アダプター メタデータの追加]** を選択し、 **[テンプレート]** 側の **[アダプター メタデータの追加]** を選択し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-182">Select **Add Adapter Metadata** in the **Categories** pane, select **Add Adapter Metadata** on the **Templates** side, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="b0f17-183">アダプターの追加ウィザードで **[PeopleSoft Enterprise]** アダプターを選択し、前の手順で作成した **[PeopleSoftSamplePort]** 送信ポートを選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-183">In the Add Adapter Wizard, select the **PeopleSoft Enterprise** adapter, select the **PeopleSoftSamplePort** send port that you created in the preceding procedure, and then click **Next**.</span></span>  
  
     <span data-ttu-id="b0f17-184">![](../core/media/ed0dedc5-a8fb-444c-b884-e310cf56462c.gif "ed0dedc5-a8fb-444c-b884-e310cf56462c")</span><span class="sxs-lookup"><span data-stu-id="b0f17-184">![](../core/media/ed0dedc5-a8fb-444c-b884-e310cf56462c.gif "ed0dedc5-a8fb-444c-b884-e310cf56462c")</span></span>  
  
4.  <span data-ttu-id="b0f17-185">**[インポートするサービスの選択]** ページで、 **[PeopleSoft]**、 **[CI]** の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-185">On the **Select Services to Import** page, expand **PeopleSoft**, and then expand **CI**.</span></span>  
  
     <span data-ttu-id="b0f17-186">PeopleSoft システムは Browsing Agent を使用してアダプターから問い合わせられます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-186">The PeopleSoft system is interrogated by the adapter using the Browsing Agent.</span></span> <span data-ttu-id="b0f17-187">**[CI]** を展開すると、BrowsingAgent.exe プロセスが開始され (タスク マネージャーで実行中であることを確認できます)、次の図のようにサービスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-187">When you expand **CI**, the BrowsingAgent.exe process starts (you can view it as running in Task Manager) and returns the services shown in the following figure.</span></span>  
  
     <span data-ttu-id="b0f17-188">![](../core/media/6988104c-6483-4df2-a637-3301628ea665.gif "6988104c-6483-4df2-a637-3301628ea665")</span><span class="sxs-lookup"><span data-stu-id="b0f17-188">![](../core/media/6988104c-6483-4df2-a637-3301628ea665.gif "6988104c-6483-4df2-a637-3301628ea665")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0f17-189">PeopleSoft システムから取得されて表示される PeopleSoft サービスは、この図とは一部異なることもあります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-189">The PeopleSoft services obtained and displayed from your PeopleSoft system may be slightly different than the services displayed here.</span></span>  
  
5.  <span data-ttu-id="b0f17-190">スクロールし、 **[LOCATION]** を選択し、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-190">Scroll down, select **LOCATION**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="b0f17-191">![](../core/media/0506affd-3caa-47cb-9c25-f49c8a0ad614.gif "0506affd-3caa-47cb-9c25-f49c8a0ad614")</span><span class="sxs-lookup"><span data-stu-id="b0f17-191">![](../core/media/0506affd-3caa-47cb-9c25-f49c8a0ad614.gif "0506affd-3caa-47cb-9c25-f49c8a0ad614")</span></span>  
  
6.  <span data-ttu-id="b0f17-192">ソリューション エクスプローラーには、新しい BizTalk オーケストレーションと、2 つの新しい関連スキーマ ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-192">In Solution Explorer, there is a new BizTalk orchestration and two new associated schema files.</span></span> <span data-ttu-id="b0f17-193">これらのファイルはアダプターの追加ウィザードによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-193">These files are created by the Add Adapter Wizard.</span></span> <span data-ttu-id="b0f17-194">**BizTalk Orchestration.odx** ファイルをダブルクリックし、オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-194">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
     <span data-ttu-id="b0f17-195">![](../core/media/825c5690-78eb-4048-9a47-cd3fc7310b7b.gif "825c5690-78eb-4048-9a47-cd3fc7310b7b")</span><span class="sxs-lookup"><span data-stu-id="b0f17-195">![](../core/media/825c5690-78eb-4048-9a47-cd3fc7310b7b.gif "825c5690-78eb-4048-9a47-cd3fc7310b7b")</span></span>  
  
 <span data-ttu-id="b0f17-196">このオーケストレーションは、入力として、PeopleSoft **Get** メソッド用にフォーマットされた XML ファイルを受け入れ、XML ファイルを PeopleSoft システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-196">This orchestration accepts as input an XML file formatted for the PeopleSoft **Get** method and sends the XML file to the PeopleSoft system.</span></span> <span data-ttu-id="b0f17-197">**Get** メソッドは、PeopleSoft システムのロケーション情報を取得し、BizTalk オーケストレーションに返します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-197">The **Get** method retrieves location information from the PeopleSoft system and returns it to the BizTalk orchestration.</span></span> <span data-ttu-id="b0f17-198">オーケストレーションでは、アダプターおよび PeopleSoft システムとのこの通信を容易にするためにポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-198">The orchestration uses ports to facilitate this communication with the adapter and the PeopleSoft system.</span></span> <span data-ttu-id="b0f17-199">ここで構成するポートは、XML ファイルの送受信用です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-199">The ports you will configure here are for receiving and sending XML files.</span></span> <span data-ttu-id="b0f17-200">送信 XML ファイルは、これが **Get** 操作であることを PeopleSoft システムに示します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-200">The outgoing XML file tells the PeopleSoft system that this is a **Get** operation.</span></span> <span data-ttu-id="b0f17-201">受信 XML ファイルは、オーケストレーションに場所情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-201">The incoming XML file returns the location information to the orchestration.</span></span>  
  
 <span data-ttu-id="b0f17-202">オーケストレーションを完成させるには、XML の送信と受信のためのポートを作成および構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-202">To complete the orchestration, you need to create and configure ports to receive and send the XML files.</span></span> <span data-ttu-id="b0f17-203">まず、 **Get** メソッドを含む最初の XML 入力ファイルを受け入れてオーケストレーションを開始できるように、新しい受信ポートをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-203">First, set up a new receive port to accept the initial XML input file that contains the **Get** method to start the orchestration.</span></span>  
  
#### <a name="configure-a-receive-port"></a><span data-ttu-id="b0f17-204">受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-204">Configure a receive port</span></span>  
  
1.  <span data-ttu-id="b0f17-205">前の手順で開いた BizTalk Orchestration.odx ファイル内で、左のポート画面を右クリックし、 **[新しい構成済みのポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-205">Within the BizTalk Orchestration.odx file that you opened in the previous step, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="b0f17-206">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-206">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="b0f17-207">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-207">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="b0f17-208">**[ポートのプロパティ]** ページで、 `FileIn` に「 **FileIn**の順にポイントし、 **[次へ]** 用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-208">On the **Port Properties** page, enter `FileIn` for **Name**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="b0f17-209">**[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]** を選択し、次のプロパティ値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-209">In the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="b0f17-210">**ポートの種類名**: `FileInPort`</span><span class="sxs-lookup"><span data-stu-id="b0f17-210">**Port Type Name**: `FileInPort`</span></span>  
  
     <span data-ttu-id="b0f17-211">**[通信方式]**: **一方向**</span><span class="sxs-lookup"><span data-stu-id="b0f17-211">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="b0f17-212">**[アクセスの制限]**: **[内部 - このプロジェクト限定]**</span><span class="sxs-lookup"><span data-stu-id="b0f17-212">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4.  <span data-ttu-id="b0f17-213">**[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-213">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="b0f17-214">**[ポートの通信方向]**: **常にこのポートでメッセージを受信する**</span><span class="sxs-lookup"><span data-stu-id="b0f17-214">**Port direction of communication**: **I'll always be receiving messages on this port**</span></span>  
  
     <span data-ttu-id="b0f17-215">**[ポートのバインド]**: **[後で指定する]**</span><span class="sxs-lookup"><span data-stu-id="b0f17-215">**Port binding**: **Specify later**</span></span>  
  
5.  <span data-ttu-id="b0f17-216">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-216">Click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="b0f17-217">このファイルをディスクからの入力として受け入れるには、ファイル アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-217">You will use the File adapter to accept this file as input from disk.</span></span>  
  
 <span data-ttu-id="b0f17-218">次に、PeopleSoft **Get** メソッドに対する呼び出しからの場所の結果を含む XML ファイルを受け入れる送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-218">Next, create a send port to accept the XML file containing the location results from the call to the PeopleSoft **Get** method.</span></span> <span data-ttu-id="b0f17-219">オーケストレーションでは、この送信ポートを介してディスクにこの XML ファイルを書き込むためにファイル アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-219">The orchestration uses the File adapter to write that XML file to disk through this send port.</span></span>  
  
#### <a name="configure-a-send-port"></a><span data-ttu-id="b0f17-220">送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-220">Configure a send port</span></span>  
  
1.  <span data-ttu-id="b0f17-221">BizTalk Orchestration.odx ファイルで、左のポート画面を右クリックし、 **[新しい構成済みのポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-221">Within the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="b0f17-222">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-222">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="b0f17-223">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-223">On the **Welcome to the Port Configuration Wizard** page click **Next**.</span></span>  
  
2.  <span data-ttu-id="b0f17-224">**[ポートのプロパティ]** ページで、 `FileOut` に「 **FileIn**の順にポイントし、 **[次へ]** 用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-224">On the **Port Properties** page, enter `FileOut` for **Name**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="b0f17-225">**[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]** を選択し、次のプロパティ値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-225">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="b0f17-226">**ポートの種類名**: `FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="b0f17-226">**Port Type Name**: `FileOutPort`</span></span>  
  
     <span data-ttu-id="b0f17-227">**[通信方式]**: **一方向**</span><span class="sxs-lookup"><span data-stu-id="b0f17-227">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="b0f17-228">**[アクセスの制限]**: **[内部 - このプロジェクト限定]**</span><span class="sxs-lookup"><span data-stu-id="b0f17-228">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4.  <span data-ttu-id="b0f17-229">**[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-229">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="b0f17-230">**[ポートの通信方向]**: **[常にこのポートでメッセージを送信する]**</span><span class="sxs-lookup"><span data-stu-id="b0f17-230">**Port direction of communication**: **I'll always be sending messages on this port**</span></span>  
  
     <span data-ttu-id="b0f17-231">**[ポートのバインド]**: **[後で指定する]**</span><span class="sxs-lookup"><span data-stu-id="b0f17-231">**Port binding**: **Specify later**</span></span>  
  
5.  <span data-ttu-id="b0f17-232">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-232">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="b0f17-233">最後に、PeopleSoft システムに対する **Get** メソッドを含む最初の XML 入力ファイルを送信するために、送信/受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-233">Finally, create a send/receive port to send the initial XML input file containing the **Get** method to the PeopleSoft system.</span></span> <span data-ttu-id="b0f17-234">また、このポートは、PeopleSoft システムでの **Get** メソッドの呼び出し結果である場所情報を含む XML ファイルも受信します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-234">This port will also receive an XML file containing the location information that results from the **Get** method call on the PeopleSoft system.</span></span>  
  
#### <a name="configure-a-sendreceive-port"></a><span data-ttu-id="b0f17-235">送信/受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-235">Configure a send/receive port</span></span>  
  
1.  <span data-ttu-id="b0f17-236">BizTalk Orchestration.odx ファイルで、右のポート画面を右クリックし、 **[新しい構成済みのポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-236">Within the BizTalk Orchestration.odx file, right-click the right port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="b0f17-237">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-237">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="b0f17-238">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-238">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="b0f17-239">**[ポートのプロパティ]** ページで、 `PeopleSoft_Port` に「 **FileIn**の順にポイントし、 **[次へ]** 用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-239">On the **Port Properties** page, enter `PeopleSoft_Port` for **Name**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="b0f17-240">**[ポートの種類の選択]** ページで、 **[既存のポートの種類を使用する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-240">On the **Select a Port Type** page, select **Use an existing Port Type**.</span></span> <span data-ttu-id="b0f17-241">**[利用可能なポートの種類]** について **[PS_Test.LOCATION]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-241">For **Available Port Types**, select **PS_Test.LOCATION**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="b0f17-242">![](../core/media/d8b443ec-294d-4124-a29d-aeb42bbb107e.gif "d8b443ec-294d-4124-a29d-aeb42bbb107e")</span><span class="sxs-lookup"><span data-stu-id="b0f17-242">![](../core/media/d8b443ec-294d-4124-a29d-aeb42bbb107e.gif "d8b443ec-294d-4124-a29d-aeb42bbb107e")</span></span>  
  
4.  <span data-ttu-id="b0f17-243">**[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-243">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="b0f17-244">**[ポートの通信方向]**: **[常に要求を送信し、応答を受信します。]**</span><span class="sxs-lookup"><span data-stu-id="b0f17-244">**Port direction of communication**: **I'll always be sending a request and receiving a response**</span></span>  
  
     <span data-ttu-id="b0f17-245">**[ポートのバインド]**: **[後で指定する]**</span><span class="sxs-lookup"><span data-stu-id="b0f17-245">**Port binding**: **Specify later**</span></span>  
  
5.  <span data-ttu-id="b0f17-246">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-246">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="b0f17-247">ポート画面には、PeopleSoft Location サービスの新しいポートと使用できるメソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-247">Displayed on the port surface are the new port and the available methods for the PeopleSoft Location service.</span></span> <span data-ttu-id="b0f17-248">後で、PeopleSoft システムからファイルを送受信する PeopleSoft アダプターを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-248">Later you will specify the PeopleSoft adapter to send and receive files from the PeopleSoft system.</span></span>  
  
 <span data-ttu-id="b0f17-249">ここでは、2 つの **送信** 図形と 2 つの **受信** 図形をオーケストレーションに挿入し、作成したポートにリンクします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-249">Now insert two **Send** shapes and two **Receive** shapes into the orchestration to link to the ports you just created.</span></span>  
  
#### <a name="add-send-and-receive-shapes"></a><span data-ttu-id="b0f17-250">追加の送信と受信図形</span><span class="sxs-lookup"><span data-stu-id="b0f17-250">Add Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="b0f17-251">ツールボックスから **受信** コンポーネントをドラッグし、オーケストレーション (緑色の円) の先頭の真下にドロップします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-251">Drag a **Receive** component from the Toolbox and drop it immediately below the start of the orchestration (the green circle).</span></span> <span data-ttu-id="b0f17-252">**受信** 図形をクリックし、[プロパティ] ウィンドウで `FromDisk` に「 **FileIn**」と入力し、 **[アクティブ化]** を `true`用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-252">Click the **Receive** shape, and in the Properties window, enter `FromDisk` for the **Name**, and set **Activate** to `true`.</span></span> <span data-ttu-id="b0f17-253">このように設定すると、この受信ポートでドキュメントを受信したときにオーケストレーションがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-253">Doing so will activate the orchestration when an incoming document is received on this receive port.</span></span>  
  
2.  <span data-ttu-id="b0f17-254">ドラッグ、 **送信** コンポーネントをツールボックスからすぐ下にドロップし、 **FromDiskReceive** 図形です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-254">Drag a **Send** component from the Toolbox and drop it immediately below the **FromDiskReceive** shape.</span></span> <span data-ttu-id="b0f17-255">新しい **送信** 図形をクリックし、[プロパティ] ウィンドウで `ToPS` に「 **FileIn**用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-255">Click the new **Send** shape, and in the Properties window, enter `ToPS` for the **Name**.</span></span>  
  
3.  <span data-ttu-id="b0f17-256">ドラッグ、 **受信** コンポーネントをツールボックスからすぐ下にドロップし、 **To_PS \* \* \* 送信** 図形です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-256">Drag a **Receive** component from the Toolbox and drop it immediately below the **To_PS****Send** shape.</span></span> <span data-ttu-id="b0f17-257">**受信** 図形をクリックし、[プロパティ] ウィンドウで `FromPS` に「 **FileIn**用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-257">Click the **Receive** shape, and in the Properties window, enter `FromPS` for the **Name**.</span></span>  
  
4.  <span data-ttu-id="b0f17-258">ドラッグ、 **送信** コンポーネントをツールボックスからすぐ下にドロップし、 **From_PSReceive** 図形です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-258">Drag a **Send** component from the Toolbox and drop it immediately below the **From_PSReceive** shape.</span></span> <span data-ttu-id="b0f17-259">新しい **送信** 図形をクリックし、[プロパティ] ウィンドウで `ToDisk` に「 **FileIn**用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-259">Click the new **Send** shape, and in the Properties window, enter `ToDisk` for the **Name**.</span></span>  
  
 <span data-ttu-id="b0f17-260">これらの図形を論理ポートに接続するには、処理するメッセージの種類を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-260">Before you can connect these shapes to logical ports, you need to define the message types to be processed.</span></span> <span data-ttu-id="b0f17-261">アダプターには受信 (**Request** メソッド) メッセージおよび送信 (**Response** メソッド) メッセージの両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-261">The adapter needs both an incoming (**Request** method) message and an outgoing (**Response** method) message.</span></span> <span data-ttu-id="b0f17-262">各メソッドのメッセージは異なります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-262">The messages for each of the methods are different.</span></span>  
  
 <span data-ttu-id="b0f17-263">このオーケストレーションでは、 **Get-Request** メッセージと **Get-Response** メッセージのみを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b0f17-263">In this orchestration, you are only using the **Get-Request** and **Get-Response** messages.</span></span> <span data-ttu-id="b0f17-264">オーケストレーションが (たとえば **UpdateEx** メソッドを使用して) データを更新する場合、別の Request/Response メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-264">If the orchestration were updating the data, say by using the **UpdateEx** method, it would require different Request/Response messages.</span></span>  
  
#### <a name="define-and-assign-messages-to-ports"></a><span data-ttu-id="b0f17-265">定義し、ポートへのメッセージの割り当てください</span><span class="sxs-lookup"><span data-stu-id="b0f17-265">Define and assign messages to ports</span></span>  
  
1.  <span data-ttu-id="b0f17-266">左のポート画面で、 **[FileIn]** ポートの **[Request]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-266">On the left port surface, click **Request** on the **FileIn** port.</span></span> <span data-ttu-id="b0f17-267">[プロパティ] ウィンドウで、 **[メッセージの種類]**、 **[マルチパート メッセージ]** の順に展開し、 **[PS_Test.Get]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-267">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **PS_Test.Get**.</span></span>  
  
2.  <span data-ttu-id="b0f17-268">左のポート画面で、 **[FileOut]** ポートの **[Request]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-268">On the left port surface, click **Request** on the **FileOut** port.</span></span> <span data-ttu-id="b0f17-269">[プロパティ] ウィンドウで、 **[メッセージの種類]**、 **[マルチパート メッセージ]** の順に展開し、 **[PS_Test.GetResponse]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-269">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **PS_Test.GetResponse**.</span></span>  
  
     <span data-ttu-id="b0f17-270">![](../core/media/6b844ca3-322a-47b3-8cfd-68652c950752.gif "6b844ca3-322a-47b3-8cfd-68652c950752")</span><span class="sxs-lookup"><span data-stu-id="b0f17-270">![](../core/media/6b844ca3-322a-47b3-8cfd-68652c950752.gif "6b844ca3-322a-47b3-8cfd-68652c950752")</span></span>  
  
3.  <span data-ttu-id="b0f17-271">**[FileIn]** ポートを選択し、外向きの送信の矢印を **[FromDisk]** 図形の内向きの受信の矢印にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-271">Select the **FileIn** port and drag its outgoing send arrow to the incoming converse receive arrow on the **FromDisk** shape.</span></span>  
  
4.  <span data-ttu-id="b0f17-272">**[FileOut]** ポートを選択し、内向きの受信の矢印を **[ToDisk]** 図形の外向きの送信の矢印にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-272">Select the **FileOut** port and drag its incoming converse receive arrow to the outgoing send arrow on the **ToDisk** shape.</span></span>  
  
5.  <span data-ttu-id="b0f17-273">優れたアプリケーションの設計原則に従って、既存の汎用メッセージ名をよりわかりやすい名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-273">Rename existing generic message names to more descriptive names to adhere to good application design principles.</span></span> <span data-ttu-id="b0f17-274">ソリューション エクスプローラーで、 **[オーケストレーションの種類]** タブをクリックします。**メッセージ**の識別子を変更**Message_1**に**PS_Msg**です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-274">In Solution Explorer, click the **Orchestration View** tab. Under **Messages**, change the identifier for **Message_1** to **PS_Msg**.</span></span> <span data-ttu-id="b0f17-275">**[Message_2]** の識別子を **[PS_Resp]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-275">Change the identifier for **Message_2** to **PS_Resp**.</span></span>  
  
     <span data-ttu-id="b0f17-276">![](../core/media/5ec92b81-4a55-4d44-a360-78a6aaa64255.gif "5ec92b81-4a55-4d44-a360-78a6aaa64255")</span><span class="sxs-lookup"><span data-stu-id="b0f17-276">![](../core/media/5ec92b81-4a55-4d44-a360-78a6aaa64255.gif "5ec92b81-4a55-4d44-a360-78a6aaa64255")</span></span>  
  
     <span data-ttu-id="b0f17-277">![](../core/media/04b31c26-73a6-40a6-8d50-39c7c929d6a1.gif "04b31c26-73a6-40a6-8d50-39c7c929d6a1")</span><span class="sxs-lookup"><span data-stu-id="b0f17-277">![](../core/media/04b31c26-73a6-40a6-8d50-39c7c929d6a1.gif "04b31c26-73a6-40a6-8d50-39c7c929d6a1")</span></span>  
  
6.  <span data-ttu-id="b0f17-278">**[To_PS]** 送信図形を選択し、 **[Message]** プロパティを **[PS_Msg]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-278">Highlight the **To_PS** send shape and set its **Message** property to **PS_Msg**.</span></span>  
  
7.  <span data-ttu-id="b0f17-279">**[From_PS]** 受信図形を選択し、 **[Message]** プロパティを **[PS_Resp]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-279">Highlight the **From_PS** receive shape and set its **Message** property to **PS_Resp**.</span></span>  
  
8.  <span data-ttu-id="b0f17-280">**[To_PS]** 送信図形を、 **[PeopleSoft_Port]** ポートの **[Get]** メソッドの **[Request]** 部分に接続します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-280">Connect the **To_PS** send shape to the **Request** portion of the **Get** method on the **PeopleSoft_Port** port.</span></span>  
  
9. <span data-ttu-id="b0f17-281">**[From_PS]** 送信図形を、 **[PeopleSoft_Port]** ポートの **[Get]** メソッドの **[Response]** 部分に接続します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-281">Connect the **From_PS** send shape to the **Response** portion of the **Get** method on the **PeopleSoft_Port** port.</span></span>  
  
     <span data-ttu-id="b0f17-282">![](../core/media/d16e02bc-954c-4aa2-99d6-3fee1222c730.gif "d16e02bc-954c-4aa2-99d6-3fee1222c730")</span><span class="sxs-lookup"><span data-stu-id="b0f17-282">![](../core/media/d16e02bc-954c-4aa2-99d6-3fee1222c730.gif "d16e02bc-954c-4aa2-99d6-3fee1222c730")</span></span>  
  
## <a name="step-4-build-and-deploy-the-project"></a><span data-ttu-id="b0f17-283">手順 4: ビルドし、プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="b0f17-283">Step 4: Build and Deploy the Project</span></span>  
 <span data-ttu-id="b0f17-284">BizTalk プロジェクトが完成したので、ビルドし、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に展開できます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-284">Now the BizTalk project is complete and you can build and deploy it in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="b0f17-285">Visual Studio で、指す**Visual Studio Tools**、し、Visual Studio コマンド プロンプト * *。</span><span class="sxs-lookup"><span data-stu-id="b0f17-285">In Visual Studio, point to **Visual Studio Tools**, and then select Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="b0f17-286">プロジェクトをビルドするには、厳密な名前キーファイルが必要です。コマンド プロンプトに次のように入力し、厳密な名前のキー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-286">To build the project, you need a strong name key file.At the command prompt, enter the following to create a strong name key file:</span></span>  
  
     <span data-ttu-id="b0f17-287">**sn-k labs.snk**</span><span class="sxs-lookup"><span data-stu-id="b0f17-287">**sn -k labs.snk**</span></span>  
  
3.  <span data-ttu-id="b0f17-288">ソリューション エクスプローラーで、 **[PS_Test]** プロジェクトを右クリックし、 **[プロパティ]** をクリックして、プロジェクトのプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-288">In Solution Explorer, right-click the **PS_Test** project and then click **Properties** to launch the Project Designer for the project..</span></span>  
  
4.  <span data-ttu-id="b0f17-289">**[署名]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-289">Click the **Signing** tab.</span></span>  
  
5.  <span data-ttu-id="b0f17-290">**[アセンブリの署名]** オプションを選択し、 **[厳密な名前のキー ファイルを選択してください]** オプションのドロップダウン リストをクリックして、 **[参照]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-290">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
6.  <span data-ttu-id="b0f17-291">キー ファイル **labs.snk**を一覧から選択して **[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-291">Browse to select the key file: **labs.snk**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="b0f17-292">プロジェクト デザイナーの **[展開]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-292">Click **Deployment** tab in the Project Designer.</span></span>  
  
8.  <span data-ttu-id="b0f17-293">**[アプリケーション名]** を `PS_Test`用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-293">Set the **Application Name** to `PS_Test`.</span></span>  
  
9. <span data-ttu-id="b0f17-294">ソリューション エクスプローラーで **[PS_Test]** プロジェクトを右クリックし、 **[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-294">In Solution Explorer, right-click the **PS_Test** project, and then click **Build.**</span></span>  
  
10. <span data-ttu-id="b0f17-295">ビルドが正常に完了したら、 **[PS_Test]** プロジェクトを右クリックし、 **[展開]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-295">After the build completes successfully, right-click the **PS_Test** project, and then click **Deploy**.</span></span>  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a><span data-ttu-id="b0f17-296">手順 5: テスト アプリケーションと XML 出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-296">Step 5: Test the Application and Viewing the XML Output</span></span>  
 <span data-ttu-id="b0f17-297">次に、作成して展開したアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-297">Now you will test the application that you have created and deployed.</span></span> <span data-ttu-id="b0f17-298">初めに、オーケストレーション プロセスを開始する XML ファイルを作成します。次に、アプリケーション内で XML ファイルを送受信するためのフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-298">You will create the XML file that starts the orchestration process, and then you will configure folders to receive and send XML files within the application.</span></span> <span data-ttu-id="b0f17-299">アプリケーションの構成後は、アプリケーションを実行し、オーケストレーションが返す XML ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-299">After you have configured the application, you will run it and view the XML files that the orchestration returns.</span></span>  
  
#### <a name="generate-the-xml-file-for-the-query"></a><span data-ttu-id="b0f17-300">クエリの XML ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-300">Generate the XML file for the query</span></span>  
  
1.  <span data-ttu-id="b0f17-301">ソリューション エクスプローラーで、 **LOCATIONService_LOCATION_x5d.xsd** をクリックしてファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-301">In Solution Explorer, double-click **LOCATIONService_LOCATION_x5d.xsd** to open the file.</span></span>  
  
2.  <span data-ttu-id="b0f17-302">**LOCATIONService_LOCATION_x5d.xsd** を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-302">Right-click **LOCATIONService_LOCATION_x5d.xsd** and then click **Properties**.</span></span> <span data-ttu-id="b0f17-303">**[出力インスタンス ファイル名]** に、サンプル XML のパスとファイル名を次のとおりに入力します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-303">For the **Output Instance Filename** enter the following path and file name for the sample XML:</span></span>  
  
     `C:\LABS\PS_TEST\SAMPLEQUERY.XML`  
  
3.  <span data-ttu-id="b0f17-304">クリックして **OK.**</span><span class="sxs-lookup"><span data-stu-id="b0f17-304">Click **OK.**</span></span> <span data-ttu-id="b0f17-305">[プロパティ] ウィンドウで選択**\<スキーマ\>** 設定と**ルート参照: 取得**です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-305">In the Properties window, select **\<Schema\>** and set **Root Reference: Get**.</span></span>  
  
4.  <span data-ttu-id="b0f17-306">**LOCATIONService_LOCATION_x5d.xsd** を右クリックし、 **[インスタンスの生成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-306">Right-click **LOCATIONService_LOCATION_x5d.xsd** and then click **Generate Instance**.</span></span> <span data-ttu-id="b0f17-307">**SampleQuery.xml** ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-307">This generates the **SampleQuery.xml** file.</span></span> <span data-ttu-id="b0f17-308">このファイルは、オーケストレーション プロセスを開始するアダプターに対する入力として、受信場所にドロップされます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-308">This file will be dropped in the receive location as input to the adapter to start the orchestration process.</span></span>  
  
     <span data-ttu-id="b0f17-309">![](../core/media/ef65a96c-2daa-44db-ab95-d18b1fda934e.gif "ef65a96c-2daa-44db-ab95-d18b1fda934e")</span><span class="sxs-lookup"><span data-stu-id="b0f17-309">![](../core/media/ef65a96c-2daa-44db-ab95-d18b1fda934e.gif "ef65a96c-2daa-44db-ab95-d18b1fda934e")</span></span>  
  
#### <a name="configure-and-start-the-biztalk-application"></a><span data-ttu-id="b0f17-310">構成および BizTalk アプリケーションの開始</span><span class="sxs-lookup"><span data-stu-id="b0f17-310">Configure and start the BizTalk application</span></span>  
  
1.  <span data-ttu-id="b0f17-311">入力ファイルの受信と送出ファイルの送信のフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-311">Configure folders for receiving the incoming files and sending the outgoing files.</span></span> <span data-ttu-id="b0f17-312">**C:\LABS\PS_TEST** を開き、 `FileIn` メッセージと `FileOut`用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-312">Go to **C:\LABS\PS_TEST** and create two new subfolders named `FileIn` and `FileOut`.</span></span>  
  
2.  <span data-ttu-id="b0f17-313">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[**コンソール ルート**、展開**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**、展開**BizTalk グループ**、展開**アプリケーション**を右クリックして**PS_Test** ] をクリックし、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-313">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Console Root**, expand **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, expand **BizTalk Group**, expand **Applications**, right-click **PS_Test** and then click **Configure**.</span></span>  
  
     <span data-ttu-id="b0f17-314">![](../core/media/e45f4c8b-fc8a-492a-9824-5232eb728d95.gif "e45f4c8b-fc8a-492a-9824-5232eb728d95")</span><span class="sxs-lookup"><span data-stu-id="b0f17-314">![](../core/media/e45f4c8b-fc8a-492a-9824-5232eb728d95.gif "e45f4c8b-fc8a-492a-9824-5232eb728d95")</span></span>  
  
3.  <span data-ttu-id="b0f17-315">**[Orchestration_1]** を選択し、 **[ホスト]** ドロップダウン ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-315">Select **Orchestration_1** and click the **Host** drop-down box.</span></span> <span data-ttu-id="b0f17-316">**[BizTalkServerApplication]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-316">Select **BizTalkServerApplication**.</span></span>  
  
4.  <span data-ttu-id="b0f17-317">**受信ポート**をクリックして **\<None\>** です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-317">Under **Receive Ports**, click **\<None\>**.</span></span> <span data-ttu-id="b0f17-318">ドロップダウン リストの **[新しい受信ポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-318">In the drop-down list, select **New Receive Port**.</span></span>  
  
5.  <span data-ttu-id="b0f17-319">For **FileIn**に「 `FileInPort`の順にポイントし、 **[OK]** 用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-319">For **Name**, type `FileInPort`, and then click **OK**.</span></span> <span data-ttu-id="b0f17-320">受信場所を指定する必要があるというメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-320">A message box appears stating that you need to designate a receive location.</span></span> <span data-ttu-id="b0f17-321">**[OK]** をクリックし、 **[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-321">Click **OK**, and then click **New**.</span></span>  
  
     <span data-ttu-id="b0f17-322">![](../core/media/298638b6-0eb8-49c4-8a2e-485571d070cf.gif "298638b6-0eb8-49c4-8a2e-485571d070cf")</span><span class="sxs-lookup"><span data-stu-id="b0f17-322">![](../core/media/298638b6-0eb8-49c4-8a2e-485571d070cf.gif "298638b6-0eb8-49c4-8a2e-485571d070cf")</span></span>  
  
6.  <span data-ttu-id="b0f17-323">プロパティに次の値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-323">Type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="b0f17-324">**名前**: `FileInLoc`</span><span class="sxs-lookup"><span data-stu-id="b0f17-324">**Name**: `FileInLoc`</span></span>  
  
     <span data-ttu-id="b0f17-325">**種類**: **ファイル**</span><span class="sxs-lookup"><span data-stu-id="b0f17-325">**Type**: **File**</span></span>  
  
     <span data-ttu-id="b0f17-326">**受信ハンドラー**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="b0f17-326">**Receive Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="b0f17-327">**受信パイプライン**: **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="b0f17-327">**Receive Pipeline**: **XMLReceive**</span></span>  
  
     <span data-ttu-id="b0f17-328">![](../core/media/613a5dbc-effe-4827-a72b-d16eef8d0e8a.gif "613a5dbc-effe-4827-a72b-d16eef8d0e8a")</span><span class="sxs-lookup"><span data-stu-id="b0f17-328">![](../core/media/613a5dbc-effe-4827-a72b-d16eef8d0e8a.gif "613a5dbc-effe-4827-a72b-d16eef8d0e8a")</span></span>  
  
7.  <span data-ttu-id="b0f17-329">**[構成]** をクリックし、 `C:\LABS\PS_TEST\FILEIN` に「 **C:\LABS\PS_TEST\FILEIN**の順にポイントし、 **[OK]** を 3 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-329">Click **Configure** and type `C:\LABS\PS_TEST\FILEIN` for **Receive Folder**, and then click **OK** three times.</span></span>  
  
     <span data-ttu-id="b0f17-330">![](../core/media/513eebb0-58ca-4aaa-a33b-31700f9cf7a8.gif "513eebb0-58ca-4aaa-a33b-31700f9cf7a8")</span><span class="sxs-lookup"><span data-stu-id="b0f17-330">![](../core/media/513eebb0-58ca-4aaa-a33b-31700f9cf7a8.gif "513eebb0-58ca-4aaa-a33b-31700f9cf7a8")</span></span>  
  
8.  <span data-ttu-id="b0f17-331">をクリックして**\<None\>** の**PeopleSoft_Port**ドロップダウン リストでします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-331">Click **\<None\>** for **PeopleSoft_Port** in the drop-down list.</span></span>  
  
9. <span data-ttu-id="b0f17-332">**[新しい送信ポート]** を選択し、プロパティに次の値を選択または入力します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-332">Select **New Send Port** and then select or type the following values for the properties.</span></span>  
  
     <span data-ttu-id="b0f17-333">**名前**: `PS_Test_Port`</span><span class="sxs-lookup"><span data-stu-id="b0f17-333">**Name**: `PS_Test_Port`</span></span>  
  
     <span data-ttu-id="b0f17-334">**種類**: **PeopleSoft**</span><span class="sxs-lookup"><span data-stu-id="b0f17-334">**Type**: **PeopleSoft**</span></span>  
  
     <span data-ttu-id="b0f17-335">**[送信ハンドラー]**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="b0f17-335">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="b0f17-336">**[パイプライン]**: **XMLTransmit** および **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="b0f17-336">**Pipelines**: **XMLTransmit** and **XMLReceive**</span></span>  
  
10. <span data-ttu-id="b0f17-337">**[構成]** をクリックし、次のプロパティ値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-337">Click **Configure**, and then enter the following property values:</span></span>  
  
    1.  <span data-ttu-id="b0f17-338">**[アプリケーション サーバーのパス]**: **//Servername:9000**</span><span class="sxs-lookup"><span data-stu-id="b0f17-338">**Application server path**: **//Servername:9000**</span></span>  
  
         <span data-ttu-id="b0f17-339">Servername には、使用しているアプリケーション サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-339">Servername is your application server.</span></span> <span data-ttu-id="b0f17-340">これは、この PeopleSoft システムの固有のサーバー名または IP アドレスとポート番号です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-340">This is the specific server name or IP address and port number for this PeopleSoft system.</span></span>  
  
    2.  <span data-ttu-id="b0f17-341">**[JAVA_HOME]**: **C:\J2SDK1.4.2_08**</span><span class="sxs-lookup"><span data-stu-id="b0f17-341">**JAVA_HOME**: **C:\J2SDK1.4.2_08**</span></span>  
  
         <span data-ttu-id="b0f17-342">このパスは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の Java SDK インストールに固有のパスです。</span><span class="sxs-lookup"><span data-stu-id="b0f17-342">This path is specific to the Java SDK installation on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    3.  <span data-ttu-id="b0f17-343">**パスワード**: \<PeopleSoft パスワードを入力してください\></span><span class="sxs-lookup"><span data-stu-id="b0f17-343">**Password**: \<enter your PeopleSoft password\></span></span>  
  
    4.  <span data-ttu-id="b0f17-344">**[PeopleSoft 8.x JAR ファイル]**: **C:\PSJARS\VER841\PSJOA.JAR**</span><span class="sxs-lookup"><span data-stu-id="b0f17-344">**PeopleSoft 8.x JAR files**: **C:\PSJARS\VER841\PSJOA.JAR**</span></span>  
  
     <span data-ttu-id="b0f17-345">**ユーザー名:** \<PeopleSoft UserID を入力してください\></span><span class="sxs-lookup"><span data-stu-id="b0f17-345">**User name:** \<enter your PeopleSoft UserID\></span></span>  
  
11. <span data-ttu-id="b0f17-346">**[OK]** を 2 回クリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-346">Click **OK** twice to close the dialog boxes.</span></span>  
  
12. <span data-ttu-id="b0f17-347">構成 Applicationwindow、クリックして**\<None\>** の**FileOut**ドロップダウン リストでします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-347">In the Configure Applicationwindow, click **\<None\>** for **FileOut** in the drop-down list.</span></span>  
  
13. <span data-ttu-id="b0f17-348">**[新しい送信ポート]** を選択し、プロパティの値を次のとおりに入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-348">Select **New Send Port** and type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="b0f17-349">**名前**: `FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="b0f17-349">**Name**: `FileOutPort`</span></span>  
  
     <span data-ttu-id="b0f17-350">**種類**: **ファイル**</span><span class="sxs-lookup"><span data-stu-id="b0f17-350">**Type**: **File**</span></span>  
  
     <span data-ttu-id="b0f17-351">**[送信ハンドラー]**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="b0f17-351">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="b0f17-352">**送信パイプライン**: **XMLTransmit**</span><span class="sxs-lookup"><span data-stu-id="b0f17-352">**Send Pipeline**: **XMLTransmit**</span></span>  
  
14. <span data-ttu-id="b0f17-353">**[構成]** をクリックし、`C:\Labs\PS_Test\FileOut` に「 **C:\Labs\PS_Test\FileOut**</span><span class="sxs-lookup"><span data-stu-id="b0f17-353">Click **Configure** and type`C:\Labs\PS_Test\FileOut` for **Destination Folder.**</span></span> <span data-ttu-id="b0f17-354">」と入力します。 **[ファイル名]** に「 **%MessageID%.xml** because this results in a unique file に「 each message.</span><span class="sxs-lookup"><span data-stu-id="b0f17-354">Keep **%MessageID%.xml** for **File Name** because this results in a unique file for each message.</span></span>  
  
15. <span data-ttu-id="b0f17-355">**[OK]** を 3 回クリックして、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-355">Click **OK** three times to close the dialog boxes.</span></span>  
  
16. <span data-ttu-id="b0f17-356">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして、 **PS_Test**アプリケーションをクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-356">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,right-click the **PS_Test** application and then click **Start**.</span></span>  
  
     <span data-ttu-id="b0f17-357">![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")</span><span class="sxs-lookup"><span data-stu-id="b0f17-357">![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")</span></span>  
  
#### <a name="test-the-orchestration"></a><span data-ttu-id="b0f17-358">オーケストレーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-358">Test the orchestration</span></span>  
  
1.  <span data-ttu-id="b0f17-359">**C:\Labs\PS_Test** ディレクトリの **Samplequery.xml** ファイルを次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-359">In the **C:\Labs\PS_Test** directory, change the **Samplequery.xml** file to the following:</span></span>  
  
    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
      <ns0:SETID>SHARE</ns0:SETID>  
      <ns0:LOCATION>AUS01</ns0:LOCATION>  
      <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b0f17-360">**SHARE** データ値はすべてのシステムで使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-360">The **SHARE** data value will be used on all systems.</span></span> <span data-ttu-id="b0f17-361">ただし、この XML ファイルの **Location** に使用される値は、実際のシステムに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-361">However the value you will use for **Location** in this XML file must exist on your system.</span></span> <span data-ttu-id="b0f17-362">これはラボ 1 で確認しました。</span><span class="sxs-lookup"><span data-stu-id="b0f17-362">You found this out in Lab 1.</span></span>  
  
2.  <span data-ttu-id="b0f17-363">変更内容を保存し、ファイルを **C:\Labs\PS_Test\FileIn** フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b0f17-363">Save the changes and copy the file to the **C:\Labs\PS_Test\FileIn** folder.</span></span> <span data-ttu-id="b0f17-364">これは、オーケストレーション プロセスが開始される FileIn の受信場所です。</span><span class="sxs-lookup"><span data-stu-id="b0f17-364">This is the receive location for FileIn that starts the orchestration process.</span></span>  
  
3.  <span data-ttu-id="b0f17-365">数秒後に、XML ファイルが **C:\Labs\PS_Test\FileOut** フォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-365">In a few seconds, an XML file should appear in the **C:\Labs\PS_Test\FileOut** folder.</span></span> <span data-ttu-id="b0f17-366">このファイルには、場所が AUS01 であるレコードのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b0f17-366">This should contain the data from the record where the location is AUS01.</span></span>  
  
     <span data-ttu-id="b0f17-367">![](../core/media/1320ea3c-b2bc-4717-b200-c3c550079ccb.gif "1320ea3c-b2bc-4717-b200-c3c550079ccb")</span><span class="sxs-lookup"><span data-stu-id="b0f17-367">![](../core/media/1320ea3c-b2bc-4717-b200-c3c550079ccb.gif "1320ea3c-b2bc-4717-b200-c3c550079ccb")</span></span>  
  
     <span data-ttu-id="b0f17-368">この返されたレコード データは、PeopleSoft ラボ 1 での PeopleSoft システムに対するクエリで返された内容と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f17-368">This returned record data should match what was returned by the query against the PeopleSoft system in PeopleSoft Lab 1.</span></span> <span data-ttu-id="b0f17-369">値を比較して、ラボ 1 で取得、具体的には、 **Address1**と**住所 2**線にはここで示した、 **\<場所: ADDRESS1\>** と**\<場所: 住所 2\>** フィールド、ことを確認することができます、**取得**メソッドが正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="b0f17-369">By comparing the values you obtained in Lab 1, specifically the **Address1** and **Address2** lines, to what is shown here in the **\<LOCATION:ADDRESS1\>** and **\<LOCATION:ADDRESS2\>** fields, you can verify that the **Get** method worked properly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="b0f17-370">概要</span><span class="sxs-lookup"><span data-stu-id="b0f17-370">Summary</span></span>  
 <span data-ttu-id="b0f17-371">このラボでは、PeopleSoft システムにアクセスするための前提条件が適切にセットアップされていることを最初に確認しました。</span><span class="sxs-lookup"><span data-stu-id="b0f17-371">In this lab, you first verified that the prerequisites were set up correctly to access the PeopleSoft system.</span></span> <span data-ttu-id="b0f17-372">次に、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、オーケストレーションが含まれる新しい BizTalk プロジェクトを作成しました。</span><span class="sxs-lookup"><span data-stu-id="b0f17-372">Then you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project containing an orchestration.</span></span> <span data-ttu-id="b0f17-373">また、BizTalk オーケストレーションを構成し、PeopleSoft アダプターを使用して PeopleSoft システムのデータを取得しました。</span><span class="sxs-lookup"><span data-stu-id="b0f17-373">You configured the BizTalk orchestration to use the PeopleSoft adapter to get data from the PeopleSoft system.</span></span> <span data-ttu-id="b0f17-374">オーケストレーションを構成するために、送信ポート、受信ポート、および送信/受信ポートを作成しました。</span><span class="sxs-lookup"><span data-stu-id="b0f17-374">To configure the orchestration, you created send, receive, and send/receive ports.</span></span> <span data-ttu-id="b0f17-375">これらのポートを PeopleSoft アダプターにバインドし、メッセージを適切なポートに割り当てました。</span><span class="sxs-lookup"><span data-stu-id="b0f17-375">You bound these ports to the PeopleSoft adapter, and assigned messages to the appropriate ports.</span></span>  
  
 <span data-ttu-id="b0f17-376">BizTalk プロジェクトの作成後、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してプロジェクトをビルドして展開しました。</span><span class="sxs-lookup"><span data-stu-id="b0f17-376">After you completed the BizTalk project, you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build and deploy it.</span></span> <span data-ttu-id="b0f17-377">次に、新しいアプリケーションを構成し、実行して PeopleSoft システムのデータを取得しました。</span><span class="sxs-lookup"><span data-stu-id="b0f17-377">You then configured your new application and ran it to get data from the PeopleSoft system.</span></span> <span data-ttu-id="b0f17-378">アプリケーションが適切に動作していることを確認するために、出力 XML ファイルを、ラボ 1 で PeopleSoft システムから受信したファイルと比較しました。</span><span class="sxs-lookup"><span data-stu-id="b0f17-378">To verify that the application worked correctly, you compared its output XML file to the file that you received from the PeopleSoft system in Lab 1.</span></span>