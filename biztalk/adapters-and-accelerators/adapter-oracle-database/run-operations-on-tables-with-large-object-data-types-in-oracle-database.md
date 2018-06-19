---
title: Oracle データベース内のラージ オブジェクト データ型とテーブルに対する操作を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, performing on tables
- operations, performing on LOB data
ms.assetid: 74276b85-daf1-4d0f-92f9-46d5c27a95a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a1116947450fb1d900ea38be0254fb3d0f7f7c1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967848"
---
# <a name="run-operations-on-tables-with-large-object-data-types-in-oracle-database"></a>Oracle データベース内のラージ オブジェクト データ型とテーブルに対する操作を実行します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle ラージ オブジェクト (LOB) データ型のサポートを提供します。  
  
-   バイナリ ラージ オブジェクト (BLOB)  
  
-   文字ラージ オブジェクト (CLOB)  
  
-   各国語文字ラージ オブジェクト (NCLOB)  
  
-   バイナリ ファイル (BFILE)。 詳細については、次を参照してください。 [BizTalk Server を使用して Oracle データベースで BFILE データ型を持つテーブルでの操作の実行](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)です。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]はテーブルの LOB 列が含まれている ReadLOB および UpdateLOB 操作を提示することで。 これらの操作の詳細については、次を参照してください。[テーブルおよびビューを含む LOB データをする Oracle データベースで操作を](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)です。 これらの操作を呼び出すため、SOAP メッセージの構造に関する詳細については、次を参照してください。[特別な LOB 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)です。  
  
> [!NOTE]
>  使用する場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、ReadLOB 操作は、Oracle データベースからの LOB 型データのストリーミングをサポートしていません。 使用して Oracle データベースから LOB データをストリーミングする[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]選択操作を代わりに使用する必要があります。 ストリーミングの詳細については、次を参照してください。 [Oracle データベースでの LOB データ型のストリーミング サポート](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)です。 また、ReadLOB 操作用の Oracle データベースからの応答には、WSDL と照らし合わせた検証は失敗します。 エラーを回避する方法については、次を参照してください。[運用上の問題のトラブルシューティング](https://msdn.microsoft.com/library/dd787883.aspx)です。  
  
## <a name="how-to-perform-operations-on-lob-data"></a>LOB データに対して操作を実行する方法  
 Oracle データベースを使用して、操作を実行[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、[の Oracle データベースと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)です。 Oracle データベースでのテーブルに対する ReadLOB と UpdateLOB の両方の操作を呼び出すには、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、ReadLOB と UpdateLOB の両方の操作のスキーマを生成します。  
  
2.  Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。 要求を送信して、両方の操作の応答の受信メッセージを作成する必要があります。  
  
3.  ReadLOB と UpdateLOB の両方の操作の呼び出しにオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、Operate_LOB、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは ReadLOB と UpdateLOB の操作を実行する方法を示すを生成、CUSTOMER テーブル、SCOTT、Oracle データベース スキーマの下に表示されるこれらの操作のメタデータ。 次の表は、サンプルに用意されている SQL スクリプトを実行して SCOTT スキーマで作成されます。 サンプルの詳細を知るには、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類 ウィンドウからのメッセージに最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つの要求-応答メッセージのセットを作成する必要があります: ReadLOB 操作および UpdateLOB 操作に対して設定 2 番目の要求-応答の 1 つの要求-応答を設定します。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、クリックして**オーケストレーション ビュー**です。  
  
2.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
3.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*Operate_LOB です。OracleDBBindingSchema.ReadLOB**、* 場所*Operate_LOB* BizTalk プロジェクトの名前を指定します。 *OracleDBBindingSchema*顧客テーブルに ReadLOB および UpdateLOB 操作に対して生成されるスキーマです。|  
  
5.  次の 3 つ以上のメッセージを作成する前の手順を繰り返します。 **プロパティ**、新しいメッセージ ウィンドウ、次の操作します。  
  
    |識別子に設定します。|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |応答|*Operate_LOB です。OracleDBBindingSchema.ReadLOBResponse*|  
    |Request2|*Operate_LOB です。OracleDBBindingSchema.UpdateLOB*|  
    |Response2|*Operate_LOB です。OracleDBBindingSchema.UpdateLOBResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ReadLOB と UpdateLOB のテーブルに対する操作を呼び出すためです。 このオーケストレーションでは、ReadLOB 操作および UpdateLOB 操作に対して、その他の 1 つずつ、2 つの要求メッセージを削除します。 これらのメッセージは、受信場所で削除されます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージを使用し、Oracle データベースにログオン ODP を介して渡します。 Oracle データベースからの応答は、別の場所に保存されます。  
  
 オーケストレーションは、2 つの要求を同時に取得ため、並列アクション図形をオーケストレーションに含める必要があります。 各並列操作の送信を組み込み、Oracle データベースにメッセージを送信し、応答を受信する図形を受信します。 ただし、両方の操作用のメッセージを送受信するためのと同じポートを使用できます。 ReadLOB と UpdateLOB の操作を同時に実行するための一般的なオーケストレーションにが含まれます。  
  
-   Oracle データベースにメッセージを送信し、応答を受信する図形を送受信します。  
  
-   一方向の受信ポートを Oracle データベースに送信する要求メッセージを受信します。  
  
-   双方向の送信要求メッセージを Oracle データベースし、応答の受信を送信するポート。  
  
-   フォルダーに Oracle データベースからの応答を送信する一方向の送信ポートです。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![オーケストレーションの読み取りと LOB データの更新を](../../adapters-and-accelerators/adapter-oracle-database/media/6523b5e4-3689-433a-8287-eebc36f10442.gif "6523b5e4-3689-433a-8287-eebc36f10442")  
  
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
  
 2 つの要求を処理しているため、これらのポートを使用して応答メッセージは、ポートが 1 つのメッセージの種類に対応する各操作ごとに 2 つの操作を作成する必要があります。 操作を作成するには、ポート図形を右クリックし **新しい操作**です。 最初の操作としては、各ポートの名前を付けます**ReadLOB**としてポートごとに 2 番目の操作と**UpdateLOB**です。  
  
### <a name="using-correlation"></a>相関関係の使用  
 関連付けは、受信メッセージをオーケストレーションの適切なインスタンスに一致させるプロセスです。 削除するオーケストレーションに 2 つの要求メッセージは、各オーバー ロードのいずれか。 オーケストレーションを右要求メッセージを関連付ける相関関係を使用します。 相関関係の詳細については、次を参照してください。[オーケストレーションでの相関関係を使用して](../../core/using-correlations-in-orchestrations.md)です。  
  
##### <a name="to-use-correlations"></a>相関関係を使用するには  
  
1.  操作ごとに生成されるスキーマのプロパティを昇格します。 たとえば、ReadLOB 操作スキーマから LOB_COLUMN プロパティを昇格させるUpdateLOB 操作のスキーマからフィルター プロパティを昇格します。 プロパティを昇格させるには、スキーマ ビューでプロパティを右クリックし、順にポイント**昇格**、し、**クイック昇格**です。 これにより、PropertySchema.xsd ファイルが、BizTalk プロジェクトに追加されます。  
  
     プロパティを昇格させる方法については、次を参照してください。[プロパティの昇格](../../core/promoting-properties.md)です。  
  
2.  オーケストレーション ビューを右クリックして**関連付けの種類**、し、**新しい関連付けの種類**です。  
  
3.  **関連付けのプロパティ** ダイアログ ボックスには、手順 1. で昇格させたプロパティが一覧表示されます。 プロパティを選択し、をクリックして**追加**です。  
  
4.  **[OK]** をクリックします。  
  
5.  その他の昇格させたプロパティの関連付けの種類を作成するには、この手順を繰り返します。  
  
6.  関連付けられている操作に基づいた関連付けの種類の名前を変更します。 関連付けの種類の名前を変更する可能性があります*CorrelationType_ReadLOB* (ReadLOB 操作) のおよび*CorrelationType_UpdateLOB* (用、UpdateLOB 操作)。  
  
7.  オーケストレーション ビューを右クリックして**関連付けセット**、し、**新しい関連付けセット**です。  
  
8.  新しく追加された関連付けセットを右クリックし、をクリックして**プロパティ**です。 **プロパティ** ウィンドウで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[関連付けの種類]|*Operate_LOB です。CorrelationType_ReadLOB*|  
    |[Identifier]|*Correlation_ReadLOB*|  
  
9. 別の関連付けセットを追加し、[プロパティ] ウィンドウから次のプロパティを指定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[関連付けの種類]|*Operate_LOB です。CorrelationType_UpdateLOB*|  
    |[Identifier]|*Correlation_UpdateLOB*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形のメッセージを指定して、ポートへの接続  
 次の表は、プロパティとその値をアクション図形のメッセージを指定し、ポートへのリンクを設定する必要がありますを指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**イニシャライズ関連付けセット**に*Correlation_ReadLOB*<br />-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.ReadLOB.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.ReadLOB.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.ReadLOB.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.ReadLOB.Request*|  
|ReceiveMessage2|-設定**イニシャライズ関連付けセット**に*Correlation_UpdateLOB*<br />-設定**メッセージ**に*Request2*<br />-設定**操作**に*FileIn.UpdateLOB.Request*|  
|SendMessage2|-設定**メッセージ**に*Request2*<br />-設定**操作**に*LOBPort.UpdateLOB.Request*|  
|ReceiveResponse2|-設定**メッセージ**に*Response2*<br />-設定**操作**に*LOBPort.UpdateLOB.Response*|  
|SendResponse2|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.UpdateLOB.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード_ディスクと ReadLOB および UpdateLOB 操作に対して 1 つずつ要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは、要求メッセージを処理し、Oracle データベースに送信されます。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが、各操作は、Oracle データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 Wcf-custom または Wcf-oracledb のポートを作成する方法については、次を参照してください。 [Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)です。 Wcf-custom または Wcf-oracledb の送信ポートの送信と 1 つ以上のスキーマに準拠したメッセージを受信、2 つの操作を実行ために、動的操作の両方の操作を設定する必要があります。 アクションの詳細については、次を参照してください。 [Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)です。 このオーケストレーションのアクションを次のように設定してください。  
  
        ```  
        <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
          <Operation Name="ReadLOB" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/ReadLOB" />  
          <Operation Name="UpdateLOB" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB" />  
        </BtsActionMapping>  
        ```  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または受信ポート (着信)、BizTalk Server 管理コンソールから、このバインド ファイルをインポートすることができます。 詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle データベースで操作を実行するための BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   WCF カスタム ポート送受信メッセージを送信するデータベースが実行されている Oracle への Wcf-oracledb。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後は、ファイルへのメッセージの受信場所の要求を削除する必要があります。 要求メッセージのスキーマは、以前に生成した操作のスキーマに準拠する必要があります。 参照してください[特別な LOB 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)、要求メッセージ スキーマを使用して、LOB データ型に対する操作を呼び出すための詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
 オーケストレーションは、要求のメッセージを使用し、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  
  
 このオーケストレーションでは、CUSTOMER テーブルの BLOB データ型の PHOTO 列を更新する UpdateLOB 操作の要求メッセージ最初にドロップします。 特定の顧客用、PHOTO 列の更新プログラムを起動する要求メッセージは次のとおりです。  
  
```  
<UpdateLOB xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <LOB_COLUMN>PHOTO</LOB_COLUMN>  
  <FILTER>Name='Mindy Martin'</FILTER>  
  <Stream>YWJjZA==</Stream>  
</UpdateLOB>  
```  
  
> [!NOTE]
>  フィルター文字列フェッチする必要があります常に 1 つの一致する行それ以外の場合 XmlReaderParsingException、Oracle データベース アダプターをスローします。 値も、\<ストリーム\>要素は、base64Binary 型である必要があります。  
  
 UpdateLOB 操作の応答には次のとおりです。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<UpdateLOBResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER"></UpdateLOBResponse>  
```  
  
 UpdateLOB 操作によって更新されたデータを読み取る ReadLOB 操作の要求メッセージを削除するようになりました。 操作を呼び出し、ReadLOB、PHOTO 列で、特定の顧客に要求メッセージは次のとおりです。  
  
```  
<ReadLOB xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <LOB_COLUMN>PHOTO</LOB_COLUMN>  
  <FILTER>NAME='Mindy Martin'</FILTER>  
</ReadLOB>  
```  
  
> [!NOTE]
>  フィルター文字列は、1 つの一致する行をフェッチ常にする必要があります。 1 つ以上の一致する行がある場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のみ (照合) の最初の行の LOB 列が返されます。  
  
 ReadLOB 操作の応答には次のとおりです。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ReadLOBResponse mlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <ReadLOBResult>YWJjZA==</ReadLOBResult>  
</ReadLOBResponse>  
```  
  
> [!NOTE]
>  検証の WSDL に使用する ReadLOB 操作の応答があります。 WSDL に対して ReadLOB を検証する特定のタスクを実行する必要があります。 詳細については、次を参照してください。[運用上の問題のトラブルシューティング](https://msdn.microsoft.com/library/dd787883.aspx)です。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外に関する情報を使用して LOB データを含むテーブルに対する操作の実行中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラー処理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle データベースと開発の BizTalk アプリケーションのビルド ブロック](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)