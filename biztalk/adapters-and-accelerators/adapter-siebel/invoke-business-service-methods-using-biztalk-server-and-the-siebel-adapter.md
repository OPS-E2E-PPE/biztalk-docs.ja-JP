---
title: ビジネス サービス メソッドを使用して BizTalk Server と Siebel アダプターを呼び出す |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke business service methods
- business service methods, invoking
ms.assetid: cf437c4f-fa65-4f89-a197-c83869930b2c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79a11d3be19ca27bd27146ef728ce168c3285884
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966160"
---
# <a name="invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter"></a>ビジネス サービス メソッドを使用して BizTalk Server と Siebel アダプターを呼び出し
Siebel ビジネス サービスは、Siebel の直接呼び出すことができるビジネス メソッドのコレクションです。 方法の詳細については[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]Siebel システムでのビジネス サービスを呼び出すサポートを参照してください[の Siebel ビジネス サービスを運用](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md)です。 SOAP の構造の詳細については、ビジネス サービス操作を実行するメッセージを参照してください[ビジネス サービス操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)です。  
  
## <a name="how-to-invoke-business-services"></a>ビジネス サービスを呼び出す方法ですか。  
 Siebel システムを使用して、操作を実行、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [Siebel アダプターと BizTalk アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)です。 ビジネス サービスを呼び出すには、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、呼び出し先のビジネス サービス メソッドのスキーマを生成します。  
  
2.  Siebel システムからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  Siebel システムで、ビジネス サービス メソッドを呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、BusinessService、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [Siebel アダプターのサンプル](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、ビジネス サービス メソッドを呼び出す方法を示すためを生成用のスキーマ、 **Execute**によって公開されるメソッド、**タイムスタンプ**ビジネス サービス。 参照してください[Siebel 操作の Visual Studio でのメタデータを取得する](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  
  
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
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*BusinessService.SiebelBindingSchema.Execute*ここで、 *BusinessService* BizTalk プロジェクトの名前を指定します。 *SiebelBindingSchema*を呼び出すために生成されたスキーマは、 *Execute*ビジネス サービスのメソッドです。|  
  
5.  新しいメッセージを作成する前の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*BusinessService.SiebelBindingSchema.ExecuteResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ビジネス サービスを呼び出すためです。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]このメッセージを消費し、Siebel システムに渡します。 Siebel システムからの応答は、別の場所に保存されます。 ビジネス サービス メソッドを呼び出すための一般的なオーケストレーションにが含まれます。  
  
-   Siebel にメッセージを送信し、応答を受信する図形を送受信します。  
  
-   一方向の受信ポートを Siebel に送信する要求メッセージを受信します。  
  
-   Siebel に要求メッセージを送信し、応答を受信するポートを双方向に送信します。  
  
-   Siebel からフォルダーに、応答を送信する一方向の送信ポートです。  
  
 呼び出し元のサンプル オーケストレーション、 *Execute*のメソッド、*タイムスタンプ*ビジネス サービス、次のようになります。  
  
 ![ビジネス サービスを呼び出すオーケストレーション](../../adapters-and-accelerators/adapter-siebel/media/5a776e5d-855f-4d1b-8d26-7de747b1865d.gif "5a776e5d-855f-4d1b-8d26-7de747b1865d")  
  
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
|ReceiveXML|-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.ServiceInvoke.Request*|  
|SendToLOB|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.ServiceInvoke.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.ServiceInvoke.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.ServiceInvoke.Request*|  
  
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
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートするには、BizTalk 管理コンソールから (発信) の送信ポートを作成します。 詳細については、次を参照してください。 [Siebel するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)です。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 実行するための BizTalk アプリケーションを起動する必要があります、 *Execute*メソッドを*タイムスタンプ*で Siebel ビジネス サービス。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。 [BizTalk アプリケーションを起動](../../core/how-to-start-and-stop-a-biztalk-application.md)または[オーケストレーションを開始](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Siebel システムへのメッセージを送信する Wcf-custom または WCF Siebel 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 ファイルに要求メッセージを削除する必要がありますの受信場所。 要求メッセージのスキーマは、このトピックの前半で生成したスキーマに入力してください。 参照してください[ビジネス サービス操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)ビジネス サービスを呼び出すためのスキーマの詳細についてはします。 など、要求メッセージを呼び出し、 *Execute*メソッドを*タイムスタンプ*ビジネス サービスは。  
  
```  
<Execute xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/TimeStamp/Operation" />  
```  
  
 オーケストレーションは、要求メッセージを消費し、Siebel システムに渡されます。 Siebel システムからの応答は、ファイル送信場所に保存されます。 上記の要求メッセージに対する応答は次のとおりです。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ExecuteResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/TimeStamp/Operation">  
  <ExecuteResult>  
    <Time xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/TimeStamp">2007-11-25T20:42:11.0000000</Time>  
  </ExecuteResult>  
</ExecuteResponse>  
```  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外に関する情報のビジネス サービスを使用して操作を実行中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラーの Siebel アダプターと処理](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Siebel アダプターのアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)です。
  
## <a name="see-also"></a>参照  
[Siebel アダプターと BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)