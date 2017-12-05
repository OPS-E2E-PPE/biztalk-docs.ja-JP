---
title: "BizTalk adapter 用 mySAP Business Suite、ServiceModel メタデータ ユーティリティ ツールを使用して |Microsoft ドキュメント"
description: "Svcutil.exe を使用して、既定以外のバインディングまたは SAP アダプターの BizTalk アダプター パック (BAP) と WCF クライアント クラスまたは WCF サービス コントラクトを作成するには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceModel Metadata Utility Tool, creating a WCF Client Class or a WCF service contract with the tool
- ServiceModel Metadata Utility Tool, configuring the tool for the adapter
ms.assetid: 7ac08012-bb12-4983-9402-be84fe3997d8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15c4612db6e3cde4e46385b1c5d1810fbb00eb70
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="686a2-103">BizTalk adapter 用 mySAP Business Suite、ServiceModel メタデータ ユーティリティ ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="686a2-103">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="686a2-104">ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用するには、WCF クライアント クラスまたは操作用の WCF サービス コントラクト (インターフェイス) を生成する、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]を公開します。</span><span class="sxs-lookup"><span data-stu-id="686a2-104">You can use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class or a WCF service contract (interface) for operations that the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes.</span></span> <span data-ttu-id="686a2-105">WCF クライアント クラスまたは WCF サービス コントラクトのいずれかを生成する svcutil.exe を実行した後、コードで生成されたファイルを含めると、生成されたクラスのインスタンスを作成したり、SAP で操作を実行する、生成されたインターフェイスから WCF サービスを実装システムです。</span><span class="sxs-lookup"><span data-stu-id="686a2-105">After you run svcutil.exe to generate either a WCF client class or a WCF service contract, you can include the generated file in your code and create instances of the generated class or implement a WCF service from the generated interface to perform operations on the SAP system.</span></span>  
  
 <span data-ttu-id="686a2-106">Svcutil.exe を使用して、接続の資格情報を含む URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="686a2-106">Using svcutil.exe requires you to supply a connection URI that contains credentials.</span></span> <span data-ttu-id="686a2-107">既定では、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]資格情報を無効に URI の接続での既定以外のバインディングを使用する svcutil.exe を構成する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="686a2-107">Because, by default, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] disables credentials in the connection URI, you must configure svcutil.exe to use a non-default binding for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="686a2-108">は、既定以外のバインディングでその他のバインドのプロパティを構成することもできますたとえば、BAPI 操作用の WCF クライアントを作成する必要があります設定する、 **EnableSafeTyping**にプロパティのバインド**true**です。</span><span class="sxs-lookup"><span data-stu-id="686a2-108">You can also configure other binding properties in the non-default binding; for example, to create a WCF client for BAPI operations, you must set the **EnableSafeTyping** binding property to **true**.</span></span>  
  
 <span data-ttu-id="686a2-109">Svcutil.exe を使用して WCF クライアント コードまたは WCF サービス コントラクトを生成する方法と、svcutil.exe を構成する方法を次のセクションでは、表示、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="686a2-109">The following sections show you how to configure svcutil.exe and how to use svcutil.exe to generate WCF client code or a WCF service contract with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
##  <a name="BKMK_ConfigureSvcutil"></a><span data-ttu-id="686a2-110">SAP アダプターの svcutil.exe の構成</span><span class="sxs-lookup"><span data-stu-id="686a2-110">Configuring svcutil.exe for the SAP Adapter</span></span>  
 <span data-ttu-id="686a2-111">既定以外のバインディングを使用する svcutil.exe を構成するのにする必要があります svcutil.exe のローカル コピーを作成し、作成または変更する svcutil.exe.config の構成ファイルのローカル コピーします。</span><span class="sxs-lookup"><span data-stu-id="686a2-111">To configure svcutil.exe to use a non-default binding, you must create a local copy of svcutil.exe and then create or modify a local copy of the svcutil.exe.config configuration file.</span></span>  
  
1.  <span data-ttu-id="686a2-112">フォルダーを作成し、svcutil.exe を新しいフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="686a2-112">Create a folder, and copy svcutil.exe into the new folder.</span></span> <span data-ttu-id="686a2-113">通常、Windows SDK のインストール場所で svcutil.exe を入手できます C:\Program files \microsoft SDKs\Windows\v6.0\Bin 具体的には、します。</span><span class="sxs-lookup"><span data-stu-id="686a2-113">You can typically find svcutil.exe at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span></span>  
  
2.  <span data-ttu-id="686a2-114">新しいフォルダーに svcutil.exe.config という名前のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="686a2-114">Create a file named svcutil.exe.config in the new folder.</span></span>  
  
3.  <span data-ttu-id="686a2-115">Svcutil.exe.config ファイルにバインドし、クライアント エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="686a2-115">Add a binding and a client endpoint to the svcutil.exe.config file.</span></span> <span data-ttu-id="686a2-116">適切な構成が使用されるようにする新しいフォルダーから svcutil.exe を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="686a2-116">You must run svcutil.exe from the new folder to ensure that the correct configuration is used.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="686a2-117">クライアント エンドポイントの name 属性には、接続 URI で使用されるスキームを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="686a2-117">The name attribute of the client endpoint must specify the scheme used in the connection URI.</span></span> <span data-ttu-id="686a2-118">この値は、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="686a2-118">This value is case-sensitive.</span></span>  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="sap"  
                    binding="sapBinding"  
                    bindingConfiguration="SAPBinding"  
                    contract="IMetadataExchange" />  
        </client>  
        <bindings>  
          <sapBinding>  
            <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
          </sapBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
 <span data-ttu-id="686a2-119">バインドのプロパティのいずれかを設定することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインド構成にします。</span><span class="sxs-lookup"><span data-stu-id="686a2-119">You can set any of the binding properties of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in the binding configuration.</span></span> <span data-ttu-id="686a2-120">たとえば、svcutil.exe を使用して BAPI 操作用の WCF クライアントを生成する次の既定以外のバインディングを指定できます。</span><span class="sxs-lookup"><span data-stu-id="686a2-120">For example, you could specify the following non-default binding to use svcutil.exe to generate a WCF client for BAPI operations.</span></span>  
  
```  
<bindings>  
  <sapBinding>  
    <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
  </sapBinding>  
</bindings>  
```  
  
 <span data-ttu-id="686a2-121">Svcutil.exe の既定以外のバインディングを構成する方法の詳細については、次を参照してください。、[カスタム セキュリティで保護されたメタデータ エンドポイント](https://msdn.microsoft.com/library/aa395212.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="686a2-121">For more information about configuring a non-default binding for svcutil.exe, see the [Custom Secure Metadata Endpoint](https://msdn.microsoft.com/library/aa395212.aspx).</span></span>
  
## <a name="creating-a-wcf-client-class-or-a-wcf-service-contract-with-svcutilexe"></a><span data-ttu-id="686a2-122">Svcutil.exe で WCF クライアント クラスまたは WCF サービス コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="686a2-122">Creating a WCF Client Class or a WCF Service Contract with svcutil.exe</span></span>  
 <span data-ttu-id="686a2-123">WCF クライアント コードまたは WCF サービス コントラクト (インターフェイス) を生成するに svcutil.exe を使用する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、Ws-metadata Exchange (MEX) エンドポイントと、または複数の操作を svcutil.exe の対象となるを指定する URI の接続を指定する必要がありますコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="686a2-123">To use svcutil.exe to generate WCF client code or a WCF service contract (interface) for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must supply a connection URI that specifies a WS-Metadata Exchange (MEX) endpoint and the operation or operations for which you want svcutil.exe to generate code.</span></span> <span data-ttu-id="686a2-124">接続 URI でも、SAP システムの接続の資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="686a2-124">You must also specify connection credentials for the SAP system in the connection URI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="686a2-125">Svcutil.exe を使用する前に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、既定以外の値を使用するように構成する必要がありますバインディングです。 これを行う方法に関する情報を参照してください[SAP アダプターの svcutil.exe の構成](#BKMK_ConfigureSvcutil)です。</span><span class="sxs-lookup"><span data-stu-id="686a2-125">Before you can use svcutil.exe with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must configure it to use a non-default binding; for information about how to do this, see [Configuring svcutil.exe for the SAP Adapter](#BKMK_ConfigureSvcutil).</span></span>  
  
 <span data-ttu-id="686a2-126">MEX エンドポイントとターゲットの操作を指定する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続 URI を次のようにします。</span><span class="sxs-lookup"><span data-stu-id="686a2-126">You specify a MEX endpoint and target operations in the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="686a2-127">クエリ文字列には、"wsdl"パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="686a2-127">You must include the "wsdl" parameter in the query string.</span></span> <span data-ttu-id="686a2-128">クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定されています。</span><span class="sxs-lookup"><span data-stu-id="686a2-128">If it is the first parameter in the query string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="686a2-129">場合は、最初のパラメーターでない場合は、その必要がありますの前に、アンパサンド (&)。</span><span class="sxs-lookup"><span data-stu-id="686a2-129">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="686a2-130">1 つまたは複数の"op"パラメーターで、"wsdl"パラメーターに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="686a2-130">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="686a2-131">各"op"パラメーターは、前にアンパサンド (&) し、ターゲットの操作のノード ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="686a2-131">Each "op" parameter is preceded by an ampersand (&) and specifies the node ID of a target operation.</span></span>  
  
 <span data-ttu-id="686a2-132">次の 3 つの例では、svcutil.exe を使用して、さまざまな操作を対象にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="686a2-132">The following three examples show how to target various operations by using svcutil.exe.</span></span>  
  
 <span data-ttu-id="686a2-133">この例では、RFC_CALCULATE_TAXES の WCF クライアント クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="686a2-133">This example creates a WCF client class for RFC_CALCULATE_TAXES.</span></span>  
  
 <span data-ttu-id="686a2-134">**。 \svcutil"sap://User=YourUserName;Passwd 貼り付けたり; を =クライアント = 800 です。Lang = EN です。@a/YourSAPHost/00? wsdl & op http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES を ="**</span><span class="sxs-lookup"><span data-stu-id="686a2-134">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**</span></span>  
  
 <span data-ttu-id="686a2-135">この例では、SALESORDER_CREATEFROMDAT201 と SALESORDER_CREATEFROMDAT202 IDOC の両方の WCF クライアント クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="686a2-135">This example creates a WCF client class for both the SALESORDER_CREATEFROMDAT201 and SALESORDER_CREATEFROMDAT202 IDOC.</span></span>  
  
 <span data-ttu-id="686a2-136">**。 \svcutil"sap://User=YourUserName;Passwd 貼り付けたり; を =クライアント = 800 です。Lang = EN です。@a/YourSAPHost/00? wsdl & op = http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send & op http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send を ="**</span><span class="sxs-lookup"><span data-stu-id="686a2-136">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**</span></span>  
  
 <span data-ttu-id="686a2-137">この例では、SAP システムから SALESORDER_CREATEFROMDAT201 IDOC を受信する WCF サービス コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="686a2-137">This example creates a WCF service contract to receive the SALESORDER_CREATEFROMDAT201 IDOC from the SAP system.</span></span> <span data-ttu-id="686a2-138">ノード ID では、受信操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="686a2-138">The NODE ID specifies a Receive operation.</span></span> <span data-ttu-id="686a2-139">この例は、メタデータの取得時に処理をするため、接続 URI の query_string でリスナーのパラメーターを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="686a2-139">Because this example deals with retrieving metadata, there is no need to specify the listener parameters in the query_string of the connection URI.</span></span>  
  
 <span data-ttu-id="686a2-140">**。 \svcutil"sap://User=YourUserName;Passwd 貼り付けたり; を =クライアント = 800 です。Lang = EN です。@a/YourSAPHost/00? wsdl & op http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive を ="**</span><span class="sxs-lookup"><span data-stu-id="686a2-140">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="686a2-141">引用符で囲まれたコマンド ラインで、接続 URI を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="686a2-141">You must place the connection URI in quotation marks on the command line.</span></span> <span data-ttu-id="686a2-142">それ以外の場合、svcutil.exe しようとすると操作のメタデータを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="686a2-142">Otherwise, svcutil.exe attempts to retrieve metadata for operations that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support.</span></span> <span data-ttu-id="686a2-143">これらの試行の結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="686a2-143">The results of such an attempt are undefined.</span></span>  
  
 <span data-ttu-id="686a2-144">既定では、svcutil.exe に生成されたコード ファイル内に配置 output.cs です。ただし、出力ファイルの名前を変更して、オプションの他多数のコマンド ライン スイッチを設定して svcutil.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="686a2-144">By default, svcutil.exe places the generated code in the output.cs file; however, you can change the name of the output file and many other options that svcutil.exe uses by setting command-line switches.</span></span> <span data-ttu-id="686a2-145">オプションの詳細については、svcutil.exe がサポートするを参照してください、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="686a2-145">For more information about the options that svcutil.exe supports, see the [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).</span></span>
  
 <span data-ttu-id="686a2-146">Svcutil.exe は、操作 (たとえば、ワイルドカード文字を使用) を検索する機能を提供しません。</span><span class="sxs-lookup"><span data-stu-id="686a2-146">Svcutil.exe does not provide the capability to search for operations (for example, by using wildcard characters).</span></span> <span data-ttu-id="686a2-147">対象となる特定の操作のノード Id を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="686a2-147">You must explicitly specify node IDs for the specific operations you want to target.</span></span> <span data-ttu-id="686a2-148">操作のノード ID は、メッセージ アクション文字列に相当します。</span><span class="sxs-lookup"><span data-stu-id="686a2-148">The node ID of an operation is equivalent to its message action string.</span></span> <span data-ttu-id="686a2-149">ノードのカテゴリのみを参照している Id を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="686a2-149">You cannot specify node IDs that refer only to categories.</span></span> <span data-ttu-id="686a2-150">ノード Id の詳細についてを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスを参照してください[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。</span><span class="sxs-lookup"><span data-stu-id="686a2-150">For more information about the node IDs that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
 <span data-ttu-id="686a2-151">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]高度な参照が大幅に簡素化に役立つ、WCF クライアント クラスと WCF サービス コントラクトを生成する検索機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="686a2-151">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] provides advanced browse and search capabilities that can greatly simplify generating a WCF client class and WCF service contract.</span></span> <span data-ttu-id="686a2-152">詳細については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="686a2-152">For more information about the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
