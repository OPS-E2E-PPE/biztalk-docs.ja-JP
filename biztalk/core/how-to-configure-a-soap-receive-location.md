---
title: SOAP 受信場所を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], virtual directories
- SOAP adapters, code samples
- configuring [SOAP adapters], receive locations
- virtual directories, SOAP adapters
- SOAP adapters, receive locations
- code samples, SOAP adapters
- configuring [SOAP adapters], code samples
- SOAP adapters, virtual directories
- receive locations, SOAP adapters
ms.assetid: 7e348409-9181-47e4-b3c0-c73eb2acffa3
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b33886296441082ea7d7e83b92659f81140d71f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250162"
---
# <a name="how-to-configure-a-soap-receive-location"></a><span data-ttu-id="b780e-102">SOAP の受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b780e-102">How to Configure a SOAP Receive Location</span></span>
<span data-ttu-id="b780e-103">SOAP の受信場所は、プログラムから、または [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="b780e-103">You can configure a SOAP receive location either programmatically or by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="b780e-104">**構成する SOAP の受信場所プログラムによる方法**</span><span class="sxs-lookup"><span data-stu-id="b780e-104">**How to Configure a SOAP Receive Location Programmatically**</span></span>  
  
 <span data-ttu-id="b780e-105">BizTalk エクスプ ローラー オブジェクト モデルを使用すると、作成および構成は受信場所をプログラムでします。</span><span class="sxs-lookup"><span data-stu-id="b780e-105">The BizTalk Explorer object model enables you to create and configure receive locations programmatically.</span></span> <span data-ttu-id="b780e-106">BizTalk エクスプ ローラー オブジェクト モデルは、公開、**という**受信場所の構成インターフェイスを持つ、 **TransportTypeData**読み取り/書き込みプロパティです。</span><span class="sxs-lookup"><span data-stu-id="b780e-106">The BizTalk Explorer object model exposes the**IReceiveLocation** receive location configuration interface that has a **TransportTypeData** read/write property.</span></span> <span data-ttu-id="b780e-107">このプロパティでは、名前と値の組の XML 文字列の形式で SOAP の受信場所の構成プロパティ バッグを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b780e-107">This property accepts a SOAP receive location configuration property bag in the form of a name-value pair of XML strings.</span></span> <span data-ttu-id="b780e-108">BizTalk エクスプ ローラー オブジェクト モデルでこのプロパティを設定に設定する必要があります、 **InboundTransportLocation**のプロパティ、**という**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b780e-108">To set this property in the BizTalk Explorer object model, you must set the **InboundTransportLocation** property of the **IReceiveLocation** interface.</span></span>  
  
 <span data-ttu-id="b780e-109">**TransportTypeData**のプロパティ、**という**インターフェイスを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b780e-109">The **TransportTypeData** property of the **IReceiveLocation** interface does not have to be set.</span></span> <span data-ttu-id="b780e-110">このプロパティを設定しない場合、SOAP アダプターでは、次の表に記載されている SOAP 受信場所の構成の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b780e-110">If it is not set, the SOAP adapter uses the default values for the SOAP receive location configuration as indicated in the following table.</span></span>  
  
 <span data-ttu-id="b780e-111">次の表に、BizTalk エクスプローラーのオブジェクト モデルで SOAP 受信場所用に設定できる構成プロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="b780e-111">The following table lists the configuration properties that you can set in the BizTalk Explorer object model for the SOAP receive location.</span></span>  
  
|<span data-ttu-id="b780e-112">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="b780e-112">Property name</span></span>|<span data-ttu-id="b780e-113">型</span><span class="sxs-lookup"><span data-stu-id="b780e-113">Type</span></span>|<span data-ttu-id="b780e-114">Description</span><span class="sxs-lookup"><span data-stu-id="b780e-114">Description</span></span>|  
|-------------------|----------|-----------------|  
|<span data-ttu-id="b780e-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="b780e-115">**URI**</span></span>|<span data-ttu-id="b780e-116">文字列</span><span class="sxs-lookup"><span data-stu-id="b780e-116">String</span></span>|<span data-ttu-id="b780e-117">展開サーバーの Web サービスを含んでいる仮想ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="b780e-117">Virtual directory containing the Web service on the deployment server.</span></span>|  
|<span data-ttu-id="b780e-118">**AddressableURI**</span><span class="sxs-lookup"><span data-stu-id="b780e-118">**AddressableURI**</span></span>|<span data-ttu-id="b780e-119">文字列</span><span class="sxs-lookup"><span data-stu-id="b780e-119">String</span></span>|<span data-ttu-id="b780e-120">呼び出し可能な URL 全体を含むパブリック アドレス フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b780e-120">Public address field containing the entire, callable URL.</span></span><br /><br /> <span data-ttu-id="b780e-121">既定値: 空白</span><span class="sxs-lookup"><span data-stu-id="b780e-121">Default value: Blank</span></span>|  
|<span data-ttu-id="b780e-122">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="b780e-122">**UseSSO**</span></span>|<span data-ttu-id="b780e-123">ブール値</span><span class="sxs-lookup"><span data-stu-id="b780e-123">Boolean</span></span>|<span data-ttu-id="b780e-124">SOAP アダプターが、この受信場所で受信するメッセージにシングル サインオン チケットを発行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b780e-124">Specifies whether the SOAP adapter issues the Single Sign-On ticket to the messages that arrive on this receive location.</span></span><br /><br /> <span data-ttu-id="b780e-125">既定値: False</span><span class="sxs-lookup"><span data-stu-id="b780e-125">Default value: False</span></span>|  
  
 <span data-ttu-id="b780e-126">これらのプロパティを設定するには、以下の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="b780e-126">Use the following format to set the properties:</span></span>  
  
```  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
```  
  
 <span data-ttu-id="b780e-127">**URI**と**AddressableURI**を使用してプロパティを設定、**アドレス**と**PublicAddress**受信場所のプロパティオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b780e-127">The **URI** and **AddressableURI** properties are set using the **Address** and **PublicAddress** properties of the receive location object.</span></span>  
  
 <span data-ttu-id="b780e-128">次のコードは、SOAP 受信場所の作成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b780e-128">The following code fragment illustrates creating a SOAP receive location:</span></span>  
  
```  
// Use BizTalk Explorer object model to create new SOAP receive location.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  
  
// Add a new Request-Response port  
ReceivePort receivePort = explorer.AddNewReceivePort(true);  
receivePort.Name = "SampleReceivePort";  
receivePort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
  
// Add primary SOAP receive location  
ReceiveLocation receiveLocation = receivePort.AddNewReceiveLocation();  
receiveLocation.Name = "SampleReceiveLocation";  
receiveLocation.Address = "/PurchaseOrder/POOrchestration.asmx";  
receiveLocation.TransportType = explorer.ProtocolTypes["SOAP"];  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
receiveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
foreach (ReceiveHandler receiveHandler in explorer.ReceiveHandlers)  
{  
if (receiveHandler.TransportType.Name == receiveLocation.TransportType.Name)  
{  
receiveLocation.ReceiveHandler = receiveHandler;   
}  
}  
  
// Save  
explorer.SaveChanges();   
```  
  
 <span data-ttu-id="b780e-129">**SOAP 受信場所を BizTalk Server 管理コンソールを構成する方法**</span><span class="sxs-lookup"><span data-stu-id="b780e-129">**How to Configure a SOAP Receive Location with the BizTalk Server Administration Console**</span></span>  
  
 <span data-ttu-id="b780e-130">SOAP の受信場所のアダプター変数は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで設定できます。</span><span class="sxs-lookup"><span data-stu-id="b780e-130">You can set SOAP receive location adapter variables in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b780e-131">受信場所のプロパティが設定されていない場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで設定された既定の受信ハンドラーの値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b780e-131">If properties are not set in the receive location, the default receive handler values set in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console are used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b780e-132">次の手順を実行する前に、受信ポートを追加しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b780e-132">Before completing the following procedures you must have already added a receive port.</span></span> <span data-ttu-id="b780e-133">詳細については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="b780e-133">For more information, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span>  
  
### <a name="to-configure-variables-for-a-soap-receive-location"></a><span data-ttu-id="b780e-134">SOAP の受信場所の変数を構成するには</span><span class="sxs-lookup"><span data-stu-id="b780e-134">To configure variables for a SOAP receive location</span></span>  
  
1.  <span data-ttu-id="b780e-135">BizTalk Server 管理コンソールで、次のように展開します**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、の順に展開し、。受信場所を作成するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="b780e-135">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application you want to create a receive location in.</span></span>  
  
2.  <span data-ttu-id="b780e-136">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの左側のウィンドウをクリックして、**受信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="b780e-136">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, in the left pane, click the **Receive Port** node.</span></span> <span data-ttu-id="b780e-137">次に右ウィンドウで、既存の受信場所に関連付けられているか、新しい受信場所に関連付ける受信ポートを右クリックし、[ **プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b780e-137">Then in the right pane, right-click the receive port that is associated with an existing receive location or that you want to associate with a new receive location, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="b780e-138">**受信ポートのプロパティ**ダイアログ ボックスで、左ペインで、select、**受信場所**、右側のペインをダブルクリックして、既存の受信場所またはをクリックし **新規**新しい受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="b780e-138">In the **Receive Port Properties** dialog box, in the left pane, select **Receive Locations**, and then in the right pane, double-click an existing receive location or click **New**to create a new receive location.</span></span>  
  
4.  <span data-ttu-id="b780e-139">**受信場所のプロパティ**] ダイアログ ボックスで、**トランスポート**横**型**[ **SOAP**ドロップダウン リストからクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b780e-139">In the **Receive Location Properties** dialog box, in the **Transport** section next to **Type**, select **SOAP** from the drop-down list, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="b780e-140">**SOAP トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b780e-140">In the **SOAP Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="b780e-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b780e-141">Use this</span></span>|<span data-ttu-id="b780e-142">目的</span><span class="sxs-lookup"><span data-stu-id="b780e-142">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b780e-143">**仮想ディレクトリと Web サービス .asmx ファイル**</span><span class="sxs-lookup"><span data-stu-id="b780e-143">**Virtual directory plus Web Service .asmx file**</span></span>|<span data-ttu-id="b780e-144">Microsoft BizTalk Web サービス公開ウィザードで作成された .asmx ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="b780e-144">Indicate the .asmx file created by the BizTalk Web Services Publishing Wizard.</span></span><br /><br /> <span data-ttu-id="b780e-145">このメッセージの形式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b780e-145">The format of this message is similar to the following:</span></span><br /><br /> <span data-ttu-id="b780e-146">/PurchaseOrder/POOrchestration.asmx</span><span class="sxs-lookup"><span data-stu-id="b780e-146">/PurchaseOrder/POOrchestration.asmx</span></span><br /><br /> <span data-ttu-id="b780e-147">この場合、.asmx ファイルの完全な場所は http://localhost/PurchaseOrder/POOrchestration.asmx になります。</span><span class="sxs-lookup"><span data-stu-id="b780e-147">Where the full location of the .asmx file is http://localhost/PurchaseOrder/POOrchestration.asmx.</span></span> <span data-ttu-id="b780e-148">**注:** の URI を送信ポートまたは受信場所は、256 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="b780e-148">**Note:**  The URI for a send port or receive location cannot exceed 256 characters.</span></span>|  
    |<span data-ttu-id="b780e-149">**パブリック アドレス**</span><span class="sxs-lookup"><span data-stu-id="b780e-149">**Public address**</span></span>|<span data-ttu-id="b780e-150">この受信場所の完全修飾 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="b780e-150">Specify the fully qualified URI for this receive location.</span></span> <span data-ttu-id="b780e-151">このプロパティの値は、サーバー名と仮想ディレクトリの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="b780e-151">The value for this property is a combination of the server name and the virtual directory.</span></span> <span data-ttu-id="b780e-152">指定した URI は、取引先が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージを送信するときに接続するパブリック Web サイトの URL を示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b780e-152">The specified URI should designate the public Web site URL for trading partners to connect to when sending messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="b780e-153">この情報は省略可能であり、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では使用されません。</span><span class="sxs-lookup"><span data-stu-id="b780e-153">This information is optional and is not used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b780e-154">このパラメーターを使用すると、管理者は、受信場所が関連付けられているパブリック URL を記述できます。</span><span class="sxs-lookup"><span data-stu-id="b780e-154">This parameter is available to allow administrators to document the public URL that the receive location is tied to.</span></span>|  
    |<span data-ttu-id="b780e-155">**シングル サインオンを使用します。**</span><span class="sxs-lookup"><span data-stu-id="b780e-155">**Use Single Sign-On**</span></span>|<span data-ttu-id="b780e-156">SOAP アダプターがエンタープライズ シングル サインオンを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="b780e-156">Indicate that the SOAP adapter uses Enterprise Single Sign-On.</span></span> <span data-ttu-id="b780e-157">**注:** BizTalk Web サービス公開ウィザードでは、SharePoint Portal Server シングル サインオンを使用することができます。 このプロパティは、エンタープライズ シングル サインオンだけ有効です。</span><span class="sxs-lookup"><span data-stu-id="b780e-157">**Note:**  The BizTalk Web Services Publishing Wizard allows you to use SharePoint Portal Server Single Sign-On; this property only enables Enterprise Single Sign-On.</span></span>|  
  
6.  <span data-ttu-id="b780e-158">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b780e-158">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="b780e-159">**受信場所のプロパティ** ダイアログ ボックスで、受信場所の構成を完了し、をクリックするには、適切な値を入力して**OK**設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="b780e-159">In the **Receive Location Properties** dialog box, enter the appropriate values to complete the configuration of the receive location, and then click **OK** to save settings.</span></span> <span data-ttu-id="b780e-160">については、**受信場所のプロパティ**ダイアログ ボックスを参照してください[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="b780e-160">For information about the **Receive Locations Properties** dialog box, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
 <span data-ttu-id="b780e-161">SOAP の受信場所で使用されるセキュリティ設定は IIS で設定します。</span><span class="sxs-lookup"><span data-stu-id="b780e-161">The security settings used by the SOAP receive location are set in IIS.</span></span> <span data-ttu-id="b780e-162">既定では、SOAP の受信場所は、匿名認証を使用するように設定されていません。</span><span class="sxs-lookup"><span data-stu-id="b780e-162">By default, the SOAP receive location is not set to use anonymous authentication.</span></span>  
  
 <span data-ttu-id="b780e-163">SOAP クライアントが Web サービスを呼び出すと、SOAP アダプターでは、匿名認証、基本認証、ダイジェスト認証、または Windows 統合認証を使用して SOAP クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="b780e-163">While the SOAP client calls the Web service, the SOAP adapter authenticates the SOAP client by using either Anonymous, Basic, Digest, or Windows Integrated authentication.</span></span> <span data-ttu-id="b780e-164">ユーザーが確認されると、受信ハンドラーにユーザー コンテキストが渡されます。</span><span class="sxs-lookup"><span data-stu-id="b780e-164">If the user is verified, the user context is passed to the receive handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b780e-165">同一プロセスを共有する SOAP と HTTP を使用する IIS 構成は無効です。</span><span class="sxs-lookup"><span data-stu-id="b780e-165">Any IIS configuration that leads to SOAP and HTTP sharing the same process is not valid.</span></span> <span data-ttu-id="b780e-166">プロセスごとに 1 つの分離受信場所のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b780e-166">You can have only one isolated receiver per process.</span></span>  
  
### <a name="to-update-a-virtual-directory-to-use-aspnet-40"></a><span data-ttu-id="b780e-167">ASP.NET 4.0 を使用する仮想ディレクトリを更新するには</span><span class="sxs-lookup"><span data-stu-id="b780e-167">To update a virtual directory to use ASP.NET 4.0</span></span>  
  
1.  <span data-ttu-id="b780e-168">インターネット インフォメーション サービス (IIS) マネージャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="b780e-168">Launch the Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b780e-169">をクリックして**開始**をクリックして**すべてのプログラム**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="b780e-169">Click **Start**, click **All Programs**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="b780e-170">リモートの IIS サーバーに接続する場合は、右クリックして、**インターネット インフォメーション サービス**ノードをクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="b780e-170">If you need to connect to a remote IIS server, right click the **Internet Information Services** node and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="b780e-171">リモートの IIS サーバーのコンピューター名を入力し、必要な場合は資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b780e-171">Type the computer name for the remote IIS server and credentials if necessary.</span></span>  
  
4.  <span data-ttu-id="b780e-172">設定を更新する Web サイトまたは仮想ディレクトリをホストしているサーバー名を展開します。</span><span class="sxs-lookup"><span data-stu-id="b780e-172">Expand the server name that houses the Web site or virtual directory to be updated.</span></span>  
  
5.  <span data-ttu-id="b780e-173">展開**サイト**です。</span><span class="sxs-lookup"><span data-stu-id="b780e-173">Expand **Sites**.</span></span>  
  
6.  <span data-ttu-id="b780e-174">展開**既定の Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="b780e-174">Expand **Default Web Site**.</span></span>  
  
7.  <span data-ttu-id="b780e-175">規定の Web サイトを展開し、Web サイトの下にある仮想ディレクトリを表示します。</span><span class="sxs-lookup"><span data-stu-id="b780e-175">Expand the Default Web site to view the virtual directories under the Web site.</span></span>  
  
8.  <span data-ttu-id="b780e-176">ASP.NET 4.0 を使用して、をクリックを更新する仮想ディレクトリを右クリックして**アプリケーションの管理**、クリックして**詳細設定**です。</span><span class="sxs-lookup"><span data-stu-id="b780e-176">Right-click the virtual directory that you want to update to use ASP.NET 4.0, click **Manage Application**, and then click **Advanced Settings**.</span></span> <span data-ttu-id="b780e-177">**アプリケーション プール**フィールドには、選択した仮想ディレクトリの設定、アプリケーション プールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b780e-177">The **Application Pool** field displays the application pool set for the selected virtual directory.</span></span> <span data-ttu-id="b780e-178">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b780e-178">Click **OK**.</span></span>  
  
9. <span data-ttu-id="b780e-179">インターネット インフォメーション サービス (IIS) マネージャー] ウィンドウで、[**アプリケーション プール**です。</span><span class="sxs-lookup"><span data-stu-id="b780e-179">In the Internet Information Services (IIS) Manager window, click **Application Pools**.</span></span> <span data-ttu-id="b780e-180">詳細ペインに、サーバーのアプリケーション プールの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b780e-180">The details pane displays a list of application pools on the server.</span></span>  
  
10. <span data-ttu-id="b780e-181">手順 8 でアプリケーション プールのセットを右クリックし、をクリックして**基本設定**です。</span><span class="sxs-lookup"><span data-stu-id="b780e-181">Right-click the application pool set in step 8, and then click **Basic Settings**.</span></span>  
  
11. <span data-ttu-id="b780e-182">**アプリケーション プールの編集** ダイアログ ボックスで、次の変更します。</span><span class="sxs-lookup"><span data-stu-id="b780e-182">In the **Edit Application Pool** dialog box, change the following:</span></span>  
  
    -   <span data-ttu-id="b780e-183">**.NET framework のバージョン**に**4.0**</span><span class="sxs-lookup"><span data-stu-id="b780e-183">**.NET Framework version** to **4.0**</span></span>  
  
    -   <span data-ttu-id="b780e-184">**マネージ パイプライン モード**に**クラシック**</span><span class="sxs-lookup"><span data-stu-id="b780e-184">**Managed pipeline mode** to **Classic**</span></span>  
  
12. <span data-ttu-id="b780e-185">をクリックして**OK**変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="b780e-185">Click **OK** to apply the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b780e-186">参照</span><span class="sxs-lookup"><span data-stu-id="b780e-186">See Also</span></span>  
 [<span data-ttu-id="b780e-187">Web サービスの使用</span><span class="sxs-lookup"><span data-stu-id="b780e-187">Consuming Web Services</span></span>](../core/consuming-web-services.md)