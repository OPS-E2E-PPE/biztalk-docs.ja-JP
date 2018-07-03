---
title: MVG フィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントに対する操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c5db211-76a2-4c27-97f4-382302c722da
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35ec36bd9dd0949289a8799be8844721cd5bb8ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979995"
---
# <a name="run-operations-on-business-components-with-mvg-fields-using-biztalk-server-and-the-siebel-adapter"></a>MVG フィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントに対する操作を実行します。
このセクションでは、複数値フィールドを含むビジネス コンポーネント操作の実行について説明します。 このようなビジネス コンポーネントでエンド ツー エンドの操作を示すためを実行する必要があります。  
  
- 親ビジネス コンポーネントに対して、挿入操作  
  
- 子ビジネス コンポーネントに対して、挿入操作  
  
- 親呼び子ビジネス コンポーネント間の複数値リンクの関連付け操作  
  
- 親ビジネス コンポーネントのレコードに対して Query_ [MVG_Child_Business_Comp] 操作  
  
  方法の詳細については[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ビジネス コンポーネントに対するサポートの操作を参照してください[ビジネス コンポーネントに対する操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)します。 SOAP の構造の詳細については、これらの操作を実行するメッセージを参照してください[ビジネス コンポーネント操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)します。  
  
## <a name="how-to-perform-operations-on-a-business-component-with-multi-value-fields"></a>複数値フィールドを持つビジネス コンポーネントに対する操作を実行する方法でしょうか。  
 Siebel システムを使用して、操作を実行する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Siebel アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)します。 ビジネス コンポーネント操作を実行するには、これらのタスクは。  
  
1. BizTalk プロジェクトを作成し、ビジネス コンポーネントを呼び出すすべての操作のスキーマを生成します。 前述のように、複数値フィールドを持つビジネス コンポーネント操作を実行するには親呼び子ビジネス コンポーネントに対する挿入操作のスキーマを生成、親と子間の複数値リンクの操作を関連付けるビジネス コンポーネントは、親ビジネス コンポーネントでのクエリ操作。  
  
2. Siebel システムからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. Siebel システムでさまざまな操作を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル MVLDemo、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。[の Siebel アダプターのサンプル](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 親ビジネス コンポーネントに関連付ける方法を示すために、このトピックで**アカウント**子ビジネス コンポーネントに**連絡先**次のスキーマを生成します。  
  
- に対する挿入操作、**アカウント**ビジネス コンポーネント。 参照してください[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)します。  
  
- に対する挿入操作、**連絡先**ビジネス コンポーネント。  
  
- 関連付ける操作、**アカウント**ビジネス コンポーネント。  
  
- QUERY_CONTACT 操作、**アカウント**ビジネス コンポーネント。  
  
  参照してください[Visual Studio で Siebel 操作のメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)スキーマを生成する方法の詳細について。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションからメッセージを最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、要求と応答メッセージの Siebel システムで呼び出すことが各操作の 1 つの 4 つのセットを作成する必要があります。 各セットは、要求メッセージと応答メッセージが必要です。 例としては、次の手順は、関連付け操作の要求と応答メッセージを作成する手順を示します。 その他の操作のメッセージを作成するのと同様の手順を実行する必要があります。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順に従います。  
  
### <a name="create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマへのリンク  
  
1.  オーケストレーションの種類を BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他の Windows**、 をクリック**オーケストレーション**します。  
  
2.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
3.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**AccountAssociate_Request**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*MVLDemo.SiebelBindingSchema.Associate*ここで、 *MVLDemo* BizTalk プロジェクトの名前を指定します。 *SiebelBindingSchema*は呼び出し元の生成スキーマ、*関連付ける*操作*アカウント*ビジネス コンポーネント。|  
  
5.  新しいメッセージを作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**AccountAssociate_Response**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択および*MVLDemo.SiebelBindingSchema.AssociateResponse*します。|  
  
## <a name="set-up-the-orchestrations"></a>オーケストレーションをセットアップします。  
 これで、使用するオーケストレーションを設定する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アカウントおよび連絡先のビジネス コンポーネントに対する操作を実行するためです。  
  
- 挿入操作を実行するオーケストレーションを設定、**アカウント**ビジネス コンポーネント。 参照してください[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)します。  
  
- 挿入操作を実行するオーケストレーションを設定、**連絡先**ビジネス コンポーネント。 これは、挿入操作に似ています、**アカウント**ビジネス コンポーネント。  
  
- 関連付ける操作を実行するオーケストレーションを設定、**アカウント**ビジネス コンポーネント。  
  
- QUERY_CONTACT 操作を実行するオーケストレーションを設定、**アカウント**ビジネス コンポーネント。  
  
  このトピックに関連付ける操作のオーケストレーションをセットアップする方法を示しますが、**アカウント**ビジネス コンポーネント。 残りのオーケストレーションも設定するのと同様のタスクを実行する必要があります。  
  
  オーケストレーションに関連付けるアカウントのビジネス コンポーネント操作のようになります。  
  
  ![Siebel の mvl オーケストレーション](../../adapters-and-accelerators/adapter-siebel/media/6c7d548d-dc80-490f-89fe-12aff10fa3cf.gif "6c7d548d-dc80-490f-89fe-12aff10fa3cf")  
  
  次のセクションでは、メッセージの構築図形、ポートなど、スキーマのリンクのメッセージを削除することにより、このオーケストレーションを設定する方法について説明します。他のオーケストレーションも設定するのと同様のタスクを実行する必要があります。  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 表示される名前、*図形*列は、メッセージの構築図形の名前、オーケストレーションの上に表示されます。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|AccountAssociateXML|Receive|-設定**名前**に*AccountAssociateXML*<br />-設定**アクティブ**に*は True。*|  
|SendToLOB|Send|-設定**名前**に*SendToLOB*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 表示される名前、*ポート*列は、ポートの名前、オーケストレーションに表示されます。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|FileIn_AccountAssociate|-設定**識別子**に*FileIn_AccountAssociate*<br />-設定**型**に*FileInAccountAssociateType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort_AccountAssociate|-設定**識別子**に*LOBPort_AccountAssociate*<br />-設定**型**に*LOBPortAccountAssociateType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse_AccountAssociate|-設定**識別子**に*SaveResponse_AccountAssociate*<br />-設定**型**に*SaveResponseAccountAssociateType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表には、プロパティとメッセージのアクション図形とポートにリンクすることを指定するために設定するには、その値を指定します。 表示される名前、*図形*列は、メッセージの構築図形の名前、オーケストレーションの上に表示されます。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|AccountAssociateXML|-設定**メッセージ**に*AccountAssociate_Request*<br />-設定**操作**に*FileIn_AccountAssociate.Associate.Request*|  
|SendToLOB|-設定**メッセージ**に*AccountAssociate_Request*<br />-設定**操作**に*LOBPort_AccountAssociate.Associate.Request*|  
|ReceiveResponse|-設定**メッセージ**に*AccountAssociate_Response*<br />-設定**操作**に*LOBPort_AccountAssociate.Associate.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse_AccountAssociate.Associate.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[オーケストレーションのビルド方法](../../core/how-to-build-orchestrations.md)と[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションを構成する方法の詳細については、次を参照してください。[アプリケーションを作成する方法](../../core/how-to-create-an-application.md)します。  
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、Siebel システムに送信します。 4 つすべてのオーケストレーションの同じポートがあることができます。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションで Siebel システムからの応答を含む応答メッセージをドロップする場所の場所を定義します。 4 つすべてのオーケストレーションの同じポートがあることができます。  
  
  - Siebel システムへのメッセージを送信する物理 Wcf-custom または WCF Siebel 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、次を参照してください。 [Siebel アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)します。 次の 4 つすべてのオーケストレーションに異なるポートが必要です。  
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成する BizTalk 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、次を参照してください。 [Siebel にポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)します。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Child business component する親ビジネス コンポーネントを関連付けるための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。 [BizTalk アプリケーションを起動](../../core/how-to-start-and-stop-a-biztalk-application.md)または[オーケストレーションを開始する](../../core/how-to-start-an-orchestration.md)します。  
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   4 つ Wcf-custom または WCF Siebel 送信ポートに 1 つずつ、Siebel システムにメッセージを送信するために実行しています。  
  
-   さまざまな操作の 4 つの BizTalk オーケストレーションを実行しています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 要求を削除する必要がありますファイルへのメッセージの受信ポート。 要求メッセージのスキーマは、トピックの前半で生成したスキーマに準拠する必要があります。 参照してください[ビジネス コンポーネント操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)さまざまな操作の要求メッセージのスキーマの詳細についてはします。 次の順序で要求メッセージを削除する必要があります。  
  
- レコードを挿入する要求メッセージをドロップ、**アカウント**ビジネス コンポーネント。 要求メッセージは、トピックの「アカウントのビジネス コンポーネントでレコードを挿入するために削除されたようになります[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)します。 オーケストレーションはメッセージを使用し、Siebel システムに送信します。 Siebel システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  
  
- レコードを挿入する要求メッセージをドロップ、**連絡先**ビジネス コンポーネント。 要求メッセージは、トピックの「アカウントのビジネス コンポーネントでレコードを挿入するために削除されたようになります[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターの操作を実行](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)します。 オーケストレーションはメッセージを使用し、Siebel システムに送信します。 Siebel システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  
  
- 関連付ける操作を実行する要求メッセージをドロップ、**アカウント**ビジネス コンポーネント。 これは、検索式と、入力 XML で指定した複数値フィールドの名前に基づく親呼び子ビジネス コンポーネントに関連付けます。 次の点に注意してください。  
  
  - 関連付け操作で親検索式は、親テーブルの一意なレコードと一致する必要があります。  
  
  - 関連付け操作で子検索式は、子テーブルの一意なレコードと一致する必要があります。  
  
    たとえば、アカウントのビジネス コンポーネントに関連付ける操作を実行する要求メッセージには。  
  
  ```  
  <Associate xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
    <ViewMode>3</ViewMode>  
    <ParentSearchExpr>[Name] LIKE "SampleName1"</ns0:ParentSearchExpr>   
    <ParentMVGField>Bill To First Name</ns0:ParentMVGField>   
    <ChildSearchExpr>[First Name] LIKE "SampleName2"</ns0:ChildSearchExpr>   
  </Associate>  
  ```  
  
   オーケストレーションはメッセージを使用し、Siebel システムに送信します。 Siebel システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージの応答には。  
  
  ```  
  <?xml version="1.0" encoding="utf-8"?>  
  <AssociateResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
    <AssociateResult>  
      <ChildID xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">1-8AO09</ChildID>  
      <ParentID xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">1-8ANZ5</ParentID>  
    </AssociateResult>  
  </AssociateResponse>  
  ```  
  
- QUERY_CONTACT 操作を実行する要求メッセージをドロップ、**アカウント**ビジネス コンポーネント。 たとえば、QUERY_CONTACT 操作の要求メッセージは次のとおりです。  
  
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
  
   オーケストレーションはメッセージを使用し、Siebel システムに送信します。 Siebel システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。  
  
  参照してください[ビジネス コンポーネント操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)要求メッセージのスキーマの詳細についてはします。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 については、例外を使用して複数値フィールドを持つビジネス コンポーネントに対する操作の実行中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラー処理](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)します。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)します。  
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)