---
title: BizTalk アダプターを使用した、ServiceModel メタデータ ユーティリティ ツールを使用して BizTalk Server での Oracle データベースの |Microsoft Docs
description: Svcutil.exe を使用して、既定以外のバインディングまたは Oracle DB アダプターの BizTalk アダプター パック (BAP) と WCF クライアント クラスまたは WCF サービス コントラクトを作成するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8660014-da04-4692-89e8-f14fcb419496
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fe432c9cf7e586269f85beb5f584bbe2aa37210
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999363"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-oracle-database"></a>BizTalk adapter for Oracle Database、ServiceModel メタデータ ユーティリティ ツールを使用します。
ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して WCF クライアント クラスまたは操作用の WCF サービス コントラクト (インターフェイス) を生成することができる[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]を公開します。 WCF クライアント クラスまたは WCF サービス コントラクトを生成する svcutil.exe を実行した後、コードで生成されたファイルを含めると、生成されたクラスのインスタンスを作成したり、Oracle での操作を実行する、コントラクトから WCF サービスの実装データベース。  
  
 Svcutil.exe を使用して、接続の資格情報を含む URI を指定する必要があります。 既定で、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]資格情報を無効にします。 URI の接続での既定以外のバインディングを使用して svcutil.exe を構成する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
 Svcutil.exe を構成する方法と svcutil.exe を使用して、WCF クライアント コードまたは WCF サービスのコントラクトを生成する方法を次のセクションでは、表示、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
##  <a name="BKMK_ConfigureSvcutil"></a> 既定以外のバインディングの svcutil.exe を構成します。   
 既定以外のバインディングを使用して svcutil.exe で構成するには、必要があります svcutil.exe のローカル コピーを作成し、作成または変更する svcutil.exe.config 構成ファイルのローカル コピーを。  
  
1.  フォルダーを作成し、svcutil.exe を新しいフォルダーにコピーします。 通常、Windows SDK のインストール場所で svcutil.exe を入手できます C:\Program files \microsoft SDKs\Windows\v6.0\Bin 具体的には、します。  
  
2.  新しいフォルダーに svcutil.exe.config という名前のファイルを作成します。  
  
3.  Svcutil.exe.config ファイルには、バインディング、およびクライアント エンドポイントを追加します。 Svcutil.exe は、適切な構成が使用されるようにする新しいフォルダーから実行する必要があります。  
  
    > [!IMPORTANT]
    >  クライアント エンドポイントの name 属性には、接続 URI で使用するスキームを指定する必要があります。 この値は、大文字と小文字が区別されます。  
  
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
>  バインドのプロパティのいずれかを設定することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド構成にします。  
  
 Svcutil.exe の既定以外のバインディングを構成する方法の詳細については、WCF ドキュメントの「カスタム セキュリティで保護されたメタデータのエンドポイント」トピックを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077)します。  
  
### <a name="configure-a-non-default-binding-for-the-pollingstmt-operation"></a>既定以外の POLLINGSTMT 操作のバインディングを構成します。  
 Svcutil.exe を使用して、POLLINGSTMT 操作の WCF サービス コントラクトを作成する、含める既定以外のバインディングを構成する必要があります、 **pollingStatement**プロパティのほかに、 **acceptCredentialsInUri**. **PollingStatement**テーブルを対象とする SELECT ステートメントを含める必要があります。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作によって返されることを厳密に型指定された結果を表すクラスを生成するには、このプロパティの設定を使用します。 次の例では、/SCOTT/EMP テーブルを対象とする POLLINGSTMT 操作の WCF サービス コントラクトを生成するために使用するバインド構成を示します。  
  
```  
<bindings>  
    <oracleDBBinding>  
        <binding name="OracleDBBinding" acceptCredentialsInUri="true"   
                                   pollingStatement="SELECT * FROM EMP FOR UPDATE" />  
    </oracleDBBinding>  
</bindings>  
```  
  
## <a name="create-a-wcf-client-class-or-wcf-service-contract-with-svcutilexe"></a>Svcutil.exe で WCF クライアント クラスまたは WCF サービス コントラクトを作成します。  
 Svcutil.exe を使用しての WCF クライアント コードまたは WCF サービス コントラクト (インターフェイス) を生成する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、Ws-metadata Exchange (MEX) エンドポイントと操作、または svcutil.exe に操作を指定する URI の接続を指定する必要がありますコードを生成します。 接続 URI で Oracle データベースの接続の資格情報を指定することも必要があります。  
  
> [!NOTE]
>  Svcutil.exe を使用する前に、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、既定以外の値を使用するように構成する必要がありますバインディングです。 これを行う方法に関する情報を参照してください[、Oracle データベース アダプターの svcutil.exe の構成](#BKMK_ConfigureSvcutil)します。  
  
 MEX エンドポイントとターゲットの操作を指定する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続 URI を次のようにします。  
  
- Query_string"wsdl"パラメーターを含める必要があります。 クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定します。 最初のパラメーターではない場合、アンパサンドを付ける必要があります (&)。  
  
- 1 つまたは複数の"op"パラメーターで"wsdl"パラメーターに従う必要があります。 各"op"パラメーターは、前にアンパサンド (&) を対象の操作のノード ID を指定します。  
  
  次の 3 つの例では、svcutil.exe を使用してさまざまな操作を対象にする方法を示します。  
  
  この例では、/SCOTT/EMP テーブルに対する挿入操作の WCF クライアント クラスを作成します。  
  
  **。 \svcutil"oracledb://User=SCOTT;パスワード =TIGER@ADAPTER? wsdl & op =http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"**  
  
  この例では、挿入および/SCOTT/EMP テーブルに対する削除操作の WCF クライアント クラスを作成します。  
  
  **。 \svcutil"oracledb://User=SCOTT;パスワード =TIGER@ADAPTER? wsdl & op =http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"**  
  
  この例では、POLLLINGSTMT 操作の WCF サービス コントラクトを作成します。 (Svcutil.exe を使用して、POLLINGSTMT 操作の WCF サービス コントラクトを生成する、ポーリング ステートメントを含む svcutil.exe の既定以外のバインディングを構成する必要があります)。  
  
  **。 \svcutil"oracledb://User=SCOTT;パスワード =TIGER@ADAPTER? wsdl & op =http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT"**  
  
> [!IMPORTANT]
>  コマンドラインで引用符では、接続 URI を配置する必要があります。 Svcutil.exe が操作のメタデータを取得しようとした場合を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はサポートしていません。 このような試行の結果は未定義です。  
  
 既定では、svcutil.exe は output.cs ファイル内で生成されたコードを配置します。ただし、出力ファイルの名前を変更して、他の多くのオプションを svcutil.exe は、コマンド ライン スイッチを設定して使用します。 その svcutil.exe のサポート オプションの詳細については、WCF のドキュメント「ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=72777](http://go.microsoft.com/fwlink/?LinkId=72777)します。  
  
 Svcutil.exe は、操作 (たとえば、ワイルドカード文字を使用) を検索する機能を提供していません。 ノード Id を対象とする特定の操作を明示的に指定する必要があります。 ノード カテゴリだけを参照する Id を指定することはできません。 ノード Id の詳細についてを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスを参照してください[メタデータ ノード Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)します。  
  
 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]高度な参照と WCF クライアント クラスと WCF サービス コントラクトを生成する大幅に簡略化できる検索機能を提供します。 詳細については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Oracle データベース ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)