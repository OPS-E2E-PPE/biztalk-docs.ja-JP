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
ms.openlocfilehash: 143fefc3a35f70e08a9e1288cc019fe6561c2bb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-oracle-database"></a>Oracle データベースの BizTalk アダプターで、ServiceModel メタデータ ユーティリティ ツールの使用
ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用するには、WCF クライアント クラスまたは操作用の WCF サービス コントラクト (インターフェイス) を生成する、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]を公開します。 WCF クライアント クラスまたは WCF サービス コントラクトのいずれかを生成する svcutil.exe を実行した後、コードで生成されたファイルを含めると、生成されたクラスのインスタンスを作成したり、Oracle で操作を実行するためのコントラクトから WCF サービスを実装データベースです。  
  
 Svcutil.exe を使用して、接続の資格情報を含む URI を指定する必要があります。 既定では、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]資格情報を無効に URI の接続での既定以外のバインディングを使用する svcutil.exe を構成する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
 Svcutil.exe を使用して WCF クライアント コードまたは WCF サービス コントラクトを生成する方法と、svcutil.exe を構成する方法を次のセクションでは、表示、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
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
          \<!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
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
  
      \</system.serviceModel>  
  
    </configuration>  
    ```  
  
> [!NOTE]
>  バインドのプロパティのいずれかを設定することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド構成にします。  
  
 Svcutil.exe の既定以外のバインディングを構成する方法の詳細についてを参照してください「カスタム セキュリティで保護されたメタデータのエンドポイント」で、WCF ドキュメント[http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077)です。  
  
### <a name="configure-a-non-default-binding-for-the-pollingstmt-operation"></a>既定以外の POLLINGSTMT 操作のバインドを構成します。  
 Svcutil.exe を使用して、POLLINGSTMT 操作用の WCF サービス コントラクトを作成するに含める既定以外のバインディングを構成する必要があります、 **pollingStatement**だけでなく、プロパティ**acceptCredentialsInUri**. **PollingStatement**テーブルを対象とする SELECT ステートメントを含める必要があります。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作によって返されることを厳密に型指定された結果を表すクラスを生成するには、このプロパティの設定を使用します。 次の例では、/SCOTT/EMP テーブルを対象とする POLLINGSTMT 操作の WCF サービス コントラクトの生成に使用されるバインド構成を示します。  
  
```  
<bindings>  
    <oracleDBBinding>  
        <binding name="OracleDBBinding" acceptCredentialsInUri="true"   
                                   pollingStatement="SELECT * FROM EMP FOR UPDATE" />  
    </oracleDBBinding>  
</bindings>  
```  
  
## <a name="create-a-wcf-client-class-or-wcf-service-contract-with-svcutilexe"></a>Svcutil.exe で WCF クライアント クラスまたは WCF サービス コントラクトを作成します。  
 WCF クライアント コードまたは WCF サービス コントラクト (インターフェイス) を生成するに svcutil.exe を使用する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、Ws-metadata Exchange (MEX) エンドポイントと、または複数の操作を svcutil.exe の対象となるを指定する URI の接続を指定する必要がありますコードを生成します。 接続 URI でも、Oracle データベースの接続の資格情報を指定する必要があります。  
  
> [!NOTE]
>  Svcutil.exe を使用する前に、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、既定以外の値を使用するように構成する必要がありますバインディングです。 これを行う方法に関する情報を参照してください[Oracle データベース アダプターの svcutil.exe の構成](#BKMK_ConfigureSvcutil)です。  
  
 MEX エンドポイントとターゲットの操作を指定する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続 URI を次のようにします。  
  
-   Query_string"wsdl"パラメーターを含める必要があります。 クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定されています。 場合は、最初のパラメーターでない場合は、その必要がありますの前に、アンパサンド (&)。  
  
-   1 つまたは複数の"op"パラメーターで、"wsdl"パラメーターに従う必要があります。 各"op"パラメーターは、前にアンパサンド (&) し、ターゲットの操作のノード ID を指定します。  
  
 次の 3 つの例では、svcutil.exe を使用して、さまざまな操作を対象にする方法を示します。  
  
 この例では、/SCOTT/EMP テーブルに対して挿入操作の WCF クライアント クラスを作成します。  
  
 **.\svcutil "oracledb://User=SCOTT;パスワード=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"**  
  
 この例では、Insert および/SCOTT/EMP テーブルに対する削除操作の WCF クライアント クラスを作成します。  
  
 **.\svcutil "oracledb://User=SCOTT;パスワード=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"**  
  
 この例では、POLLLINGSTMT 操作の WCF サービス コントラクトを作成します。 (POLLINGSTMT 操作の WCF サービス コントラクトの生成に svcutil.exe を使用するには、ポーリング ステートメントを含む svcutil.exe の既定以外のバインディングを構成する必要があります)。  
  
 **.\svcutil "oracledb://User=SCOTT;パスワード=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT"**  
  
> [!IMPORTANT]
>  引用符で囲まれたコマンド ラインで、接続 URI を配置する必要があります。 それ以外の場合、svcutil.exe しようとすると操作のメタデータを取得する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はサポートしていません。 これらの試行の結果は未定義です。  
  
 既定では、svcutil.exe に生成されたコード ファイル内に配置 output.cs です。ただし、出力ファイルの名前を変更して、オプションの他多数のコマンド ライン スイッチを設定して svcutil.exe を使用します。 その svcutil.exe をサポートしているオプションの詳細については、WCF のドキュメント「ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)」を参照してください[http://go.microsoft.com/fwlink/?LinkId=72777](http://go.microsoft.com/fwlink/?LinkId=72777)です。  
  
 Svcutil.exe は、操作 (たとえば、ワイルドカード文字を使用) を検索する機能を提供しません。 対象となる特定の操作のノード Id を明示的に指定する必要があります。 ノードのカテゴリのみを参照している Id を指定することはできません。 ノード Id の詳細についてを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスを参照してください[メタデータのノード Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)です。  
  
 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]高度な参照が大幅に簡素化に役立つ、WCF クライアント クラスと WCF サービス コントラクトを生成する検索機能を提供します。 詳細については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Oracle データベース ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)