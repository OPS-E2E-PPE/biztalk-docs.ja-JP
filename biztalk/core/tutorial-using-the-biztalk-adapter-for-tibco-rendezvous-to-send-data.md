---
title: "チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用してデータを送信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b761ce2d-3465-43e0-bd8d-4d68b523226a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63540402ca8e060d26c8398af010a81eaad0a6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data"></a><span data-ttu-id="d6809-102">チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用したデータの送信</span><span class="sxs-lookup"><span data-stu-id="d6809-102">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data</span></span>
<span data-ttu-id="d6809-103">BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システムにデータを送信できます。</span><span class="sxs-lookup"><span data-stu-id="d6809-103">You can use the BizTalk Adapter for TIBCO Rendezvous to send data to a TIBCO system.</span></span> <span data-ttu-id="d6809-104">このチュートリアルでは、これを示す SDK サンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d6809-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d6809-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="d6809-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="d6809-106">このサンプルをビルドして展開するには、アダプターが実行されている [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="d6809-106">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
-   <span data-ttu-id="d6809-107">サンプルでは、メッセージ コンテキストのプロパティを含んでいる Microsoft.BizTalk.Adapters.TibRV.Properties.dll という DLL を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6809-107">The sample uses a DLL containing message context properties: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span> <span data-ttu-id="d6809-108">ソリューションからこのライブラリへの参照を更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6809-108">You may need to update the solution's reference to this library.</span></span> <span data-ttu-id="d6809-109">詳細については、次を参照してください。 [BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)](../core/biztalk-server-message-context-properties-send-handlers.md)です。</span><span class="sxs-lookup"><span data-stu-id="d6809-109">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="d6809-110">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="d6809-110">What This Sample Does</span></span>  
 <span data-ttu-id="d6809-111">このサンプルでは、ファイル フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システム内にレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="d6809-111">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Rendezvous to create a record in the TIBCO system.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="d6809-112">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="d6809-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="d6809-113">このサンプルは、[!INCLUDE[vs2010](../includes/vs2010-md.md)] でデザインされたもので、BizTalk Adapter for TIBCO Rendezvous を BizTalk オーケストレーションと共に使用する場合の基本的な機能を示します。</span><span class="sxs-lookup"><span data-stu-id="d6809-113">This sample, designed in [!INCLUDE[vs2010](../includes/vs2010-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Rendezvous with a BizTalk orchestration.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="d6809-114">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="d6809-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="d6809-115">このサンプルの既定の場所は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d6809-115">The default location for the sample is</span></span>  
  
 <span data-ttu-id="d6809-116">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend</span><span class="sxs-lookup"><span data-stu-id="d6809-116">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend</span></span>  
  
 <span data-ttu-id="d6809-117">次の表に、サンプル内のファイルとその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="d6809-117">The following table lists and describes the files in the sample.</span></span>  
  
|<span data-ttu-id="d6809-118">**ランタイム プロジェクト ファイル名**</span><span class="sxs-lookup"><span data-stu-id="d6809-118">**Runtime Project Filename**</span></span>|<span data-ttu-id="d6809-119">**ランタイム プロジェクト ファイルの説明**</span><span class="sxs-lookup"><span data-stu-id="d6809-119">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="d6809-120">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="d6809-120">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="d6809-121">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="d6809-121">OneWaySend.sln</span></span>|<span data-ttu-id="d6809-122">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="d6809-122">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="d6809-123">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="d6809-123">Schema.xsd</span></span><br /><br /> <span data-ttu-id="d6809-124">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="d6809-124">PropertySchema.xsd</span></span>|<span data-ttu-id="d6809-125">アプリケーションのスキーマおよびプロパティ スキーマ ファイル。</span><span class="sxs-lookup"><span data-stu-id="d6809-125">Schema and property schema files for the application.</span></span>|  
|<span data-ttu-id="d6809-126">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="d6809-126">Orchestration.odx</span></span>|<span data-ttu-id="d6809-127">アプリケーションが使用するオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="d6809-127">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="d6809-128">TIBCORendezvousOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="d6809-128">TIBCORendezvousOneWaySend.snk</span></span>|<span data-ttu-id="d6809-129">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="d6809-129">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="d6809-130">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="d6809-130">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="d6809-131">BizTalk Adapter for TIBCO Rendezvous の新しいインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="d6809-131">Create a new instance of the BizTalk Adapter for TIBCO Rendezvous</span></span>  
  
1.  <span data-ttu-id="d6809-132">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを起動します。</span><span class="sxs-lookup"><span data-stu-id="d6809-132">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="d6809-133">をクリックして**開始**、**プログラム**、 **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 **BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-133">Click **Start**, **Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d6809-134">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**をクリックして**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-134">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="d6809-135">右クリック**アダプター**を指す**新規**、**アダプターしています.**</span><span class="sxs-lookup"><span data-stu-id="d6809-135">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="d6809-136">表示する、**アダプター プロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="d6809-136">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="d6809-137">値を入力して、**名前**フィールド、たとえば**TIBCO Rendezvous**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-137">Enter a value for the **Name** field, for example **TIBCO Rendezvous**.</span></span>  
  
5.  <span data-ttu-id="d6809-138">選択**TIBCO(r) Rendezvous(r)**で利用可能なアダプターの一覧から、**アダプター**ドロップダウン リスト をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-138">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="d6809-139">BizTalk 送信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="d6809-139">Create a BizTalk Send Port</span></span>  
  
1.  <span data-ttu-id="d6809-140">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-140">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="d6809-141">右クリック**送信ポート**を指す**新規**、**静的な一方向送信ポートしています.**</span><span class="sxs-lookup"><span data-stu-id="d6809-141">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="d6809-142">表示する、**送信ポートのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="d6809-142">to display the **Send Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="d6809-143">値を入力して、**名前**フィールド、たとえば**TIBCORndOneWaySP**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-143">Enter a value for the **Name** field, for example **TIBCORndOneWaySP**.</span></span>  
  
4.  <span data-ttu-id="d6809-144">使用可能なアダプターの一覧から TIBCO Rendezvous アダプターを選択して、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d6809-144">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6809-145">この値は、TIBCO Enterprise Message System アダプターで作成したときに指定された名前、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="d6809-145">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
5.  <span data-ttu-id="d6809-146">値を入力して、**証明された送信者プロパティ**:</span><span class="sxs-lookup"><span data-stu-id="d6809-146">Enter values for the **Certified Sender Properties**:</span></span>  
  
    |<span data-ttu-id="d6809-147">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="d6809-147">**Property**</span></span>|<span data-ttu-id="d6809-148">**値**</span><span class="sxs-lookup"><span data-stu-id="d6809-148">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="d6809-149">台帳ファイル名</span><span class="sxs-lookup"><span data-stu-id="d6809-149">Ledger file name</span></span>|<span data-ttu-id="d6809-150">永続的な認証されたメッセージ配信に使用する台帳ファイル名。</span><span class="sxs-lookup"><span data-stu-id="d6809-150">Ledger file name to use for persistent certified message delivery.</span></span>|  
    |<span data-ttu-id="d6809-151">再利用可能な名前</span><span class="sxs-lookup"><span data-stu-id="d6809-151">Reusable name</span></span>|<span data-ttu-id="d6809-152">認証されたメッセージ配信に使用する再利用可能な送信者名です。</span><span class="sxs-lookup"><span data-stu-id="d6809-152">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="d6809-153">この名前は、ネットワーク上のすべての認証されたメッセージの送信者名の中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6809-153">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
6.  <span data-ttu-id="d6809-154">値を入力して、**資格情報**:</span><span class="sxs-lookup"><span data-stu-id="d6809-154">Enter values for the **Credentials**:</span></span>  
  
    |<span data-ttu-id="d6809-155">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="d6809-155">**Property**</span></span>|<span data-ttu-id="d6809-156">**値**</span><span class="sxs-lookup"><span data-stu-id="d6809-156">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="d6809-157">Password</span><span class="sxs-lookup"><span data-stu-id="d6809-157">Password</span></span>|<span data-ttu-id="d6809-158">TIBCO Rendezvous サーバーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="d6809-158">The password for the TIBCO Rendezvous server.</span></span>|  
    |<span data-ttu-id="d6809-159">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="d6809-159">User name</span></span>|<span data-ttu-id="d6809-160">TIBCO Rendezvous サーバーのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="d6809-160">The user name for the TIBCO Rendezvous server.</span></span>|  
  
7.  <span data-ttu-id="d6809-161">値を入力して、 **RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="d6809-161">Enter values for the **RendezvousTransport**:</span></span>  
  
    |<span data-ttu-id="d6809-162">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="d6809-162">**Property**</span></span>|<span data-ttu-id="d6809-163">**値**</span><span class="sxs-lookup"><span data-stu-id="d6809-163">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="d6809-164">デーモン</span><span class="sxs-lookup"><span data-stu-id="d6809-164">Daemon</span></span>|<span data-ttu-id="d6809-165">Rendezvous トランスポート デーモン パラメーター。</span><span class="sxs-lookup"><span data-stu-id="d6809-165">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="d6809-166">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="d6809-166">Network</span></span>|<span data-ttu-id="d6809-167">Rendezvous トランスポート ネットワーク パラメーター。</span><span class="sxs-lookup"><span data-stu-id="d6809-167">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="d6809-168">サービス</span><span class="sxs-lookup"><span data-stu-id="d6809-168">Service</span></span>|<span data-ttu-id="d6809-169">Rendezvous トランスポート サービス パラメーター。</span><span class="sxs-lookup"><span data-stu-id="d6809-169">Rendezvous Transport Service parameter.</span></span>|  
  
     <span data-ttu-id="d6809-170">プロパティの詳細については、次を参照してください。 [TIBCO Rendezvous トランスポートのプロパティの設定方法](../core/how-to-set-tibco-rendezvous-transport-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="d6809-170">For more information about the properties, see [How to Set TIBCO Rendezvous Transport Properties](../core/how-to-set-tibco-rendezvous-transport-properties.md).</span></span>  
  
8.  <span data-ttu-id="d6809-171">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6809-171">Click **OK**.</span></span>  
  
9. <span data-ttu-id="d6809-172">選択、 **XML Transmit**パイプラインで使用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン リスト をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-172">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
10. <span data-ttu-id="d6809-173">送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="d6809-173">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="create-a-file-receive-port"></a><span data-ttu-id="d6809-174">ファイル受信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="d6809-174">Create a file receive port</span></span>  
  
1.  <span data-ttu-id="d6809-175">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-175">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="d6809-176">受信ポート フォルダーを右クリックし、をクリックして**新規**、**一方向の受信ポートしています.**受信ポートのプロパティ ダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="d6809-176">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the Receive Port Properties dialog.</span></span>  
  
3.  <span data-ttu-id="d6809-177">値を入力、**名前**フィールド、たとえば**TIBCORndOneWayFileRP**、 をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-177">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-file-receive-location"></a><span data-ttu-id="d6809-178">ファイル受信場所を作成する</span><span class="sxs-lookup"><span data-stu-id="d6809-178">Create a file receive location</span></span>  
  
1.  <span data-ttu-id="d6809-179">監視対象のファイル受信場所となるフォルダー (たとえば C:\Filesource) を作成します。</span><span class="sxs-lookup"><span data-stu-id="d6809-179">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  
  
2.  <span data-ttu-id="d6809-180">右クリックし、新しい受信ポートをクリックし、**新規**、**受信場所の追加.**</span><span class="sxs-lookup"><span data-stu-id="d6809-180">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="d6809-181">表示する、**受信場所のプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="d6809-181">to display the **Receive Location Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="d6809-182">値を入力して、**名前**フィールド、たとえば**TIBCORndOneWayFileRL**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-182">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRL**.</span></span>  
  
4.  <span data-ttu-id="d6809-183">選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d6809-183">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="d6809-184">用に作成したフォルダーの場所を入力、**受信フォルダー**プロパティをクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-184">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  
  
6.  <span data-ttu-id="d6809-185">選択**[xmlreceive]**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン リスト ボックスし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-185">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="d6809-186">受信場所を右クリックし、をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-186">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="generate-a-document-instance-from-the-schema"></a><span data-ttu-id="d6809-187">スキーマからドキュメント インスタンスを生成する</span><span class="sxs-lookup"><span data-stu-id="d6809-187">Generate a document instance from the schema</span></span>  
  
1.  <span data-ttu-id="d6809-188">ソリューション エクスプ ローラーで、Schema.xsd を右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-188">Right-click Schema.xsd in Solution Explorer and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d6809-189">プロパティ ウィンドウでクリックして選択、**出力インスタンス ファイル名**オプションで 、**全般**セクションです。</span><span class="sxs-lookup"><span data-stu-id="d6809-189">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  
  
3.  <span data-ttu-id="d6809-190">表示するには、省略記号ボタン (...) をクリックして、 **出力ファイルの**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="d6809-190">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  
  
4.  <span data-ttu-id="d6809-191">たとえば、フォルダーと出力ファイル インスタンスの名前を指定**C:\instance.xml**  をクリック**保存**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-191">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6809-192">ファイル受信場所に指定したフォルダーの場所は、ここに指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="d6809-192">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  
  
5.  <span data-ttu-id="d6809-193">ソリューション エクスプ ローラーで、Schema.xsd を右クリックし、をクリックして**インスタンスの生成**を指定した場所にドキュメント インスタンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="d6809-193">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  
  
#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="d6809-194">生成されたドキュメント インスタンスを変更する</span><span class="sxs-lookup"><span data-stu-id="d6809-194">Modify the generated document instance</span></span>  
  
1.  <span data-ttu-id="d6809-195">生成されたドキュメント インスタンスをメモ帳などのテキスト エディターで開き、ドキュメント インスタンスの内容を編集して、データによって TIBCO システムで一意のレコードが生成されるようにします。</span><span class="sxs-lookup"><span data-stu-id="d6809-195">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="d6809-196">データ ファイルの最初の部分を例として次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6809-196">For example the code below shows the first part of the data file:</span></span>  
  
    ```  
    <ns0:Root xmlns:ns0="http://TibcoRendezvousOneWaySend.TibcoRendezvousOneWaySendSchema">  
        <Name>Punya Palit</Name>  
        <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  
  
2.  <span data-ttu-id="d6809-197">変更したドキュメント インスタンスを保存します。</span><span class="sxs-lookup"><span data-stu-id="d6809-197">Save the modified document instance.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="d6809-198">プロジェクトのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="d6809-198">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="d6809-199">右クリックし、 **OneWaySend**ソリューション エクスプ ローラーでプロジェクトを**プロパティ**プロジェクトのプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="d6809-199">Right-click the **OneWaySend** project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="d6809-200">クリックして、**展開**タブです。</span><span class="sxs-lookup"><span data-stu-id="d6809-200">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="d6809-201">適切な値を入力、**サーバー**プロパティおよび**構成データベース**プロパティの  **BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-201">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  
  
4.  <span data-ttu-id="d6809-202">ソリューション エクスプ ローラーで OneWaySend プロジェクトを右クリックし、をクリックして**展開**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。</span><span class="sxs-lookup"><span data-stu-id="d6809-202">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="d6809-203">オーケストレーションをバインドして参加させる</span><span class="sxs-lookup"><span data-stu-id="d6809-203">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="d6809-204">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="d6809-204">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="d6809-205">をクリックして、**更新**MMC ツールバーまたはキーを押してボタン、 **f5 キーを押して**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。</span><span class="sxs-lookup"><span data-stu-id="d6809-205">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="d6809-206">表示するオーケストレーションをダブルクリック、**オーケストレーションのプロパティ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="d6809-206">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="d6809-207">をクリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左ペインでします。</span><span class="sxs-lookup"><span data-stu-id="d6809-207">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="d6809-208">バインド オプションに適切な値を指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d6809-208">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="d6809-209">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="d6809-209">**Parameter**</span></span>|<span data-ttu-id="d6809-210">**値**</span><span class="sxs-lookup"><span data-stu-id="d6809-210">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="d6809-211">Host</span><span class="sxs-lookup"><span data-stu-id="d6809-211">Host</span></span>|<span data-ttu-id="d6809-212">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="d6809-212">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="d6809-213">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="d6809-213">FileReceivePort</span></span>|<span data-ttu-id="d6809-214">TIBCORndOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="d6809-214">TIBCORndOneWayFileRP</span></span>|  
    |<span data-ttu-id="d6809-215">TibcoRendezvousSend</span><span class="sxs-lookup"><span data-stu-id="d6809-215">TibcoRendezvousSend</span></span>|<span data-ttu-id="d6809-216">TIBCORndOneWaySP</span><span class="sxs-lookup"><span data-stu-id="d6809-216">TIBCORndOneWaySP</span></span>|  
  
6.  <span data-ttu-id="d6809-217">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6809-217">Click OK.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="d6809-218">オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d6809-218">Start the orchestration</span></span>  
  
-   <span data-ttu-id="d6809-219">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、オーケストレーションを右クリックし、をクリックして**開始**を参加させて、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d6809-219">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="d6809-220">ファイル受信場所の監視対象フォルダーにドキュメント インスタンスをドロップする</span><span class="sxs-lookup"><span data-stu-id="d6809-220">Drop a document instance into the folder monitored by the file receive location</span></span>  
  
-   <span data-ttu-id="d6809-221">先ほど作成したドキュメント インスタンスを、アプリケーションが監視するファイル受信フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d6809-221">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  
  
#### <a name="verify-that-the-tibco-system-is-updated"></a><span data-ttu-id="d6809-222">TIBCO システムが更新されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="d6809-222">Verify that the TIBCO system is updated</span></span>  
  
-   <span data-ttu-id="d6809-223">TIBCO Web インターフェイスを使用して、XML ファイルのデータからレコードが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d6809-223">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  
  
 <span data-ttu-id="d6809-224">ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="d6809-224">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="d6809-225">ファイル アダプターがフォルダーからファイルを取得し、メッセージボックスに BizTalk メッセージとして公開します。</span><span class="sxs-lookup"><span data-stu-id="d6809-225">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="d6809-226">この公開されたメッセージをオーケストレーションがサブスクライブします。その結果、BizTalk メッセージング エンジンによってオーケストレーションのインスタンスがアクティブ化され、メッセージがオーケストレーション インスタンスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="d6809-226">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="d6809-227">オーケストレーション インスタンスがオーケストレーションで指定されたロジックを使用してメッセージを処理し、メッセージ ボックスにメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="d6809-227">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="d6809-228">この公開されたメッセージを TIBCO 送信ポートがサブスクライブします。その結果、BizTalk メッセージング エンジンによってこのメッセージが TIBCO 送信ポートに送信されます。</span><span class="sxs-lookup"><span data-stu-id="d6809-228">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  
  
5.  <span data-ttu-id="d6809-229">送信ポートがメッセージを BizTalk Adapter for TIBCO Rendezvous に渡します。</span><span class="sxs-lookup"><span data-stu-id="d6809-229">The send port hands the message to the BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
6.  <span data-ttu-id="d6809-230">BizTalk Adapter for TIBCO Rendezvous がメッセージを TIBCO システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="d6809-230">The BizTalk Adapter for TIBCO Rendezvous sends the message to the TIBCO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6809-231">参照</span><span class="sxs-lookup"><span data-stu-id="d6809-231">See Also</span></span>  
 <span data-ttu-id="d6809-232">[チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用してデータを受信するには](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="d6809-232">[Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Receive Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span></span>  
 <span data-ttu-id="d6809-233">[チュートリアル: Microsoft BizTalk Adapter を使用して TIBCO Rendezvous の](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="d6809-233">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="d6809-234">作業の開始</span><span class="sxs-lookup"><span data-stu-id="d6809-234">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)