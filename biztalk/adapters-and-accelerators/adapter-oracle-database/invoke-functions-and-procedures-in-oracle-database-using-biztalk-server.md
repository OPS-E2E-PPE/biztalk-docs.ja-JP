---
title: 関数と BizTalk Server を使用して Oracle データベースでプロシージャを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functions and procedures, invoking by using BizTalk Server
ms.assetid: 35f2c40e-1151-4941-9030-16464fc1caf8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd864d2cb800233612a82a34d2f65be62a68bdd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376510"
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-biztalk-server"></a>関数と BizTalk Server を使用して Oracle データベースでプロシージャを呼び出す
アダプター クライアントを使用して関数および Oracle データベースでプロシージャを呼び出すことができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]プロシージャ、関数、およびパッケージの操作として表示されます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントを呼び出すことができます。  
  
- オーバー ロードされた関数とストアド プロシージャ。 参照してください[オーバー ロードされた関数を呼び出すと BizTalk Server を使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)します。  
  
- 関数およびプロシージャの OUT、IN を持つと REF CURSOR を IN パラメーター。 参照してください[関数を呼び出すと、BizTalk Server を使用して Oracle データベース内の REF CURSOR を使用したプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md)します。  
  
- 関数とプロシージャの OUT、IN を持つレコードを IN パラメーターを入力します。 参照してください[BizTalk Server を使用して Oracle データベースでレコードの種類で呼び出す関数とプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md)します。  
  
  関数およびストアド プロシージャを使用して操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[関数と Oracle データベースでストアド プロシージャに対する操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-stored-procedures-in-oracle-database.md)します。 関数およびプロシージャを呼び出すため、SOAP メッセージの構造については、次を参照してください。[関数およびプロシージャのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)します。  
  
## <a name="how-to-invoke-functions-in-an-oracle-database"></a>Oracle データベースでの関数を呼び出す方法でしょうか。  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)します。 これらのタスクは、Oracle データベースで関数の呼び出しには。  
  
1. BizTalk プロジェクトを作成し、Oracle データベースで、呼び出し先関数のスキーマを生成します。  
  
2. Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. Oracle データベースで関数を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル InvokeFunction、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックで、関数を呼び出す方法を示すを呼び出す SCOTT\Package\ACCOUNT_PKG スキーマの下にある CREATE_ACCOUNT 関数。 このパッケージは、サンプルで提供される SQL スクリプトを実行して、SCOTT スキーマの下に作成されます。 CREATE_ACCOUNT 関数は考慮に入れたアドレス情報を入力としてと、アカウントと顧客のテーブルのレコードを作成します。 レコードが既に存在する場合、関数は 0 以外を返しますそれ以外の場合、関数は、アカウント ID を返します。 サンプルとの SQL スクリプトの詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)します。  
  
 CREATE_ACCOUNT 関数を呼び出す、SCOTT\Package\ACCOUNT_PKG スキーマで同じ関数のスキーマを生成する必要があります。 参照してください[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法の詳細について。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類 ウィンドウからのメッセージを最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: Oracle データベースとその他の応答を受信する要求を送信する 1 つ。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順に従います。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
2.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
3.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *InvokeFunction.OracleDBBindingSchema.CREATE_ACCOUNT*ここで、 *InvokeFunction*の名前を指定します、BizTalk プロジェクトです。 *OracleDBBindingSchema* CREATE_ACCOUNT 関数に対して生成されるスキーマです。|  
  
5.  新しいメッセージを作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *InvokeFunction.OracleDBBindingSchema.CREATE_ACCOUNTResponse*します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle データベースに使用する関数を呼び出すためです。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]がこのメッセージを使用して、ODP を使用して Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。 関数と Oracle データベースでプロシージャを呼び出すための一般的なオーケストレーションが含まれます。  
  
- Oracle データベースにメッセージを送信し、応答を受信する図形を送受信します。  
  
- Oracle データベースに送信する要求メッセージを受信するポートは一方向の受信します。  
  
- 双方向の送信要求メッセージを Oracle データベースし、応答の受信を送信するポート。  
  
- フォルダーに Oracle データベースからの応答を送信する一方向の送信ポート。  
  
  サンプル オーケストレーションには、次のようになります。  
  
  ![Oracle で関数を呼び出すオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/f102c81b-be2b-4e3c-89aa-25a4af5e6739.gif "f102c81b-be2b-4e3c-89aa-25a4af5e6739")  
  
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
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br />-設定**型**に*SaveResponseType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形は、メッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.Function.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Function.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Function.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.Function.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、Oracle データベースに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 Wcf-custom または Wcf-oracledb のポートを作成する方法については、次を参照してください。 [、Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)します。  
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk Server 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、次を参照してください。 [Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)します。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle のデータベース テーブル内の関数を呼び出す BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。  
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Oracle データベースにメッセージを送信する Wcf-custom または Wcf-oracledb の送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。 要求メッセージのスキーマは、以前に作成した関数のスキーマに準拠する必要があります。 参照してください[関数およびプロシージャのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)を使用する関数を呼び出すための要求メッセージ スキーマの詳細について、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
 たとえば、CREATE_ACCOUNT 関数の呼び出しに要求メッセージには。  
  
```  
<CREATE_ACCOUNT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
  <ACCT>  
    <ACCTID xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT"></ACCTID>  
    <NAME xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">John Smith</NAME>  
    <BALANCE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">10000</BALANCE>  
  </ACCT>  
  <ADDR>  
    <STREET xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">BelRed Road</STREET>  
    <CITY xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">Redmond</CITY>  
    <STATE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT">WA</STATE>  
  </ADDR>  
</CREATE_ACCOUNT>  
```  
  
 オーケストレーションはメッセージを使用し、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージ用の Oracle データベースからの応答には。  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<CREATE_ACCOUNTResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
<CREATE_ACCOUNTResult>[ID]</CREATE_ACCOUNTResult>  
</CREATE_ACCOUNTResponse>  
```  
  
 ここで、[ID] は、関数によって作成されたアカウントの ID です。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外に関する情報の関数とを使用してプロシージャの呼び出し中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラー処理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)します。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)します。  
  
## <a name="see-also"></a>参照  
[Oracle Database による開発の BizTalk アプリケーションを構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)