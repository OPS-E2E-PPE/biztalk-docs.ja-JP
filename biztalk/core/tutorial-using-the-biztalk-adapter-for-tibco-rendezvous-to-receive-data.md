---
title: 'チュートリアル: では、TIBCO Rendezvous アダプターを使用して、受信 |Microsoft ドキュメント'
description: BizTalk Server で TIBCO Rendezvous の BizTalk アダプタを使用して TIBCO システムからデータを受信するステップ バイ ステップ ガイド
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58e7a739-701d-4085-a840-54f81c55e943
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75aaba0cc2e455676e78381c04934dda30741a85
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015441"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a><span data-ttu-id="e2d3d-103">チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用したデータの受信</span><span class="sxs-lookup"><span data-stu-id="e2d3d-103">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Receive Data</span></span>
<span data-ttu-id="e2d3d-104">BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システムからデータを受信できます。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-104">You can use the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="e2d3d-105">このチュートリアルでは、これを示す SDK サンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-105">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e2d3d-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="e2d3d-106">Prerequisites</span></span>  
  
<span data-ttu-id="e2d3d-107">このサンプルをビルドして展開するには、アダプターが実行されている [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-107">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
## <a name="about-the-sample"></a><span data-ttu-id="e2d3d-108">サンプルについて</span><span class="sxs-lookup"><span data-stu-id="e2d3d-108">About the sample</span></span> 
- <span data-ttu-id="e2d3d-109">このサンプルでは、BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システムからデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-109">This sample uses the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="e2d3d-110">オーケストレーションがメッセージを処理し、ファイル アダプターを使用して、指定されたフォルダーにデータを XML ファイルとして書き込みます。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-110">An orchestration processes the message and, using the file adapter, writes the data as an XML file in a specified folder.</span></span>  
  
- <span data-ttu-id="e2d3d-111">このサンプルは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデザインされ、BizTalk Adapter for TIBCO Enterprise Message Service を BizTalk オーケストレーションと組み合わせて使用する基本的な機能を紹介する目的で作成されました。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-111">This sample, designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2d3d-112">このサンプルでは、処理するアプリケーション用の TIBCO からメッセージを送信する方法を理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-112">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  
  
- <span data-ttu-id="e2d3d-113">サンプルの既定の場所は`C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`、次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-113">The default location for the sample is `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`, and includes the following files:</span></span> 
  
    |<span data-ttu-id="e2d3d-114">**ランタイム プロジェクト ファイル名**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-114">**Runtime Project Filename**</span></span>|<span data-ttu-id="e2d3d-115">**ランタイム プロジェクト ファイルの説明**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-115">**Runtime Project File Description**</span></span>|  
    |---|---|  
    |<span data-ttu-id="e2d3d-116">OneWayReceive.btproj、</span><span class="sxs-lookup"><span data-stu-id="e2d3d-116">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="e2d3d-117">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="e2d3d-117">OneWayReceive.sln</span></span>|<span data-ttu-id="e2d3d-118">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-118">Project and solution files for the application.</span></span>|  
    |<span data-ttu-id="e2d3d-119">PureMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="e2d3d-119">PureMessage.xsd,</span></span>|<span data-ttu-id="e2d3d-120">アプリケーションのスキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-120">Schema file for the application.</span></span>|  
    |<span data-ttu-id="e2d3d-121">TIBCORvOWR.odx</span><span class="sxs-lookup"><span data-stu-id="e2d3d-121">TIBCORvOWR.odx</span></span>|<span data-ttu-id="e2d3d-122">アプリケーションが使用するオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-122">The orchestration used by the application.</span></span>|  
    |<span data-ttu-id="e2d3d-123">TIBCORv.snk</span><span class="sxs-lookup"><span data-stu-id="e2d3d-123">TIBCORv.snk</span></span>|<span data-ttu-id="e2d3d-124">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-124">The strong naming key file.</span></span>|  
  
  
## <a name="step-1-add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="e2d3d-125">手順 1: アダプターを BizTalk 管理コンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-125">Step 1: Add the adapter to BizTalk Administration</span></span>
  
1.  <span data-ttu-id="e2d3d-126">**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順にクリック**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-126">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="e2d3d-127">右クリック**アダプター**を指す**新規**、**アダプターしています.**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-127">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="e2d3d-128">表示する、**アダプター プロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-128">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="e2d3d-129">値を入力して、**名前**フィールド、たとえば**TIBCO Rendezvous**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-129">Enter a value for the **Name** field, for example **TIBCO Rendezvous**.</span></span>  
  
5.  <span data-ttu-id="e2d3d-130">選択**TIBCO(r) Rendezvous(r)** で利用可能なアダプターの一覧から、**アダプター**ドロップダウン リスト をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-130">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
## <a name="step-2-create-a-receive-port"></a><span data-ttu-id="e2d3d-131">手順 2: 作成、受信ポート</span><span class="sxs-lookup"><span data-stu-id="e2d3d-131">Step 2: Create a Receive Port</span></span>  
  
1.  <span data-ttu-id="e2d3d-132">**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-132">In  **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="e2d3d-133">受信ポート フォルダーを右クリックし、をクリックして**新規**、**一方向の受信ポートしています.** を表示する、**受信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-133">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the **Receive Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="e2d3d-134">値を入力、**名前**フィールド、たとえば**TIBCORvOneWayRP**、 をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-134">Enter a value for the **Name** field, for example **TIBCORvOneWayRP**, and click **OK**.</span></span>  
  
## <a name="step-3-create-a-receive-location"></a><span data-ttu-id="e2d3d-135">手順 3: 作成、受信場所</span><span class="sxs-lookup"><span data-stu-id="e2d3d-135">Step 3: Create a Receive Location</span></span>  
  
1.  <span data-ttu-id="e2d3d-136">右クリックし、新しい受信ポートをクリックし、**新規**、**受信場所の追加.**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-136">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="e2d3d-137">表示する、**受信場所のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-137">to display the **Receive Location Properties** dialog.</span></span>  
  
2.  <span data-ttu-id="e2d3d-138">値を入力して、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-138">Enter a value for the **Name** field.</span></span> <span data-ttu-id="e2d3d-139">たとえば、入力**TIBCORvOneWayRL**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-139">For example, enter **TIBCORvOneWayRL**.</span></span>  
  
3.  <span data-ttu-id="e2d3d-140">使用可能なアダプターの一覧から TIBCO Rendezvous アダプターを選択して、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-140">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2d3d-141">この値は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで TIBCO アダプターを作成したときに指定した名前です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-141">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="e2d3d-142">値を入力して、 **RendezvousSubjectName**下にある、 **AdapterRequiredProperties**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-142">Enter a value for the **RendezvousSubjectName** under the **AdapterRequiredProperties**.</span></span>  
  
5.  <span data-ttu-id="e2d3d-143">値を入力して、**証明されたリスナーのプロパティ**:</span><span class="sxs-lookup"><span data-stu-id="e2d3d-143">Enter values for the **Certified Listener Properties**:</span></span>  
  
    |<span data-ttu-id="e2d3d-144">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-144">**Property**</span></span>|<span data-ttu-id="e2d3d-145">**値**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-145">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="e2d3d-146">台帳ファイル名</span><span class="sxs-lookup"><span data-stu-id="e2d3d-146">Ledger file name</span></span>|<span data-ttu-id="e2d3d-147">永続的な認証されたメッセージ配信に使用する台帳ファイル名。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-147">Ledger file name to use for persistent certified message delivery.</span></span>|  
    |<span data-ttu-id="e2d3d-148">再利用可能な名前</span><span class="sxs-lookup"><span data-stu-id="e2d3d-148">Reusable name</span></span>|<span data-ttu-id="e2d3d-149">認証されたメッセージ配信に使用する再利用可能な送信者名です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-149">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="e2d3d-150">この名前は、ネットワーク上のすべての認証されたメッセージの送信者名の中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-150">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
6.  <span data-ttu-id="e2d3d-151">値を入力して、**資格情報**:</span><span class="sxs-lookup"><span data-stu-id="e2d3d-151">Enter values for the **Credentials**:</span></span>  
  
    |<span data-ttu-id="e2d3d-152">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-152">**Property**</span></span>|<span data-ttu-id="e2d3d-153">**値**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-153">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="e2d3d-154">Password</span><span class="sxs-lookup"><span data-stu-id="e2d3d-154">Password</span></span>|<span data-ttu-id="e2d3d-155">TIBCO Rendezvous サーバーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-155">The password for the TIBCO Rendezvous server.</span></span>|  
    |<span data-ttu-id="e2d3d-156">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="e2d3d-156">User name</span></span>|<span data-ttu-id="e2d3d-157">TIBCO Rendezvous サーバーのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-157">The user name for the TIBCO Rendezvous server.</span></span>|  
  
7.  <span data-ttu-id="e2d3d-158">値を入力して、 **RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="e2d3d-158">Enter values for the **RendezvousTransport**:</span></span>  
  
    |<span data-ttu-id="e2d3d-159">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-159">**Property**</span></span>|<span data-ttu-id="e2d3d-160">**値**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-160">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="e2d3d-161">デーモン</span><span class="sxs-lookup"><span data-stu-id="e2d3d-161">Daemon</span></span>|<span data-ttu-id="e2d3d-162">Rendezvous トランスポート デーモン パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-162">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="e2d3d-163">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="e2d3d-163">Network</span></span>|<span data-ttu-id="e2d3d-164">Rendezvous トランスポート ネットワーク パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-164">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="e2d3d-165">サービス</span><span class="sxs-lookup"><span data-stu-id="e2d3d-165">Service</span></span>|<span data-ttu-id="e2d3d-166">Rendezvous トランスポート サービス パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-166">Rendezvous Transport Service parameter.</span></span>|  
  
     <span data-ttu-id="e2d3d-167">プロパティの詳細については、次を参照してください。[受信作成の成果物](../core/creating-tibco-rendezvous-receive-handlers.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-167">For more information about the properties, see [Create Receive artifacts](../core/creating-tibco-rendezvous-receive-handlers.md).</span></span>  
  
8.  <span data-ttu-id="e2d3d-168">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-168">Click **OK**.</span></span>  
  
9. <span data-ttu-id="e2d3d-169">選択 **[xmlreceive]** で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン リスト ボックスし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-169">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
10. <span data-ttu-id="e2d3d-170">受信場所を右クリックし、をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-170">Right-click the receive location and click **Enable**.</span></span>  
  
## <a name="step-4-create-a-one-way-send-port"></a><span data-ttu-id="e2d3d-171">手順 4: 一方向の送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-171">Step 4: Create a one-way send port</span></span>  
  
1.  <span data-ttu-id="e2d3d-172">送信ポートが使用する送信先フォルダー (たとえば、C:\FilesOut) を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-172">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  
  
2.  <span data-ttu-id="e2d3d-173">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-173">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="e2d3d-174">右クリック**送信ポート**を指す**新規**、**静的な一方向送信ポートしています.**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-174">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="e2d3d-175">表示する、**送信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-175">to display the **Send Port Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="e2d3d-176">値を入力して、**名前**フィールド、たとえば**TIBCORvOneWayFileSP**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-176">Enter a value for the **Name** field, for example **TIBCORvOneWayFileSP**.</span></span>  
  
5.  <span data-ttu-id="e2d3d-177">選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-177">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
6.  <span data-ttu-id="e2d3d-178">**コピー先フォルダー**プロパティ、先ほど作成したフォルダーの場所を入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-178">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  
  
7.  <span data-ttu-id="e2d3d-179">選択、 **xmltransmit**パイプラインで使用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン リスト をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-179">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
8.  <span data-ttu-id="e2d3d-180">送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-180">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
## <a name="step-5-build-and-deploy-the-project"></a><span data-ttu-id="e2d3d-181">手順 5: ビルドし、プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="e2d3d-181">Step 5: Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="e2d3d-182">ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-182">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="e2d3d-183">クリックして、**展開**タブです。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-183">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="e2d3d-184">適切な値を入力、**サーバー**プロパティおよび**構成データベース**プロパティの  **BizTalk グループ**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-184">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  
  
4.  <span data-ttu-id="e2d3d-185">ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**展開**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-185">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
## <a name="step-6-bind-enlist-and-start-the-orchestration"></a><span data-ttu-id="e2d3d-186">手順 6: バインド、参加、およびオーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="e2d3d-186">Step 6: Bind, Enlist, and start the orchestration</span></span>  
  
1.  <span data-ttu-id="e2d3d-187">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-187">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="e2d3d-188">をクリックして、**更新**ボタンをクリックして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール ツールバーまたはキーを押して、 **f5 キーを押して**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-188">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="e2d3d-189">表示するオーケストレーションをダブルクリック、**オーケストレーションのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-189">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="e2d3d-190">をクリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左ペインでします。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-190">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="e2d3d-191">バインド オプションに適切な値を指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-191">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="e2d3d-192">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-192">**Parameter**</span></span>|<span data-ttu-id="e2d3d-193">**値**</span><span class="sxs-lookup"><span data-stu-id="e2d3d-193">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="e2d3d-194">Host</span><span class="sxs-lookup"><span data-stu-id="e2d3d-194">Host</span></span>|<span data-ttu-id="e2d3d-195">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="e2d3d-195">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="e2d3d-196">SendPort</span><span class="sxs-lookup"><span data-stu-id="e2d3d-196">SendPort</span></span>|<span data-ttu-id="e2d3d-197">TIBCORvOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="e2d3d-197">TIBCORvOneWayFileSP</span></span>|  
    |<span data-ttu-id="e2d3d-198">ReceivePort</span><span class="sxs-lookup"><span data-stu-id="e2d3d-198">ReceivePort</span></span>|<span data-ttu-id="e2d3d-199">TIBCORvOneWayRP</span><span class="sxs-lookup"><span data-stu-id="e2d3d-199">TIBCORvOneWayRP</span></span>|  
  
6.  <span data-ttu-id="e2d3d-200">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-200">Click **OK**.</span></span>  
  
7. <span data-ttu-id="e2d3d-201">オーケストレーションを右クリックし、をクリックして**開始**を参加させて、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-201">Right-click the orchestration, and click **Start** to enlist and start the orchestration.</span></span>  
  
## <a name="step-7-confirm-the-application-receives-a-message"></a><span data-ttu-id="e2d3d-202">手順 7: アプリケーションがメッセージを受信を確認します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-202">Step 7: Confirm the application receives a message</span></span>  
  
-   <span data-ttu-id="e2d3d-203">File 送信ポートに送信し、出力ドキュメントが生成されたことを確認してください。 構成されているフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-203">Open the folder that the file send port is configured to send to, and verify that an output document was generated.</span></span>  
  
 <span data-ttu-id="e2d3d-204">ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-204">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="e2d3d-205">TIBCO Rendezvous アダプターが TIBCO システムからメッセージを取得し、BizTalk メッセージとしてメッセージ ボックスに公開します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-205">The TIBCO Rendezvous adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="e2d3d-206">オーケストレーションがこの公開されたメッセージをサブスクライブします。これにより、BizTalk メッセージング エンジンがオーケストレーションのインスタンスをアクティブ化し、オーケストレーション インスタンスにメッセージを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-206">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="e2d3d-207">オーケストレーション インスタンスがメッセージ ボックスにメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-207">The orchestration instance publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="e2d3d-208">ファイル送信ポートがこのメッセージをサブスクライブし、BizTalk がメッセージをファイル アダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-208">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  
  
5.  <span data-ttu-id="e2d3d-209">ファイル アダプターが、結果セットを含むメッセージを指定の出力フォルダーに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="e2d3d-209">The File adapter writes the message containing the result set to the designated output folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d3d-210">参照</span><span class="sxs-lookup"><span data-stu-id="e2d3d-210">See Also</span></span>  
 <span data-ttu-id="e2d3d-211">[チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用してデータを送信するには](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="e2d3d-211">[Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span></span>  
 <span data-ttu-id="e2d3d-212">[チュートリアル: Microsoft BizTalk Adapter を使用して TIBCO Rendezvous の](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="e2d3d-212">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="e2d3d-213">作業の開始</span><span class="sxs-lookup"><span data-stu-id="e2d3d-213">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)