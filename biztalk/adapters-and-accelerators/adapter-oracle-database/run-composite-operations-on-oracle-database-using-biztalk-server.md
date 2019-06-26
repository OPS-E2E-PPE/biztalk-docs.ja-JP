---
title: BizTalk Server を使用して Oracle データベースでの複合操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf47d95e-cdf1-4c9b-a15a-7cf123d0ea6d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e213421e7b97f6b8152be05830a381bd44e441d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376110"
---
# <a name="run-composite-operations-on-oracle-database-using-biztalk-server"></a>BizTalk Server を使用して Oracle データベースでの複合操作の実行します。
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントが Oracle データベースでの複合操作を実行できるようにします。 複合操作を含めることができます。  

- 挿入、更新、削除、およびテーブルとビューで操作を選択します。  

- ストアド プロシージャおよび関数、内部または外部パッケージ。  

  1 つの複合操作では、任意の順序でこれらの操作の任意の数を持つことができます。 たとえば、2 つの insert、delete、および最後に、ストアド プロシージャの実行後にすることができます。 また、さまざまなオペレーションを別のデータベース テーブルまたはビューを対象とすることができます。 アダプターが複合操作をサポートする方法の詳細については、次を参照してください。 [Oracle データベースで複合操作を実行する](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)します。 複合操作の SOAP メッセージの構造については、次を参照してください。[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)します。  

## <a name="how-to-perform-composite-operations-on-oracle-database"></a>Oracle データベースでの複合操作を実行する方法は?  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)します。 これらのタスクは Oracle database での複合操作を行うには。  

1. BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を呼び出したいすべての操作のスキーマを生成します。  

2. 前の手順で生成したすべてのスキーマへの参照が含まれるスキーマ ファイルを手動で作成します。  

3. Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。 これらのメッセージは、前の手順で作成した要求と応答のスキーマに準拠する必要があります。  

4. Oracle データベースでの複合操作を呼び出すオーケストレーションを作成します。  

5. ビルドし、BizTalk プロジェクトを配置します。  

6. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  

7. BizTalk アプリケーションを起動します。  

   このトピックでは、これらのタスクを実行する方法について説明します。  

## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、複合操作を実行する方法を示すに、同じ順序で、次のタスクが実行しますされます。  

- ACCOUNTACTIVITY テーブルにレコードを挿入します。  

- ACCOUNT_PKG パッケージ内で GET_ALL_ACTIVITY プロシージャを呼び出すことによって、ACCOUNTACTIVITY テーブル内のすべてのレコードを取得します。  

- ACCOUNTACTIVITY テーブルからレコードを削除します。  

  ACCOUNTACTIVITY テーブルを作成するサンプルに付属のスクリプトを実行します。 サンプルの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)します。  

  BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  

## <a name="creating-a-composite-schema-definition"></a>複合のスキーマ定義を作成します。  
 複合でスキーマを作成する必要が今すぐ、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]個々 の操作用に作成したスキーマを参照する BizTalk プロジェクト。 複合のスキーマ定義を作成する次の手順を実行します。  

#### <a name="to-add-a-composite-schema-definition"></a>複合のスキーマ定義を追加するには  

1. BizTalk プロジェクトにスキーマ ファイルを追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 ソリューション名を右クリックし、[**追加**、] をクリックし、**新しい項目の**します。 **新しい項目の追加**] ダイアログ ボックスから、**カテゴリ**ボックスで、[**スキーマ ファイル**します。 **テンプレート**ボックスで、**スキーマ**します。 スキーマ ファイルの名前を指定し、クリックして**OK**します。  

    この例で、スキーマ ファイル名を指定`CompositeSchema.xsd`します。  

2. 実行するさまざまな操作の生成スキーマへの参照を追加します。 この例では、操作に対して生成されたさまざまなスキーマは。  

   - OracleDBBinding.xsd、ACCOUNTACTIVITY テーブルに対する Insert および Delete の操作。  

   - OracleDBBinding2.xsd、GET_ALL_ACTIVITY プロシージャ。  

     参照を追加します。  

   1.  ルートを右クリックして **\<スキーマ\>** CompositeSchema.xsd をクリックしますノード**プロパティ**します。  

   2.  **プロパティ**ボックスで、省略記号ボタンをクリックします **([...])。** に対して、 **Imports**プロパティ。  

        ![スキーマの定義をインポート](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")  

   3.  **インポート**] ダイアログ ボックスから、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、順にクリックします**追加**します。  

   4.  **BizTalk 型の選択** ダイアログ ボックスで、BizTalk プロジェクト名のノードを展開し、展開**スキーマ**、しをインポートするスキーマを選択します。 この例では、< BizTalk_project_name > を選択します。OracleDBBinding.xsd します。 **[OK]** をクリックします。  

        Repeat this step to import <BizTalk_project_name>.OracleDBBinding2.xsd too.  

   5.  **インポート**ダイアログ ボックスで、をクリックして**OK**。  

3. ルート スキーマ ノードには、2 つの子ノードを追加します。 1 つの子ノードは、複合操作を実行するための要求スキーマに対応します。 その他の子ノードは、応答スキーマに対応します。 要求スキーマに対応するノードは、任意の名前を持つことができます。 応答スキーマに対応するノードには、< request_schema_node > 応答を呼び出す必要があります。 この例では、要求スキーマのノードとしてを呼び出し、**要求**します。 そのため、応答スキーマのノードと呼びます**RequestResponse**します。  

   > [!NOTE]
   >  既定で、**ルート**ノードは、新しいスキーマ ファイルにも追加されます。 名前を変更することができます、**ルート**ノード**要求**します。 ノードの名前を変更するノード名を右クリックし、をクリックして**の名前を変更**します。  

    下のノードを追加する、 **\<スキーマ\>** ノード。  

   1.  右クリックし、 **\<スキーマ\>** に**スキーマ ノードの挿入**、 をクリック**子レコード**します。  

   2.  新しいノードの名前を変更**RequestResponse**します。  

4. 下の子ノードを追加、**要求**複合操作の一部として実行する各操作の要求スキーマに対応するノード。 この例では、次に対応する子ノードを追加する必要があります。  

   -   挿入し、ACCOUNTACTIVITY テーブルに対する操作を削除します。  

   -   GET_ALL_ACTIVITY プロシージャです。  

   > [!IMPORTANT]
   >  操作を実行するのと同じ順序でノードを追加する必要があります。 など、レコードを挿入し、ストアド プロシージャを実行し、挿入操作のノードを追加する必要があります最初のレコードを削除する場合は、後に、ストアド プロシージャのノードと最後に、削除操作のノード。  

    子ノードを追加する、**要求**ノード。  

   1.  右クリックし、**要求**に**スキーマ ノードの挿入**、 をクリックし、**子レコード**します。  

        ![スキーマの子ノードの挿入](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")  

   2.  複合操作の一環として実行する操作の要求スキーマに対応するレコードの名前を変更します。 たとえば、"Insert"するノードの名前を変更します。  

   3.  マップ、**挿入**ACCOUNTACTIVITY テーブルに対する挿入操作の要求スキーマのノード。 これを行うを右クリックし、**挿入**ノード、およびクリック**プロパティ**。 **プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **Insert (リファレンス)** します。  

        ![要求スキーマに子ノードをマップ](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")  

   4.  GET_ALL_ACTIVITY ストアド プロシージャと削除操作の要求スキーマのノードを追加するには、この手順を繰り返します。 ノード名を指定し、次の表で説明したように、それらを対応するスキーマにマップします。  

       |ノード名|スキーマにマップ|  
       |---------------|----------------------|  
       |GET_ALL_ACTIVITY|GET_ALL_ACTIVITY (リファレンス)|  
       |DELETE|削除 (リファレンス)|  

5. 下の子ノードを追加、 **RequestResponse**複合操作の一部として実行する各操作の応答スキーマに対応するノード。 この例では、次に対応する子ノードを追加する必要があります。  

   -   挿入し、ACCOUNTACTIVITY テーブルに対する操作を削除します。  

   -   GET_ALL_ACTIVITY はストアド プロシージャです。  

   > [!IMPORTANT]
   >  下の子ノードと同じ順序で子ノードを追加する必要があります、**要求**ノード。  

    子ノードを追加する、 **RequestResponse**ノード。  

   1.  右クリックし、 **RequestResponse**に**スキーマ ノードの挿入**、 をクリック**子レコード**します。  

   2.  複合操作の一環として実行する操作の応答スキーマに対応するレコードの名前を変更します。 たとえば、"InsertResponse"するノードの名前を変更します。  

   3.  マップ、 **InsertResponse**を ACCOUNTACTIVITY テーブルに対する挿入操作の応答スキーマのノード。 これを行うを右クリックし、 **InsertResponse**ノード、およびクリック**プロパティ**します。 **プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **InsertResponse (リファレンス)** します。  

   4.  GET_ALL_ACTIVITY ストアド プロシージャと削除操作の応答スキーマのノードを追加するには、この手順を繰り返します。 ノード名を指定し、次の表で説明したように、それらを対応するスキーマにマップします。  

       |ノード名|スキーマにマップ|  
       |---------------|----------------------|  
       |GET_ALL_ACTIVITYResponse|GET_ALL_ACTIVITYResponse (リファレンス)|  
       |DeleteResponse|DeleteResponse (リファレンス)|  

6. 保存、 **CompositeSchema.xsd**ファイル。  

## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 最後の手順で作成した複合スキーマでは、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 オーケストレーションのメッセージを作成し、前の手順で作成したスキーマにそれらをリンクする必要がありますようになりました。  

#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  

1. オーケストレーションを BizTalk プロジェクトに追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  

2. 開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  

3. オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  

4. 新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  

5. **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  


   |   プロパティ   |                                                                                                                  目的                                                                                                                   |
   |--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  [Identifier]  |                                                                                                                「`Request`」と入力します。                                                                                                                 |
   | メッセージ型 | ドロップダウン リストから展開**スキーマ**、し、 *Composite_Op.CompositeSchema.Request*Composite_Op は、BizTalk プロジェクトの名前です。 CompositeSchema は複合操作用に手動で作成したスキーマを示します。 |


6. 新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  

   |プロパティ|目的|  
   |--------------|----------------|  
   |[Identifier]|「`Response`」と入力します。|  
   |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *Composite_Op.CompositeSchema.RequestResponse*します。|  

## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle database での複合操作を実行するためです。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 要求メッセージは、先ほど作成した複合スキーマに準拠する必要があります。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]がこのメッセージを使用して、Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。 送信を含めるし、受信図形を Oracle データベースにメッセージを送信し、それぞれ、応答を受信する必要があります。 複合操作を実行するための基本的なオーケストレーションには、次のようになります。  

 ![複合操作を実行するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")  

### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  

|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  

### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  

|Port|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  

### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形は、メッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  

|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.CompositeOp.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.CompositeOp.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.CompositeOp.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.CompositeOp.Request*|  

 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  

 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。  

## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。

 アプリケーションを構成する必要があります。  

- アプリケーションのホストを選択します。  

- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  

  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、Oracle データベースに送信します。  

  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。  

  - Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。 複合操作の一部が単一のトランザクションで実行されるようが含まれている操作を確認するため、 **UseAmbientTransaction**に設定されているプロパティのバインド**True**します。  

     送信ポートでアクションを指定することも必要があります。 複合操作のアクションは、"<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”>します。 ポートを作成する方法については、次を参照してください。 [、Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)します。 ポートのアクションを指定する方法の詳細については、次を参照してください。 [Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)します。  

    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。 詳細については、次を参照してください。 [Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)します。 選択したすべての操作に関連する動的アクションには、送信ポートでアクションが設定されているこのバインド ファイルをインポートする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中にします。 複合操作の場合は、動的操作を置き換える必要があります"<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”>します。  

## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle データベースでの複合演算を実行する BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。  

 この段階で、ことを確認します。  

-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  

-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  

-   Oracle データベースにメッセージを送信する Wcf-custom または Wcf-oracledb 送信ポートが実行されています。  

-   操作の BizTalk オーケストレーションが実行されています。  

## <a name="executing-the-operation"></a>操作の実行  
 ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。 要求メッセージのスキーマは、先ほど作成した複合操作のスキーマに準拠する必要があります。 たとえば、ACCOUNTACTIVITY テーブルにレコードを挿入、GET_ALL_ACTIVITY ストアド プロシージャを呼び出すし、ACCOUNTACTIVITY テーブルからレコードを削除する要求メッセージには。  

```  
<Request xmlns="http://Composite_Op.CompositeSchema">  
  <Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <RECORDSET>  
      <ACCOUNTACTIVITYRECORDINSERT>  
        <TID>1</TID>  
        <ACCOUNT>100001</ACCOUNT>  
        <AMOUNT>1500</AMOUNT>  
        <DESCRIPTION></DESCRIPTION>  
        <TRANSDATE>2008-06-21T15:52:19</TRANSDATE>  
        <PROCESSED>n</PROCESSED>  
      </ACCOUNTACTIVITYRECORDINSERT >  
    </RECORDSET>  
  </Insert>  
  <GET_ALL_ACTIVITY xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"/>  
  <Delete xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <FILTER>WHERE AMOUNT = 1500</FILTER>  
  </Delete>  
</Request>  
```  

 前の要求メッセージでは、最初のレコードを挿入して、ACCOUNTACTIVITY テーブル内のすべてのレコードを取得する GET_ALL_ACTIVITY プロシージャを呼び出します。 次に、フィルター句を指定することによって、挿入されたレコードが削除されます。 参照してください[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)Oracle に対する複合操作を実行するための要求メッセージ スキーマの詳細については、データベースを使用して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  

 オーケストレーションはメッセージを使用し、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、前の要求メッセージ用の Oracle データベースからの応答は、次するようになります。  

```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://Composite_Op.CompositeSchema">  
  <InsertResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOOT/Table/ACCOUNTACTIVITY">  
    <InsertResult>1</InsertResult>   
  </InsertResponse>  
  <GET_ALL_ACTIVITYResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
    <ALLRECS>  
      <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
        <xs:element msdata:IsDataSet="true" name="NewDataSet">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="AMOUNT" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="DESCRIPTION" type="xs:string" />   
                    <xs:element minOccurs="0" name="TRANSDATE" type="xs:dateTime" />   
                    <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                  </xs:sequence>  
                </xs:complexType>  
              </xs:element>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:schema>  
      <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
        <NewDataSet xmlns="">  
          <NewTable>  
            ......   
            ......   
          </NewTable>  
          ......  
          ......  
          <NewTable>  
            <TID>10</TID>   
            <ACCOUNT>100001</ACCOUNT>   
            <AMOUNT>1000</AMOUNT>   
            <TRANSDATE>2008-07-28T21:39:57</TRANSDATE>   
            <PROCESSED>n</PROCESSED>   
          </NewTable>  
        </NewDataSet>  
      </diffgr:diffgram>  
    </ALLRECS>  
  </GET_ALL_ACTIVITYResponse>  
  <DeleteResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  

 前の応答には、複合操作の一部として実行されるさまざまな操作を対応する複数の結果セットが含まれています。 たとえば、`InsertResult`要素に '1'、挿入操作によって挿入された行の数を示すが含まれています。 同様に、`DeleteResult`要素に '1'、削除操作によって削除された行の数を示すが含まれています。  

> [!IMPORTANT]
>  複合操作の実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が、複合操作に関連する操作の数より少ない。  
> 
> - OUT、BFILE、BLOB、CLOB、NCLOB、および REF CURSOR を含むストアド プロシージャまたは IN OUT パラメーター。  
>   -   操作を選択します。  
> 
>   この問題を解決するには、複合操作では、このような操作の数を"n"がある場合は、値が指定を確認する必要があります、 **MinPoolSize** "n+1"プロパティをバインドは以上です。 詳細については、 **MinPoolSize**プロパティ、バインドを参照してください[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)します。  

## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、次を参照してください。[再利用の Oracle データベース アダプターのバインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)します。  

## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)