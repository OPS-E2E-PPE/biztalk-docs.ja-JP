---
title: ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターに対する操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business components, performing operations by using BizTalk Server
- how to, perform operations on a business component by using BizTalk Server
ms.assetid: 5bd0f4d7-60ec-42ea-84c0-618aeef9688f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49236c834477111ec8b940b4b44585731994fcd3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989299"
---
# <a name="run-operations-on-business-components-using-biztalk-server-and-the-siebel-adapter"></a>ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターに対する操作を実行します。
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェスのビジネス コンポーネント操作を呼び出すことができます。 ビジネス コンポーネントに対する操作として分類できます。  
  
- 標準的なビジネス コンポーネント操作。 これらは、挿入、クエリ、更新プログラムを含めるし、削除します。 このトピックを使用してこれらの操作を実行する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
- 複数値を持つグループのフィールドを含むビジネス コンポーネントに対する操作。 これらは、標準的な操作として関連付ける関連付け解除、Query_ [MVG_Child_Bussiness_Comp] などがあります。 これらの操作を実行する方法については、次を参照してください[MVG フィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントに対する操作を実行。](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)  
  
- 候補リストのフィールドを格納しているビジネス コンポーネントに対する操作。 これらの操作を実行する方法については、[候補リストのフィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントに対する操作を実行](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md)を参照してください。  
  
  方法の詳細については[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ビジネス コンポーネントに対するサポートの操作を参照してください[で Siebel ビジネス コンポーネントに対する操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)します。 SOAP の構造の詳細については、これらの操作を実行するメッセージを参照してください[ビジネス コンポーネント操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)します。  
  
## <a name="how-to-perform-operations-on-a-business-component"></a>ビジネス コンポーネントに対する操作を実行する方法  
 Siebel システムを使用して、操作を実行する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)します。 
 
 ビジネス コンポーネント操作を完了するには、これらのタスクは。  
  
1. BizTalk プロジェクトを作成し、呼び出すビジネス コンポーネント操作用のスキーマを生成します。  
  
2. Siebel システムからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. Siebel システムで、操作を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル SiebelAccount、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、[の Siebel アダプターのサンプル](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)を参照してください。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックで、ビジネス コンポーネントに対する操作を呼び出す方法を示すためにスキーマに対して生成されますアカウント business component の挿入操作。 参照してください[Visual Studio で Siebel 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)スキーマを生成する方法の詳細について。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションからメッセージを最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: Siebel システムと他の応答を受信する要求を送信する 1 つ。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順に従います。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションの種類を BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他の Windows**、 をクリック**オーケストレーション**します。  
  
2.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
3.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*SiebelAccount.SiebelBindingSchema.Insert*ここで、 *SiebelAccount* BizTalk プロジェクトの名前を指定します。 *SiebelBindingSchema*を呼び出すために生成されたスキーマには、*挿入*操作*アカウント*ビジネス コンポーネント。|  
  
5.  新しいメッセージを作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択および*SiebelAccount.SiebelBindingSchema.InsertResponse*します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Siebel ビジネス コンポーネント操作を実行します。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]がこのメッセージを使用し、Siebel システムに渡します。 Siebel システムからの応答は、別の場所に保存されます。 Siebel ビジネス コンポーネントに対する操作を実行するための一般的なオーケストレーションが含まれます。  
  
- Siebel にメッセージを送信し、応答を受信する図形を送受信します。  
  
- Siebel に送信する要求メッセージを受信するポートは一方向の受信します。  
  
- Siebel に要求メッセージを送信し、応答を受信するポートを双方向に送信します。  
  
- Siebel からフォルダーに、応答を送信する一方向の送信ポート。  
  
  サンプル オーケストレーションを*挿入*で操作、*アカウント*次のようにビジネス コンポーネント。  
  
  ![Siebel BC にデータを挿入するオーケストレーション](../../adapters-and-accelerators/adapter-siebel/media/f005df04-dfbf-4c75-8f9b-2bc3a357d52b.gif "f005df04-dfbf-4c75-8f9b-2bc3a357d52b")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 表示される名前、*図形*列は、メッセージの構築図形の名前、オーケストレーションの上に表示されます。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveXML|Receive|-設定**名前**に*ReceiveXML*<br />-設定**アクティブ**に*は True。*|  
|SendToLOB|Send|-設定**名前**に*SendToLOB*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 表示される名前、*ポート*列は、ポートの名前、オーケストレーションに表示されます。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br />-設定**型**に*SaveResponseType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表には、プロパティとメッセージのアクション図形とポートにリンクすることを指定するために設定するには、その値を指定します。 表示される名前、*図形*列は、メッセージの構築図形の名前、オーケストレーションの上に表示されます。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveXML|-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.Insert.Request*|  
|SendToLOB|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Insert.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Insert.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.Insert.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、[オーケストレーションのビルド方法](../../core/how-to-build-orchestrations.md)と[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)を参照してください。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 [アプリケーションを作成する方法](../../core/how-to-create-an-application.md)の手順を示します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、Siebel システムに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションで Siebel システムからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - Siebel システムにメッセージを送信する物理 Wcf-custom または WCF Siebel 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、[Siebel アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)を参照してください。
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成する BizTalk 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、[Siebel にポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)を参照してください。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 実行するための BizTalk アプリケーションを起動する必要があります、*挿入*操作、*アカウント*で Siebel ビジネス コンポーネント。 BizTalk アプリケーションを開始する手順については、[BizTalk アプリケーションを起動](../../core/how-to-start-and-stop-a-biztalk-application.md)または[オーケストレーションを開始する](../../core/how-to-start-an-orchestration.md)を参照してください。
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Siebel システムへのメッセージを送信する Wcf-custom または WCF Siebel 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、ファイルに要求メッセージを削除する必要がありますの受信場所。 要求メッセージのスキーマに従う必要があります (ビジネス コンポーネントのアカウント) に対する挿入操作のスキーマに先に生成します。 たとえば、アカウントのビジネス コンポーネントにレコードを挿入する要求メッセージには。  
  
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
    </AccountInsertRecord>  
  </ArrayOfAccountInsertRecord>  
</Insert>  
```  
  
 参照してください[ビジネス コンポーネント操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)要求メッセージのスキーマの詳細についてはします。  
  
 オーケストレーションでは、要求メッセージを使用し、Siebel システムに渡します。 Siebel システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージの Siebel システムからの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<InsertResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
  <InsertResult>  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">1-8ANYV</string>  
  </InsertResult>  
</InsertResponse>  
```  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 については、例外を使用してビジネス コンポーネントに対する操作の実行中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラーの Siebel アダプターを使用した処理](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)します。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、[Siebel アダプターのアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)を参照してください。
  
## <a name="see-also"></a>参照  
[Siebel アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)