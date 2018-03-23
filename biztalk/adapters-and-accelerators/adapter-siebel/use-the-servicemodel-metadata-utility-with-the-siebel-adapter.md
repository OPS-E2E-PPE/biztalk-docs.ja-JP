---
title: BizTalk adapter 用 Siebel eBusiness Applications ServiceModel メタデータ ユーティリティ ツールを使用して |Microsoft ドキュメント
description: Svcutil.exe を使用して、既定以外のバインディングまたは Siebel アダプターの BizTalk アダプター パック (BAP) と WCF クライアント クラスまたは WCF サービス コントラクトを作成するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03d16481-cc8b-4e28-a33c-92e48a9a7e8f
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bcf80d4a1ea9fc6b54403faa14084816e413be
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="57a99-103">BizTalk adapter 用 Siebel eBusiness Applications ServiceModel メタデータ ユーティリティ ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="57a99-103">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="57a99-104">ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用するには操作のための WCF クライアント クラスを生成すること、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]を公開します。</span><span class="sxs-lookup"><span data-stu-id="57a99-104">You can use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class for operations that the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes.</span></span> <span data-ttu-id="57a99-105">WCF クライアント クラスを生成する svcutil.exe を実行した後は、コードで生成されたファイルをインクルードし、Siebel システムに対して操作を実行する WCF クライアント クラスのインスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="57a99-105">After you run svcutil.exe to generate a WCF client class, you can include the generated file in your code and create instances of the WCF client class to perform operations on the Siebel system.</span></span>  
  
 <span data-ttu-id="57a99-106">Svcutil.exe を使用して、接続の資格情報を含む URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a99-106">Using svcutil.exe requires you to supply a connection URI that contains credentials.</span></span> <span data-ttu-id="57a99-107">既定では、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]資格情報を無効に URI の接続での既定以外のバインディングを使用する svcutil.exe を構成する必要があります、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="57a99-107">Because, by default, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] disables credentials in the connection URI, you must configure svcutil.exe to use a non-default binding for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="57a99-108">既定以外のバインディングでその他のバインドのプロパティを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="57a99-108">You can also configure other binding properties in the non-default binding.</span></span>  
  
 <span data-ttu-id="57a99-109">Svcutil.exe を構成する方法と svcutil.exe を使用して、WCF クライアント コードを生成する方法を次のセクションでは、表示、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="57a99-109">The following sections show you how to configure svcutil.exe and how to use svcutil.exe to generate WCF client code with the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
##  <a name="BKMK_ConfigureSvcutil"></a><span data-ttu-id="57a99-110">既定以外のバインディングを svcutil.exe を構成します。</span><span class="sxs-lookup"><span data-stu-id="57a99-110">Configure svcutil.exe for a non-default binding</span></span>   
 <span data-ttu-id="57a99-111">既定以外のバインディングを使用する svcutil.exe を構成するのにする必要があります svcutil.exe のローカル コピーを作成し、作成または変更する svcutil.exe.config の構成ファイルのローカル コピーします。</span><span class="sxs-lookup"><span data-stu-id="57a99-111">To configure svcutil.exe to use a non-default binding, you must create a local copy of svcutil.exe and then create or modify a local copy of the svcutil.exe.config configuration file.</span></span>  
  
 
1.  <span data-ttu-id="57a99-112">フォルダーを作成し、svcutil.exe を新しいフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="57a99-112">Create a folder, and copy svcutil.exe into the new folder.</span></span> <span data-ttu-id="57a99-113">通常、Windows SDK のインストール場所で svcutil.exe を入手できます C:\Program files \microsoft SDKs\Windows\v6.0\Bin 具体的には、します。</span><span class="sxs-lookup"><span data-stu-id="57a99-113">You can typically find svcutil.exe at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span></span>  
  
2.  <span data-ttu-id="57a99-114">新しいフォルダーに svcutil.exe.config という名前のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="57a99-114">Create a file named svcutil.exe.config in the new folder.</span></span>  
  
3.  <span data-ttu-id="57a99-115">Svcutil.exe.config ファイルにバインドし、クライアント エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="57a99-115">Add a binding and a client endpoint to the svcutil.exe.config file.</span></span> <span data-ttu-id="57a99-116">適切な構成が使用されるようにする新しいフォルダーから svcutil.exe を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a99-116">You must run svcutil.exe from the new folder to ensure that the correct configuration is used.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="57a99-117">クライアント エンドポイントの name 属性には、接続 URI で使用されるスキームを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a99-117">The name attribute of the client endpoint must specify the scheme used in the connection URI.</span></span> <span data-ttu-id="57a99-118">この値は、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="57a99-118">This value is case-sensitive.</span></span>  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <!-- the name should match the required scheme of the Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="siebel"  
            binding="siebelBinding"  
            bindingConfiguration="SiebelBinding"  
            contract="IMetadataExchange" />  
        </client>  
        <bindings>  
          <siebelBinding>  
            <binding name="SiebelBinding" acceptCredentialsInUri="true" />  
          </siebelBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="57a99-119">バインドのプロパティのいずれかを設定することができます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインド構成にします。</span><span class="sxs-lookup"><span data-stu-id="57a99-119">You can set any of the binding properties of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in the binding configuration.</span></span>  
  
 <span data-ttu-id="57a99-120">Svcutil.exe の既定以外のバインディングを構成する方法の詳細についてを参照してください「カスタム セキュリティで保護されたメタデータのエンドポイント」で、WCF ドキュメント[ http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077)です。</span><span class="sxs-lookup"><span data-stu-id="57a99-120">For more information about configuring a non-default binding for svcutil.exe, see the "Custom Secure Metadata Endpoint" topic in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077).</span></span>  
  
## <a name="creating-a-wcf-client-class-with-svcutilexe"></a><span data-ttu-id="57a99-121">Svcutil.exe で WCF クライアント クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="57a99-121">Creating a WCF Client Class with svcutil.exe</span></span>  
 <span data-ttu-id="57a99-122">WCF クライアント コードを生成する svcutil.exe を使用する、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、接続を指定する URI を指定する必要があります、 **IMetadataExchange** (mex) エンドポイントと操作の対象となる svcutil.exe を生成するにはコードです。</span><span class="sxs-lookup"><span data-stu-id="57a99-122">To use svcutil.exe to generate WCF client code for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], you must supply a connection URI that specifies an **IMetadataExchange** (mex) endpoint and the operation or operations for which you want svcutil.exe to generate code.</span></span> <span data-ttu-id="57a99-123">Siebel システムの接続の資格情報は、接続 URI でも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a99-123">You must also specify connection credentials for the Siebel system in the connection URI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57a99-124">Svcutil.exe を使用する前に、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、既定以外の値を使用するように構成する必要がありますバインディングです。 これを行う方法に関する情報を参照してください[Siebel アダプターの svcutil.exe の構成](#BKMK_ConfigureSvcutil)です。</span><span class="sxs-lookup"><span data-stu-id="57a99-124">Before you can use svcutil.exe with the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], you must configure it to use a non-default binding; for information about how to do this, see [Configuring svcutil.exe for the Siebel Adapter](#BKMK_ConfigureSvcutil).</span></span>  
  
 <span data-ttu-id="57a99-125">Mex エンドポイントとターゲットの操作を指定する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]接続 URI を次のようにします。</span><span class="sxs-lookup"><span data-stu-id="57a99-125">You specify a mex endpoint and target operations in the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="57a99-126">Query_string"wsdl"パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a99-126">You must include the "wsdl" parameter in the query_string.</span></span> <span data-ttu-id="57a99-127">クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定されています。</span><span class="sxs-lookup"><span data-stu-id="57a99-127">If it is the first parameter in the query_string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="57a99-128">場合は、最初のパラメーターでない場合は、その必要がありますの前に、アンパサンド (&)。</span><span class="sxs-lookup"><span data-stu-id="57a99-128">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="57a99-129">1 つまたは複数の"op"パラメーターで、"wsdl"パラメーターに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a99-129">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="57a99-130">各"op"パラメーターは、前にアンパサンド (&) し、ターゲットの操作のノード ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="57a99-130">Each "op" parameter is preceded by an ampersand (&) and specifies the node ID of a target operation.</span></span>  
  
 <span data-ttu-id="57a99-131">次の 2 つの例では、svcutil.exe を使用して、さまざまな操作を対象にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="57a99-131">The following two examples show how to target various operations by using svcutil.exe.</span></span>  
  
 <span data-ttu-id="57a99-132">この例では、ACCOUNT\ACCOUNT ビジネス オブジェクトの挿入操作の WCF クライアント クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="57a99-132">This example creates a WCF client class for an insert operation on the ACCOUNT\ACCOUNT Business Object.</span></span>  
  
 <span data-ttu-id="57a99-133">**.\svcutil "siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"**</span><span class="sxs-lookup"><span data-stu-id="57a99-133">**.\svcutil "siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"**</span></span>  
  
 <span data-ttu-id="57a99-134">この例では、挿入操作と ACCOUNT\ACCOUNT ビジネス オブジェクトの削除操作の両方の WCF クライアント クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="57a99-134">This example creates a WCF client class for both an insert operation and a delete operation on the ACCOUNT\ACCOUNT Business Object.</span></span>  
  
 <span data-ttu-id="57a99-135">**。 \svcutil"siebel://Username=YourUserName;パスワード =YourPassword@Siebel_server:1234しますか?SiebelEnterpriseServer = ent_server & SiebelObjectManager = obj_mgr & 言語日本語 & wsdl op を = =http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete"**</span><span class="sxs-lookup"><span data-stu-id="57a99-135">**.\svcutil " siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete"**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="57a99-136">引用符で囲まれたコマンド ラインで、接続 URI を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a99-136">You must place the connection URI in quotation marks on the command line.</span></span> <span data-ttu-id="57a99-137">それ以外の場合、svcutil.exe しようとすると操作のメタデータを取得する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="57a99-137">Otherwise, svcutil.exe attempts to retrieve metadata for operations that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not support.</span></span> <span data-ttu-id="57a99-138">これらの試行の結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="57a99-138">The results of such an attempt are undefined.</span></span>  
  
 <span data-ttu-id="57a99-139">既定では、svcutil.exe に生成されたコード ファイル内に配置 output.cs です。ただし、出力ファイルの名前を変更して、オプションの他多数のコマンド ライン スイッチを設定して svcutil.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="57a99-139">By default, svcutil.exe places the generated code in the output.cs file; however, you can change the name of the output file and many other options that svcutil.exe uses by setting command-line switches.</span></span>  
  
 <span data-ttu-id="57a99-140">Svcutil.exe は、操作 (たとえば、ワイルドカード文字を使用) を検索する機能を提供しません。</span><span class="sxs-lookup"><span data-stu-id="57a99-140">Svcutil.exe does not provide the capability to search for operations (for example, by using wildcard characters).</span></span> <span data-ttu-id="57a99-141">対象となる特定の操作のノード Id を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a99-141">You must explicitly specify node IDs for the specific operations you want to target.</span></span> <span data-ttu-id="57a99-142">ノードのカテゴリのみを参照している Id を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="57a99-142">You cannot specify node IDs that refer only to categories.</span></span> <span data-ttu-id="57a99-143">ノード Id の詳細についてを[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェスを参照してください[メタデータのノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)です。</span><span class="sxs-lookup"><span data-stu-id="57a99-143">For more information about the node IDs that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>  
  
 <span data-ttu-id="57a99-144">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]高度な参照が大幅に簡素化に役立つ WCF クライアント クラスを生成する検索機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="57a99-144">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] provides advanced browse and search capabilities that can greatly simplify generating a WCF client class.</span></span> <span data-ttu-id="57a99-145">詳細については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[WCF クライアントまたは Siebel ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="57a99-145">For more information about the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for Siebel solution artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span></span>  
  
