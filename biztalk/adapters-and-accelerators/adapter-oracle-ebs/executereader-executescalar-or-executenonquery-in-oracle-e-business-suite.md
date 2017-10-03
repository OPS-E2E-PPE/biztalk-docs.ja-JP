---
title: "Oracle E-business Suite で ExecuteReader、ExecuteScalar、ExecuteNonQuery 操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e2d377d-60a2-45fe-8458-433e6f4f6619
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cff3d58712ca8e926ada18519fcebb5fddc7ea65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-oracle-e-business-suite"></a>Oracle E-business Suite で ExecuteReader、ExecuteScalar、ExecuteNonQuery 操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]などの一般的な操作を公開する**ExecuteNonQuery**、 **ExecuteReader**、および**ExecuteScalar**です。 これらの操作を使用して、Oracle データベースで任意の SQL ステートメントを実行することができます。 これらの操作は、応答するための SQL ステートメントの種類によって異なります。 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。  
  
 このトピックは、実行する方法を示します、 **ExecuteReader**操作を使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 実行するには、このトピックで説明する手順の同じセットを行うことができる**ExecuteNonQuery**と**ExecuteScalar**操作します。  
  
## <a name="how-to-invoke-executereader-operation-on-oracle-database"></a>Oracle データベースでの呼び出しの ExecuteReader 操作する方法  
 使用して Oracle データベースでの操作を実行[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [Oracle E-business Suite アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)です。 呼び出す、 **ExecuteReader** Oracle データベースに対する操作は、これらのタスクは。  
  
1.  BizTalk プロジェクトを作成しのスキーマを生成、 **ExecuteReader**操作します。  
  
2.  Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  Oracle データベースで操作を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックを呼び出す方法を示します、 **ExecuteReader** Oracle データベースを使用して、操作、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 **ExecuteReader**操作は、パラメーターとして任意の SQL ステートメントを受け取りし、データセットの配列として、操作の結果セットを返します。 このトピックを使用して ACCOUNTACTIVITY テーブルの SELECT ステートメントを実行お、 **ExecuteReader**操作します。 ACCOUNTACTIVITY テーブルは、サンプルに用意されているスクリプトを実行して作成されます。 スクリプトの詳細については、次を参照してください。[サンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。  
  
 呼び出す方法をデモンストレーションする**ExecuteReader**操作、スキーマの生成は、 **ExecuteReader**操作します。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 スキーマを生成する方法の詳細については、次を参照してください。 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)です。  
  
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
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *Execute_Reader.GenericOperation.ExecuteReader*Execute_Reader は、BizTalk プロジェクトの名前。 *GenericOperation*に対して生成されたスキーマは、 **ExecuteReader**操作します。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *Execute_Reader.GenericOperation.ExecuteReaderResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle データベースで操作を実行します。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]このメッセージを消費し、Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。 など、一般的な操作を呼び出すための一般的なオーケストレーション**ExecuteReader**が含まれます。  
  
-   Oracle データベースからメッセージを送受信する図形を送受信します。  
  
-   双方向の受信ポートを送信し、Oracle データベースからメッセージを受信します。  
  
-   フォルダーに Oracle データベースからの応答を送信する一方向の送信ポートです。  
  
 呼び出すためのサンプル オーケストレーション、 **ExecuteReader**操作、次のようになります。  
  
 ![ExecuteReader 操作を呼び出すオーケストレーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/37b63331-76b7-47a2-b9d3-0c60e165d993.gif "37b63331-76b7-47a2-b9d3-0c60e165d993")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 各メッセージの構築図形の次のプロパティを構成する必要があります。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前に対応します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次の表に、プロパティを構成します。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前に対応します。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形のメッセージを指定して、ポートへの接続  
 次の表では、アクション図形のメッセージを指定して、メッセージ、ポートにリンクのプロパティの値を指定します。 示されている名前、**図形**列は、以前に、オーケストレーション ダイアグラムで表示される、メッセージの構築図形の名前に対応します。  
  
 これらのプロパティを構成すると、メッセージの構築図形とポートを接続しているし、オーケストレーションが完了します。  
  
 次に、BizTalk ソリューションをビルドし、BizTalk Server に展開する必要がありますようになりました。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.Exec_Reader.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Exec_Reader.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Exec_Reader.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.Exec_Reader.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートを接続しているし、オーケストレーションが完了します。  
  
 BizTalk ソリューションをビルドし、BizTalk Server に展開する必要がありますようになりました。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**ペインで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。  
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、Oracle データベースに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   Oracle データベースにメッセージを送信するには、物理 Wcf-custom または Wcf-oracleebs 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 送信ポートを作成する方法については、次を参照してください。 [Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)です。  
  
        > [!IMPORTANT]
        >  格納されている汎用の操作の一部のオブジェクトに対する操作を実行している場合などプロシージャ、関数、インターフェイスのテーブル、または Oracle E-business Suite アプリケーションに属するインターフェイス ビューを指定して、アプリケーションのコンテキストを設定する必要があります。必要なバインドのプロパティです。 アプリケーション コンテキストの設定の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
        >   
        >  アプリケーション コンテキストを設定するには、バインドのプロパティを指定することによって、またはメッセージによって公開されるコンテキスト プロパティを設定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 バインドのプロパティを設定する方法の手順については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定する方法の手順については、次を参照してください。 [Oracle E-business suite アプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。[を構成する物理ポートのバインドを使用して、ポートのバインド ファイルを Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 呼び出す前に、BizTalk アプリケーションを開始する必要があります**ExecuteReader** Oracle データベースで操作します。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Wcf-custom または Wcf-oracleebs は、Oracle データベースが実行中にメッセージを送信ポートを送信します。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、ファイルに要求メッセージをドロップする必要がありますの受信場所。 要求メッセージのスキーマが用のスキーマに従う必要があります、 **ExecuteReader**以前に生成する操作。 使用して、SELECT ステートメントを実行する要求メッセージなど、 **ExecuteReader**操作します。  
  
```  
<ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/">  
  <Query>SELECT * FROM ACCOUNTACTIVITY</Query>  
</ExecuteReader>  
```  
  
 ExecuteReader、ExecuteScalar、および ExecuteNonQuery 操作を呼び出すための要求メッセージ スキーマの詳細については、メッセージ スキーマを参照してください、 **ExecuteReader**操作を使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
 オーケストレーションはメッセージを使用して、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 応答、 **ExecuteReader**操作には、データセットとして結果セットが含まれています。 たとえば、前の要求メッセージの Oracle データベースからの応答には。  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>   
<ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/">  
  <ExecuteReaderResult>  
    \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
      \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
        \<xs:complexType>  
          \<xs:sequence>  
            \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
              \<xs:complexType>  
                \<xs:sequence>  
                  \<xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                  \<xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                  \<xs:element minOccurs="0" name="AMOUNT" type="xs:decimal" />   
                  \<xs:element minOccurs="0" name="DESCRIPTION" type="xs:string" />   
                  \<xs:element minOccurs="0" name="TRANSDATE" type="xs:dateTime" />   
                  \<xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                \</xs:sequence>  
              \</xs:complexType>  
            \</xs:element>  
          \</xs:sequence>  
        \</xs:complexType>  
      \</xs:element>  
    \</xs:schema>  
    \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
      <NewDataSet xmlns="">  
        <NewTable>  
          <TID>1</TID>   
          <ACCOUNT>100001</ACCOUNT>   
          <AMOUNT>500</AMOUNT>   
          <DESCRIPTION />   
          <TRANSDATE>2008-08-04T13:04:20</TRANSDATE>   
          <PROCESSED>n</PROCESSED>   
        </NewTable>  
        <NewTable>  
          ......  
          ......  
        </NewTable>  
        ......  
        ......  
      </NewDataSet>  
    \</diffgr:diffgram>  
  </ExecuteReaderResult>  
</ExecuteReaderResponse>  
```  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成した後できるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business Suite でアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)