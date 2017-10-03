---
title: "BizTalk adapter 用 Siebel eBusiness Applications ServiceModel メタデータ ユーティリティ ツールを使用して |Microsoft ドキュメント"
description: "Svcutil.exe を使用して、既定以外のバインディングまたは Siebel アダプターの BizTalk アダプター パック (BAP) と WCF クライアント クラスまたは WCF サービス コントラクトを作成するには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03d16481-cc8b-4e28-a33c-92e48a9a7e8f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0c2c016387f6b70870e04b211b0bdfe047de11d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a>BizTalk adapter 用 Siebel eBusiness Applications ServiceModel メタデータ ユーティリティ ツールを使用します。
ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用するには操作のための WCF クライアント クラスを生成すること、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]を公開します。 WCF クライアント クラスを生成する svcutil.exe を実行した後は、コードで生成されたファイルをインクルードし、Siebel システムに対して操作を実行する WCF クライアント クラスのインスタンスを作成できます。  
  
 Svcutil.exe を使用して、接続の資格情報を含む URI を指定する必要があります。 既定では、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]資格情報を無効に URI の接続での既定以外のバインディングを使用する svcutil.exe を構成する必要があります、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 既定以外のバインディングでその他のバインドのプロパティを構成することもできます。  
  
 Svcutil.exe を構成する方法と svcutil.exe を使用して、WCF クライアント コードを生成する方法を次のセクションでは、表示、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
##  <a name="BKMK_ConfigureSvcutil"></a>既定以外のバインディングを svcutil.exe を構成します。   
 既定以外のバインディングを使用する svcutil.exe を構成するのにする必要があります svcutil.exe のローカル コピーを作成し、作成または変更する svcutil.exe.config の構成ファイルのローカル コピーします。  
  
 
1.  フォルダーを作成し、svcutil.exe を新しいフォルダーにコピーします。 通常、Windows SDK のインストール場所で svcutil.exe を入手できます C:\Program files \microsoft SDKs\Windows\v6.0\Bin 具体的には、します。  
  
2.  新しいフォルダーに svcutil.exe.config という名前のファイルを作成します。  
  
3.  Svcutil.exe.config ファイルにバインドし、クライアント エンドポイントを追加します。 適切な構成が使用されるようにする新しいフォルダーから svcutil.exe を実行する必要があります。  
  
    > [!IMPORTANT]
    >  クライアント エンドポイントの name 属性には、接続 URI で使用されるスキームを指定する必要があります。 この値は、大文字と小文字が区別されます。  
  
    ```  
    <configuration>  
      \<system.serviceModel>  
        <client>  
          \<!-- the name should match the required scheme of the Metadata Exchange endpoint   
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
  
      \</system.serviceModel>  
  
    </configuration>  
  
    ```  
  
> [!NOTE]
>  バインドのプロパティのいずれかを設定することができます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインド構成にします。  
  
 Svcutil.exe の既定以外のバインディングを構成する方法の詳細についてを参照してください「カスタム セキュリティで保護されたメタデータのエンドポイント」で、WCF ドキュメント[http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077)です。  
  
## <a name="creating-a-wcf-client-class-with-svcutilexe"></a>Svcutil.exe で WCF クライアント クラスを作成します。  
 WCF クライアント コードを生成する svcutil.exe を使用する、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、接続を指定する URI を指定する必要があります、 **IMetadataExchange** (mex) エンドポイントと操作の対象となる svcutil.exe を生成するにはコードです。 Siebel システムの接続の資格情報は、接続 URI でも指定する必要があります。  
  
> [!NOTE]
>  Svcutil.exe を使用する前に、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、既定以外の値を使用するように構成する必要がありますバインディングです。 これを行う方法に関する情報を参照してください[Siebel アダプターの svcutil.exe の構成](#BKMK_ConfigureSvcutil)です。  
  
 Mex エンドポイントとターゲットの操作を指定する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]接続 URI を次のようにします。  
  
-   Query_string"wsdl"パラメーターを含める必要があります。 クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定されています。 場合は、最初のパラメーターでない場合は、その必要がありますの前に、アンパサンド (&)。  
  
-   1 つまたは複数の"op"パラメーターで、"wsdl"パラメーターに従う必要があります。 各"op"パラメーターは、前にアンパサンド (&) し、ターゲットの操作のノード ID を指定します。  
  
 次の 2 つの例では、svcutil.exe を使用して、さまざまな操作を対象にする方法を示します。  
  
 この例では、ACCOUNT\ACCOUNT ビジネス オブジェクトの挿入操作の WCF クライアント クラスを作成します。  
  
 **。 \svcutil"siebel://Username=YourUserName;パスワード =YourPassword@Siebel_server:1234しますか?SiebelEnterpriseServer = ent_server & SiebelObjectManager = obj_mgr & 言語日本語 & wsdl op を = = http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"**  
  
 この例では、挿入操作と ACCOUNT\ACCOUNT ビジネス オブジェクトの削除操作の両方の WCF クライアント クラスを作成します。  
  
 **。 \svcutil"siebel://Username=YourUserName;パスワード =YourPassword@Siebel_server:1234しますか?SiebelEnterpriseServer = ent_server & SiebelObjectManager = obj_mgr & 言語日本語 & wsdl op を = = http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert & op http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete を ="**  
  
> [!IMPORTANT]
>  引用符で囲まれたコマンド ラインで、接続 URI を配置する必要があります。 それ以外の場合、svcutil.exe しようとすると操作のメタデータを取得する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]はサポートしていません。 これらの試行の結果は未定義です。  
  
 既定では、svcutil.exe に生成されたコード ファイル内に配置 output.cs です。ただし、出力ファイルの名前を変更して、オプションの他多数のコマンド ライン スイッチを設定して svcutil.exe を使用します。  
  
 Svcutil.exe は、操作 (たとえば、ワイルドカード文字を使用) を検索する機能を提供しません。 対象となる特定の操作のノード Id を明示的に指定する必要があります。 ノードのカテゴリのみを参照している Id を指定することはできません。 ノード Id の詳細についてを[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェスを参照してください[メタデータのノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)です。  
  
 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]高度な参照が大幅に簡素化に役立つ WCF クライアント クラスを生成する検索機能を提供します。 詳細については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[WCF クライアントまたは Siebel ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)です。  
  
