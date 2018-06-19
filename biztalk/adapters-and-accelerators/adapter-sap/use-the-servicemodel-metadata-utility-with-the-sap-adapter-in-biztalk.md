---
title: BizTalk adapter 用 mySAP Business Suite、ServiceModel メタデータ ユーティリティ ツールを使用して |Microsoft ドキュメント
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
ms.openlocfilehash: 15c4612db6e3cde4e46385b1c5d1810fbb00eb70
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "25962768"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-mysap-business-suite"></a>BizTalk adapter 用 mySAP Business Suite、ServiceModel メタデータ ユーティリティ ツールを使用します。
ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用するには、WCF クライアント クラスまたは操作用の WCF サービス コントラクト (インターフェイス) を生成する、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]を公開します。 WCF クライアント クラスまたは WCF サービス コントラクトのいずれかを生成する svcutil.exe を実行した後、コードで生成されたファイルを含めると、生成されたクラスのインスタンスを作成したり、SAP で操作を実行する、生成されたインターフェイスから WCF サービスを実装システムです。  
  
 Svcutil.exe を使用して、接続の資格情報を含む URI を指定する必要があります。 既定では、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]資格情報を無効に URI の接続での既定以外のバインディングを使用する svcutil.exe を構成する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 は、既定以外のバインディングでその他のバインドのプロパティを構成することもできますたとえば、BAPI 操作用の WCF クライアントを作成する必要があります設定する、 **EnableSafeTyping**にプロパティのバインド**true**です。  
  
 Svcutil.exe を使用して WCF クライアント コードまたは WCF サービス コントラクトを生成する方法と、svcutil.exe を構成する方法を次のセクションでは、表示、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
##  <a name="BKMK_ConfigureSvcutil"></a> SAP アダプターの svcutil.exe の構成  
 既定以外のバインディングを使用する svcutil.exe を構成するのにする必要があります svcutil.exe のローカル コピーを作成し、作成または変更する svcutil.exe.config の構成ファイルのローカル コピーします。  
  
1.  フォルダーを作成し、svcutil.exe を新しいフォルダーにコピーします。 通常、Windows SDK のインストール場所で svcutil.exe を入手できます C:\Program files \microsoft SDKs\Windows\v6.0\Bin 具体的には、します。  
  
2.  新しいフォルダーに svcutil.exe.config という名前のファイルを作成します。  
  
3.  Svcutil.exe.config ファイルにバインドし、クライアント エンドポイントを追加します。 適切な構成が使用されるようにする新しいフォルダーから svcutil.exe を実行する必要があります。  
  
    > [!IMPORTANT]
    >  クライアント エンドポイントの name 属性には、接続 URI で使用されるスキームを指定する必要があります。 この値は、大文字と小文字が区別されます。  
  
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
  
 バインドのプロパティのいずれかを設定することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインド構成にします。 たとえば、svcutil.exe を使用して BAPI 操作用の WCF クライアントを生成する次の既定以外のバインディングを指定できます。  
  
```  
<bindings>  
  <sapBinding>  
    <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
  </sapBinding>  
</bindings>  
```  
  
 Svcutil.exe の既定以外のバインディングを構成する方法の詳細については、次を参照してください。、[カスタム セキュリティで保護されたメタデータ エンドポイント](https://msdn.microsoft.com/library/aa395212.aspx)です。
  
## <a name="creating-a-wcf-client-class-or-a-wcf-service-contract-with-svcutilexe"></a>Svcutil.exe で WCF クライアント クラスまたは WCF サービス コントラクトを作成します。  
 WCF クライアント コードまたは WCF サービス コントラクト (インターフェイス) を生成するに svcutil.exe を使用する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、Ws-metadata Exchange (MEX) エンドポイントと、または複数の操作を svcutil.exe の対象となるを指定する URI の接続を指定する必要がありますコードを生成します。 接続 URI でも、SAP システムの接続の資格情報を指定する必要があります。  
  
> [!NOTE]
>  Svcutil.exe を使用する前に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、既定以外の値を使用するように構成する必要がありますバインディングです。 これを行う方法に関する情報を参照してください[SAP アダプターの svcutil.exe の構成](#BKMK_ConfigureSvcutil)です。  
  
 MEX エンドポイントとターゲットの操作を指定する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続 URI を次のようにします。  
  
-   クエリ文字列には、"wsdl"パラメーターを含める必要があります。 クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定されています。 場合は、最初のパラメーターでない場合は、その必要がありますの前に、アンパサンド (&)。  
  
-   1 つまたは複数の"op"パラメーターで、"wsdl"パラメーターに従う必要があります。 各"op"パラメーターは、前にアンパサンド (&) し、ターゲットの操作のノード ID を指定します。  
  
 次の 3 つの例では、svcutil.exe を使用して、さまざまな操作を対象にする方法を示します。  
  
 この例では、RFC_CALCULATE_TAXES の WCF クライアント クラスを作成します。  
  
 **.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**  
  
 この例では、SALESORDER_CREATEFROMDAT201 と SALESORDER_CREATEFROMDAT202 IDOC の両方の WCF クライアント クラスを作成します。  
  
 **.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**  
  
 この例では、SAP システムから SALESORDER_CREATEFROMDAT201 IDOC を受信する WCF サービス コントラクトを作成します。 ノード ID では、受信操作を指定します。 この例は、メタデータの取得時に処理をするため、接続 URI の query_string でリスナーのパラメーターを指定する必要はありません。  
  
 **.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**  
  
> [!IMPORTANT]
>  引用符で囲まれたコマンド ラインで、接続 URI を配置する必要があります。 それ以外の場合、svcutil.exe しようとすると操作のメタデータを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]はサポートしていません。 これらの試行の結果は未定義です。  
  
 既定では、svcutil.exe に生成されたコード ファイル内に配置 output.cs です。ただし、出力ファイルの名前を変更して、オプションの他多数のコマンド ライン スイッチを設定して svcutil.exe を使用します。 オプションの詳細については、svcutil.exe がサポートするを参照してください、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)です。
  
 Svcutil.exe は、操作 (たとえば、ワイルドカード文字を使用) を検索する機能を提供しません。 対象となる特定の操作のノード Id を明示的に指定する必要があります。 操作のノード ID は、メッセージ アクション文字列に相当します。 ノードのカテゴリのみを参照している Id を指定することはできません。 ノード Id の詳細についてを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスを参照してください[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。  
  
 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]高度な参照が大幅に簡素化に役立つ、WCF クライアント クラスと WCF サービス コントラクトを生成する検索機能を提供します。 詳細については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
