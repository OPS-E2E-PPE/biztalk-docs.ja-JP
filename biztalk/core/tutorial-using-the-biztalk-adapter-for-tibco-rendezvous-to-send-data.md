---
title: 'チュートリアル: TIBCO Rendezvous アダプターを使用して送信する |Microsoft Docs'
description: BizTalk Server で TIBCO Rendezvous の BizTalk アダプターを使用して、TIBCO システムにデータを送信するステップ バイ ステップ ガイド
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b761ce2d-3465-43e0-bd8d-4d68b523226a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef842eacf261904173b90728ba2702513973cf53
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966939"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data"></a><span data-ttu-id="15fb3-103">チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用したデータの送信</span><span class="sxs-lookup"><span data-stu-id="15fb3-103">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data</span></span>
<span data-ttu-id="15fb3-104">BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システムにデータを送信できます。</span><span class="sxs-lookup"><span data-stu-id="15fb3-104">You can use the BizTalk Adapter for TIBCO Rendezvous to send data to a TIBCO system.</span></span> <span data-ttu-id="15fb3-105">このチュートリアルでは、これを示す SDK サンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-105">This walkthrough describes an SDK sample that illustrates this.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="15fb3-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="15fb3-106">Prerequisites</span></span>  

- <span data-ttu-id="15fb3-107">このサンプルをビルドして展開するには、アダプターが実行されている [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="15fb3-107">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  

- <span data-ttu-id="15fb3-108">サンプルでは、メッセージ コンテキストのプロパティを含んでいる Microsoft.BizTalk.Adapters.TibRV.Properties.dll という DLL を使用します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-108">The sample uses a DLL containing message context properties: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span> <span data-ttu-id="15fb3-109">ソリューションからこのライブラリへの参照を更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="15fb3-109">You may need to update the solution's reference to this library.</span></span> <span data-ttu-id="15fb3-110">詳細については、[BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)](../core/biztalk-server-message-context-properties-send-handlers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15fb3-110">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md).</span></span>  

## <a name="about-the-sample"></a><span data-ttu-id="15fb3-111">サンプルについて</span><span class="sxs-lookup"><span data-stu-id="15fb3-111">About the sample</span></span> 

- <span data-ttu-id="15fb3-112">このサンプルでは、ファイル フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システム内にレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-112">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Rendezvous to create a record in the TIBCO system.</span></span>  

- <span data-ttu-id="15fb3-113">このサンプルは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデザインされたもので、BizTalk Adapter for TIBCO Rendezvous を BizTalk オーケストレーションと共に使用する場合の基本的な機能を示します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-113">This sample, designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Rendezvous with a BizTalk orchestration.</span></span>  

- <span data-ttu-id="15fb3-114">サンプルの既定の場所は`C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`、次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="15fb3-114">The default location for the sample is `C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`, and includes the following files:</span></span> 

    |<span data-ttu-id="15fb3-115">**ランタイム プロジェクト ファイル名**</span><span class="sxs-lookup"><span data-stu-id="15fb3-115">**Runtime Project Filename**</span></span>|<span data-ttu-id="15fb3-116">**ランタイム プロジェクト ファイルの説明**</span><span class="sxs-lookup"><span data-stu-id="15fb3-116">**Runtime Project File Description**</span></span>|  
    |---|---|  
    |<span data-ttu-id="15fb3-117">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="15fb3-117">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="15fb3-118">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="15fb3-118">OneWaySend.sln</span></span>|<span data-ttu-id="15fb3-119">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="15fb3-119">Project and solution files for the application.</span></span>|  
    |<span data-ttu-id="15fb3-120">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="15fb3-120">Schema.xsd</span></span><br /><br /> <span data-ttu-id="15fb3-121">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="15fb3-121">PropertySchema.xsd</span></span>|<span data-ttu-id="15fb3-122">アプリケーションのスキーマおよびプロパティ スキーマ ファイル。</span><span class="sxs-lookup"><span data-stu-id="15fb3-122">Schema and property schema files for the application.</span></span>|  
    |<span data-ttu-id="15fb3-123">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="15fb3-123">Orchestration.odx</span></span>|<span data-ttu-id="15fb3-124">アプリケーションが使用するオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="15fb3-124">The orchestration used by the application.</span></span>|  
    |<span data-ttu-id="15fb3-125">TIBCORendezvousOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="15fb3-125">TIBCORendezvousOneWaySend.snk</span></span>|<span data-ttu-id="15fb3-126">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="15fb3-126">The strong naming key file.</span></span>|  

## <a name="step-1-add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="15fb3-127">手順 1: アダプターを BizTalk 管理コンソールを追加します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-127">Step 1: Add the adapter to BizTalk Administration</span></span>

1.  <span data-ttu-id="15fb3-128">**BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、 をクリックし、**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-128">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3.  <span data-ttu-id="15fb3-129">右クリックして**アダプター**  をポイント**新規**、**アダプター.**</span><span class="sxs-lookup"><span data-stu-id="15fb3-129">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="15fb3-130">表示する、**アダプター プロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="15fb3-130">to display the **Adapter Properties** dialog.</span></span>  

4.  <span data-ttu-id="15fb3-131">値を入力、**名前**フィールド。</span><span class="sxs-lookup"><span data-stu-id="15fb3-131">Enter a value for the **Name** field.</span></span> <span data-ttu-id="15fb3-132">たとえば、入力**TIBCO Rendezvous**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-132">For example, enter **TIBCO Rendezvous**.</span></span>  

5.  <span data-ttu-id="15fb3-133">選択**TIBCO(r) Rendezvous(r)** で利用可能なアダプターの一覧から、**アダプター**ドロップダウンをクリック **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="15fb3-133">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

## <a name="step-2-create-a-send-port"></a><span data-ttu-id="15fb3-134">手順 2: 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-134">Step 2: Create a Send Port</span></span>  

1. <span data-ttu-id="15fb3-135">**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-135">In  **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="15fb3-136">右クリックして**送信ポート** をポイント**新規**、**静的な一方向送信ポートしています.**</span><span class="sxs-lookup"><span data-stu-id="15fb3-136">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="15fb3-137">表示する、**送信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="15fb3-137">to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="15fb3-138">値を入力、**名前**フィールドに、たとえば**TIBCORndOneWaySP**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-138">Enter a value for the **Name** field, for example **TIBCORndOneWaySP**.</span></span>  

4. <span data-ttu-id="15fb3-139">使用可能なアダプターの一覧から TIBCO Rendezvous アダプターを選択、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="15fb3-139">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="15fb3-140">この値は、TIBCO Enterprise Message System アダプターで作成されたときに指定された名前、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="15fb3-140">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

5. <span data-ttu-id="15fb3-141">値を入力、**証明された送信者プロパティ**:</span><span class="sxs-lookup"><span data-stu-id="15fb3-141">Enter values for the **Certified Sender Properties**:</span></span>  


   |   <span data-ttu-id="15fb3-142">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="15fb3-142">**Property**</span></span>   |                                                                         <span data-ttu-id="15fb3-143">**[値]**</span><span class="sxs-lookup"><span data-stu-id="15fb3-143">**Value**</span></span>                                                                          |
   |------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="15fb3-144">台帳ファイル名</span><span class="sxs-lookup"><span data-stu-id="15fb3-144">Ledger file name</span></span> |                                             <span data-ttu-id="15fb3-145">永続的な認証されたメッセージ配信に使用する台帳ファイル名。</span><span class="sxs-lookup"><span data-stu-id="15fb3-145">Ledger file name to use for persistent certified message delivery.</span></span>                                             |
   |  <span data-ttu-id="15fb3-146">再利用可能な名前</span><span class="sxs-lookup"><span data-stu-id="15fb3-146">Reusable name</span></span>   | <span data-ttu-id="15fb3-147">認証されたメッセージ配信に使用する再利用可能な送信者名です。</span><span class="sxs-lookup"><span data-stu-id="15fb3-147">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="15fb3-148">この名前は、ネットワーク上のすべての認証されたメッセージの送信者名の中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="15fb3-148">The name must be unique among all certified message correspondent names on the network.</span></span> |


6. <span data-ttu-id="15fb3-149">値を入力、**資格情報**:</span><span class="sxs-lookup"><span data-stu-id="15fb3-149">Enter values for the **Credentials**:</span></span>  


   | <span data-ttu-id="15fb3-150">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="15fb3-150">**Property**</span></span> |                   <span data-ttu-id="15fb3-151">**[値]**</span><span class="sxs-lookup"><span data-stu-id="15fb3-151">**Value**</span></span>                    |
   |--------------|------------------------------------------------|
   |   <span data-ttu-id="15fb3-152">パスワード</span><span class="sxs-lookup"><span data-stu-id="15fb3-152">Password</span></span>   | <span data-ttu-id="15fb3-153">TIBCO Rendezvous サーバーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="15fb3-153">The password for the TIBCO Rendezvous server.</span></span>  |
   |  <span data-ttu-id="15fb3-154">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="15fb3-154">User name</span></span>   | <span data-ttu-id="15fb3-155">TIBCO Rendezvous サーバーのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="15fb3-155">The user name for the TIBCO Rendezvous server.</span></span> |


7. <span data-ttu-id="15fb3-156">値を入力、 **RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="15fb3-156">Enter values for the **RendezvousTransport**:</span></span>  

   |<span data-ttu-id="15fb3-157">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="15fb3-157">**Property**</span></span>|<span data-ttu-id="15fb3-158">**[値]**</span><span class="sxs-lookup"><span data-stu-id="15fb3-158">**Value**</span></span>|  
   |------------------|---------------|  
   |<span data-ttu-id="15fb3-159">デーモン</span><span class="sxs-lookup"><span data-stu-id="15fb3-159">Daemon</span></span>|<span data-ttu-id="15fb3-160">Rendezvous トランスポート デーモン パラメーター。</span><span class="sxs-lookup"><span data-stu-id="15fb3-160">Rendezvous Transport Daemon parameter.</span></span>|  
   |<span data-ttu-id="15fb3-161">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="15fb3-161">Network</span></span>|<span data-ttu-id="15fb3-162">Rendezvous トランスポート ネットワーク パラメーター。</span><span class="sxs-lookup"><span data-stu-id="15fb3-162">Rendezvous Transport Network parameter.</span></span>|  
   |<span data-ttu-id="15fb3-163">サービス</span><span class="sxs-lookup"><span data-stu-id="15fb3-163">Service</span></span>|<span data-ttu-id="15fb3-164">Rendezvous トランスポート サービス パラメーター。</span><span class="sxs-lookup"><span data-stu-id="15fb3-164">Rendezvous Transport Service parameter.</span></span>|  

    <span data-ttu-id="15fb3-165">プロパティの詳細については、[送信アイテムの作成](../core/creating-tibco-rendezvous-send-handlers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15fb3-165">For more information about the properties, see [Create the send artifacts](../core/creating-tibco-rendezvous-send-handlers.md).</span></span>  

8. <span data-ttu-id="15fb3-166">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15fb3-166">Click **OK**.</span></span>  

9. <span data-ttu-id="15fb3-167">選択、 **XML Transmit**で利用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン をクリック**OK**。</span><span class="sxs-lookup"><span data-stu-id="15fb3-167">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

10. <span data-ttu-id="15fb3-168">送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-168">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

## <a name="step-3-create-a-receive-port"></a><span data-ttu-id="15fb3-169">手順 3: 受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-169">Step 3: Create a receive port</span></span>  

1.  <span data-ttu-id="15fb3-170">**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-170">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2.  <span data-ttu-id="15fb3-171">受信ポート フォルダーを右クリックし、をクリックし、**新規**、**一方向の受信ポート.** 受信ポートのプロパティ ダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-171">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the Receive Port Properties dialog.</span></span>  

3.  <span data-ttu-id="15fb3-172">値を入力、**名前**フィールドに**TIBCORndOneWayFileRP**、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-172">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRP**, and click **OK**.</span></span>  

## <a name="step-4-create-a-receive-location"></a><span data-ttu-id="15fb3-173">手順 4: 受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-173">Step 4: Create a receive location</span></span>  

1.  <span data-ttu-id="15fb3-174">監視対象のファイル受信場所となるフォルダー (たとえば C:\Filesource) を作成します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-174">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  

2.  <span data-ttu-id="15fb3-175">右クリックし、新しい受信ポート をクリックし、**新規**、**受信場所.**</span><span class="sxs-lookup"><span data-stu-id="15fb3-175">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="15fb3-176">表示する、**受信場所のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="15fb3-176">to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="15fb3-177">値を入力、**名前**フィールドに、たとえば**TIBCORndOneWayFileRL**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-177">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRL**.</span></span>  

4.  <span data-ttu-id="15fb3-178">選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="15fb3-178">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="15fb3-179">先ほど作成したフォルダーの場所を入力、**受信フォルダー**プロパティをクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-179">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="15fb3-180">選択**XMLReceive**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン ボックスし、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="15fb3-180">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="15fb3-181">受信場所を右クリックし、をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-181">Right-click the receive location and click **Enable**.</span></span>  

## <a name="step-5-generate-a-document-instance-from-the-schema"></a><span data-ttu-id="15fb3-182">手順 5: スキーマからドキュメント インスタンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-182">Step 5: Generate a document instance from the schema</span></span>  

1.  <span data-ttu-id="15fb3-183">Visual Studio で、ソリューション エクスプ ローラーで、Schema.xsd を右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-183">In Visual Studio,right-click Schema.xsd in Solution Explorer, and click **Properties**.</span></span>  

2.  <span data-ttu-id="15fb3-184">プロパティ ウィンドウでクリックして選択、**出力インスタンス ファイル名**オプションで 、**全般**セクション。</span><span class="sxs-lookup"><span data-stu-id="15fb3-184">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  

3.  <span data-ttu-id="15fb3-185">表示するには、省略記号ボタン (...) をクリックして、**出力ファイルの選択**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="15fb3-185">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

4.  <span data-ttu-id="15fb3-186">たとえば、フォルダーと出力ファイル インスタンスの名前を指定**C:\instance.xml**  をクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-186">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="15fb3-187">ファイル受信場所に指定したフォルダーの場所は、ここに指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="15fb3-187">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

5.  <span data-ttu-id="15fb3-188">ソリューション エクスプ ローラーで、Schema.xsd を右クリックし、をクリックして**インスタンスの生成**指定された場所にドキュメント インスタンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-188">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

## <a name="step-6-update-the-generated-document-instance"></a><span data-ttu-id="15fb3-189">手順 6: 生成されたドキュメント インスタンスを更新します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-189">Step 6: Update the generated document instance</span></span>  

1.  <span data-ttu-id="15fb3-190">テキスト エディター (メモ帳動作) で生成されたドキュメント インスタンスを開き、データが TIBCO システムに一意のレコードを生成することを確認するドキュメント インスタンスの内容を編集します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-190">Open the generated document instance in a text editor(Notepad works), and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="15fb3-191">たとえば、次のコードは、データ ファイルの最初の部分を示しています。</span><span class="sxs-lookup"><span data-stu-id="15fb3-191">For example, the follow code shows the first part of the data file:</span></span>  

    ```  
    <ns0:Root xmlns:ns0="http://TibcoRendezvousOneWaySend.TibcoRendezvousOneWaySendSchema">  
        <Name>Punya Palit</Name>  
        <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  

2.  <span data-ttu-id="15fb3-192">変更したドキュメント インスタンスを保存します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-192">Save the modified document instance.</span></span>  

## <a name="step-7-build-and-deploy-the-project"></a><span data-ttu-id="15fb3-193">手順 7: 構築し、プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="15fb3-193">Step 7: Build and deploy the project</span></span>  

1. <span data-ttu-id="15fb3-194">右クリックし、 **OneWaySend**ソリューション エクスプ ローラーでプロジェクトを**プロパティ**をプロジェクトのプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-194">Right-click the **OneWaySend** project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  

2. <span data-ttu-id="15fb3-195">をクリックして、**展開**タブ。</span><span class="sxs-lookup"><span data-stu-id="15fb3-195">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="15fb3-196">適切な値を入力、 **Server**プロパティと**構成データベース**のプロパティの  **BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-196">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  

4. <span data-ttu-id="15fb3-197">ソリューション エクスプ ローラーで OneWaySend プロジェクトを右クリックし、をクリックして**デプロイ**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。</span><span class="sxs-lookup"><span data-stu-id="15fb3-197">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

## <a name="step-8-bind-enlist-and-start-the-orchestration"></a><span data-ttu-id="15fb3-198">手順 8: バインド、参加、およびオーケストレーションを開始します</span><span class="sxs-lookup"><span data-stu-id="15fb3-198">Step 8: Bind, enlist, and start the orchestration</span></span>  

1. <span data-ttu-id="15fb3-199">**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-199">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="15fb3-200">をクリックして、**更新**MMC ツールバーまたはキーを押してボタン、 **F5**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。</span><span class="sxs-lookup"><span data-stu-id="15fb3-200">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  

3. <span data-ttu-id="15fb3-201">表示するオーケストレーションをダブルクリックして、**オーケストレーションのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="15fb3-201">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="15fb3-202">クリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="15fb3-202">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="15fb3-203">バインド オプションに適切な値を指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-203">Specify the appropriate values for the binding options, for example:</span></span>  


   |    <span data-ttu-id="15fb3-204">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="15fb3-204">**Parameter**</span></span>    |        <span data-ttu-id="15fb3-205">**[値]**</span><span class="sxs-lookup"><span data-stu-id="15fb3-205">**Value**</span></span>         |
   |---------------------|--------------------------|
   |        <span data-ttu-id="15fb3-206">ホスト</span><span class="sxs-lookup"><span data-stu-id="15fb3-206">Host</span></span>         | <span data-ttu-id="15fb3-207">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="15fb3-207">BizTalkServerApplication</span></span> |
   |   <span data-ttu-id="15fb3-208">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="15fb3-208">FileReceivePort</span></span>   |   <span data-ttu-id="15fb3-209">TIBCORndOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="15fb3-209">TIBCORndOneWayFileRP</span></span>   |
   | <span data-ttu-id="15fb3-210">TibcoRendezvousSend</span><span class="sxs-lookup"><span data-stu-id="15fb3-210">TibcoRendezvousSend</span></span> |     <span data-ttu-id="15fb3-211">TIBCORndOneWaySP</span><span class="sxs-lookup"><span data-stu-id="15fb3-211">TIBCORndOneWaySP</span></span>     |


6. <span data-ttu-id="15fb3-212">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15fb3-212">Click OK.</span></span>  

7. <span data-ttu-id="15fb3-213">オーケストレーションを右クリックし、をクリックして**開始**を参加させて、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-213">Right-click the orchestration, and click **Start** to enlist and start the orchestration.</span></span>  

## <a name="step-9-drop-a-document-and-check-the-tibco-system"></a><span data-ttu-id="15fb3-214">手順 9: ドキュメントを削除して TIBCO システムを確認します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-214">Step 9: Drop a document, and check the TIBCO system</span></span>

-   <span data-ttu-id="15fb3-215">先ほど作成したドキュメント インスタンスを、アプリケーションが監視するファイル受信フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="15fb3-215">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  

-   <span data-ttu-id="15fb3-216">TIBCO Web インターフェイスを使用して、XML ファイルのデータからレコードが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-216">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  


<span data-ttu-id="15fb3-217">ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-217">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="15fb3-218">ファイル アダプターがフォルダーからファイルを取得し、メッセージボックスに BizTalk メッセージとして公開します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-218">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="15fb3-219">この公開されたメッセージをオーケストレーションがサブスクライブします。その結果、BizTalk メッセージング エンジンによってオーケストレーションのインスタンスがアクティブ化され、メッセージがオーケストレーション インスタンスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="15fb3-219">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="15fb3-220">オーケストレーション インスタンスがオーケストレーションで指定されたロジックを使用してメッセージを処理し、メッセージ ボックスにメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-220">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="15fb3-221">この公開されたメッセージを TIBCO 送信ポートがサブスクライブします。その結果、BizTalk メッセージング エンジンによってこのメッセージが TIBCO 送信ポートに送信されます。</span><span class="sxs-lookup"><span data-stu-id="15fb3-221">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  

5.  <span data-ttu-id="15fb3-222">送信ポートがメッセージを BizTalk Adapter for TIBCO Rendezvous に渡します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-222">The send port hands the message to the BizTalk Adapter for TIBCO Rendezvous.</span></span>  

6.  <span data-ttu-id="15fb3-223">BizTalk Adapter for TIBCO Rendezvous がメッセージを TIBCO システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="15fb3-223">The BizTalk Adapter for TIBCO Rendezvous sends the message to the TIBCO system.</span></span>  

## <a name="see-also"></a><span data-ttu-id="15fb3-224">参照</span><span class="sxs-lookup"><span data-stu-id="15fb3-224">See Also</span></span>  
 <span data-ttu-id="15fb3-225">[チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用してデータを受信するには](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="15fb3-225">[Tutorial: Use the BizTalk Adapter for TIBCO Rendezvous to Receive Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span></span>  
 <span data-ttu-id="15fb3-226">[チュートリアル: TIBCO Rendezvous 用の Microsoft BizTalk Adapter の使用](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="15fb3-226">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="15fb3-227">作業の開始</span><span class="sxs-lookup"><span data-stu-id="15fb3-227">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)