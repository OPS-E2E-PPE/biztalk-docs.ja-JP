---
title: "Oracle E-business Suite で複合操作を完了 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 886d066d-2ec8-41b4-bdd5-d8afcb5e3e58
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6e53179e82e7f41f264401b5ebf1c9c022e9727
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="complete-composite-operations-on-oracle-e-business-suite"></a>Oracle E-business Suite で複合操作を完了します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが Oracle データベースでの複合操作を実行できるようにします。 複合操作を含めることができます。  
  
-   挿入、更新、削除、およびデータベースのテーブルに対する操作を選択します。 データベース ビューに対して操作を選択します。  
  
-   挿入、更新、削除、およびインターフェイス テーブルに対する操作を選択します。 インターフェイス ビューで操作を選択します。  
  
-   ストアド プロシージャおよび関数、内部または外部パッケージです。  
  
 1 つの複合操作は、任意の順序でこれらの操作の任意の数を持つことができます。 たとえば、2 つの insert、delete、およびストアド プロシージャの実行の最後に続くことができます。 また、さまざまな操作が別のデータベース テーブルまたはビューを対象とすることができます。 アダプターが複合操作をサポートする方法の詳細については、次を参照してください。[複合操作に対するサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)です。 複合操作用の SOAP メッセージの構造については、次を参照してください。[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)です。  
  
## <a name="how-to-perform-composite-operations-on-oracle-database"></a>Oracle データベースでの複合操作を実行する方法  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [Oracle E-business Suite アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)です。 Oracle データベースでの複合操作を実行するには、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]し、呼び出し先のすべての操作のスキーマを生成します。  
  
2.  前の手順で生成したすべてのスキーマへの参照を含むスキーマ ファイルを手動で作成します。  
  
3.  Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。 これらのメッセージは、前の手順で作成した要求と応答のスキーマに準拠する必要があります。  
  
4.  Oracle データベースで複合操作を呼び出すオーケストレーションを作成します。  
  
5.  構築し、BizTalk プロジェクトを展開します。  
  
6.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
7.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する方法についてを説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、複合操作を実行する方法を示すは実行します同じ順序で次のタスク。  
  
-   ACCOUNTACTIVITY テーブルにレコードを挿入します。  
  
-   ACCOUNT_PKG パッケージ内で GET_ALL_ACTIVITY プロシージャを呼び出すことによって、ACCOUNTACTIVITY テーブル内のすべてのレコードを取得します。  
  
-   ACCOUNTACTIVITY テーブルからレコードを削除します。  
  
 ACCOUNTACTIVITY テーブルを作成するサンプルに用意されているスクリプトを実行します。 サンプルの詳細については、次を参照してください。[サンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。  
  
 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  
  
## <a name="creating-a-composite-schema-definition"></a>複合のスキーマ定義を作成します。  
 今すぐに複合スキーマを作成する必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]個々 の操作用に作成したスキーマを参照する BizTalk プロジェクトです。 複合のスキーマ定義を作成する次の手順を実行します。  
  
#### <a name="to-add-a-composite-schema-definition"></a>複合のスキーマ定義を追加するには  
  
1.  BizTalk プロジェクトにスキーマ ファイルを追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 ソリューション名を右クリックし、**追加**、クリックして**新しい項目の**します。 **新しい項目の追加** ダイアログ ボックスから、**カテゴリ**ボックスで、クリックして**スキーマ ファイル**です。 **テンプレート**ボックスで、クリックして**スキーマ**です。 スキーマ ファイルの名前を指定し、をクリックして**OK**です。  
  
     この例で、ファイルとスキーマ名を指定`CompositeSchema.xsd`です。  
  
2.  実行する別の操作の生成スキーマへの参照を追加します。 この例では操作に対して生成されるさまざまなスキーマには。  
  
    -   OracleEBSBinding.xsd、ACCOUNTACTIVITY テーブルに対する挿入および削除の操作です。  
  
    -   OracleEBSBinding2.xsd、GET_ALL_ACTIVITY プロシージャです。  
  
     参照を追加します。  
  
    1.  ルートを右クリックして**\<スキーマ\>** CompositeSchema.xsd、およびクリック ノード**プロパティ**です。  
  
    2.  **プロパティ**ボックスで、省略記号ボタンをクリックして**([...])**に対して、 **Imports**プロパティです。  
  
         ![スキーマ定義をインポート](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")  
  
    3.  **Imports** ] ダイアログ ボックスから、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、順にクリック**追加**です。  
  
    4.  **BizTalk 型の選択** ダイアログ ボックスで、BizTalk プロジェクト名 ノードを展開し、展開**スキーマ**、し、インポートするスキーマを選択します。 この例では、< BizTalk_project_name > を選択します。OracleEBSBinding.xsd です。 **[OK]**をクリックします。  
  
         < BizTalk_project_name > をインポートするには、この手順を繰り返します。OracleEBSBinding2.xsd すぎます。  
  
    5.  **Imports**ダイアログ ボックスで、をクリックして**OK**です。  
  
3.  ルート スキーマ ノードに 2 つの子ノードを追加します。 1 つの子ノードは、複合操作を実行するため、要求スキーマに対応します。 その他の子ノードは、応答スキーマに対応します。 Request スキーマに対応するノードには、任意の名前を持つことができます。 応答スキーマに対応するノードには、< request_schema_node > 応答を呼び出す必要があります。 この例として、要求スキーマのノードを呼び出しては**要求**です。 そのため、応答スキーマのノードと呼びます**RequestResponse**です。  
  
    > [!NOTE]
    >  既定では、**ルート**ノードが新しいスキーマ ファイルにも追加します。 名前を変更することができます、**ルート**ノード**要求**です。 ノードの名前を変更するノード名を右クリックし、をクリックして**の名前を変更**です。  
  
     下のノードを追加する、 **\<スキーマ\>**ノード。  
  
    1.  右クリックし、 **\<スキーマ\>**に**スキーマ ノードの挿入**、 をクリック**子レコード**です。  
  
    2.  新しいノードの名前を**RequestResponse**です。  
  
4.  下に子ノードを追加、**要求**複合操作の一部として実行する各操作の要求スキーマに対応するノードです。 この例では、次に対応する子ノードを追加する必要があります。  
  
    -   挿入し、ACCOUNTACTIVITY テーブルに対する操作を削除します。  
  
    -   GET_ALL_ACTIVITY プロシージャです。  
  
    > [!IMPORTANT]
    >  操作を実行する同じ順序でのノードを追加する必要があります。 たとえば、レコードを挿入し、ストアド プロシージャを実行し、挿入操作のノードを追加する必要があります最初のレコードを削除する場合は、後に、ストアド プロシージャのノードと最後に、削除操作のノード。  
  
     子ノードを追加する、**要求**ノード。  
  
    1.  右クリックし、**要求**に**スキーマ ノードの挿入**、順にクリック**子レコード**です。  
  
         ![スキーマの子ノードの挿入](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")  
  
    2.  複合操作の一部として実行する操作の要求スキーマに対応するレコードの名前を変更します。 たとえば、"Insert"するノードの名前を変更します。  
  
    3.  マップ、**挿入**ACCOUNTACTIVITY テーブルに対する挿入操作の要求スキーマのノードです。 これを行うを右クリックし、**挿入** ノードをクリック**プロパティ**です。 **プロパティ**] ボックスから、 **Data Structure Type**一覧で、[**挿入 (参照)**です。  
  
         ![要求スキーマに子ノードをマップ](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")  
  
    4.  GET_ALL_ACTIVITY ストアド プロシージャおよび削除操作の要求スキーマのノードを追加する手順を繰り返します。 ノード名を指定し、次の表で説明したように、対応するスキーマにマップします。  
  
        |ノード名|スキーマにマップされています。|  
        |---------------|----------------------|  
        |GET_ALL_ACTIVITY|GET_ALL_ACTIVITY (参照)|  
        |DELETE|削除 (参照)|  
  
5.  下に子ノードを追加、 **RequestResponse**複合操作の一部として実行する各操作の応答スキーマに対応するノードです。 この例では、次に対応する子ノードを追加する必要があります。  
  
    -   挿入し、ACCOUNTACTIVITY テーブルに対する操作を削除します。  
  
    -   GET_ALL_ACTIVITY はストアド プロシージャです。  
  
    > [!IMPORTANT]
    >  下の子ノードと同じ順序で子ノードを追加する必要があります、**要求**ノード。  
  
     子ノードを追加する、 **RequestResponse**ノード。  
  
    1.  右クリックし、 **RequestResponse**に**スキーマ ノードの挿入**、 をクリック**子レコード**です。  
  
    2.  複合操作の一部として実行する操作の応答スキーマに対応するレコードの名前を変更します。 たとえば、"InsertResponse"するノードの名前を変更します。  
  
    3.  マップ、 **InsertResponse** ACCOUNTACTIVITY テーブルに対する挿入操作用の応答スキーマにノードです。 これを行うを右クリックし、 **InsertResponse**ノード、およびクリック**プロパティ**です。 **プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **InsertResponse (参照)**です。  
  
    4.  GET_ALL_ACTIVITY ストアド プロシージャおよび削除操作の応答スキーマのノードを追加する手順を繰り返します。 ノード名を指定し、次の表で説明したように、対応するスキーマにマップします。  
  
        |ノード名|スキーマにマップされています。|  
        |---------------|----------------------|  
        |GET_ALL_ACTIVITYResponse|GET_ALL_ACTIVITYResponse (参照)|  
        |DeleteResponse|DeleteResponse (参照)|  
  
6.  保存、 **CompositeSchema.xsd**ファイル。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 最後の手順で作成した複合スキーマでは、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 オーケストレーションのメッセージを作成し、それらを前の手順で作成したスキーマにリンクする必要がありますようになりました。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *Composite_Op.CompositeSchema.Request*Composite_Op は、BizTalk プロジェクトの名前。 CompositeSchema は、複合操作用に手動で作成したスキーマです。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *Composite_Op.CompositeSchema.RequestResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle データベースでの複合操作を実行します。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 要求メッセージは、先ほど作成した複合スキーマに準拠する必要があります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]このメッセージを消費し、Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。 送信を含めるし、受信図形を Oracle データベースにメッセージを送信し、それぞれ、応答を受信する必要があります。 複合操作を実行するための基本的なオーケストレーションには、次のようになります。  
  
 ![複合操作を実行するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形のメッセージを指定して、ポートへの接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.CompositeOp.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.CompositeOp.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.CompositeOp.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.CompositeOp.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで以前に作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。  
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、Oracle データベースに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracleebs 送信ポートを定義します。 操作の場合は、単一のトランザクションで複合操作の一部が実行されるとしていることを確認するため、 **UseAmbientTransaction**に設定されているプロパティのバインド**True**です。  
  
         送信ポートでアクションを指定することもあります。 複合操作のアクションは、"CompositeOperation"です。 ポートを作成する方法については、次を参照してください。 [Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)です。 ポートのアクションを指定する方法の詳細については、次を参照してください。 [for Oracle E-business Suite SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)です。  
  
        > [!IMPORTANT]
        >  格納されている複合操作は、の一部、オブジェクトで操作を実行している場合は、たとえばプロシージャ、関数、インターフェイスのテーブル、または Oracle E-business Suite アプリケーションに属するインターフェイス ビュー、アプリケーションのコンテキストを設定する必要があります。必要なバインドのプロパティを指定します。 アプリケーション コンテキストの設定の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
        >   
        >  アプリケーション コンテキストを設定するには、バインドのプロパティを指定することによって、またはメッセージによって公開されるコンテキスト プロパティを設定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 バインドのプロパティを設定する方法の手順については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定する方法の手順については、次を参照してください。 [Oracle E-business suite アプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。[を構成する物理ポートのバインドを使用して、ポートのバインド ファイルを Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)です。 選択したすべての操作に関連する動的なアクションには、送信ポートでアクションが設定されているこのバインド ファイルをインポートする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中にします。 複合操作では、"CompositeOperation"がある動的アクションを置き換える必要があります。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle データベースでの複合操作を実行する BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Wcf-custom または Wcf-oracleebs は、Oracle データベースが実行中にメッセージを送信ポートを送信します。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、ファイルに要求メッセージをドロップする必要がありますの受信場所。 要求メッセージのスキーマは、先ほど作成した複合操作のスキーマに準拠する必要があります。 たとえば、ACCOUNTACTIVITY テーブルにレコードを挿入、GET_ALL_ACTIVITY ストアド プロシージャを呼び出すし、ACCOUNTACTIVITY テーブルからレコードを削除する要求メッセージには。  
  
```  
<Request xmlns="http://Composite_Op.CompositeSchema">  
  <Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/ACCOUNTACTIVITY">  
    <RECORDSET>  
      <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/SCOTT/ACCOUNTACTIVITY">  
        <TID InlineValue="tid_seq.nextval"></TID>  
        <ACCOUNT>100001</ACCOUNT>  
        <AMOUNT>1500</AMOUNT>  
        <DESCRIPTION></DESCRIPTION>  
        <TRANSDATE InlineValue="sysdate">1999-05-31T13:20:00</TRANSDATE>  
        <PROCESSED>n</PROCESSED>  
      </InsertRecord>  
    </RECORDSET>  
  </Insert>  
  <GET_ALL_ACTIVITY xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG" />  
  <Delete xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/ACCOUNTACTIVITY">  
    <FILTER>WHERE AMOUNT = 1500</FILTER>  
  </Delete>  
</Request>  
```  
  
 上記の要求メッセージは、最初のレコードを挿入して、ACCOUNTACTIVITY テーブルのすべてのレコードを取得する GET_ALL_ACTIVITY プロシージャを呼び出します。 次に、挿入されたレコードは、フィルター句を指定することによって削除されます。 詳細については、要求メッセージ スキーマを使用して Oracle データベースでの複合操作を実行する複合操作のメッセージ スキーマを参照してください、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
> [!NOTE]
>  上記のメッセージには、挿入操作の抜粋は、"InlineValue"属性を使用します。 "InlineValue"属性の詳細については、挿入操作のスキーマの説明を参照してください[Insert、Update、Delete、および選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)です。  
  
 オーケストレーションはメッセージを使用して、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、次のよう、上記の要求メッセージ用の Oracle データベースからの応答。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://Composite_Op.CompositeSchema">  
  <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/ACCOUNTACTIVITY">  
    <InsertResult>1</InsertResult>   
  </InsertResponse>  
  <GET_ALL_ACTIVITYResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG">  
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
  <DeleteResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/ACCOUNTACTIVITY">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  
  
 前の応答には、複合操作の一部として実行されるさまざまな操作を対応する複数の結果セットが含まれています。 たとえば、`InsertResult`要素には、'1'、挿入操作によって挿入された行の数を示すが含まれています。 同様に、`DeleteResult`要素には、'1'、削除操作によって削除された行の数を示すが含まれています。  
  
> [!IMPORTANT]
>  複合操作を実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が関係する複合操作の操作の数より少ない。  
>   
>  -   BFILE、BLOB、CLOB、NCLOB、および REF CURSOR とアウトを含むストアド プロシージャまたは IN OUT パラメーターです。  
> -   操作を選択します。  
>   
>  この問題を解決するには、ある複合操作では、このような操作の"n"の数がある場合は、指定した値を確認する必要があります、 **MinPoolSize** "n+1"プロパティのバインドは以上です。 詳細については、 **MinPoolSize**バインディング プロパティを参照してください[BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business Suite でアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)