---
title: "BizTalk アダプターに、ServiceModel メタデータ ユーティリティ ツールを使用して BizTalk Server での Oracle データベースの |Microsoft ドキュメント"
description: "Svcutil.exe を使用して、既定以外のバインディング、または Oracle データベース アダプターの BizTalk アダプター パック (BAP) と WCF クライアント クラスまたは WCF サービス コントラクトを作成するには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8660014-da04-4692-89e8-f14fcb419496
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dfbdbd60333a2e5683b4f37a65edb928a451e46
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="50ca6-103">Oracle データベースの BizTalk アダプターで、ServiceModel メタデータ ユーティリティ ツールの使用</span><span class="sxs-lookup"><span data-stu-id="50ca6-103">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="50ca6-104">ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用するには、WCF クライアント クラスまたは操作用の WCF サービス コントラクト (インターフェイス) を生成する、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]を公開します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-104">You can use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class or a WCF service contract (interface) for operations that the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes.</span></span> <span data-ttu-id="50ca6-105">WCF クライアント クラスまたは WCF サービス コントラクトのいずれかを生成する svcutil.exe を実行した後、コードで生成されたファイルを含めると、生成されたクラスのインスタンスを作成したり、Oracle で操作を実行するためのコントラクトから WCF サービスを実装データベースです。</span><span class="sxs-lookup"><span data-stu-id="50ca6-105">After you run svcutil.exe to generate either a WCF client class or a WCF service contract, you can include the generated file in your code and create instances of the generated class or implement a WCF service from the contract to perform operations on the Oracle database.</span></span>  
  
 <span data-ttu-id="50ca6-106">Svcutil.exe を使用して、接続の資格情報を含む URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ca6-106">Using svcutil.exe requires you to supply a connection URI that contains credentials.</span></span> <span data-ttu-id="50ca6-107">既定では、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]資格情報を無効に URI の接続での既定以外のバインディングを使用する svcutil.exe を構成する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="50ca6-107">Because, by default, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] disables credentials in the connection URI, you must configure svcutil.exe to use a non-default binding for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="50ca6-108">Svcutil.exe を使用して WCF クライアント コードまたは WCF サービス コントラクトを生成する方法と、svcutil.exe を構成する方法を次のセクションでは、表示、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="50ca6-108">The following sections show you how to configure svcutil.exe and how to use svcutil.exe to generate WCF client code or a WCF service contract with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
##  <a name="BKMK_ConfigureSvcutil"></a><span data-ttu-id="50ca6-109">既定以外のバインディングを svcutil.exe を構成します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-109">Configure svcutil.exe for a non-default binding</span></span>   
 <span data-ttu-id="50ca6-110">既定以外のバインディングを使用する svcutil.exe を構成するのにする必要があります svcutil.exe のローカル コピーを作成し、作成または変更する svcutil.exe.config の構成ファイルのローカル コピーします。</span><span class="sxs-lookup"><span data-stu-id="50ca6-110">To configure svcutil.exe to use a non-default binding, you must create a local copy of svcutil.exe and then create or modify a local copy of the svcutil.exe.config configuration file.</span></span>  
  
1.  <span data-ttu-id="50ca6-111">フォルダーを作成し、svcutil.exe を新しいフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="50ca6-111">Create a folder, and copy svcutil.exe into the new folder.</span></span> <span data-ttu-id="50ca6-112">通常、Windows SDK のインストール場所で svcutil.exe を入手できます C:\Program files \microsoft SDKs\Windows\v6.0\Bin 具体的には、します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-112">You can typically find svcutil.exe at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span></span>  
  
2.  <span data-ttu-id="50ca6-113">新しいフォルダーに svcutil.exe.config という名前のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-113">Create a file named svcutil.exe.config in the new folder.</span></span>  
  
3.  <span data-ttu-id="50ca6-114">Svcutil.exe.config ファイルにバインドし、クライアント エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-114">Add a binding and a client endpoint to the svcutil.exe.config file.</span></span> <span data-ttu-id="50ca6-115">適切な構成が使用されるようにする新しいフォルダーから svcutil.exe を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ca6-115">You must run svcutil.exe from the new folder to ensure that the correct configuration is used.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="50ca6-116">クライアント エンドポイントの name 属性には、接続 URI で使用されるスキームを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ca6-116">The name attribute of the client endpoint must specify the scheme used in the connection URI.</span></span> <span data-ttu-id="50ca6-117">この値は、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="50ca6-117">This value is case-sensitive.</span></span>  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="oracledb"  
                    binding="oracleDBBinding"  
                    bindingConfiguration="OracleDBBinding"  
                    contract="IMetadataExchange" />  
        </client>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" acceptCredentialsInUri="true" />  
            </oracleDBBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="50ca6-118">バインドのプロパティのいずれかを設定することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド構成にします。</span><span class="sxs-lookup"><span data-stu-id="50ca6-118">You can set any of the binding properties of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the binding configuration.</span></span>  
  
 <span data-ttu-id="50ca6-119">Svcutil.exe の既定以外のバインディングを構成する方法の詳細についてを参照してください「カスタム セキュリティで保護されたメタデータのエンドポイント」で、WCF ドキュメント[http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077)です。</span><span class="sxs-lookup"><span data-stu-id="50ca6-119">For more information about configuring a non-default binding for svcutil.exe, see the "Custom Secure Metadata Endpoint" topic in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077).</span></span>  
  
### <a name="configure-a-non-default-binding-for-the-pollingstmt-operation"></a><span data-ttu-id="50ca6-120">既定以外の POLLINGSTMT 操作のバインドを構成します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-120">Configure a Non-Default Binding for the POLLINGSTMT Operation</span></span>  
 <span data-ttu-id="50ca6-121">Svcutil.exe を使用して、POLLINGSTMT 操作用の WCF サービス コントラクトを作成するに含める既定以外のバインディングを構成する必要があります、 **pollingStatement**だけでなく、プロパティ**acceptCredentialsInUri**.</span><span class="sxs-lookup"><span data-stu-id="50ca6-121">To use svcutil.exe to create a WCF service contract for the POLLINGSTMT operation, you must configure the non-default binding to include the **pollingStatement** property, in addition to **acceptCredentialsInUri**.</span></span> <span data-ttu-id="50ca6-122">**PollingStatement**テーブルを対象とする SELECT ステートメントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ca6-122">The **pollingStatement** must contain the SELECT statement that targets the table.</span></span> <span data-ttu-id="50ca6-123">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作によって返されることを厳密に型指定された結果を表すクラスを生成するには、このプロパティの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-123">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses this property to generate the class that represents the strongly-typed result set that the POLLINGSTMT operation returns.</span></span> <span data-ttu-id="50ca6-124">次の例では、/SCOTT/EMP テーブルを対象とする POLLINGSTMT 操作の WCF サービス コントラクトの生成に使用されるバインド構成を示します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-124">The following example shows a binding configuration that is used to generate a WCF service contract for a POLLINGSTMT operation that targets the /SCOTT/EMP table.</span></span>  
  
```  
<bindings>  
    <oracleDBBinding>  
        <binding name="OracleDBBinding" acceptCredentialsInUri="true"   
                                   pollingStatement="SELECT * FROM EMP FOR UPDATE" />  
    </oracleDBBinding>  
</bindings>  
```  
  
## <a name="create-a-wcf-client-class-or-wcf-service-contract-with-svcutilexe"></a><span data-ttu-id="50ca6-125">Svcutil.exe で WCF クライアント クラスまたは WCF サービス コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-125">Create a WCF Client Class or WCF Service Contract with svcutil.exe</span></span>  
 <span data-ttu-id="50ca6-126">WCF クライアント コードまたは WCF サービス コントラクト (インターフェイス) を生成するに svcutil.exe を使用する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、Ws-metadata Exchange (MEX) エンドポイントと、または複数の操作を svcutil.exe の対象となるを指定する URI の接続を指定する必要がありますコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-126">To use svcutil.exe to generate WCF client code or a WCF service contract (interface) for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must supply a connection URI that specifies an WS-Metadata Exchange (MEX) endpoint and the operation or operations for which you want svcutil.exe to generate code.</span></span> <span data-ttu-id="50ca6-127">接続 URI でも、Oracle データベースの接続の資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ca6-127">You must also specify connection credentials for the Oracle database in the connection URI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50ca6-128">Svcutil.exe を使用する前に、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、既定以外の値を使用するように構成する必要がありますバインディングです。 これを行う方法に関する情報を参照してください[Oracle データベース アダプターの svcutil.exe の構成](#BKMK_ConfigureSvcutil)です。</span><span class="sxs-lookup"><span data-stu-id="50ca6-128">Before you can use svcutil.exe with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must configure it to use a non-default binding; for information about how to do this, see [Configuring svcutil.exe for the Oracle Database Adapter](#BKMK_ConfigureSvcutil).</span></span>  
  
 <span data-ttu-id="50ca6-129">MEX エンドポイントとターゲットの操作を指定する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続 URI を次のようにします。</span><span class="sxs-lookup"><span data-stu-id="50ca6-129">You specify a MEX endpoint and target operations in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="50ca6-130">Query_string"wsdl"パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ca6-130">You must include the "wsdl" parameter in the query_string.</span></span> <span data-ttu-id="50ca6-131">クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定されています。</span><span class="sxs-lookup"><span data-stu-id="50ca6-131">If it is the first parameter in the query_string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="50ca6-132">場合は、最初のパラメーターでない場合は、その必要がありますの前に、アンパサンド (&)。</span><span class="sxs-lookup"><span data-stu-id="50ca6-132">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="50ca6-133">1 つまたは複数の"op"パラメーターで、"wsdl"パラメーターに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ca6-133">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="50ca6-134">各"op"パラメーターは、前にアンパサンド (&) し、ターゲットの操作のノード ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-134">Each "op" parameter is preceded by an ampersand (&) and specifies the node ID of a target operation.</span></span>  
  
 <span data-ttu-id="50ca6-135">次の 3 つの例では、svcutil.exe を使用して、さまざまな操作を対象にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-135">The following three examples show how to target various operations by using svcutil.exe.</span></span>  
  
 <span data-ttu-id="50ca6-136">この例では、/SCOTT/EMP テーブルに対して挿入操作の WCF クライアント クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-136">This example creates a WCF client class for an Insert operation on the /SCOTT/EMP table.</span></span>  
  
 <span data-ttu-id="50ca6-137">**.\svcutil "oracledb://User=SCOTT;パスワード=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"**</span><span class="sxs-lookup"><span data-stu-id="50ca6-137">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"**</span></span>  
  
 <span data-ttu-id="50ca6-138">この例では、Insert および/SCOTT/EMP テーブルに対する削除操作の WCF クライアント クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-138">This example creates a WCF client class for the Insert and the Delete operations on the /SCOTT/EMP table.</span></span>  
  
 <span data-ttu-id="50ca6-139">**.\svcutil "oracledb://User=SCOTT;パスワード=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"**</span><span class="sxs-lookup"><span data-stu-id="50ca6-139">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"**</span></span>  
  
 <span data-ttu-id="50ca6-140">この例では、POLLLINGSTMT 操作の WCF サービス コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-140">This example creates a WCF service contract for the POLLLINGSTMT operation.</span></span> <span data-ttu-id="50ca6-141">(POLLINGSTMT 操作の WCF サービス コントラクトの生成に svcutil.exe を使用するには、ポーリング ステートメントを含む svcutil.exe の既定以外のバインディングを構成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="50ca6-141">(To use svcutil.exe to generate a WCF service contract for the POLLINGSTMT operation, you must configure a non-default binding for svcutil.exe that includes a polling statement.)</span></span>  
  
 <span data-ttu-id="50ca6-142">**.\svcutil "oracledb://User=SCOTT;パスワード=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT"**</span><span class="sxs-lookup"><span data-stu-id="50ca6-142">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT"**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="50ca6-143">引用符で囲まれたコマンド ラインで、接続 URI を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ca6-143">You must place the connection URI in quotation marks on the command line.</span></span> <span data-ttu-id="50ca6-144">それ以外の場合、svcutil.exe しようとすると操作のメタデータを取得する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="50ca6-144">Otherwise, svcutil.exe attempts to retrieve metadata for operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support.</span></span> <span data-ttu-id="50ca6-145">これらの試行の結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="50ca6-145">The results of such an attempt are undefined.</span></span>  
  
 <span data-ttu-id="50ca6-146">既定では、svcutil.exe に生成されたコード ファイル内に配置 output.cs です。ただし、出力ファイルの名前を変更して、オプションの他多数のコマンド ライン スイッチを設定して svcutil.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-146">By default, svcutil.exe places the generated code in the output.cs file; however, you can change the name of the output file and many other options that svcutil.exe uses by setting command-line switches.</span></span> <span data-ttu-id="50ca6-147">その svcutil.exe をサポートしているオプションの詳細については、WCF のドキュメント「ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)」を参照してください[http://go.microsoft.com/fwlink/?LinkId=72777](http://go.microsoft.com/fwlink/?LinkId=72777)です。</span><span class="sxs-lookup"><span data-stu-id="50ca6-147">For more information about the options that svcutil.exe supports, see the "ServiceModel Metadata Utility Tool (Svcutil.exe)" topic in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=72777](http://go.microsoft.com/fwlink/?LinkId=72777).</span></span>  
  
 <span data-ttu-id="50ca6-148">Svcutil.exe は、操作 (たとえば、ワイルドカード文字を使用) を検索する機能を提供しません。</span><span class="sxs-lookup"><span data-stu-id="50ca6-148">Svcutil.exe does not provide the capability to search for operations (for example, by using wildcard characters).</span></span> <span data-ttu-id="50ca6-149">対象となる特定の操作のノード Id を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ca6-149">You must explicitly specify node IDs for the specific operations you want to target.</span></span> <span data-ttu-id="50ca6-150">ノードのカテゴリのみを参照している Id を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="50ca6-150">You cannot specify node IDs that refer only to categories.</span></span> <span data-ttu-id="50ca6-151">ノード Id の詳細についてを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスを参照してください[メタデータのノード Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)です。</span><span class="sxs-lookup"><span data-stu-id="50ca6-151">For more information about the node IDs that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span></span>  
  
 <span data-ttu-id="50ca6-152">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]高度な参照が大幅に簡素化に役立つ、WCF クライアント クラスと WCF サービス コントラクトを生成する検索機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="50ca6-152">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] provides advanced browse and search capabilities that can greatly simplify generating a WCF client class and WCF service contract.</span></span> <span data-ttu-id="50ca6-153">詳細については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Oracle データベース ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="50ca6-153">For more information about the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generating a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50ca6-154">参照</span><span class="sxs-lookup"><span data-stu-id="50ca6-154">See Also</span></span>  
 [<span data-ttu-id="50ca6-155">BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="50ca6-155">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)