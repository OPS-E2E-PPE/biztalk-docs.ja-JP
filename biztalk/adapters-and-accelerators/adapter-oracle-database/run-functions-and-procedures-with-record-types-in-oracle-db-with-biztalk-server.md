---
title: "関数と BizTalk Server を使用して Oracle データベースでレコードの種類を持つプロシージャを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccdc150e-055a-47df-af3e-64931946455d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d8aa9b3202adaf57e7ec213a81384606eb1b8a4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-functions-and-procedures-with-record-types-in-oracle-database-using-biztalk-server"></a>関数と BizTalk Server を使用して Oracle データベースでレコードの種類を持つプロシージャを呼び出す
Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]複雑な XML 型としてレコードの種類を表示します。 方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サポートのレコードの種類を参照してください[関数と Oracle データベースのレコード型での手順に従って操作します。](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md)です。 レコードの種類の XML 構造については、次を参照してください。[レコードの種類のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)です。  
  
## <a name="how-to-invoke-functions-in-an-oracle-database"></a>Oracle データベースで関数を呼び出す方法ですか。  
 Oracle データベースを使用して、操作を実行[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、[の Oracle データベースと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)です。 返す単純でネストされた Oracle データベースで関数を呼び出すレコードの種類、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、Oracle データベースで、呼び出し先関数のスキーマを生成します。  
  
2.  Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  Oracle データベースで関数を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、Func_RecordTypes、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックの内容を示すために方法、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を呼び出すパラメーターを型のレコードを返す関数を呼び出すことサポート。  
  
-   単純なレコードの種類を返す GET_ACCOUNTADDRESS 関数です。  
  
-   入れ子になったレコード型を返す GET_ACCOUNTINFO 関数。  
  
 これらの関数は使用可能なサンプルに用意されている SQL スクリプトを実行して作成された ACCOUNT_PKG の一部として。 サンプルおよび SQL スクリプトの詳細を知るには、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)です。  
  
 そのため、両方の関数では、GET_ACCOUNTADDRESS と GET_ACCOUNTINFO、SCOTT\Package\ACCOUNT_PKG スキーマで使用可能なスキーマを生成するあります。 参照してください[Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類 ウィンドウからのメッセージに最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つの要求-応答メッセージのセットを作成する必要があります: 1 つの要求-応答が GET_ACCOUNTADDRESS 関数を呼び出して応答を受信する; に設定その他の要求-応答メッセージは、GET_ACCOUNTINFO 関数を呼び出すし、応答を受信する設定。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
2.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
3.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTINFO*ここで、 *Func_RecordTypes*の名前を指定します、BizTalk プロジェクトです。 *OracleDBBindingSchema* GET_ACCOUNTADDRESS 関数に対して生成されるスキーマです。|  
  
5.  次の 3 つ以上のメッセージを作成する前の手順を繰り返します。 **プロパティ**、新しいメッセージ ウィンドウ、次の操作します。  
  
    |識別子に設定します。|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |応答|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTINFOResponse*|  
    |Request2|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTADDRESS*|  
    |Response2|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTADDRESSResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]レコードの種類を単純または複雑な関数を呼び出すことを返します。 このオーケストレーションでは、2 つの要求メッセージを削除します。  
  
-   単純なレコード型を返す GET_ACCOUNTADDRESS 関数のいずれかです。  
  
-   入れ子になったレコード型を返す GET_ACCOUNTINFO 関数のいずれかです。  
  
 これらのメッセージは、受信場所で削除されます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージを使用し、Oracle データベースにログオン ODP を介して渡します。 Oracle データベースからの応答は、別の場所に保存されます。 オーケストレーションは、2 つの要求を同時に取得ため、並列アクション図形をオーケストレーションに含める必要があります。 各並列操作の送信を組み込み、受信図形を Oracle データベースにメッセージを送信し、それぞれ、応答を受信します。 ただし、両方の操作用のメッセージを送受信するためのと同じポートを使用できます。 両方の操作を同時に実行するための一般的なオーケストレーションにが含まれます。  
  
-   Oracle データベースにメッセージを送信し、応答を受信する図形を送受信します。  
  
-   一方向の受信ポートを Oracle データベースに送信する要求メッセージを受信します。  
  
-   双方向の送信要求メッセージを Oracle データベースし、応答の受信を送信するポート。  
  
-   フォルダーに Oracle データベースからの応答を送信する一方向の送信ポートです。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![Oracle でレコードの種類を使用するためのオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/6ee5e57b-48d5-435a-a16b-83bac878d0b7.gif "6ee5e57b-48d5-435a-a16b-83bac878d0b7")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。 次の表には、並列アクションの 1 つ含める必要があります、図形が一覧表示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
 次の表には、他の並列アクションを含める必要がある図形が一覧表示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage2|Receive|-設定**名前**に*ReceiveMessage2*<br />-設定**アクティブ**に*は True。*|  
|SendMessage2|Send|-設定**名前**に*SendMessage2*|  
|ReceiveResponse2|Receive|-設定**名前**に*ReceiveResponse2*<br />-設定**アクティブ**に*False*|  
|SendResponse2|Send|-設定**名前**に*SendResponse2*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br />-設定**型**に*SaveResponseType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
 2 つの要求を処理しているため、これらのポートを使用して応答メッセージは、ポートが 1 つのメッセージの種類に対応する各操作ごとに 2 つの操作を作成する必要があります。 操作を作成するには、ポート図形を右クリックして**新しい操作**です。 最初の操作としては、各ポートの名前を付けます**NestedRecType**としてポートごとに 2 番目の操作と**SimpleRecType**です。  
  
### <a name="using-correlations"></a>関連付けの使用  
 関連付けは、受信メッセージをオーケストレーションの適切なインスタンスに一致させるプロセスです。 削除するオーケストレーションに 2 つの要求メッセージは、各オーバー ロードのいずれか。 オーケストレーションを右要求メッセージを関連付ける相関関係を使用します。 相関関係の詳細については、次を参照してください[オーケストレーションでの相関関係を使用する。](../../core/using-correlations-in-orchestrations.md)  
  
##### <a name="to-use-correlations"></a>相関関係を使用するには  
  
1.  各関数の生成スキーマからプロパティを昇格します。 たとえば、GET_ACCOUNTADDRESS 関数のスキーマから CUSTNAME プロパティを昇格させるGET_ACCOUNTINFO 関数のスキーマから補助プロパティを昇格します。 プロパティを昇格させるには、スキーマ ビューでプロパティを右クリックし、順にポイント**昇格**、し、**クイック昇格**です。 これにより、PropertySchema.xsd ファイルが、BizTalk プロジェクトに追加されます。  
  
     プロパティを昇格させる方法については、次を参照してください。[プロパティの昇格](../../core/promoting-properties.md)です。  
  
2.  オーケストレーション ビューを右クリックして**関連付けの種類**、し、**新しい関連付けの種類**です。  
  
3.  **関連付けのプロパティ** ダイアログ ボックスには、手順 1. で昇格させたプロパティが一覧表示されます。 プロパティを選択し、をクリックして**追加**です。  
  
4.  **[OK]**をクリックします。  
  
5.  その他の昇格させたプロパティの関連付けの種類を作成するには、この手順を繰り返します。  
  
6.  関連付けられているプロパティに基づいて関連付けの種類の名前を変更します。 関連付けの種類の名前を変更する可能性があります*CorrelationType_CUSTNAME* CUSTNAME プロパティ) と*CorrelationType_AID*補助プロパティ)。  
  
7.  オーケストレーション ビューを右クリックして**関連付けセット**、し、**新しい関連付けセット**です。  
  
8.  新しく追加された関連付けセットを右クリックし、をクリックして**プロパティ**です。 **プロパティ** ウィンドウで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[関連付けの種類]|*Func_RecordTypes.CorrelationType_CUSTNAME*|  
    |[Identifier]|*Correlation_CUSTNAME*|  
  
9. 別の関連付けセットを追加し、次のプロパティを指定して、**プロパティ**ウィンドウです。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[関連付けの種類]|*Func_RecordTypes.CorrelationType_AID*|  
    |[Identifier]|*Correlation_AID*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形のメッセージを指定して、ポートへの接続  
 次の表は、プロパティとその値をアクション図形のメッセージを指定し、ポートへのリンクを設定する必要がありますを指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**イニシャライズ関連付けセット**に*Correlation_AID*<br />-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.NestedRecType.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.NestedRecType.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.NestedRecType.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.NestedRecType.Request*|  
|ReceiveMessage2|-設定**イニシャライズ関連付けセット**に*Correlation_CUSTNAME*<br />-設定**メッセージ**に*Request2*<br />-設定**操作**に*FileIn.SimpleRecType.Request*|  
|SendMessage2|-設定**メッセージ**に*Request2*<br />-設定**操作**に*LOBPort.SimpleRecType.Request*|  
|ReceiveResponse2|-設定**メッセージ**に*Response2*<br />-設定**操作**に*LOBPort.SimpleRecType.Response*|  
|SendResponse2|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.SimpleRecType.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
-   ハード_ディスクとオーバー ロードされた各手順のいずれかの要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを処理し、Oracle データベースに送信されます。  
  
-   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが、Oracle データベースからの応答を含む、関数ごとに 1 つの応答メッセージをドロップする場所に場所を定義します。  
  
    -   Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 Wcf-custom または Wcf-oracledb のポートを作成する方法については、次を参照してください。 [Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)です。 Wcf-custom または Wcf-oracledb の送信ポートの送信と 1 つ以上のスキーマに準拠したメッセージを受信、2 つの操作を実行ために、動的操作の両方の操作を設定する必要があります。 アクションの詳細については、次を参照してください。 [Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)です。 このオーケストレーションのアクションを次のように設定してください。  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="NestedRecType" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO" />  
          <Operation Name="SimpleRecType" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS" />  
        </BtsActionMapping>  
        ```  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または受信ポート (着信)、BizTalk Server 管理コンソールから、このバインド ファイルをインポートすることができます。 詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle データベース テーブル内の関数を呼び出すための BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Oracle データベースにメッセージを送信する Wcf-custom または Wcf-oracledb 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、2 つを削除する必要があります (各関数の 1 つ) ファイルにメッセージを受信場所の要求。 要求メッセージのスキーマは、以前に生成する関数のスキーマに準拠する必要があります。 オーケストレーションは、要求のメッセージを使用し、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  
  
 参照してください[関数およびプロシージャのメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)の詳細については、要求メッセージ スキーマを呼び出す関数を使用して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
 たとえば、GET_ACCOUNINFO 関数を呼び出すための要求メッセージには。  
  
```  
<GET_ACCOUNTINFO xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <AID>100000</AID>  
</GET_ACCOUNTINFO>  
```  
  
 同様に、GET_ACCOUNTADDRESS 関数を呼び出すための要求メッセージには。  
  
```  
<GET_ACCOUNTADDRESS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <CUSTNAME>Mindy Martin</CUSTNAME>  
</GET_ACCOUNTADDRESS>  
```  
  
 最初の要求メッセージは、入れ子になったレコード型を返す GET_ACCOUNTINFO 関数を呼び出します。 GET_ACCOUNTINFO 関数を呼び出すことの応答メッセージは次のとおりです。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<GET_ACCOUNTINFOResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <GET_ACCOUNTINFOResult>  
    <ACCT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO">  
      <ACCTID>100000</ACCTID>   
      <NAME>Kim Ralls</NAME>   
      <BALANCE>10000</BALANCE>   
    </ACCT>  
    <ADDRESS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO">  
      <STREET>1234 Main St.</STREET>   
      <CITY>Seattle</CITY>   
      <STATE>WA</STATE>   
    </ADDRESS>  
  </GET_ACCOUNTINFOResult>  
</GET_ACCOUNTINFOResponse>  
```  
  
 2 番目の要求メッセージは、単純なレコード型を返す GET_ACCOUNTADDRESS 関数を呼び出します。 GET_ACCOUNTADDRESS 関数を呼び出すことの応答メッセージは次のとおりです。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<GET_ACCOUNTADDRESSResponse mlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <GET_ACCOUNTADDRESSResult>  
    <ID xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">100004</ID>  
    <NAME xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">Mindy Martin</NAME>  
    <STREET xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">6789 Cherry St.</STREET>  
    <CITY xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">New York</CITY>  
    <STATE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS">NY</STATE>  
  </GET_ACCOUNTADDRESSResult>  
</GET_ACCOUNTADDRESSResponse>  
```  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外に関する情報の関数またはを使用してプロシージャの呼び出し中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外と、Oracle データベース アダプターによるエラー処理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle データベースと開発の BizTalk アプリケーションのビルド ブロック](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)