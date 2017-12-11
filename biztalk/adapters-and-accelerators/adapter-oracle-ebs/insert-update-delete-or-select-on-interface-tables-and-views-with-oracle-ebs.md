---
title: "挿入、更新、削除、またはインターフェイスのテーブルおよび Oracle E-business Suite のインターフェイス ビューの選択 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85f42431-80fb-49be-86d1-bb21eee5e4f5
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adc837fb72c0e18370d28450bf40f162f9849230
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="insert-update-delete-or-select-on-interface-tables-and-interface-views-with-oracle-e-business-suite"></a>挿入、更新、削除、またはインターフェイスのテーブルおよび Oracle E-business Suite のインターフェイス ビューの選択
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェス Insert などの標準的な操作のセットは、インターフェイスに対する Update、Delete、Select がテーブルし、ビューします。 このトピックでは、アダプターを使用してこれらの操作を実行する方法についてを説明します。 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。[インターフェイス テーブルとのインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)です。 これらの操作用の SOAP メッセージの構造については、次を参照してください。 [Insert、Update、Delete、および選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)です。  
  
> [!NOTE]
>  アダプターでは、テーブルおよび BLOB、CLOB、NCLOB、BFILE などの大規模なデータ型を含むビューの特定の操作も公開します。 このような操作の詳細については、次を参照してください。[インターフェイス テーブル、インターフェイス ビュー、テーブル、およびビューを含む LOB データに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)です。 BizTalk Server を使用して大規模なデータ型でテーブルおよび列に対する操作を実行する方法については、次を参照してください。 [WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルでの操作を完了](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)です。  
  
## <a name="how-to-perform-basic-operations-on-oracle-e-business-suite"></a>Oracle E-business Suite の基本的な操作を実行する方法  
 使用して Oracle E-business Suite での操作を実行[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [Oracle E-business Suite アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)です。 Oracle E-business Suite の Insert、Update、Delete、またはテーブルとビューに対する Select 操作を実行するには、これらのタスクは。  
  
1.  BizTalk プロジェクトを作成し、インターフェイス テーブルまたはビューを起動する操作のスキーマを生成します。  
  
2.  Oracle E-business Suite からメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  インターフェイス テーブルまたはビューに対する操作を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、Oracle E-business Suite で AR_ARCHIVE_PURGE_INTERIM インターフェイス テーブルにレコードを挿入して基本的な Insert、Update、Delete、または Select 操作を実行する方法を示します。 このインターフェイス テーブルで使用できる、**債権**Oracle E-business suite アプリケーションです。  
  
 レコードを挿入する方法を示すためには、AR_ARCHIVE_PURGE_INTERIM テーブルに対して挿入操作のスキーマが生成されます。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは通常、対応するスキーマによって定義された型の変数です。 オーケストレーションのメッセージを作成し、それらを前の手順で生成されたスキーマにリンクする必要がありますようになりました。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *InsertInterfaceTable.OracleEBSBinding.Insert*InsertInterfaceTable は、BizTalk プロジェクトの名前。 OracleEBSBinding は、AR_ARCHIVE_PURGE_INTERIM テーブルに対する挿入操作に対して生成されたスキーマでは。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *InsertInterfaceTable.OracleEBSBinding.InsertResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle E-business Suite での操作を実行するためです。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]このメッセージを消費し、Oracle E-business Suite に渡します。 Oracle E-business Suite からの応答は、別の場所に保存されます。 Oracle データベースでの基本的なテーブルの操作を実行するための一般的なオーケストレーションにが含まれます。  
  
-   Oracle データベースにメッセージを送信し、応答を受信する図形を送受信します。  
  
-   一方向の受信ポートを Oracle データベースに送信する要求メッセージを受信します。  
  
-   双方向の送信要求メッセージを Oracle データベースし、応答の受信を送信するポート。  
  
-   フォルダーに Oracle データベースからの応答を送信する一方向の送信ポートです。  
  
 Select 操作のサンプルのオーケストレーションには、次のようになります。  
  
 ![インターフェイス テーブルにデータを挿入するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/8a4508c5-9949-4043-9de5-d1226db8117b.gif "8a4508c5-9949-4043-9de5-d1226db8117b")  
  
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
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.Insert.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Insert.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Insert.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.Insert.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートを接続しているし、オーケストレーションが完了します。  
  
 BizTalk ソリューションをビルドし、BizTalk Server に展開する必要がありますようになりました。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで以前に作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。  
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、Oracle E-business Suite に送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Oracle E-business Suite からの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   Oracle E-business Suite にメッセージを送信する物理 Wcf-custom または Wcf-oracleebs 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください[Oracle E-business アダプターを物理ポート バインドを手動で構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)  
  
         インターフェイスのテーブルまたはインターフェイスで操作を実行するビューを使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]操作が呼び出される適切なアプリケーション コンテキストを設定する必要があります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のすべての操作のアプリケーション コンテキストを指定する特定のバインディング プロパティを提供します。 インターフェイス テーブルに対する操作を実行するために使用する Wcf-custom または Wcf-oracleebs のポートでは、これらのバインディング プロパティを設定する必要があります。  
  
        -   場合、 **ClientCredentialType**に設定されているプロパティのバインド**データベース**、し、アプリケーションのコンテキストを設定する次のバインドのプロパティを指定する必要があります。  
  
            |プロパティのバインド|値|  
            |----------------------|-----------|  
            |**OracleUserName**|Oracle E-business Suite ユーザーの名前を指定します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力する値の大文字と小文字は保持されません、 **OracleUserName** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準的な規則を使用して Oracle E-business Suite に渡されるユーザー名 * とします。 ただし、保持するユーザー名の大文字と小文字の場合、または特殊文字を格納しているユーザー名を入力する場合は、二重引用符で囲まれた値を指定する必要があります。|  
            |**OraclePassword**|Oracle E-business Suite ユーザーのパスワード。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力する値の大文字と小文字は保持されません、 **OraclePassword** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準的な規則を使用して Oracle E-business Suite に渡されるパスワード * とします。 ただし、保持するパスワードの大文字と小文字の場合、または特殊文字を含むパスワードを入力する場合は、二重引用符で囲まれた値を指定する必要があります。|  
            |**OracleEBSResponsibilityName**|Oracle E-business Suite ユーザーに関連付けられた役割。|  
  
        -   場合、 **ClientCredentialType**に設定されているプロパティのバインド**EBusiness**、する必要がありますを指定していない Oracle E-business 資格情報の接続を確立中にします。 このような場合の値を指定する必要がありますのみ、 **OracleEBSResponsibilityName**プロパティをバインドします。  
  
         異なるバインディングのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。 アダプターがアプリケーションのコンテキストの設定がサポートする方法の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
        > [!NOTE]
        >  アプリケーション コンテキストを設定するには、バインドのプロパティを指定することによって、またはメッセージによって公開されるコンテキスト プロパティを設定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 バインドのプロパティを設定する方法の手順については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定する方法の手順については、次を参照してください。 [Oracle E-business suite アプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。[を構成する物理ポートのバインドを使用して、ポートのバインド ファイルを Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 AR_ARCHIVE_PURGE_INTERIM インターフェイス テーブルにレコードを挿入するための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Wcf-custom または Wcf-oracleebs Oracle E-business Suite へのメッセージが実行されている送信ポートを送信します。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、ファイルに要求メッセージをドロップする必要がありますの受信場所。 要求メッセージのスキーマは、以前に生成する挿入操作のスキーマに準拠する必要があります。 たとえば、AR_ARCHIVE_PURGE_INTERIM インターフェイス テーブルからすべてのレコードを選択する要求メッセージには。  
  
```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR/AR_ARCHIVE_PURGE_INTERIM">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">  
      <TRX_ID>001</TRX_ID>  
      <RELATED_ID>002</RELATED_ID>  
    </InsertRecord>  
  </RECORDSET>    
</Insert>  
```  
  
 この要求メッセージは、AR_ARCHIVE_PURGE_INTERIM インターフェイス テーブルにレコードが挿入されます。 参照してください[Insert、Update、Delete、および選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)を Oracle E-business Suite を使用して基本的な DML 操作の要求メッセージ スキーマの詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
 単純なデータ列の場合と同様に、前の要求メッセージで使用することも、 **InlineValue**属性。 InlineValue 属性の詳細については、内の挿入操作の説明を参照してください。[インターフェイス テーブルとのインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)です。  
  
 たとえば、インラインの値を持つ前の要求メッセージが、次のようになります。  
  
```  
<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR/AR_ARCHIVE_PURGE_INTERIM">  
  <RECORDSET>  
    <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">  
      <TRX_ID InlineValue="(Select TRX_ID FROM table_name)">001</TRX_ID>  
      <RELATED_ID>002</RELATED_ID>  
    </InsertRecord>  
  </RECORDSET>    
</Insert>  
```  
  
 この要求メッセージで TRX_ID 列の値は、別のテーブルから取得されます。 そのため、TRX_ID の値として「001」を指定すると、場合でも、InlineValue 属性の指定した SELECT ステートメントの値は、テーブルに挿入を取得します。  
  
 オーケストレーションはメッセージを使用して、Oracle E-business Suite に送信します。 Oracle E-business Suite からの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、前の要求メッセージの Oracle E-business Suite からの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR/AR_ARCHIVE_PURGE_INTERIM">  
  <InsertResult>1</InsertResult>   
</InsertResponse>  
```  
  
 応答には、テーブルに挿入される行の数が含まれています。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成した後できるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business Suite でアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)