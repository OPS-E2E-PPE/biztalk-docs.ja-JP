---
title: "Oracle E-business Suite で大量のデータ型を持つテーブルの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 501aa302-0f82-4221-b99f-423bc8621a6a
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d65bd37e6ad9c8b8b196df6092a0573d2774a756
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="working-with-tables-that-have-large-data-types-in-oracle-e-business-suite"></a>Oracle E-business Suite で大量のデータ型を持つテーブルの操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが BLOB、CLOB、NCLOB、BFILE などの大規模なデータ型とのインターフェイス テーブルやビューでの操作を実行できるようにします。  
  
-   BLOB、CLOB、NCLOB、アダプターは、型の列を読み取るできるだけでなく、データ更新のクライアントを使用できます。 アダプター公開 Read_\<LOBColName\>と Update_\<LOBColName\>を読み取り、それぞれのデータを更新操作、 \<LOBColName\>で大きな列の名前を指定しますデータ型です。 大規模なデータ型は、1 つのインターフェイス テーブルで 1 つ以上の列がある場合、アダプターは、多くの読み取りし、そのインターフェイス テーブルに対して操作を更新を公開します。  
  
-   BFILE 型の列は、アダプターのクライアントは、データを読み取るだけことができます。 アダプター公開 Read_\<LOBColName\> BFILE 型の列からデータを操作します。 大規模なデータ型は、1 つのインターフェイス テーブルで 1 つ以上の列がある場合、アダプターは、多くの読み取り操作インターフェイス テーブルとしてを公開します。  
  
 これらの操作の詳細については、次を参照してください。[インターフェイス テーブル、インターフェイス ビュー、テーブル、およびビューを含む LOB データに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)です。 これらの操作を実行するためのメッセージ スキーマについては、次を参照してください。[特別な LOB 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)です。  
  
## <a name="how-to-perform-operations-on-columns-with-large-data-types"></a>大規模なデータ型を持つ列に対して操作を実行する方法  
 使用して Oracle E-business Suite での操作を実行[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [Oracle E-business Suite アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)です。 これらのタスクは大規模なデータ型を含む Oracle E-business Suite のインターフェイス テーブルとのインターフェイス ビューで操作を行うには。  
  
1.  BizTalk プロジェクトを作成し、操作のスキーマを生成 (Read_\<LOBColName\>または Update_\<LOBColName\>) をテーブルまたはビューを呼び出します。  
  
2.  Oracle E-business Suite からメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  インターフェイス テーブルまたはビューに対する操作を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="how-this-topic-demonstrates-reading-and-writing-data-into-columns-of-large-data-types"></a>このトピックの内容が大量のデータ型の列にデータの読み書きを示します  
 大規模なデータ型の列にデータを読み書きを示すには、このトピックは、オーケストレーションは、次の操作を作成する手順を示します。  
  
-   CUSTOMER テーブルの BLOB データ型の PHOTO 列を更新します。  
  
-   更新されたレコード、PHOTO 列の値を読み取る。  
  
 このオーケストレーションは、実行時に、更新操作の要求メッセージがのみ提供するように設計されています。 操作内での読み取り操作のメッセージが構築されます。  
  
> [!NOTE]
>  このトピックで、オーケストレーションを読み込んでサンプルに用意されているスクリプトを実行して作成されたベース データベース テーブルでは、CUSTOMER テーブルからデータを更新します。 インターフェイスの任意のテーブルまたはインターフェイス ビューでの update 操作または読み取りを実行するには、このトピックの説明に従ってと同様の手順を実行する必要があります。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、基本的な読み取りを実行し、CUSTOMER テーブル内の BLOB データ型)、PHOTO 列に対する更新操作の方法を示します。 次の表は、サンプルに用意されているスクリプトを実行して作成されます。  
  
 大規模なデータ型の列にデータを読み書きする方法を示すためには、スキーマが生成される、 **Update_PHOTO**と**Read_PHOTO** CUSTOMER テーブルに操作します。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 今すぐ、オーケストレーションのメッセージを作成して、前の手順で生成したスキーマにリンクします。  
  
 このオーケストレーションでは、4 つのメッセージを作成する必要があります: 1 つの受信-応答の設定を**Update_PHOTO**操作と、その他の受信-応答の設定、 **Read_PHOTO**操作します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`UpdateMessage`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *LOBOperations.OracleEBSBinding.Update_PHOTO*LOBOperations は、BizTalk プロジェクトの名前。 OracleEBSBindingSchema は呼び出しの生成スキーマ、 **Update_PHOTO** CUSTOMER テーブルで操作します。|  
  
6.  手順 3 を繰り返して次の 3 つの新しいメッセージを作成します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |識別子に設定します。|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |UpdateResponse|*LOBOperations.OracleEBSBinding.Update_PHOTOResponse*|  
    |ReadMessage|*LOBOperations.OracleEBSBinding1.Read_PHOTO*|  
    |ReadResponse|*LOBOperations.OracleEBSBinding1.Read_PHOTOResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 このオーケストレーションでは、アダプターは、CUSTOMER テーブルに Update_PHOTO 操作を実行する要求メッセージを受信します。 通知メッセージは、ファイルの場所で受信されます。 アダプターは、このメッセージを消費し、Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。 応答が受信されると、オーケストレーションは Update_PHOTO 操作によって更新、PHOTO 列の値が読み取られます Read_PHOTO 操作を呼び出すメッセージを構築します。 このメッセージの応答を同じファイルの場所にも受信します。  
  
 そのため、オーケストレーションは、次が必要があります。  
  
-   ファイルの受信ポートの要求メッセージをドロップする**Update_PHOTO**操作します。  
  
-   双方向の WCF カスタムまたは Wcf-oracleebs の送信を実行するメッセージを送信ポート、 **Update_PHOTO**操作します。  
  
-   双方向の WCF カスタムまたは Wcf-oracleebs の送信を実行するメッセージを送信ポート、 **Read_PHOTO**操作します。 両方を実行することもできます**Read_PHOTO**と**Update_PHOTO**送信ポートと同じ Wcf-custom または Wcf-oracleebs を使用します。 このトピックでは、単一の送信ポートを両方の操作を使用します。  
  
-   A**メッセージの構築**図形をオーケストレーション内でメッセージを構築します。  
  
-   ファイル送信ポートの応答メッセージの保存を**Update_PHOTO**と**Read_PHOTO**操作します。  
  
-   受信図形と送信図形。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![大規模なデータ型の列で使用するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/1976ab27-94c3-4039-a1ca-8790e8897ad5.gif "1976ab27-94c3-4039-a1ca-8790e8897ad5")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveUpdateMessage|Receive|-設定**名前**に*ReceiveUpdateMessage*<br />-設定**アクティブ**に*は True。*|  
|SendUpdateMessage|Send|-設定**名前**に*SendUpdateMessage*|  
|ReceiveUpdateResponse|Receive|-設定**名前**に*ReceiveUpdateResponse*|  
|SendUpdateResponse|Receive|-設定**名前**に*SendUpdateResponse*|  
|SendReadMessage|Send|-設定**名前**に*SendReadMessage*|  
|ReceiveReadResponse|Receive|-設定**名前**に*ReceiveReadResponse*|  
|SaveReadResponse|Send|-設定**名前**に*SaveReadResponse*|  
  
### <a name="adding-construct-message-shape"></a>メッセージの構築図形を追加します。  
 使用することができます、**メッセージの構築**図形をオーケストレーション内で実行する要求メッセージを生成、 **Read_PHOTO**操作します。 これを行うには、追加する必要があります、**メッセージの構築**図形という、**メッセージの割り当て**図形をオーケストレーションにします。 この例で、**メッセージの割り当て**図形が実行する Oracle E-business Suite に送信されるメッセージを生成するコードを呼び出す、 **Read_PHOTO**操作します。 **メッセージの割り当て**図形も、Oracle E-business Suite への送信メッセージに対するアクションを設定します。  
  
 メッセージの構築図形、設定、**メッセージ構築**プロパティを**ReadMessage**です。  
  
 応答を生成するコードは、BizTalk プロジェクトと同じ Visual Studio ソリューションの一部になります。 応答メッセージを生成するためのサンプル コードは、次のように検索します。  
  
```  
namespace MessageCreator  
{  
    public class MessageCreator  
    {  
        private static XmlDocument Message;  
        private static string XmlFileLocation;  
        private static string ResponseDoc;  
  
        public static XmlDocument XMLMessageCreator()  
        {  
            XmlFileLocation = "C:\\TestLocation\\MessageIn";  
            try  
            {  
                ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                Console.WriteLine("EXCEPTION: " + ex.ToString());  
                throw ex;  
            }  
            //Create Message From XML  
            Message = new XmlDocument();  
            Message.PreserveWhitespace = true;  
            Message.Load(ResponseDoc);  
            return Message;  
        }   
    }  
}  
```  
  
 要求メッセージを生成できるように上記のコード例での XML 要求メッセージがあります (用、 **Read_PHOTO**操作) の指定した場所に、`XmlFileLocation`変数。  
  
> [!NOTE]
>  プロジェクトをビルドした後、MessageCreator.dll はプロジェクト ディレクトリに作成されます。 グローバル アセンブリ キャッシュ (GAC) には、この DLL を追加する必要があります。 また、BizTalk プロジェクトに参照として、MessageCreator.dll を追加する必要があります。  
  
 次のコードを呼び出すには、次の式を追加、**メッセージの割り当て**図形とメッセージのアクションを設定します。 式を追加するにはダブルクリック、**メッセージの割り当て**図形式エディターを開きます。  
  
```  
ReadMessage = MessageCreator.MessageCreator.XMLMessageCreator();  
ReadMessage(WCF.Action) = "Tables/ReadLOB/SCOTT/CUSTOMER/PHOTO ";  
```  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*<br />操作を作成する*Read_LOB*です。 この操作は、大規模なデータ型の列から値を読み取るメッセージは使用されます。<br />操作を作成する*Update_LOB*です。 この操作は、大規模なデータ型の列に値を更新するメッセージを使用します。|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*<br />操作を作成する*Read_LOB*です。 この操作は、大規模なデータ型の列から値を読み取るメッセージは使用されます。<br />操作を作成する*Update_LOB*です。 この操作は、大規模なデータ型の列に値を更新するメッセージを使用します。|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveUpdateMessage|-設定**メッセージ**に*UpdateMessage*<br />-設定**操作**に*MessageIn.Update_LOB です。要求*|  
|SendUpdateMessage|-設定**メッセージ**に*UpdateMessage*<br />-設定**操作**に*LOBPort.Update_LOB です。要求*|  
|ReceiveUpdateResponse|-設定**メッセージ**に*UpdateResponse*<br />-設定**操作**に*LOBPort.Update_LOB です。応答*|  
|SendUpdateResponse|-設定**メッセージ**に*UpdateResponse*<br />-設定**操作**に*ResponseOut.Update_LOB です。要求*|  
|SendReadMessage|-設定**メッセージ**に*ReadMessage*<br />-設定**操作**に*LOBPort.Read_LOB です。要求*|  
|ReceiveReadResponse|-設定**メッセージ**に*ReadResponse*<br />-設定**操作**に*LOBPort.Read_LOB です。応答*|  
|SendReadResponse|-設定**メッセージ**に*ReadResponse*<br />-設定**操作**に*ResponseOut.Read_LOB です。要求*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで以前に作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、Oracle データベースに送信します。  
  
    -   ハード ディスクと、対応する FILE ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracleebs 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください。 [Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)です。 WCF カスタムの構成中に次の考慮事項を行う必要があります。 または Wcf-oracleebs がポートを送信します。  
  
        -   `Update_<LOBColName>`操作は、トランザクションの一部として実行する必要があります。 これには、ことを確認する、 **UseAmbientTransaction** binding プロパティを設定する必要があります**True**です。  
  
        -   Wcf-custom または Wcf-oracleebs 送信ポートの送信し 1 つ以上のスキーマに準拠したメッセージを受信、2 つの操作を実行するため、両方の操作に対して動的アクションを設定する必要があります。 アクションの詳細については、次を参照してください。 [for Oracle E-business Suite SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)です。 このオーケストレーションのアクションを次のように設定してください。  
  
            ```  
            <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
              <Operation Name="Update_LOB" Action="Tables/UpdateBlob/SCOTT/CUSTOMER/PHOTO" />  
              <Operation Name="Read_LOB" Action="Tables/ReadLOB/SCOTT/CUSTOMER/PHOTO" />  
            </BtsActionMapping>  
            ```  
  
            > [!IMPORTANT]
            >  動的操作の操作名は、BizTalk オーケストレーションを作成するときに、論理ポートを指定した操作名と同じである必要がありますに注意してください。  
  
        > [!NOTE]
        >  インターフェイス テーブルやビューのインターフェイスの操作を実行するには、アプリケーションのコンテキストを設定することも必要があります。 アダプターがアプリケーションのコンテキストの設定がサポートする方法の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。 アプリケーション コンテキストを設定するには、バインドのプロパティを指定することによって、またはメッセージによって公開されるコンテキスト プロパティを設定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 バインドのプロパティを設定する方法の手順については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定する方法の手順については、次を参照してください。 [Oracle E-business suite アプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。[を構成する物理ポートのバインドを使用して、ポートのバインド ファイルを Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 BizTalk オーケストレーションを開始する前に要求を行うことを確認して、XML を呼び出す、 **Read_PHOTO**操作は C:\TestLocation\MessageIn で使用できます。 XML 要求には、次のようになります必要があります。  
  
```  
<Read_PHOTO xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <FILTER>WHERE NAME='Mindy Martin'</FILTER>  
</Read_PHOTO>  
```  
  
> [!NOTE]
>  要求メッセージ フィルターが存在する特定の名前であるための要求メッセージで**Update_PHOTO**同じ名前の操作、PHOTO 列の値を更新します。 そのため、読み取り操作は、更新操作を使用して挿入したものと同じ値を読み取ります。  
  
 Oracle データベースから大量のデータ型の値を読み書きする BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Wcf-custom または Wcf-oracleebs は、Oracle データベースが実行中にメッセージを送信ポートを送信します。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 削除する必要があります、アプリケーションを開始した後、ファイルに要求メッセージを受信場所を使用します。 要求メッセージのスキーマが用のスキーマに従う必要があります、 **Update_PHOTO**以前に生成する操作。 たとえば、CUSTOMER テーブルの PHOTO 列を更新する要求メッセージは、次するようになります。  
  
```  
<Update_PHOTO xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <FILTER>WHERE Name='Mindy Martin'</FILTER>  
  <DATA>U2FtcGxlIERhdGE=</DATA>  
</Update_PHOTO>  
```  
  
> [!NOTE]
>  BLOB 列を更新中に、データ要素は常に base64 でエンコードされた値を含める必要があります。 CLOB や NCLOB、データ要素は、文字列値を持つことができます。  
  
 上記の要求メッセージは、WHERE 句に一致するレコードの写真の列の値を更新します。 要求メッセージ スキーマを使用して大規模なデータ型に対する操作を実行するための詳細については大きなデータ型に対する操作のメッセージ スキーマを参照してください、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
 オーケストレーションはメッセージを使用して、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、次のよう、上記の要求メッセージ用の Oracle データベースからの応答。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Update_PHOTOResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER" />  
```  
  
 これで、オーケストレーションの要求メッセージの構築、 **Read_PHOTO** C:\TestLocation\MessageIn で利用可能な要求メッセージを使用して操作します。 要求メッセージが Oracle データベースに送信され、応答は同じファイルの場所で保存します。 PHOTO 列に対する読み取り操作の応答には、次のようになります。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Read_PHOTOResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <Read_PHOTOResult>U2FtcGxlIERhdGE=</Read_PHOTOResult>  
</Read_PHOTOResponse>  
```  
  
> [!NOTE]
>  渡された、PHOTO 列に対して同じ値が応答に含まれることに注意してください、 **Update_PHOTO**操作します。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business Suite でアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)