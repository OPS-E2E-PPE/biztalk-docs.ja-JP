---
title: "MVG フィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントでの操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c5db211-76a2-4c27-97f4-382302c722da
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f2e1f867ba4f7759afa67a271bc6523b93e9a67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-business-components-with-mvg-fields-using-biztalk-server-and-the-siebel-adapter"></a>MVG フィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントでの操作を実行します。
このセクションでは、複数値フィールドを含むビジネス コンポーネント操作の実行について説明します。 このようなビジネス コンポーネントでエンド ツー エンド操作を示すためを実行する必要があります。  
  
-   親ビジネス コンポーネントで挿入操作  
  
-   子ビジネス コンポーネントで挿入操作  
  
-   親呼び子ビジネス コンポーネント間の複数値リンクに関連付ける操作  
  
-   親ビジネス コンポーネントのレコードに Query_ [MVG_Child_Business_Comp] 操作  
  
 方法の詳細については[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ビジネス コンポーネントの操作をサポートするを参照してください[ビジネス コンポーネント操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)です。 SOAP の構造の詳細については、これらの操作を実行するメッセージを参照してください[ビジネス コンポーネント操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)です。  
  
## <a name="how-to-perform-operations-on-a-business-component-with-multi-value-fields"></a>複数値フィールドのビジネス コンポーネントで操作を実行する方法  
 Siebel システムを使用して、操作を実行、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [Siebel アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)です。 ビジネス コンポーネント操作を実行するには、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、ビジネス コンポーネントに、呼び出し先のすべての操作のスキーマを生成します。 前述のように、複数値フィールドを持つビジネス コンポーネントの操作を実行する必要があります親呼び子ビジネス コンポーネントに対する挿入操作のスキーマを生成するには、関連付ける親と子の間の複数値リンクに対する操作ビジネス コンポーネントは、親ビジネス コンポーネントでクエリ操作。  
  
2.  Siebel システムからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  Siebel システムでさまざまな操作を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、MVLDemo、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [Siebel アダプターのサンプル](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 親ビジネス コンポーネントに関連付ける方法を示すために、このトピックで**アカウント**子ビジネス コンポーネントに**連絡先**次のスキーマを生成します。  
  
-   に対する挿入操作、**アカウント**ビジネス コンポーネントです。 参照してください[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)です。  
  
-   に対する挿入操作、**連絡先**ビジネス コンポーネントです。  
  
-   関連付けの操作、**アカウント**ビジネス コンポーネントです。  
  
-   QUERY_CONTACT 操作、**アカウント**ビジネス コンポーネントです。  
  
 参照してください[Siebel 操作の Visual Studio でのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類からのメッセージに最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、要求および応答メッセージの Siebel システムに対して呼び出すは操作ごとに 1 つの 4 つのセットを作成する必要があります。 各セットは、要求メッセージと応答メッセージが必要です。 例としては、次の手順は、関連付け操作の要求と応答メッセージを作成する手順を説明します。 その他の操作用のメッセージを作成する同様の手順を実行する必要があります。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
### <a name="create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマへのリンク  
  
1.  オーケストレーションの種類、BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、 をクリック**オーケストレーション**です。  
  
2.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
3.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**AccountAssociate_Request**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*MVLDemo.SiebelBindingSchema.Associate*ここで、 *MVLDemo* BizTalk プロジェクトの名前を指定します。 *SiebelBindingSchema* 、呼び出し元に対して生成されるスキーマは、*関連付ける*で操作*アカウント*ビジネス コンポーネント。|  
  
5.  新しいメッセージを作成する前の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**AccountAssociate_Response**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*MVLDemo.SiebelBindingSchema.AssociateResponse*です。|  
  
## <a name="set-up-the-orchestrations"></a>オーケストレーションをセットアップします。  
 これで、使用するオーケストレーションを設定する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アカウント、連絡先のビジネス コンポーネントの操作を実行します。  
  
-   挿入操作を実行するオーケストレーションをセットアップ、**アカウント**ビジネス コンポーネントです。 参照してください[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)です。  
  
-   挿入操作を実行するオーケストレーションをセットアップ、**連絡先**ビジネス コンポーネントです。 これはに対する挿入操作と同様、**アカウント**ビジネス コンポーネントです。  
  
-   関連付ける操作を実行するオーケストレーションをセットアップ、**アカウント**ビジネス コンポーネントです。  
  
-   QUERY_CONTACT 操作を実行するオーケストレーションをセットアップ、**アカウント**ビジネス コンポーネントです。  
  
 このトピックに関連付ける操作のオーケストレーションを設定する方法を実演、**アカウント**ビジネス コンポーネントです。 残りのオーケストレーションもを設定する同様のタスクを実行する必要があります。  
  
 ビジネス コンポーネントをアカウントに関連付ける操作のオーケストレーションは、ようになります。  
  
 ![Siebel の MVL 操作のためのオーケストレーション](../../adapters-and-accelerators/adapter-siebel/media/6c7d548d-dc80-490f-89fe-12aff10fa3cf.gif "6c7d548d-dc80-490f-89fe-12aff10fa3cf")  
  
 次のセクションでは、メッセージの構築図形、ポート、スキーマなどへのリンクのメッセージを削除することにより、このオーケストレーションをセットアップする方法について説明します。他のオーケストレーションもを設定する同様のタスクを実行する必要があります。  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|AccountAssociateXML|Receive|-設定**名前**に*AccountAssociateXML*<br />-設定**アクティブ**に*は True。*|  
|SendToLOB|Send|-設定**名前**に*SendToLOB*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 示されている名前、*ポート*オーケストレーションで表示される、列が、ポートの名前を示します。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|FileIn_AccountAssociate|-設定**識別子**に*FileIn_AccountAssociate*<br />-設定**型**に*FileInAccountAssociateType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort_AccountAssociate|-設定**識別子**に*LOBPort_AccountAssociate*<br />-設定**型**に*LOBPortAccountAssociateType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse_AccountAssociate|-設定**識別子**に*SaveResponse_AccountAssociate*<br />-設定**型**に*SaveResponseAccountAssociateType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティと、メッセージのアクション図形およびポートにリンクすることを指定するために設定するには、その値を指定します。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|AccountAssociateXML|-設定**メッセージ**に*AccountAssociate_Request*<br />-設定**操作**に*FileIn_AccountAssociate.Associate.Request*|  
|SendToLOB|-設定**メッセージ**に*AccountAssociate_Request*<br />-設定**操作**に*LOBPort_AccountAssociate.Associate.Request*|  
|ReceiveResponse|-設定**メッセージ**に*AccountAssociate_Response*<br />-設定**操作**に*LOBPort_AccountAssociate.Associate.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse_AccountAssociate.Associate.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[オーケストレーションのビルド方法](../../core/how-to-build-orchestrations.md)と[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションの構成の詳細については、次を参照してください。[アプリケーションを作成する方法](../../core/how-to-create-an-application.md)です。  
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、Siebel システムに送信します。 次の 4 つすべてのオーケストレーションの同じポートことができます。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Siebel システムからの応答を含む応答メッセージをドロップする場所に場所を定義します。 次の 4 つすべてのオーケストレーションの同じポートことができます。  
  
    -   Siebel システムへのメッセージを送信する物理 Wcf-custom または WCF Siebel 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください。 [Siebel アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)です。 次の 4 つすべてのオーケストレーションに異なるポートが必要です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートするには、BizTalk 管理コンソールから (発信) の送信ポートを作成します。 詳細については、次を参照してください。 [Siebel するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)です。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Child business component する親ビジネス コンポーネントを関連付けるための BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。 [BizTalk アプリケーションを起動](../../core/how-to-start-and-stop-a-biztalk-application.md)または[オーケストレーションを開始](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   次の 4 つ Wcf-custom または Wcf-siebel 送信ポート、1 つずつ、Siebel システムへのメッセージ送信を実行しています。  
  
-   さまざまな操作の 4 つの BizTalk オーケストレーションを実行しています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 要求を削除する必要がありますファイルへのメッセージの受信ポート。 要求メッセージのスキーマは、このトピックで生成されるスキーマに従う必要があります。 参照してください[ビジネス コンポーネント操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)さまざまな操作の要求メッセージのスキーマの詳細についてはします。 次の順序で、要求メッセージを削除する必要があります。  
  
-   レコードを挿入する要求メッセージをドロップ、**アカウント**ビジネス コンポーネントです。 要求メッセージは、トピックの「アカウント ビジネス コンポーネントのレコードを挿入するために削除するようになります[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプター操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)です。 オーケストレーションはメッセージを使用して、Siebel システムに送信します。 Siebel システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  
  
-   レコードを挿入する要求メッセージをドロップ、**連絡先**ビジネス コンポーネントです。 要求メッセージは、トピックの「アカウント ビジネス コンポーネントのレコードを挿入するために削除するようになります[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプター操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)です。 オーケストレーションはメッセージを使用して、Siebel システムに送信します。 Siebel システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  
  
-   関連付ける操作を実行する要求メッセージをドロップ、**アカウント**ビジネス コンポーネントです。 これにより、検索式と、入力 XML で指定した複数値フィールドの名前に基づく親呼び子ビジネス コンポーネントが関連付けられます。 次の点に注意してください。  
  
    -   関連付け操作で親検索式は、親テーブルに一意なレコードと一致する必要があります。  
  
    -   関連付け操作で子検索式は、子テーブルに一意なレコードと一致する必要があります。  
  
     たとえば、ビジネス コンポーネントをアカウントに関連付ける操作を実行する要求メッセージには。  
  
    ```  
    <Associate xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
      <ViewMode>3</ViewMode>  
      <ParentSearchExpr>[Name] LIKE "SampleName1"</ns0:ParentSearchExpr>   
      <ParentMVGField>Bill To First Name</ns0:ParentMVGField>   
      <ChildSearchExpr>[First Name] LIKE "SampleName2"</ns0:ChildSearchExpr>   
    </Associate>  
    ```  
  
     オーケストレーションはメッセージを使用して、Siebel システムに送信します。 Siebel システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージの応答には。  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <AssociateResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
      <AssociateResult>  
        <ChildID xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">1-8AO09</ChildID>  
        <ParentID xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">1-8ANZ5</ParentID>  
      </AssociateResult>  
    </AssociateResponse>  
    ```  
  
-   QUERY_CONTACT 操作を実行する要求メッセージをドロップ、**アカウント**ビジネス コンポーネントです。 たとえば、QUERY_CONTACT 操作の要求メッセージには。  
  
    ```  
    <Query_Contact xmlns ="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
      <ViewMode>3</ViewMode>   
      <ParentSearchExpr>[Name] LIKE "SampleName1"</ParentSearchExpr>   
      <ParentMVGField>Bill To First Name</ParentMVGField>   
      <ContactQueryInputRecord>  
        <SearchExpr xmlns:ns1="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">[Id] LIKE '*'</SearchExpr>   
      </ContactQueryInputRecord>  
    </Query_Contact>  
    ```  
  
     オーケストレーションはメッセージを使用して、Siebel システムに送信します。 Siebel システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  
  
 参照してください[ビジネス コンポーネント操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)要求メッセージのスキーマの詳細についてはします。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外に関する情報を使用して複数値フィールドのビジネス コンポーネントでの操作を実行中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラー処理](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)です。  
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)