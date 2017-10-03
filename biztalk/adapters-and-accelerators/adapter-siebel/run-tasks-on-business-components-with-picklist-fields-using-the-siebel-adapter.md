---
title: "候補リストのフィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントでの操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, perform operations with picklist fields by using BizTalk Server
- business components, performing operations with picklist fields by using BizTalk Server
ms.assetid: b62d32fa-903a-442b-951b-2343ef719bd0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 823c2959f10bbd836bd0154b2e59f07fffcc6a96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-business-components-with-picklist-fields-using-biztalk-server-and-the-siebel-adapter"></a>候補リストのフィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントに対する操作を実行します。
Siebel のピックリスト フィールドの型が使用可能な値のコレクションを構成するクライアントから Siebel システムに渡される特定の値を指定可能性があります。 つまり、候補リストのフィールドには、フィールドの許容される値の一覧が含まれています。 候補リストとその種類の詳細については、Siebel のドキュメントを参照してください。 方法の詳細については[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]候補リストのフィールドを持つビジネス コンポーネントの操作をサポートするを参照してください[で Siebel ビジネス コンポーネント操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)です。  
  
 静的範囲指定された候補リストのフィールド (候補リストの種類) を含んでいるビジネス コンポーネントのメタデータを生成するときに候補リストに指定できる値は、メタデータの一部としても公開します。 候補リストのフィールドに値を挿入する場合は、メタデータでパブリッシュされている値を指定する必要があります。  
  
## <a name="how-to-perform-operations-on-business-components-with-picklist-fields"></a>候補リストのフィールドのビジネス コンポーネントで操作を実行する方法  
 Siebel システムを使用して、操作を実行、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [Siebel アダプターと BizTalk アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)です。 
 
 候補リストのフィールドを持つビジネス コンポーネントで操作を完了するには、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、候補リストのフィールドを含むビジネス コンポーネント操作を実行するためにスキーマを生成します。  
  
2.  Siebel システムからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  Siebel システムで、操作を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、SiebelPicklist、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [Siebel アダプターのサンプル](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは候補リストのフィールドを持つビジネス コンポーネントに対する操作を呼び出す方法を示すことを生成用のスキーマ、**挿入**の操作、**アカウント**ビジネス コンポーネントです。 **アカウント**ビジネス コンポーネントが静的の候補リスト*調査型*です。  
  
 参照してください[Siebel 操作の Visual Studio でのメタデータを取得する](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  
  
 挿入操作のメタデータを生成すると、**アカウント**ビジネス コンポーネント、候補リストのフィールドと可能な値を含む個別の .xsd ファイルを取得します。 注、.xsd には、静的な候補リストを含む値のみが含まれている*調査型*です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類からのメッセージに最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: Siebel システムと他の応答を受信する要求を送信する 1 つです。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションの種類、BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、 をクリック**オーケストレーション**です。  
  
2.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
3.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*SiebelPicklist.SiebelBindingSchema.Insert*ここで、 *SiebelPicklist* BizTalk プロジェクトの名前を指定します。 *SiebelBindingSchema*を呼び出すために生成されたスキーマは、*挿入*で操作*アカウント*ビジネス コンポーネントです。|  
  
5.  新しいメッセージを作成する前の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*SiebelPicklist.SiebelBindingSchema.InsertResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]候補リストのフィールドを持つ Siebel ビジネス コンポーネントで挿入操作を実行するためです。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]このメッセージを消費し、Siebel システムに渡します。 Siebel システムからの応答は、別の場所に保存されます。 Siebel ビジネス コンポーネント操作を実行するための一般的なオーケストレーションにが含まれます。  
  
-   Siebel にメッセージを送信し、応答を受信する図形を送受信します。  
  
-   一方向の受信ポートを Siebel に送信する要求メッセージを受信します。  
  
-   Siebel に要求メッセージを送信し、応答を受信するポートを双方向に送信します。  
  
-   Siebel からフォルダーに、応答を送信する一方向の送信ポートです。  
  
 サンプルのオーケストレーションを*挿入*で操作、*アカウント*ビジネス コンポーネント、次のようになります。  
  
 ![Siebel のピックリスト値を挿入するオーケストレーション](../../adapters-and-accelerators/adapter-siebel/media/c981fbf9-9a1f-40a5-9ccb-5e146589f2d3.gif "c981fbf9-9a1f-40a5-9ccb-5e146589f2d3")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveXML|Receive|-設定**名前**に*ReceiveXML*<br />-設定**アクティブ**に*は True。*|  
|SendToLOB|Send|-設定**名前**に*SendToLOB*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 示されている名前、*ポート*オーケストレーションで表示される、列が、ポートの名前を示します。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br />-設定**型**に*SaveResponseType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティと、メッセージのアクション図形およびポートにリンクすることを指定するために設定するには、その値を指定します。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveXml|-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.Picklist.Request*|  
|SendToLOB|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Picklist.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Picklist.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.Picklist.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[オーケストレーションのビルド方法](../../core/how-to-build-orchestrations.md)と[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。 
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションの構成の詳細については、次を参照してください。[アプリケーションを作成する方法](../../core/how-to-create-an-application.md)です。  
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、Siebel システムに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Siebel システムからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   メッセージを送信する Siebel システムへの物理 Wcf-custom または WCF Siebel 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください。 [Siebel アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)です。
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートするには、BizTalk 管理コンソールから (発信) の送信ポートを作成します。 詳細については、次を参照してください。 [siebel するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)です。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 実行するための BizTalk アプリケーションを開始する必要があります、*挿入*での操作、*アカウント*Siebel ビジネス コンポーネントです。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。 [BizTalk アプリケーションを起動](../../core/how-to-start-and-stop-a-biztalk-application.md)または[オーケストレーションを開始](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Siebel システムへのメッセージを送信する Wcf-custom または WCF Siebel 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションを実行します。  
  
## <a name="executing-the-operation"></a>操作の実行  
 ファイルに要求メッセージを削除する必要がありますの受信場所。 要求メッセージのスキーマは、このトピックの前半で生成したスキーマに準拠する必要があります。 参照してください[ビジネス コンポーネント操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)要求メッセージのスキーマの詳細についてはします。  
  
 候補リストのフィールドに値を挿入するには、候補リストの使用可能な値の一覧を確認するのに生成されたスキーマを確認します。 要求メッセージに候補リストのフィールドに値を挿入する要素を確認します。 たとえば、要求メッセージが値を挿入する次の要素を含める必要があります、*調査型*候補リスト。  
  
 `<Survey_x0020_Type>1</Survey_x0020_Type>`  
  
 ここでは、「1」は、アンケートの種類の選択リストに許容される値です。  
  
 候補リスト パラメーターを含む要求メッセージの例は次のとおりです。  
  
```  
<Insert xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
  <ArrayOfAccountInsertRecord>  
    <AccountInsertRecord xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">  
      <Currency_x0020_Code>usd</Currency_x0020_Code>  
      <Current_x0020_Volume>9</Current_x0020_Volume>  
      <Customer_x0020_Account_x0020_Group>Sold-To Party</Customer_x0020_Account_x0020_Group>  
      <Location>Location_1</Location>  
      <Main_x0020_Phone_x0020_Number>4256543212</Main_x0020_Phone_x0020_Number>  
      <Name>Name_Surname</Name>  
      <Party_x0020_Name>test_party</Party_x0020_Name>  
      <Primary_x0020_Address_x0020_Id>1212 street</Primary_x0020_Address_x0020_Id>  
      <Survey_x0020_Type>1</Survey_x0020_Type>  
    </AccountInsertRecord>  
  </ArrayOfAccountInsertRecord>  
</Insert>  
```  
  
 オーケストレーションは、要求メッセージを消費し、Siebel システムに渡されます。 Siebel システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  
  
> [!NOTE]
>  候補リストの insert ステートメントに無効な値を実行することもできます。 その場合は、取得する必要があります、`TargetSystemException`です。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外に関する情報の候補リストのフィールドを使用してビジネス コンポーネントでの操作を実行中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラーの Siebel アダプターと処理](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Siebel アダプターのアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)です。
  
## <a name="see-also"></a>参照  
[Siebel アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)