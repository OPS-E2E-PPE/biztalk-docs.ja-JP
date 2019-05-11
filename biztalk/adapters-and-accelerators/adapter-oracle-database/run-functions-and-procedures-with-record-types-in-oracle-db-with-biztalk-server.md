---
title: BizTalk Server を使用して Oracle データベースでレコードの種類で関数とプロシージャを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccdc150e-055a-47df-af3e-64931946455d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27fd1cbc9ce20f7412db46f94a255304937b5de5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376096"
---
# <a name="invoke-functions-and-procedures-with-record-types-in-oracle-database-using-biztalk-server"></a>BizTalk Server を使用して Oracle データベースでレコードの種類で関数とプロシージャを呼び出す
Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの複雑な XML 型としてレコードの種類。 方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サポートのレコードの種類を参照してください[関数と Oracle データベースでレコードの種類を使用したプロシージャに対する操作。](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md)します。 レコードの種類の XML 構造については、次を参照してください。[レコードの種類のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)します。  
  
## <a name="how-to-invoke-functions-in-an-oracle-database"></a>Oracle データベースでの関数を呼び出す方法でしょうか。  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)します。 レコードの種類、これらのタスクはシンプルで入れ子になったが返す Oracle データベースでの関数の呼び出しには。  
  
1. BizTalk プロジェクトを作成し、Oracle データベースで、呼び出し先関数のスキーマを生成します。  
  
2. Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. Oracle データベースで関数を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル Func_RecordTypes、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 示すために、このトピックでどのように[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]型を呼び出すパラメーターをレコードを返す関数を呼び出したサポート。  
  
- 単純なレコード型を返す GET_ACCOUNTADDRESS 関数。  
  
- 入れ子になったレコード型を返す GET_ACCOUNTINFO 関数。  
  
  これらの関数は使用可能なサンプルで提供される SQL スクリプトを実行して作成された ACCOUNT_PKG の一部として。 サンプルとの SQL スクリプトの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)します。  
  
  そのため、両方の関数では、GET_ACCOUNTADDRESS と GET_ACCOUNTINFO、SCOTT\Package\ACCOUNT_PKG スキーマで使用可能なスキーマを生成する必要があります。 参照してください[Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法の詳細について。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類 ウィンドウからのメッセージを最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つの要求-応答メッセージのセットを作成する必要があります: GET_ACCOUNTADDRESS 関数を呼び出すし、応答を受信する 1 つの要求-応答の設定その他の要求-応答メッセージは、GET_ACCOUNTINFO 関数を呼び出すし、応答の受信に設定します。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
2.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
3.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選び*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTINFO*ここで、 *Func_RecordTypes*の名前を指定します、BizTalk プロジェクトです。 *OracleDBBindingSchema* GET_ACCOUNTADDRESS 関数に対して生成されるスキーマです。|  
  
5.  次の 3 つ以上のメッセージを作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |識別子を設定するには|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |応答|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTINFOResponse*|  
    |Request2|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTADDRESS*|  
    |Response2|*Func_RecordTypes.OracleDBBindingSchema.GET_ACCOUNTADDRESSResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]関数を呼び出す単純および複雑なレコードの種類を返します。 このオーケストレーションでは、2 つの要求メッセージをドロップします。  
  
- 単純なレコード型を返す GET_ACCOUNTADDRESS 関数の 1 つです。  
  
- 入れ子になったレコード型を返す GET_ACCOUNTINFO 関数の 1 つです。  
  
  これらのメッセージの受信場所は削除されます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージを使用し、ODP を使用して Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。 オーケストレーションでは、同時に 2 つの要求が取得するために並列アクション図形をオーケストレーションに含める必要があります。 並列アクションごとは、送信が含まれます、受信図形を Oracle データベースにメッセージを送信し、それぞれ、応答を受信する必要があります。 ただし、両方の操作のメッセージを送受信するため、同じポートを使用できます。 両方の操作を同時に実行するための一般的なオーケストレーションが含まれます。  
  
- Oracle データベースにメッセージを送信し、応答を受信する図形を送受信します。  
  
- Oracle データベースに送信する要求メッセージを受信するポートは一方向の受信します。  
  
- 双方向の送信要求メッセージを Oracle データベースし、応答の受信を送信するポート。  
  
- フォルダーに Oracle データベースからの応答を送信する一方向の送信ポート。  
  
  サンプル オーケストレーションには、次のようになります。  
  
  ![Oracle でレコードの種類を使用するためのオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/6ee5e57b-48d5-435a-a16b-83bac878d0b7.gif "6ee5e57b-48d5-435a-a16b-83bac878d0b7")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。 次の表は、図形の並列アクションの 1 つ含める必要があります。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
 次の表では、その他の並列アクションを含める必要のある図形が一覧表示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage2|Receive|-設定**名前**に*ReceiveMessage2*<br />-設定**アクティブ**に*は True。*|  
|SendMessage2|Send|-設定**名前**に*SendMessage2*|  
|ReceiveResponse2|Receive|-設定**名前**に*ReceiveResponse2*<br />-設定**アクティブ**に*False*|  
|SendResponse2|Send|-設定**名前**に*SendResponse2*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br />-設定**型**に*SaveResponseType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
 2 つの要求を処理するため、これらのポートを使用して応答メッセージは、ポートごとに各操作が 1 つのメッセージの種類に対応する 2 つの操作を作成する必要があります。 操作を作成するには、ポート図形を右クリックして**新しい操作**します。 最初の操作としては、各ポートの名前を付けます**NestedRecType**としてポートごとに 2 番目の操作と**SimpleRecType**します。  
  
### <a name="using-correlations"></a>関連付けの使用  
 関連付けは、受信メッセージをオーケストレーションの適切なインスタンスに一致させるプロセスです。 削除するオーケストレーションに 2 つの要求メッセージは、各オーバー ロードのいずれか。 相関関係を使用して、適切なオーケストレーションを要求メッセージに関連付けます。 相関関係の詳細については、次を参照してください[オーケストレーションでの相関関係を使用する。](../../core/using-correlations-in-orchestrations.md)  
  
##### <a name="to-use-correlations"></a>相関関係を使用するには  
  
1.  各関数の生成スキーマからプロパティを昇格します。 たとえば、GET_ACCOUNTADDRESS 関数のスキーマから CUSTNAME プロパティを昇格させますGET_ACCOUNTINFO 関数のスキーマから支援プロパティを昇格させます。 プロパティを昇格させるには、スキーマ ビューでプロパティを右クリックして**昇格**、し、**クイック昇格**します。 これにより、PropertySchema.xsd ファイルが BizTalk プロジェクトに追加します。  
  
     プロパティを昇格する方法の詳細については、次を参照してください。[プロパティの昇格](../../core/promoting-properties.md)します。  
  
2.  オーケストレーションの種類を右クリックして**関連付けの種類**、し、**新しい関連付けの種類**します。  
  
3.  **関連付けのプロパティ** ダイアログ ボックスには、手順 1. で昇格させたプロパティが一覧表示されます。 プロパティを選択し、**追加**します。  
  
4.  **[OK]** をクリックします。  
  
5.  その他の昇格させたプロパティの関連付けの種類を作成するには、この手順を繰り返します。  
  
6.  関連付けられているプロパティに基づいて関連付けの種類の名前を変更します。 関連付けの種類の名前を変更することが*CorrelationType_CUSTNAME* (CUSTNAME プロパティ) 用と*CorrelationType_AID* (補助プロパティ) 用。  
  
7.  オーケストレーションの種類を右クリックして**関連付けセット**、し、**新しい関連付けセット**します。  
  
8.  新しく追加された関連付けセットを右クリックし、をクリックし、**プロパティ**します。 **プロパティ**ウィンドウで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[関連付けの種類]|*Func_RecordTypes.CorrelationType_CUSTNAME*|  
    |[Identifier]|*Correlation_CUSTNAME*|  
  
9. 別の関連付けセットを追加しから次のプロパティを指定、**プロパティ**ウィンドウ。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[関連付けの種類]|*Func_RecordTypes.CorrelationType_AID*|  
    |[Identifier]|*Correlation_AID*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形は、メッセージを指定し、ポートに接続  
 次の表では、プロパティとその値をアクション図形のメッセージを指定し、それらのポートにリンクを設定する必要がありますを指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
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
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
- ハード ディスクと、各オーバー ロードされたプロシージャの 1 つの要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用して、Oracle データベースに送信します。  
  
- ハード ディスクと、BizTalk オーケストレーションが、Oracle データベースからの応答を含む、関数ごとに 1 つの応答メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。  
  
  - Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 Wcf-custom または Wcf-oracledb のポートを作成する方法については、次を参照してください。 [、Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)します。 Wcf-custom または Wcf-oracledb 送信ポートは 1 つ以上のスキーマに準拠したメッセージの送受信および 2 つの操作を実行、ためには、両方の操作のための動的アクションを設定する必要があります。 アクションの詳細については、次を参照してください。 [Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)します。 このオーケストレーションでは、アクションをよう設定する必要があります。  
  
    ```  
    <BtsActionMapping>  
      <Operation Name="NestedRecType" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO" />  
      <Operation Name="SimpleRecType" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTADDRESS" />  
    </BtsActionMapping>  
    ```  
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk Server 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、次を参照してください。 [Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)します。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle のデータベース テーブル内の関数を呼び出す BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。  
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Oracle データベースにメッセージを送信する Wcf-custom または Wcf-oracledb の送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、2 つを削除する必要がありますファイルへのメッセージ (各関数の 1 つ) の受信場所を要求します。 要求メッセージのスキーマは、以前に作成した関数のスキーマに準拠する必要があります。 オーケストレーションでは、要求メッセージを使用し、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  
  
 参照してください[関数およびプロシージャのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)を使用する関数を呼び出すための要求メッセージ スキーマの詳細について、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
 たとえば、GET_ACCOUNINFO 関数の呼び出しに要求メッセージには。  
  
```  
<GET_ACCOUNTINFO xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <AID>100000</AID>  
</GET_ACCOUNTINFO>  
```  
  
 同様に、GET_ACCOUNTADDRESS 関数の呼び出しに要求メッセージは次のとおりです。  
  
```  
<GET_ACCOUNTADDRESS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <CUSTNAME>Mindy Martin</CUSTNAME>  
</GET_ACCOUNTADDRESS>  
```  
  
 最初の要求メッセージは、入れ子になったレコード型を返す GET_ACCOUNTINFO 関数を呼び出します。 GET_ACCOUNTINFO 関数の呼び出しの応答メッセージです。  
  
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
  
 2 番目の要求メッセージは、単純なレコードの型を返す GET_ACCOUNTADDRESS 関数を呼び出します。 GET_ACCOUNTADDRESS 関数の呼び出しの応答メッセージです。  
  
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
 例外に関する情報の関数またはを使用してプロシージャの呼び出し中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外と、Oracle Database アダプターによるエラー処理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)します。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)します。  
  
## <a name="see-also"></a>参照  
[Oracle Database による開発の BizTalk アプリケーションを構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)