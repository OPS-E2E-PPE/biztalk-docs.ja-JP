---
title: BizTalk Server を使用して SQL Server での複合操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86fd2aa1-20c7-4b58-9f35-83ba0c959cf1
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62605fef85727311b2a2396463c2b43b690e86e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004331"
---
# <a name="run-composite-operations-on-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server での複合操作を実行します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントが SQL Server データベースでの複合操作を実行できるようにします。 複合操作を含めることができます。  
  
- 挿入、更新、および削除操作です。 選択操作は複合操作の一部としてサポートされていません。  
  
- ストアド プロシージャの操作として実行します。  
  
  1 つの複合操作では、任意の順序でこれらの操作の任意の数を持つことができます。 たとえば、2 つの挿入操作の後に、削除操作と最後に、ストアド プロシージャの実行することができます。 また、さまざまなオペレーションを別のデータベース テーブルまたはビューを対象とすることができます。 アダプターが複合操作をサポートする方法の詳細については、次を参照してください。[複合操作の実行、SQL アダプターを使用して SQL Server で](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)します。 複合操作の SOAP メッセージの構造については、次を参照してください。[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)します。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルに対して操作を実行している場合ことを確認するを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューで操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。  
  
## <a name="how-to-perform-composite-operations-on-sql-server"></a>SQL Server での複合操作を実行する方法  
 SQL Server を使用して、操作を実行する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)します。 これらのタスクは SQL Server データベースでの複合操作を行うには。  
  
1. BizTalk プロジェクトを作成し、呼び出すすべての操作のスキーマを生成します。  
  
2. 前の手順で生成したすべてのスキーマへの参照が含まれるスキーマ ファイルを手動で作成します。  
  
3. SQL Server データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。 これらのメッセージは、前の手順で作成した要求と応答のスキーマに準拠する必要があります。  
  
4. SQL Server データベースでの複合操作を呼び出すオーケストレーションを作成します。  
  
5. ビルドし、BizTalk プロジェクトを配置します。  
  
6. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
7. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する方法について説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル CompositeOperations、このトピックの「に基づいてが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。 [SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックで、複合操作を実行する方法を示す、次のタスクで実行されます指定された順序。  
  
- EMPLOYEE テーブルにレコードを挿入します。  
  
- GET_LAST_EMP_DATA ストアド プロシージャを呼び出すことによって、挿入された最後のレコードのすべての列を取得します。  
  
- EMPLOYEE テーブルからレコードを削除します。  
  
  EMPLOYEE テーブルを作成するサンプルに付属のスクリプトを実行します。 サンプルの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)します。  
  
  BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]これらの操作のスキーマを生成します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。  
  
## <a name="creating-a-composite-schema-definition"></a>複合のスキーマ定義を作成します。  
 個々 の操作用に作成したスキーマを参照する複合スキーマを作成する必要がありますようになりました。 複合のスキーマ定義を作成する次の手順を実行します。  
  
#### <a name="to-add-a-composite-schema-definition"></a>複合のスキーマ定義を追加するには  
  
1. スキーマ ファイルを BizTalk プロジェクトに追加します。 プロジェクト名を右クリックし、[**追加**、] をクリックし、**新しい項目の**します。 **新しい項目の追加**] ダイアログ ボックスから、**カテゴリ**ボックスで、[**スキーマ ファイル**します。 **テンプレート**ボックスで、**スキーマ**します。 スキーマ ファイルの名前を指定し、クリックして**OK**します。  
  
    この例で、スキーマ ファイル名を指定`CompositeSchema.xsd`します。  
  
2. 実行するさまざまな操作の生成スキーマへの参照を追加します。 この例では、操作に対して生成されたさまざまなスキーマは。  
  
   - TableOperation.dbo.Employee.xsd、挿入または削除操作です。  
  
   - Procedure.dbo.xsd、GET_LAST_EMP_DATA のストアド プロシージャをします。  
  
     参照を追加します。  
  
   1.  ルートを右クリックして**\<スキーマ\>** CompositeSchema.xsd をクリックしますノード**プロパティ**します。  
  
   2.  **プロパティ**ボックスで、省略記号ボタンをクリックします **([...])。** に対して、 **Imports**プロパティ。  
  
        ![スキーマの定義をインポート](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")  
  
   3.  **インポート**] ダイアログ ボックスから、**として新しいスキーマのインポート**一覧で、[ **XSD のインポート**、順にクリックします**追加**します。  
  
   4.  **BizTalk 型の選択** ダイアログ ボックスで、BizTalk プロジェクト名のノードを展開し、展開**スキーマ**、しをインポートするスキーマを選択します。 この例では、< BizTalk_project_name > を選択します。TableOperation_dbo_Employee します。 **[OK]** をクリックします。  
  
        < BizTalk_project_name > をインポートするには、この手順を繰り返します。Procedure_dbo すぎます。  
  
   5.  **インポート**ダイアログ ボックスで、をクリックして**OK**。  
  
3. ルート スキーマ ノードには、2 つの子ノードを追加します。 1 つの子ノードは、複合操作を実行するための要求スキーマに対応します。 その他の子ノードは、応答スキーマに対応します。 要求スキーマに対応するノードは、任意の名前を持つことができます。 応答スキーマに対応するノードには、< request_schema_node > 応答を呼び出す必要があります。 この例では、要求スキーマのノードとしてを呼び出し、**要求**します。 そのため、応答スキーマのノードと呼びます**RequestResponse**します。  
  
   > [!NOTE]
   >  既定で、**ルート**ノードは、新しいスキーマ ファイルにも追加されます。 名前を変更することができます、**ルート**ノード**要求**します。 ノードの名前を変更するノード名を右クリックし、をクリックして**の名前を変更**します。  
  
    下のノードを追加する、 **\<スキーマ\>** ノード。  
  
   1.  右クリックし、 **\<スキーマ\>** に**スキーマ ノードの挿入**、 をクリック**子レコード**します。  
  
   2.  新しいノードの名前を変更**RequestResponse**します。  
  
4. 下の子ノードを追加、**要求**複合操作の一部として実行する各操作の要求スキーマに対応するノード。 この例では、次に対応する子ノードを追加する必要があります。  
  
   -   挿入し、EMPLOYEE テーブルに対する操作を削除します。  
  
   -   GET_LAST_EMP_DATA はストアド プロシージャです。  
  
   > [!IMPORTANT]
   >  操作を実行するのと同じ順序でノードを追加する必要があります。 など、レコードを挿入し、ストアド プロシージャを実行し、挿入操作のノードを追加する必要があります最初のレコードを削除する場合は、後に、ストアド プロシージャのノードと最後に、削除操作のノード。  
  
    子ノードを追加する、**要求**ノード。  
  
   1.  右クリックし、**要求**に**スキーマ ノードの挿入**、 をクリックし、**子レコード**します。  
  
        ![スキーマの子ノードの挿入](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")  
  
   2.  複合操作の一環として実行する操作の要求スキーマに対応するレコードの名前を変更します。 たとえば、"Insert"するノードの名前を変更します。  
  
   3.  マップ、**挿入**EMPLOYEE テーブルに対する挿入操作の要求スキーマのノード。 これを行うを右クリックし、**挿入**ノード、およびクリック**プロパティ**。 **プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **Insert (リファレンス)** します。  
  
        ![要求スキーマに子ノードをマップ](../../adapters-and-accelerators/adapter-sql/media/5ace18be-0fe8-44c6-bd2f-cb19035494b5.gif "5ace18be-0fe8-44c6-bd2f-cb19035494b5")  
  
   4.  GET_LAST_EMP_DATA ストアド プロシージャと削除操作の要求スキーマのノードを追加するには、この手順を繰り返します。 ノード名を指定し、次の表で説明したように、それらを対応するスキーマにマップします。  
  
       |ノード名|スキーマにマップ|  
       |---------------|----------------------|  
       |GET_LAST_EMP_DATA|GET_LAST_EMP_DATA (リファレンス)|  
       |DELETE|削除 (リファレンス)|  
  
5. 下の子ノードを追加、 **RequestResponse**複合操作の一部として実行する各操作の応答スキーマに対応するノード。 この例では、次に対応する子ノードを追加する必要があります。  
  
   -   挿入し、EMPLOYEE テーブルに対する操作を削除します。  
  
   -   GET_LAST_EMP_DATA はストアド プロシージャです。  
  
   > [!IMPORTANT]
   >  下の子ノードと同じ順序で子ノードを追加する必要があります、**要求**ノード。  
  
    子ノードを追加する、 **RequestResponse**ノード。  
  
   1.  右クリックし、 **RequestResponse**に**スキーマ ノードの挿入**、 をクリック**子レコード**します。  
  
   2.  複合操作の一環として実行する操作の応答スキーマに対応するレコードの名前を変更します。 たとえば、"InsertResponse"するノードの名前を変更します。  
  
   3.  マップ、 **InsertResponse**を EMPLOYEE テーブルに対する挿入操作の応答スキーマのノード。 これを行うを右クリックし、 **InsertResponse**ノード、およびクリック**プロパティ**します。 **プロパティ**] ボックスから、 **Data Structure Type**一覧で、[ **InsertResponse (リファレンス)** します。  
  
   4.  GET_LAST_EMP_DATA ストアド プロシージャと削除操作の応答スキーマのノードを追加するには、この手順を繰り返します。 ノード名を指定し、次の表で説明したように、それらを対応するスキーマにマップします。  
  
       |ノード名|スキーマにマップ|  
       |---------------|----------------------|  
       |GET_LAST_EMP_DATAResponse|GET_LAST_EMP_DATAResponse (リファレンス)|  
       |DeleteResponse|DeleteResponse (リファレンス)|  
  
6. 保存、 **CompositeSchema.xsd**ファイル。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 最後の手順で作成した複合スキーマでは、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 オーケストレーションのメッセージを作成し、前の手順で作成したスキーマにそれらをリンクする必要がありますようになりました。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  
  
2.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *CompositeOp.CompositeSchema.Request*CompositeOp は、BizTalk プロジェクトの名前です。 CompositeSchema は複合操作用に手動で作成したスキーマを示します。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *CompositeOp.CompositeSchema.RequestResponse*します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server での複合操作を実行します。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 要求メッセージは、先ほど作成した複合スキーマに準拠する必要があります。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がこのメッセージを使用して、SQL Server に渡します。 SQL Server からの応答は、別の場所に保存されます。 送信を含めるし、受信図形を SQL Server にメッセージを送信し、それぞれ、応答を受信する必要があります。 複合操作を実行するための基本的なオーケストレーションには、次のようになります。  
  
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
 [オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、SQL Server データベースに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 複合操作の一部が単一のトランザクションで実行されるようが含まれている操作を確認するため、 **UseAmbientTransaction**に設定されているプロパティのバインド**True**します。  
  
     送信ポートでアクションを指定することも必要があります。 複合操作のアクションは、"**CompositeOperation**"。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。 ポートのアクションを指定する方法の詳細については、次を参照してください。 [SQL アダプタの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)します。
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)します。 Wcf-custom または WCF-SQL 送信ポートでアクションがで選択したすべての操作に関連する動的アクションに設定されている場合、このバインド ファイルをインポートする、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中にします。 複合操作の場合は、"CompositeOperation"で動的アクションを置き換える必要があります。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベースでの複合演算を実行する BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。 要求メッセージのスキーマは、先ほど作成した複合操作のスキーマに準拠する必要があります。 たとえば、EMPLOYEE テーブルにレコードを挿入、GET_LAST_EMP_DATA ストアド プロシージャを呼び出すし、EMPLOYEE テーブルからレコードを削除する要求メッセージには。  
  
```  
<Request xmlns="http://CompositeTest.CompositeSchema">  
  <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
        <Designation>Manager</Designation>  
        <Salary>100000</Salary>  
      </Employee>  
    </Rows>  
  </Insert>  
  <GET_LAST_EMP_DATA xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo" />  
  <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
      </Employee>  
    </Rows>  
  </Delete>  
</Request>  
```  
  
 参照してください[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)を使用して、データベースの SQL Server での複合操作を実行するための要求メッセージ スキーマの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
 オーケストレーションはメッセージを使用し、SQL Server データベースに送信します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、前の要求メッセージの SQL Server データベースからの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://CompositeTest.CompositeSchema">  
  <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <InsertResult>  
      <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10080</long>   
    </InsertResult>  
  </InsertResponse>  
  <GET_LAST_EMP_DATAResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
    <GET_LAST_EMP_DATAResult>  
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                      <xs:element minOccurs="0" name="Name" type="xs:string" />   
                      <xs:element minOccurs="0" name="DOJ" type="xs:dateTime" />   
                      <xs:element minOccurs="0" name="Designation" type="xs:string" />   
                      <xs:element minOccurs="0" name="Job_Description" type="xs:string" />   
                      <xs:element minOccurs="0" name="Photo" type="xs:base64Binary" />   
                      <xs:element minOccurs="0" name="Rating" type="xs:string" />   
                      <xs:element minOccurs="0" name="Salary" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="Last_Modified" type="xs:base64Binary" />   
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
              <Employee_ID>10080</Employee_ID>   
              <Name>John</Name>   
              <Designation>Manager</Designation>   
              <Salary>100000.00</Salary>   
              <Last_Modified>AAAAAAAAF40=</Last_Modified>   
            </NewTable>  
          </NewDataSet>  
        </diffgr:diffgram>  
      </DataSet>  
    </GET_LAST_EMP_DATAResult>  
    <ReturnValue>0</ReturnValue>   
  </GET_LAST_EMP_DATAResponse>  
  <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  
  
 前の応答には、複合操作の一部として実行されるさまざまな操作を対応する複数の結果セットが含まれています。 たとえば、`InsertResult`要素には、新しく追加されたレコードの一意の識別子、10080 が含まれています。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)します。
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)