---
title: SELECT ステートメントを使用してポーリング Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81d70b36-8b80-4ab9-b97c-ee861aafbbac
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1eda3c0afb5998485977efddb8a69d47ed4b92a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015421"
---
# <a name="poll-oracle-e-business-suite-using-select-statement"></a>SELECT ステートメントを使用してポーリング Oracle E-business Suite
構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を継続的に、インターフェイス テーブルをポーリングする SELECT ステートメントを使用して、定期的なデータ変更メッセージを受信するビュー、テーブル、および Oracle E-business Suite でのビューのインターフェイスします。 Oracle E-business Suite をポーリングするアダプターを定期的に実行するポーリング ステートメントと SELECT ステートメントを指定できます。 ポスト ポーリング PL/SQL コード ブロックを指定することも、アダプターがポーリング ステートメントが実行された後に実行します。  

 ポーリングを有効にするには、Wcf-custom または Wcf-oracleebs 特定のバインド プロパティの受信ポートを指定する必要があります。  アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)します。 ポーリング操作用の SOAP メッセージの構造については、次を参照してください。[ポーリング操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md)します。  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>Oracle E-business Suite アダプターのバインドのプロパティをポーリング操作を構成します。  
 次の表にまとめたものです、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージのバインドのプロパティを使用するデータを受信するアダプターの構成を変更します。 受信ポートを構成するときにこれらのバインドのプロパティを指定する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  


|         プロパティのバインド         |                                                                                                                                                                                                                            説明                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                          実行するかどうかを指定します**ポーリング**または**通知**操作を受信します。 既定値は**ポーリング**します。                                                                                                                                                                          |
| **PolledDataAvailableStatement** |                                                                                                             すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 指定した SELECT ステートメントのレコードを使用できる場合にのみ、 **PollingInput**プロパティのバインドが実行されます。                                                                                                              |
|       **PollingInterval**        | 秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔は、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプターが間隔内の残りの時間の間スリープします。 |
|         **PollingInput**         |                         ポーリング ステートメントを指定します。 SELECT ステートメントを使用してポーリングする、このバインドのプロパティの SELECT ステートメントを指定する必要があります。 既定値は null です。<br /><br /> 値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。                          |
|        **PollingAction**         |                                                                                                    ポーリング操作のアクションを指定します。 特定の操作を使用して、操作を生成するメタデータからのポーリング アクションを決定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。                                                                                                     |
|      **PostPollStatement**       |                                                                                                                                                                  指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。                                                                                                                                                                  |
|      **PollWhileDataFound**      |                                    指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータがポーリングされるテーブルで使用できる場合に、ポーリング ステートメントを実行します。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。 既定値は false です。                                     |

 これらのプロパティの詳細については、次を参照してください。 [for Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。 使用する方法の詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースをポーリングするさらに読み進める。  

## <a name="how-this-topic-demonstrates-polling"></a>このトピックでポーリングしていますか  
 示すために、このトピックでどのように[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]データの受信をサポートは、SELECT ステートメントを使用してメッセージを変更、BizTalk プロジェクトを作成し、スキーマを生成、**ポーリング**ポーリングするテーブルの操作。 このトピックでのスキーマを生成、**ポーリング**の操作、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルで、**アプリケーション オブジェクト ライブラリ**アプリケーション。 Oracle E-business Suite でこれらのオブジェクトを作成するサンプルで提供される create_apps_artifacts.sql スクリプトを実行するときに、このテーブルが作成されます。  

 次に、コンテンツ ベース ルーティング (CBR) で使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]からポーリング メッセージを受信する受信ポートでアプリケーションを構成する、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルと、次に、送信ポートにルーティングします。 この場合、受信場所が指定され、メッセージは送信ポートにルーティングをチェックする送信ポートでフィルターを作成します。  

 ポーリング操作を説明するために、次の項目行います。  

-   SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所インターフェイス テーブルの中にポーリングされます (MS_SAMPLE_EMPLOYEE) を決定するプロパティをバインドします。 この例では、としては、このバインド プロパティを設定できます。  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     これにより、MS_SAMPLE_EMPLOYEE インターフェイス テーブルにいくつかのレコードがある場合にのみ、アダプターがポーリング ステートメントを実行します。  

-   SELECT ステートメントを指定、 **PollingInput**プロパティをバインドします。 このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のすべての行を取得します。 この例では、としては、このバインド プロパティを設定できます。  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  SELECT ステートメントで使用される FOR UPDATE 句の詳細については、次を参照してください。 [SELECT ステートメントを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)します。  

-   DELETE ステートメントを指定の一部として、 **PostPollStatement**プロパティをバインドします。 このステートメントは、すべてのデータを MS_SAMPLE_EMPLOYEE インターフェイス テーブルから削除されます。 この例では、としては、このバインド プロパティを設定できます。  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     このような場合は、次回の指定されたステートメント**PollingInput**は実行すると、それをフェッチできませんすべてのデータ。  

-   多くのデータは MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加されるまで、すべてのメッセージのポーリングは利用できません。 そのため、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要があります。 サンプルで提供される insert_apps_data.sql スクリプトを実行して行うことができます。 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。  

## <a name="how-to-receive-data-change-messages-from-oracle-e-business-suite"></a>Oracle E-business Suite からデータ変更メッセージを受信する方法  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている次の手順のタスクが含まれます[Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)します。 これらのタスクは、SELECT ステートメントを使用して Oracle E-business Suite をポーリングするアダプターを構成するには。  

1. BizTalk プロジェクトを作成し、スキーマの生成、**ポーリング**インターフェイス テーブルをポーリングする操作。  

2. ビルドし、BizTalk プロジェクトを配置します。  

3. BizTalk アプリケーションを作成して受信し、送信ポートを構成します。 さらに、受信ポートで指定された受信場所を確認し、ポーリング メッセージは送信ポートにルーティングできるように、送信ポートでフィルターを追加します。  

   > [!IMPORTANT]
   >  常に設定する必要があります、ポーリングの受信シナリオの一方向の受信ポート。 双方向受信ポートは受信操作のサポートされていません。  

4. BizTalk アプリケーションを起動します。  

   このトピックでは、これらのタスクを実行する手順を説明します。  

## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル PollingUsingSelectStatement、ベースのこのトピックでは、BizTalk Adapter Pack 付きも提供されます。 詳細については、次を参照してください。[サンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)します。  

## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルでの操作、**アプリケーション オブジェクト ライブラリ**アプリケーション。 使用して、スキーマの生成中に、次のタスクを実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  

- コントラクトの種類を選択します。**サービス (受信操作)** します。  

- スキーマの生成、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。 選択できます。 操作と、インターフェイス テーブルから、**アプリケーション ベースのビュー**ノードまたは**成果物のビューのベース**ノード。  

  スキーマを生成する方法の詳細については、次を参照してください。[参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)します。  

## <a name="building-and-deploying-the-biztalk-project"></a>ビルドして、BizTalk プロジェクトを配置します。  
 BizTalk ソリューションをビルドし、BizTalk サーバーに配置する必要がありますようになりました。 BizTalk Server にソリューションを展開する方法の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。

## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 BizTalk プロジェクトを配置した後、アプリケーションが下に表示されます、**アプリケーション**BizTalk Server 管理コンソール内のノード。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションの構成の一環としては、アプリケーションでは、受信ポートと送信ポートを作成し、受信ポートからのすべてのメッセージが送信ポートにルーティングされるように、送信ポートにフィルターを追加する必要があります。  

 アプリケーションを構成する必要があります。  

-   アプリケーションのホストを選択します。  

-   受信し、送信ポートを作成します。  

### <a name="creating-a-receive-port"></a>作成、受信ポート  
 WCF カスタムを作成する必要がありますまたは Wcf-oracleebs 一方向受信ポートで、指定された SELECT ステートメントを使用して Oracle のポーリング、 **PollingInput**プロパティをバインドします。 受信ポートを作成する方法についてを参照してください[、Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)します。 受信ポートを作成するときに、次のバインド プロパティを指定することを確認します。  

 **ポーリング**  

|プロパティのバインド|値|  
|----------------------|-----------|  
|**InboundOperationType**|これを設定**ポーリング**します。|  
|**PolledDataAvailableStatement**|この例このバインドのプロパティを設定します。<br /><br /> `SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE`|  
|**PollingAction**|生成スキーマからポーリング アクションを取得、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する操作。 この例でこのバインドのプロパティを設定**InterfaceTables/ポーリング/ヘルプ/アプリ/MS_SAMPLE_EMPLOYEE**します。|  
|**PollingInput**|このバインド プロパティの MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのレコードを取得する SELECT ステートメントを指定します。 この例このバインドのプロパティを設定します。<br /><br /> `SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE`|  
|**PostPollStatement**|MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのデータを削除するポスト ポーリング ステートメントを指定します。 この例このバインドのプロパティを設定します。<br /><br /> `DELETE FROM MS_SAMPLE_EMPLOYEE`|  

 **アプリケーションのコンテキストを設定します。**  

 Oracle E-business Suite の成果物の操作を実行している場合は、アプリケーションのコンテキストを設定する適切なバインドのプロパティの値を指定する必要があります。 アプリケーションのコンテキストとアプリケーション コンテキストの設定に必要なバインドのプロパティの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  

 この例では、適切な値を指定します、 **oracleUserName**、 **oraclePassword**、および**oracleEBSResponsibility**プロパティをバインドします。  

> [!NOTE]
>  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧めします。、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 受信ポートを構成するときに、サービスの動作を追加することで行うことができます。 サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成と Oracle E-business Suite でのトランザクション タイムアウト](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)します。  

### <a name="creating-a-send-port"></a>送信ポートの作成  
 ハード_ディスク上の場所を定義し、対応する FILE 送信ポートを作成、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Oracle からのメッセージをドロップします。 これらのメッセージは、受信ポートの指定したポーリング ステートメントへの応答になります。 送信ポートを作成する方法については、次を参照してください。 [、Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)します。  

 受信場所から送信ポートでメッセージをルーティングするフィルターを追加する必要がありますも。 送信ポートにフィルターを追加します。  

1.  送信ポートを開くをダブルクリックして、**送信ポートのプロパティ** ダイアログ ボックス。  

2.  **送信ポートのプロパティ**ダイアログ ボックスで、をクリックして、**フィルター**タブ。  

3.  次の値を指定します。  

    -   **プロパティ**一覧で、 **BTS します。ReceivePortName**します。  

    -   **演算子**一覧で、  **==** します。  

    -   **値**フィールドに、受信ポート名を指定します。  

4.  **送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  

## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle E-business Suite をポーリングするための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。  

 この段階で、ことを確認します。  

-   Wcf-custom または Wcf-oracleebs 一方向受信ポートで、指定された SELECT ステートメントを使用して Oracle のポーリング、 **PollingInput**プロパティ、バインドが実行されています。  

-   、Oracle データベースからメッセージを受信する FILE 送信ポートが実行されています。  

## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、次の一連のアクションに、同じシーケンスを実行します。  

-   アダプターが実行、 **PolledDataAvailableStatement**アダプターに指定されたステートメントを実行することを示す正の値を返す**PollingInput**プロパティをバインドします。  

-   アダプターの SELECT ステートメントの実行、 **PollingInput** MS_SAMPLE_EMPLOYEE インターフェイス テーブルのプロパティを返しますのすべての行をバインドします。 Oracle E-business Suite からの応答には、次のようになります。  

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

-   アダプターは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのデータを削除するポーリング後ステートメントを実行します。  

-   ポーリング間隔の後、アダプターをもう一度実行します**PolledDataAvailableStatement**します。 MS_SAMPLE_EMPLOYEE インターフェイス テーブルにはレコードがあるない、ため**PolledDataAvailableStatement**正の値を返さないため、アダプターに指定されたステートメントを実行しないと、 **PollingInput**プロパティをバインドします。 結果として、アダプターのクライアントは、ポーリング メッセージを取得できません。  

-   レコードの一部は明示的な MS_SAMPLE_EMPLOYEE インターフェイス テーブルに挿入されるまで、アダプター クライアントは、これ以上ポーリング メッセージを取得できません。 以上のレコードを挿入するには、サンプルで提供される insert_apps_data.sql スクリプトを実行することができます。 次に、このスクリプトを実行した後**PolledDataAvailableStatement**が実行すると、正の値を返します。 結果として、アダプターがポーリング ステートメントを実行し、アダプター クライアントは再度ポーリング メッセージを受信します。  

> [!NOTE]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリングからの受信ポートを明示的に無効にするまでは引き続き、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、ポートと受信ポート、送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business suite アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)します。  

## <a name="see-also"></a>参照  
 [BizTalk Server を使用して Oracle E-business Suite のポーリング](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)