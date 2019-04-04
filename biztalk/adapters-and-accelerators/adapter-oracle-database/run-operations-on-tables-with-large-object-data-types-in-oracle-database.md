---
title: Oracle データベース内のラージ オブジェクト データ型を持つテーブルに対する操作の実行 |Microsoft Docs
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
ms.openlocfilehash: 9ea86bd08a926c3274b16b26b093380396f17887
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966987"
---
# <a name="run-operations-on-tables-with-large-object-data-types-in-oracle-database"></a>Oracle データベース内のラージ オブジェクト データ型を持つテーブルに対する操作を実行します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle のラージ オブジェクト (LOB) データ型のサポートを提供します。  

- バイナリ ラージ オブジェクト (BLOB)  

- 文字ラージ オブジェクト (CLOB)  

- 各国語文字ラージ オブジェクト (NCLOB)  

- バイナリ ファイル (BFILE)。 詳細については、[BizTalk Server を使用して Oracle データベースで BFILE データ型を持つテーブルで演算の実行](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)を参照してください。  

  [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は LOB 列を含むテーブルでは、ReadLOB および UpdateLOB の操作を提示することによって。 これらの操作の詳細については、[テーブルとビューを含む LOB データを Oracle データベース内で操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)を参照してください。 これらの操作を呼び出すため、SOAP メッセージの構造の詳細については、[特殊な LOB 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)を参照してください。  

> [!NOTE]
>  使用する場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、ReadLOB 操作は、Oracle データベースからのストリーミングの LOB 型のデータをサポートしていません。 使用して Oracle データベースから LOB データをストリーミングする[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]選択操作を代わりに使用する必要があります。 ストリーミングの詳細については、[Oracle データベースで LOB データ型のストリーミング サポート](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)を参照してください。 また、ReadLOB 操作用の Oracle データベースからの応答には、WSDL に対する検証は失敗します。 エラーを回避する方法については、[運用上の問題のトラブルシューティング](https://msdn.microsoft.com/library/dd787883.aspx)を参照してください。  

## <a name="how-to-perform-operations-on-lob-data"></a>LOB データの操作を実行する方法でしょうか。  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)します。 これらのタスクは、Oracle データベース内のテーブルで ReadLOB と UpdateLOB の両方の操作を呼び出すには。  

1. BizTalk プロジェクトを作成し、ReadLOB と UpdateLOB の両方の操作のスキーマを生成します。  

2. Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。 要求を送信して、両方の操作の応答の受信メッセージを作成する必要があります。  

3. ReadLOB と UpdateLOB の両方の操作を呼び出すオーケストレーションを作成します。  

4. ビルドし、BizTalk プロジェクトを配置します。  

5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  

6. BizTalk アプリケーションを起動します。  

   このトピックでは、これらのタスクを実行する手順を説明します。  

## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル Operate_LOB、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。  

## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックで ReadLOB と UpdateLOB の操作を実行する方法を示すを生成、Oracle データベースで SCOTT スキーマ CUSTOMER テーブルに表示されるこれらの操作のメタデータ。 このテーブルは、サンプルで提供される SQL スクリプトを実行して、SCOTT スキーマの下に作成されます。 サンプルの詳細については、[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)を参照してください。  

## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類 ウィンドウからのメッセージを最初の手順で生成したスキーマをリンクする必要があります。  

 このトピックでは、2 つの要求-応答メッセージのセットを作成する必要があります: ReadLOB 操作および UpdateLOB 操作用に設定 2 番目の要求-応答の 1 つの要求-応答を設定します。  

 メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  

#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  

1. 開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  

2. オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  

3. 新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  

4. **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  


   |   プロパティ   |                                                                                                                                       目的                                                                                                                                       |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  [Identifier]  |                                                                                                                                   型**要求**します。                                                                                                                                    |
   | メッセージ型 | ドロップダウン リストから展開**スキーマ**、選択および*Operate_LOB します。OracleDBBindingSchema.ReadLOB*<em>、</em>場所*Operate_LOB* BizTalk プロジェクトの名前を指定します。 *OracleDBBindingSchema*は CUSTOMER テーブルに対する ReadLOB と UpdateLOB 操作に対して生成されるスキーマです。 |


5. 次の 3 つ以上のメッセージを作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  

   |識別子を設定するには|メッセージの種類を設定|  
   |-----------------------|-------------------------|  
   |応答|*Operate_LOB します。OracleDBBindingSchema.ReadLOBResponse*|  
   |Request2|*Operate_LOB します。OracleDBBindingSchema.UpdateLOB*|  
   |Response2|*Operate_LOB します。OracleDBBindingSchema.UpdateLOBResponse*|  

## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ReadLOB と UpdateLOB のテーブルに対する操作を呼び出すためです。 このオーケストレーションでは、ReadLOB 操作と UpdateLOB 操作用に 2 つの要求メッセージをドロップします。 これらのメッセージの受信場所は削除されます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージを使用し、ODP を使用して Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。  

 オーケストレーションでは、同時に 2 つの要求が取得するために並列アクション図形をオーケストレーションに含める必要があります。 並列アクションごとも含まれます、受信図形を Oracle データベースにメッセージを送信し、応答を受信する必要があります。 ただし、両方の操作のメッセージを送受信するため、同じポートを使用できます。 ReadLOB および UpdateLOB の操作を同時に実行するための一般的なオーケストレーションが含まれます。  

- Oracle データベースにメッセージを送信し、応答を受信する図形を送受信します。  

- Oracle データベースに送信する要求メッセージを受信するポートは一方向の受信します。  

- 双方向の送信要求メッセージを Oracle データベースし、応答の受信を送信するポート。  

- フォルダーに Oracle データベースからの応答を送信する一方向の送信ポート。  

  サンプル オーケストレーションには、次のようになります。  

  ![LOB データの読み取りと更新のオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/6523b5e4-3689-433a-8287-eebc36f10442.gif "6523b5e4-3689-433a-8287-eebc36f10442")  

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

 2 つの要求を処理するため、これらのポートを使用して応答メッセージは、ポートごとに各操作が 1 つのメッセージの種類に対応する 2 つの操作を作成する必要があります。 操作を作成するポート図形を右クリックし、**新しい操作**します。 最初の操作としては、各ポートの名前を付けます**ReadLOB**としてポートごとに 2 番目の操作と**UpdateLOB**します。  

### <a name="using-correlation"></a>相関関係の使用  
 関連付けは、受信メッセージをオーケストレーションの適切なインスタンスに一致させるプロセスです。 削除するオーケストレーションに 2 つの要求メッセージは、各オーバー ロードのいずれか。 相関関係を使用して、適切なオーケストレーションを要求メッセージに関連付けます。 相関関係の詳細については、[オーケストレーションでの相関関係を使用して](../../core/using-correlations-in-orchestrations.md)を参照してください。  

##### <a name="to-use-correlations"></a>相関関係を使用するには  

1.  操作ごとに生成されたスキーマからプロパティを昇格します。 たとえば、ReadLOB 操作スキーマから LOB_COLUMN プロパティを昇格させますUpdateLOB 操作のスキーマから、FILTER プロパティを昇格します。 プロパティを昇格させるには、スキーマ ビューでプロパティを右クリックして**昇格**、し、**クイック昇格**します。 これにより、PropertySchema.xsd ファイルが BizTalk プロジェクトに追加します。  

     プロパティを昇格する方法の詳細については、[プロパティの昇格](../../core/promoting-properties.md)を参照してください。  

2.  オーケストレーションの種類を右クリックして**関連付けの種類**、し、**新しい関連付けの種類**します。  

3.  **関連付けのプロパティ** ダイアログ ボックスには、手順 1. で昇格させたプロパティが一覧表示されます。 プロパティを選択し、**追加**します。  

4.  **[OK]** をクリックします。  

5.  その他の昇格させたプロパティの関連付けの種類を作成するには、この手順を繰り返します。  

6.  関連付けられている操作に基づいて関連付けの種類の名前を変更します。 関連付けの種類の名前を変更することが*CorrelationType_ReadLOB* (ReadLOB 操作) のと*CorrelationType_UpdateLOB* (UpdateLOB 操作) にします。  

7.  オーケストレーションの種類を右クリックして**関連付けセット**、し、**新しい関連付けセット**します。  

8.  新しく追加された関連付けセットを右クリックし、をクリックし、**プロパティ**します。 **プロパティ**ウィンドウで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |[関連付けの種類]|*Operate_LOB します。CorrelationType_ReadLOB*|  
    |[Identifier]|*Correlation_ReadLOB*|  

9. 別の関連付けセットを追加し、[プロパティ] ウィンドウから次のプロパティを指定します。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |[関連付けの種類]|*Operate_LOB します。CorrelationType_UpdateLOB*|  
    |[Identifier]|*Correlation_UpdateLOB*|  

## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形は、メッセージを指定し、ポートに接続  
 次の表では、プロパティとその値をアクション図形のメッセージを指定し、それらのポートにリンクを設定する必要がありますを指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  

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

 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  

 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。  

## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)を参照してください。

 アプリケーションを構成する必要があります。  

- アプリケーションのホストを選択します。  

- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  

  - ハード ディスクと ReadLOB および UpdateLOB 操作に対して 1 つずつ要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用して、Oracle データベースに送信します。  

  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが、各操作は、Oracle データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。  

  - Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 Wcf-custom または Wcf-oracledb のポートを作成する方法については、[、Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)を参照してください。 Wcf-custom または Wcf-oracledb 送信ポートは 1 つ以上のスキーマに準拠したメッセージの送受信および 2 つの操作を実行、ためには、両方の操作のための動的アクションを設定する必要があります。 アクションの詳細については、[Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)を参照してください。 このオーケストレーションでは、アクションをよう設定する必要があります。  

    ```  
    <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
      <Operation Name="ReadLOB" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/ReadLOB" />  
      <Operation Name="UpdateLOB" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB" />  
    </BtsActionMapping>  
    ```  

    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk Server 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、[Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)を参照してください。  

## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle データベースで操作を実行するための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)を参照してください。  

 この段階で、ことを確認します。  

-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  

-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  

-   WCF カスタムでは、ポート、またはデータベースが実行されている Oracle にメッセージを送信するには、Wcf-oracledb を送信します。  

-   操作の BizTalk オーケストレーションが実行されています。  

## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後は、要求ファイルへのメッセージの受信場所を削除する必要があります。 要求メッセージのスキーマは、以前に生成した操作のスキーマに準拠する必要があります。 参照してください[特殊な LOB 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)要求メッセージ スキーマを使用して LOB データ型に対する操作を呼び出すための詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  

 オーケストレーションでは、要求メッセージを使用し、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  

 このオーケストレーションでは、写真 (BLOB のデータ型) の CUSTOMER テーブルの列を更新する UpdateLOB 操作の要求メッセージを最初にドロップします。 特定の顧客、PHOTO 列の更新プログラムを起動する要求メッセージです。  

```  
<UpdateLOB xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <LOB_COLUMN>PHOTO</LOB_COLUMN>  
  <FILTER>Name='Mindy Martin'</FILTER>  
  <Stream>YWJjZA==</Stream>  
</UpdateLOB>  
```  

> [!NOTE]
>  フィルター文字列フェッチしなければなりません常に 1 つの一致する行それ以外の場合、Oracle データベース アダプター スロー XmlReaderParsingException。 値も、 \<Stream\> base64Binary 型の要素がある必要があります。  

 UpdateLOB 操作に対する応答は次のとおりです。  

```  
<?xml version="1.0" encoding="utf-8"?>  
<UpdateLOBResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER"></UpdateLOBResponse>  
```  

 UpdateLOB 操作によって更新されたデータを読み取る ReadLOB 操作の要求メッセージを削除するようになりました。 特定の顧客の写真の列に ReadLOB 操作を呼び出す要求メッセージです。  

```  
<ReadLOB xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <LOB_COLUMN>PHOTO</LOB_COLUMN>  
  <FILTER>NAME='Mindy Martin'</FILTER>  
</ReadLOB>  
```  

> [!NOTE]
>  フィルター文字列では、1 つの一致する行がフェッチ常にする必要があります。 1 つ以上の一致する行がある場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のみ (一致する) の最初の行の LOB 列が返されます。  

 ReadLOB 操作に対する応答は次のとおりです。  

```  
<?xml version="1.0" encoding="utf-8"?>  
<ReadLOBResponse mlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <ReadLOBResult>YWJjZA==</ReadLOBResult>  
</ReadLOBResponse>  
```  

> [!NOTE]
>  WSDL の検証に使用する、ReadLOB 操作の応答があります。 WSDL に対して ReadLOB を検証する特定のタスクを実行する必要があります。 詳細については、[運用上の問題のトラブルシューティング](https://msdn.microsoft.com/library/dd787883.aspx)を参照してください。  

## <a name="possible-exceptions"></a>可能性のある例外  
 例外に関する情報を使用して LOB データを含むテーブルに対する操作の実行中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラー処理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)します。  

## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、[Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)を参照してください。  

## <a name="see-also"></a>参照  
[Oracle Database による開発の BizTalk アプリケーションを構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)