---
title: "SELECT ステートメントを使用してポーリング Oracle E-business Suite |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81d70b36-8b80-4ab9-b97c-ee861aafbbac
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83e5b40d8176b8e4ba448cadf1676013db8f2706
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="poll-oracle-e-business-suite-using-select-statement"></a>SELECT ステートメントを使用してポーリング Oracle E-business Suite
構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージを受信するデータの定期的な変更を継続的にインターフェイスのテーブルをポーリングする SELECT ステートメントを使用して、ビュー、テーブルおよびビュー Oracle E-business suite のインターフェイスです。 Oracle E-business Suite をポーリングするアダプターが定期的に実行されるポーリング ステートメントと SELECT ステートメントを指定できます。 後の投票 PL/SQL コード ブロックを指定することも、アダプターが、ポーリング ステートメントが実行された後に実行されます。  
  
 ポーリングを有効にするには、受信ポートの Wcf-custom または Wcf-oracleebs の特定のバインディング プロパティを指定する必要があります。  アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。 ポーリング操作用の SOAP メッセージの構造については、次を参照してください。[ポーリング操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md)です。  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>Oracle E-business Suite アダプターのバインドのプロパティとポーリング操作を構成します。  
 次の表、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]データを受信するアダプターの構成に使用するバインドのプロパティがメッセージを変更します。 受信ポートを構成するときにこれらのバインディング プロパティを指定する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
|プロパティのバインド|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|実行するかどうかを示す**ポーリング**または**通知**操作を受信します。 既定値は**ポーリング**です。|  
|**PolledDataAvailableStatement**|すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 レコードがある場合にのみ、SELECT ステートメントを指定するため、 **PollingInput**プロパティのバインドが実行されます。|  
|**PollingInterval**|秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔では、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプター休止状態に入ります残り時間の間隔。|  
|**PollingInput**|ポーリング ステートメントを指定します。 SELECT ステートメントを使用してポーリングを行うには、このバインディングのプロパティの SELECT ステートメントを指定する必要があります。 既定値は null です。<br /><br /> 値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。|  
|**PollingAction**|ポーリング操作のアクションを指定します。 使用して、操作を生成するメタデータから特定の操作についてのポーリング動作を指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。|  
|**PostPollStatement**|指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。|  
|**PollWhileDataFound**|指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータで使用できる場合、テーブルをポーリングするポーリング ステートメントを実行します。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。 既定値は false です。|  
  
 これらのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。 使用する方法の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]さらに、Oracle データベースをポーリングするには、読み取る。  
  
## <a name="how-this-topic-demonstrates-polling"></a>このトピックの内容がポーリングを示しています  
 このトピックの内容を示すために方法、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] SELECT ステートメントを使用してメッセージを変更する、BizTalk プロジェクトを作成およびのスキーマを生成するデータの受信をサポート、**ポーリング**ポーリングするテーブル操作。 スキーマを生成する、このトピックでは、**ポーリング**の操作、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルに、**アプリケーション オブジェクト ライブラリ**アプリケーションです。 次の表は、Oracle E-business Suite でこれらのオブジェクトを作成するサンプルに用意されている create_apps_artifacts.sql スクリプトを実行するときに作成されます。  
  
 次に、コンテンツ ベースのルーティング (CBR) で使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]からポーリング メッセージを受信する受信ポートでアプリケーションを構成する、 **MS_SAMPLE_EMPLOYEE**インターフェイスのテーブル、および送信ポートにルーティングします。 この場合、受信場所を指定し、メッセージは送信ポートにルーティングをチェックする送信ポートにフィルターを作成します。  
  
 ポーリング操作を示すためは、次を操作します。  
  
-   SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所のインターフェイス テーブルでポーリング (MS_SAMPLE_EMPLOYEE) を決定するプロパティをバインドします。 この例では、このバインディングのプロパティとしてを設定できます。  
  
    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     これにより、MS_SAMPLE_EMPLOYEE インターフェイス テーブルにレコードの一部がある場合にのみ、アダプターが、ポーリング ステートメントを実行します。  
  
-   SELECT ステートメントを指定、 **PollingInput**プロパティをバインドします。 このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のすべての行を取得します。 この例では、このバインディングのプロパティとしてを設定できます。  
  
    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  
  
    > [!NOTE]
    >  SELECT ステートメントで使用される FOR UPDATE 句の詳細については、次を参照してください。 [SELECT ステートメントを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)です。  
  
-   一部として、DELETE ステートメントを指定、 **PostPollStatement**プロパティをバインドします。 このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのデータを削除します。 この例では、このバインディングのプロパティとしてを設定できます。  
  
    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     指定されたステートメントが次回こうなる**PollingInput**は実行すると、それはフェッチできませんすべてのデータ。  
  
-   多くのデータは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加される、まで、ポーリングのすべてのメッセージは取得しません。 そのため、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要があります。 サンプルに用意されている insert_apps_data.sql スクリプトを実行して、これを行うことができます。 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。  
  
## <a name="how-to-receive-data-change-messages-from-oracle-e-business-suite"></a>Oracle E-business Suite からのデータ変更メッセージを受信する方法  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている次の手順のタスクでは、 [Oracle E-business Suite アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)です。 これらのタスクは、SELECT ステートメントを使用して Oracle E-business Suite をポーリングするアダプターを構成するのには。  
  
1.  BizTalk プロジェクトを作成しのスキーマを生成、**ポーリング**インターフェイス テーブルをポーリングする操作。  
  
2.  構築し、BizTalk プロジェクトを展開します。  
  
3.  BizTalk アプリケーションを作成して受信し、送信ポートを構成します。 さらに、受信ポートに指定された受信場所を確認し、ポーリング メッセージは送信ポートにルーティングできるように、送信ポートにフィルターを追加します。  
  
    > [!IMPORTANT]
    >  受信のポーリングのシナリオが常に設定する必要がありますの一方向の受信ポート。 双方向受信ポートが受信操作のサポートされていません。  
  
4.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、PollingUsingSelectStatement、このトピックの内容に基づくは、BizTalk Adapter Pack でも提供されます。 詳細については、次を参照してください。[サンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルの操作では、**アプリケーション オブジェクト ライブラリ**アプリケーションです。 使用して、スキーマの生成中に、次のタスクを実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
-   コントラクトの種類を選択して**サービス (入力方向の操作)**です。  
  
-   スキーマを生成、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。 操作と選択インターフェイス テーブルのいずれかから、**アプリケーション ベースのビュー**ノードまたは**成果物のベースのビュー**ノード。  
  
 スキーマを生成する方法の詳細については、次を参照してください。[参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)です。  
  
## <a name="building-and-deploying-the-biztalk-project"></a>ビルドと、BizTalk プロジェクトを配置します。  
 BizTalk ソリューションをビルドし、BizTalk Server に展開する必要がありますようになりました。 BizTalk Server にソリューションを展開する方法の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 BizTalk プロジェクトを配置した後、アプリケーションに表示される、**アプリケーション**BizTalk Server 管理コンソール内のノードです。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションの構成の一環としては、アプリケーションでは、受信ポートと送信ポートを作成し、受信ポートからのすべてのメッセージが送信ポートにルーティングされるように、送信ポートにフィルターを追加する必要があります。  
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   受信し、送信ポートを作成します。  
  
### <a name="creating-a-receive-port"></a>作成する、受信ポート  
 WCF カスタムを作成する必要がありますまたは Wcf-oracleebs 一方向受信ポートの指定した SELECT ステートメントを使用して oracle データベースをポーリングする、 **PollingInput**プロパティをバインドします。 作成する方法については、受信ポートを参照してください[Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)です。 受信ポートを作成中に次のバインドのプロパティを指定することを確認します。  
  
 **ポーリング**  
  
|プロパティのバインド|値|  
|----------------------|-----------|  
|**InboundOperationType**|これを設定して**ポーリング**です。|  
|**PolledDataAvailableStatement**|この例このバインドのプロパティを設定します。<br /><br /> `SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE`|  
|**PollingAction**|生成スキーマからポーリング アクションを取得、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。 この例では、このプロパティ バインディングを**InterfaceTables/ポーリング/ヘルプ/アプリケーション/MS_SAMPLE_EMPLOYEE**です。|  
|**PollingInput**|このバインド プロパティの MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのレコードを取得する SELECT ステートメントを指定します。 この例このバインドのプロパティを設定します。<br /><br /> `SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE`|  
|**PostPollStatement**|MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのデータを削除するポーリング後ステートメントを指定します。 この例このバインドのプロパティを設定します。<br /><br /> `DELETE FROM MS_SAMPLE_EMPLOYEE`|  
  
 **アプリケーション コンテキストを設定します。**  
  
 Oracle E-business Suite の成果物の操作を実行する場合は、アプリケーションのコンテキストを設定する適切なバインド プロパティの値を指定する必要があります。 アプリケーション コンテキストおよびアプリケーションのコンテキストの設定に必要なバインドのプロパティの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
 この例では、適切な値を指定、 **oracleUserName**、 **oraclePassword**、および**oracleEBSResponsibility**プロパティをバインドします。  
  
> [!NOTE]
>  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧め、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 受信ポートを構成するときに、サービスの動作を追加することによって行うことができます。 サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成と Oracle E-business Suite でのトランザクション タイムアウト](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)です。  
  
### <a name="creating-a-send-port"></a>送信ポートの作成  
 ハード_ディスク上の場所を定義し、対応する FILE 送信ポートを作成、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Oracle からのメッセージをドロップします。 これらのメッセージは、受信ポートの指定したポーリング ステートメントへの応答になります。 送信ポートを作成する方法については、次を参照してください。 [Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)です。  
  
 受信場所から、送信ポートでメッセージをルーティングするフィルターを追加する必要がありますもします。 送信ポートにフィルターを追加します。  
  
1.  送信ポートを開くにはダブルクリックして、**送信ポートのプロパティ** ダイアログ ボックス。  
  
2.  **送信ポートのプロパティ**ダイアログ ボックスで、をクリックして、**フィルター**タブです。  
  
3.  次の値を指定します。  
  
    -   **プロパティ**一覧で、クリックして**BTS です。ReceivePortName**です。  
  
    -   **演算子**一覧で、クリックして **==**です。  
  
    -   **値**フィールドに、受信ポート名を指定します。  
  
4.  **送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle E-business Suite をポーリングするための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   Wcf-custom または Wcf-oracleebs 一方向の受信ポートの指定した SELECT ステートメントを使用して oracle データベースをポーリングする、 **PollingInput**バインディング プロパティが実行されています。  
  
-   Oracle データベースからメッセージを受信する FILE 送信ポートが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、次の一連のアクションが実行と同じ順序で。  
  
-   アダプターが実行、 **PolledDataAvailableStatement**アダプターに指定されたステートメントを実行することを示す正の値が返されます**PollingInput**プロパティをバインドします。  
  
-   アダプターの SELECT ステートメントの実行、 **PollingInput** MS_SAMPLE_EMPLOYEE インターフェイス テーブルでのバインディング プロパティ、およびすべての行を返します。 Oracle E-business Suite からの応答には、次のようになります。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Poll xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">   
      <DATA>   
        <SelectRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">   
         <EMP_NO>10002</EMP_NO>   
         <NAME>JEFF PRICE</NAME>   
         <DESIGNATION>MANAGER</DESIGNATION>   
         <SALARY>25000</SALARY>   
         <JOIN_DATE>2007-12-15T00:00:00</JOIN_DATE>   
        </SelectRecord>   
        <SelectRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">   
         <EMP_NO>10003</EMP_NO>   
         <NAME>DON HALL</NAME>   
         <DESIGNATION>ACCOUNTANT</DESIGNATION>   
         <SALARY>12000</SALARY>   
         <JOIN_DATE>2005-10-29T00:00:00</JOIN_DATE>   
        </SelectRecord>   
        …        
        <SelectRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">   
         …   
        </SelectRecord>   
        …   
      </DATA>   
    </Poll>  
    ```  
  
-   アダプターでは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのデータを削除するポーリング後ステートメントを実行します。  
  
-   ポーリング間隔後に、アダプターがもう一度実行される**PolledDataAvailableStatement**です。 MS_SAMPLE_EMPLOYEE インターフェイス テーブルにはレコードがあるないようになりました、ため**PolledDataAvailableStatement**は正の値を返さないため、アダプターに指定されたステートメントを実行できませんし、 **PollingInput**プロパティをバインドします。 その結果、アダプターのクライアントは、ポーリング メッセージを取得できません。  
  
-   レコードの一部は明示的に MS_SAMPLE_EMPLOYEE インターフェイス テーブルに挿入されるまで、アダプターのクライアントは、これ以上ポーリング メッセージを取得できません。 複数のレコードを挿入するには、サンプルに用意されている insert_apps_data.sql スクリプトを実行できます。 次に、このスクリプトを実行した後**PolledDataAvailableStatement**が実行すると、正の値を返します。 結果として、アダプターがポーリング ステートメントを実行し、アダプターのクライアントが再度ポーリング メッセージを受信します。  
  
> [!NOTE]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はポーリングから受信ポートを明示的に無効にするまで引き続き、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、および受信ポートを送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business Suite でアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して Oracle E-business Suite のポーリング](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)