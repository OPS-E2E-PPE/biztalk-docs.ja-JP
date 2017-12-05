---
title: "アダプターの登録ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6750f0ed-4411-4a63-a7fe-f66132cd1e22
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c38d00cbaf5d34aa880f5efd1d9e9a59d59c4e0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="adapter-registration-file"></a><span data-ttu-id="9a0b9-102">アダプターの登録ファイル</span><span class="sxs-lookup"><span data-stu-id="9a0b9-102">Adapter Registration File</span></span>
<span data-ttu-id="9a0b9-103">カスタム アダプター コードを正常にビルドしたら、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-103">After the custom adapter code has been successfully built it must be registered with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="9a0b9-104">これを行うには、レジストリを適切なアダプターの設定で更新します。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-104">You do this by updating the registry with the appropriate adapter settings.</span></span> <span data-ttu-id="9a0b9-105">レジストリ ファイルは手動で記述できますが、正確かつ複雑な情報を入力する必要があるため、手動での記述はエラーを招く原因となります。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-105">You can manually write a registry file, but this is prone to errors due to the preciseness and complexity of the information that you need to enter.</span></span> <span data-ttu-id="9a0b9-106">推奨される方法は、アダプターのレジストリ ウィザードを実行することです。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-106">A better decision is to run the Adapter Registry Wizard.</span></span> <span data-ttu-id="9a0b9-107">アダプターのレジストリ ウィザードには、最初からレジストリ ファイルを作成するのとまったく同じオプションが用意されており、ファイルでエラーが発生する可能性を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-107">The Adapter Registry Wizard gives you all the same options as creating a registry file from scratch, and reduces the likelihood of errors in the file.</span></span> <span data-ttu-id="9a0b9-108">アダプター レジストリ ウィザードの詳細については、次を参照してください。[アダプター レジストリ ウィザード](../core/adapter-registry-wizard.md)です。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-108">For more information about the Adapter Registry Wizard, see [Adapter Registry Wizard](../core/adapter-registry-wizard.md).</span></span>  
  
 <span data-ttu-id="9a0b9-109">StaticAdapterManagement.reg ファイルと DynamicAdapterManagement.reg ファイル*\<ドライブ\>*: \Program Files\Microsoft BizTalk Server\SDK\Samples\AdaptersDevelopment\File アダプター。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-109">The StaticAdapterManagement.reg file and DynamicAdapterManagement.reg file are located at *\<drive\>*:\Program Files\Microsoft BizTalk Server\SDK\Samples\AdaptersDevelopment\File Adapter.</span></span> <span data-ttu-id="9a0b9-110">これらのファイルのいずれかを実行すると (ダブルクリックするか、右クリックすることができを選択し、**マージ**)、レジストリでサンプル ファイル アダプターを登録し、アセンブリをグローバル アセンブリ キャッシュにインストールします。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-110">When you run one of these files (you can double-click it or right-click it and and select **Merge**), it registers the sample file adapter with the registry and installs the assembly into the global assembly cache.</span></span> <span data-ttu-id="9a0b9-111">カスタム アダプターを登録するための最適な方法としては、アダプターのレジストリ ウィザードを使用して新しいレジストリ ファイルを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-111">To register your custom adapter the best option is to create a new registry file by using the Adapter Registry Wizard.</span></span> <span data-ttu-id="9a0b9-112">カスタムの静的アダプターがサンプル アダプターに似ている場合は、作成する代わりに既存のレジストリ ファイルを変更し、StaticAdapterManagement.reg ファイルの次のプロパティを開いて変更します。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-112">If your custom static adapter is similar to the sample adapter, and you decide to modify the existing registry file instead, open and modify the following properties in the StaticAdapterManagement.reg file:</span></span>  
  
-   <span data-ttu-id="9a0b9-113">**制約**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-113">**Constraints**</span></span>  
  
-   <span data-ttu-id="9a0b9-114">**InboundTypeName**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-114">**InboundTypeName**</span></span>  
  
-   <span data-ttu-id="9a0b9-115">**InboundAssemblyPath**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-115">**InboundAssemblyPath**</span></span>  
  
-   <span data-ttu-id="9a0b9-116">**OutboundTypeName**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-116">**OutboundTypeName**</span></span>  
  
-   <span data-ttu-id="9a0b9-117">**OutboundAssemblyPath**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-117">**OutboundAssemblyPath**</span></span>  
  
-   <span data-ttu-id="9a0b9-118">**AdapterMgmtTypeName**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-118">**AdapterMgmtTypeName**</span></span>  
  
-   <span data-ttu-id="9a0b9-119">**AdapterMgmtAssemblyPath**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-119">**AdapterMgmtAssemblyPath**</span></span>  
  
-   <span data-ttu-id="9a0b9-120">**PropertyNameSpace**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-120">**PropertyNameSpace**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a0b9-121">**OutboundAssemblyPath**と**AdapterMgmtAssemblyPath**ことをお勧めのローカル パスは、プロパティの値に含めないこと、構成が分割される場合にインストールされているさまざまなのでサーバーの場所です。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-121">For **OutboundAssemblyPath** and **AdapterMgmtAssemblyPath** we recommend that you not include the local path in the property value, because the configuration could break when installed on different server locations.</span></span> <span data-ttu-id="9a0b9-122">厳密な名前を使用し、グローバル アセンブリ キャッシュにインストールすることが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-122">A better choice is to use a strong name and install it in the global assembly cache.</span></span>  
  
 <span data-ttu-id="9a0b9-123">受信元アダプター、送信元アダプター、およびアダプター管理を実装する .NET 型を指定するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-123">You have two options for specifying the .NET type that implements the adapter receiver, adapter transmitter, and adapter management:</span></span>  
  
1.  <span data-ttu-id="9a0b9-124">フォルダーに、アダプターをインストールし、指定 * TypeName と\*AssemblyPath を\*TypeName は型です。クラスの FullName および\*AssemblyPath はアセンブリのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-124">Install the adapter to a folder and specify *TypeName and \*AssemblyPath where \*TypeName is type.FullName of the class and \*AssemblyPath is the path and file name of the assembly.</span></span>  
  
2.  <span data-ttu-id="9a0b9-125">グローバル アセンブリ キャッシュにアダプターをインストールし、だけを指定 * TypeName 場所\*TypeName は型です。クラスの AssemblyQualifiedName します。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-125">Install the adapter in the global assembly cache and specify just *TypeName where \*TypeName is type.AssemblyQualifiedName of the class.</span></span> <span data-ttu-id="9a0b9-126">これが推奨されるオプションです。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-126">This is the recommended option.</span></span>  
  
 <span data-ttu-id="9a0b9-127">すべてのアダプターには、GUID が指定されている次のレジストリ キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-127">All adapters must have the following registry keys with the specified GUID:</span></span>  
  
-   <span data-ttu-id="9a0b9-128">**カテゴリを実装\\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-128">**Implemented Categories\\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}**</span></span>  
  
-   <span data-ttu-id="9a0b9-129">**"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-129">**"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"**</span></span>  
  
-   <span data-ttu-id="9a0b9-130">**"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-130">**"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"**</span></span>  
  
-   <span data-ttu-id="9a0b9-131">**"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-131">**"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"**</span></span>  
  
-   <span data-ttu-id="9a0b9-132">**"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"**</span><span class="sxs-lookup"><span data-stu-id="9a0b9-132">**"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"**</span></span>  
  
 <span data-ttu-id="9a0b9-133">アダプター フレームワークに基づいたアダプターは、送信ハンドラー、受信ハンドラー、および場所のプロパティ ページでこれらの固有の GUID を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-133">Adapters based on the adapter framework must use these specific GUIDS for send and receive handler and location property pages.</span></span> <span data-ttu-id="9a0b9-134">アダプターが送信専用のアダプターの場合にだけ必要があることに注意してください、 **OutboundProtocol_PageProv**と**TransmitLocation_PageProv**Guid。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-134">Note that if an adapter is a send-only adapter it just needs the **OutboundProtocol_PageProv**and **TransmitLocation_PageProv**GUIDs.</span></span> <span data-ttu-id="9a0b9-135">同様に、受信専用のアダプターしか必要としない、 **InboundProtocol_PageProv**と**ReceiveLocation_PageProv** Guid。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-135">Similarly a receive-only adapter merely requires the **InboundProtocol_PageProv** and **ReceiveLocation_PageProv** GUIDs.</span></span>  
  
 <span data-ttu-id="9a0b9-136">次のコードは、StaticAdapterManagement.reg ファイルのものですが、DynamicAdapterManagement.reg ファイルのコードもこれとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-136">The following code is from the StaticAdapterManagement.reg file, and the code for the DynamicAdapterManagement.reg file is almost identical.</span></span> <span data-ttu-id="9a0b9-137">各レジストリ プロパティの詳細については、次を参照してください。[アダプターの登録](../core/registering-an-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-137">For more information about each of the registry properties, see [Registering an Adapter](../core/registering-an-adapter.md).</span></span> <span data-ttu-id="9a0b9-138">レジストリ ファイルを変更した場合は、ファイルを保存してから実行します。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-138">After making the changes to the registry file, save the file and run it.</span></span>  
  
```  
Windows Registry Editor Version 5.00  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}]  
@="Static DotNetFile Adapter"  
"AppID"="{12A6EBAA-CF68-4B58-B36E-A5A19B22C04E}"  
  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\BizTalk]  
@="BizTalk"  
"TransportType"="Static DotNetFile"  
"Constraints"=dword:00003C0b  
  
"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"  
"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"  
"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"  
"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"  
  
"InboundEngineCLSID"="{3D4B599E-2202-4bbb-9FC6-7ACA3906E5DE}"  
"InboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileReceiver""InboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll"  
"OutboundEngineCLSID"="{024DB758-AAF9-415e-A121-4AC245DD49EC}"  
"OutboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileTransmitter""OutboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll""AdapterMgmtTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.Designtime.StaticAdapterManagement""AdapterMgmtAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Design Time\\Adapter Management\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Designtime.dll""PropertyNameSpace"="http://schemas.microsoft.com/BizTalk/2003/SDK_Samples/Messaging/Transports/dotnetfile-properties"  
"AliasesXML"="<AdapterAliasList><AdapterAlias>DotNetFILE://</AdapterAlias></AdapterAliasList>"  
"ReceiveHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"ReceiveLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories]  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}]  
```  
  
### <a name="to-register-the-static-sample-adapter"></a><span data-ttu-id="9a0b9-139">サンプルの静的アダプターを登録するには</span><span class="sxs-lookup"><span data-stu-id="9a0b9-139">To register the static sample adapter</span></span>  
  
1.  <span data-ttu-id="9a0b9-140">次の手順を使用して、SDK のファイル アダプター サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-140">Complete the procedure to run the file adapter sample in the SDK.</span></span> <span data-ttu-id="9a0b9-141">詳細については、次を参照してください。[ファイル アダプター (BizTalk Server サンプル)](../core/file-adapter-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-141">For more information, see [File Adapter (BizTalk Server Sample)](../core/file-adapter-biztalk-server-sample.md).</span></span>  
  
2.  <span data-ttu-id="9a0b9-142">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリック**Windows エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-142">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
3.  <span data-ttu-id="9a0b9-143">BizTalk Server のインストール ドライブに移動しに移動し、  **<**  `drive` **>: \Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\SDK\Samples\AdaptersUsage\File アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-143">Navigate to the installation drive for BizTalk Server, and then navigate to **<**`drive`**>:\Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**\SDK\Samples\AdaptersUsage\File Adapter**.</span></span>  
  
4.  <span data-ttu-id="9a0b9-144">サンプル アダプターをレジストリに追加するにはダブルクリック**StaticAdapterManagement.reg**です。(動的ファイル アダプター、レジストリに追加実行する場合**DynamicAdapterManagement.reg**代わりに、そのファイルに適切な使用します)。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-144">To add the sample adapter to the registry, double-click **StaticAdapterManagement.reg**. (If you want to add the dynamic file adapter to the registry run **DynamicAdapterManagement.reg** instead and use that file everywhere else as appropriate.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a0b9-145">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をコンピューターの C ドライブにインストールしなかった場合は、StaticAdapterManagement.reg ファイルを変更して適切なインストール パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-145">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is not installed on drive C of your computer, you must modify the StaticAdapterManagement.reg file with the appropriate installation path.</span></span> <span data-ttu-id="9a0b9-146">C: のファイルを検索し、正しいインストール ドライブで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-146">Search the file for C: and replace it with the correct installation drive.</span></span>  
  
5.  <span data-ttu-id="9a0b9-147">**レジストリ エディター**ダイアログ ボックスで、をクリックして**はい**サンプル アダプターをレジストリに追加し、をクリックする**[ok]**情報がれたことを確認する、ダイアログ ボックスを閉じますレジストリに追加します。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-147">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK** to close the dialog box, verifying that the information was added to the registry.</span></span>  
  
6.  <span data-ttu-id="9a0b9-148">Windows エクスプ ローラーを閉じる、**ファイル** メニューのをクリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-148">To close Windows Explorer, on the **File** menu, click **Close**.</span></span>  
  
     <span data-ttu-id="9a0b9-149">これで、サンプルの静的アダプターが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に登録されました。</span><span class="sxs-lookup"><span data-stu-id="9a0b9-149">The sample static adapter is now registered with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>