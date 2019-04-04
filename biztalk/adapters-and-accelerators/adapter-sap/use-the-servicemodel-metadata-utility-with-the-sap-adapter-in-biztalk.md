---
title: BizTalk adapter for mySAP Business Suite、ServiceModel メタデータ ユーティリティ ツールを使用して |Microsoft Docs
description: Svcutil.exe を使用して、既定以外のバインディングまたは SAP アダプターの BizTalk アダプター パック (BAP) と WCF クライアント クラスまたは WCF サービス コントラクトを作成するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ServiceModel Metadata Utility Tool, creating a WCF Client Class or a WCF service contract with the tool
- ServiceModel Metadata Utility Tool, configuring the tool for the adapter
ms.assetid: 7ac08012-bb12-4983-9402-be84fe3997d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a8bdbf2a3b3a3c359a4c3e4912e2b6e18928023
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003179"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-mysap-business-suite"></a>BizTalk adapter for mySAP Business Suite、ServiceModel メタデータ ユーティリティ ツールを使用してください。
ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して WCF クライアント クラスまたは操作用の WCF サービス コントラクト (インターフェイス) を生成することができる[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]を公開します。 WCF クライアント クラスまたは WCF サービス コントラクトを生成する svcutil.exe を実行した後、コードで生成されたファイルを含めると、生成されたクラスのインスタンスを作成したり、SAP の操作を実行する生成されたインターフェイスから WCF サービスの実装システム。  
  
 Svcutil.exe を使用して、接続の資格情報を含む URI を指定する必要があります。 既定で、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]資格情報を無効にします。 URI の接続での既定以外のバインディングを使用して svcutil.exe を構成する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 既定以外のバインディング; で他のバインドのプロパティを構成することもできます。たとえば、BAPI 操作の WCF クライアントを作成する必要があります設定する、 **EnableSafeTyping**プロパティをバインド**true**します。  
  
 Svcutil.exe を構成する方法と svcutil.exe を使用して、WCF クライアント コードまたは WCF サービスのコントラクトを生成する方法を次のセクションでは、表示、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
##  <a name="BKMK_ConfigureSvcutil"></a> SAP アダプターの svcutil.exe の構成  
 既定以外のバインディングを使用して svcutil.exe で構成するには、必要があります svcutil.exe のローカル コピーを作成し、作成または変更する svcutil.exe.config 構成ファイルのローカル コピーを。  
  
1. フォルダーを作成し、svcutil.exe を新しいフォルダーにコピーします。 通常、Windows SDK のインストール場所で svcutil.exe を入手できます C:\Program files \microsoft SDKs\Windows\v6.0\Bin 具体的には、します。  
  
2. 新しいフォルダーに svcutil.exe.config という名前のファイルを作成します。  
  
3. Svcutil.exe.config ファイルには、バインディング、およびクライアント エンドポイントを追加します。 Svcutil.exe は、適切な構成が使用されるようにする新しいフォルダーから実行する必要があります。  
  
   > [!IMPORTANT]
   >  クライアント エンドポイントの name 属性には、接続 URI で使用するスキームを指定する必要があります。 この値は、大文字と小文字が区別されます。  
  
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
  
   バインドのプロパティのいずれかを設定することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインド構成にします。 たとえば、svcutil.exe を使用して、BAPI 操作用の WCF クライアントを生成する次の既定以外のバインディングを指定できます。  
  
```  
<bindings>  
  <sapBinding>  
    <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
  </sapBinding>  
</bindings>  
```  
  
 Svcutil.exe の既定以外のバインディングを構成する方法の詳細については、、[メタデータ エンドポイントのセキュリティで保護されたカスタム](https://msdn.microsoft.com/library/aa395212.aspx)を参照してください。
  
## <a name="creating-a-wcf-client-class-or-a-wcf-service-contract-with-svcutilexe"></a>Svcutil.exe で WCF クライアント クラスまたは WCF サービス コントラクトを作成します。  
 Svcutil.exe を使用しての WCF クライアント コードまたは WCF サービス コントラクト (インターフェイス) を生成する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、Ws-metadata Exchange (MEX) エンドポイントと操作、または svcutil.exe に操作を指定する URI の接続を指定する必要がありますコードを生成します。 接続 URI の SAP システムの接続の資格情報を指定することも必要があります。  
  
> [!NOTE]
>  Svcutil.exe を使用する前に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、既定以外の値を使用するように構成する必要がありますバインディングです。 これを行う方法に関する情報を参照してください[SAP アダプターの svcutil.exe の構成](#BKMK_ConfigureSvcutil)します。  
  
 MEX エンドポイントとターゲットの操作を指定する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続 URI を次のようにします。  
  
- クエリ文字列で"wsdl"パラメーターを含める必要があります。 クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定します。 最初のパラメーターではない場合、アンパサンドを付ける必要があります (&)。  
  
- 1 つまたは複数の"op"パラメーターで"wsdl"パラメーターに従う必要があります。 各"op"パラメーターは、前にアンパサンド (&) を対象の操作のノード ID を指定します。  
  
  次の 3 つの例では、svcutil.exe を使用してさまざまな操作を対象にする方法を示します。  
  
  この例では、RFC_CALCULATE_TAXES の WCF クライアント クラスを作成します。  
  
  **.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**  
  
  この例では、SALESORDER_CREATEFROMDAT201 と SALESORDER_CREATEFROMDAT202 IDOC の両方の WCF クライアント クラスを作成します。  
  
  **.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**  
  
  この例では、SAP システムから SALESORDER_CREATEFROMDAT201 IDOC を受信する WCF サービス コントラクトを作成します。 ノード ID では、受信操作を指定します。 この例では、メタデータの取得を処理、するために、接続 URI の query_string リスナーのパラメーターを指定する必要はありません。  
  
  **.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**  
  
> [!IMPORTANT]
>  コマンドラインで引用符では、接続 URI を配置する必要があります。 Svcutil.exe が操作のメタデータを取得しようとした場合を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]はサポートしていません。 このような試行の結果は未定義です。  
  
 既定では、svcutil.exe は output.cs ファイル内で生成されたコードを配置します。ただし、出力ファイルの名前を変更して、他の多くのオプションを svcutil.exe は、コマンド ライン スイッチを設定して使用します。 その svcutil.exe のサポート オプションの詳細についてを参照してください、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)します。
  
 Svcutil.exe は、操作 (たとえば、ワイルドカード文字を使用) を検索する機能を提供していません。 ノード Id を対象とする特定の操作を明示的に指定する必要があります。 操作のノード ID は、メッセージ アクション文字列と同じです。 ノード カテゴリだけを参照する Id を指定することはできません。 ノード Id の詳細についてを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスを参照してください[メタデータ ノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)します。  
  
 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]高度な参照と WCF クライアント クラスと WCF サービス コントラクトを生成する大幅に簡略化できる検索機能を提供します。 詳細については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。  
  
