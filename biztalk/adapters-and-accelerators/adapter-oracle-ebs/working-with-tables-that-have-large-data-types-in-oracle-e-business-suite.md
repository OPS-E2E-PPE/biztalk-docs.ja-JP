---
title: Oracle E-business Suite に大量のデータ型を持つテーブルの操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501aa302-0f82-4221-b99f-423bc8621a6a
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf03c256ed525274c808c75704ce252728dc2aa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971651"
---
# <a name="working-with-tables-that-have-large-data-types-in-oracle-e-business-suite"></a>Oracle E-business Suite に大量のデータ型を持つテーブルの操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが BLOB、CLOB、NCLOB、BFILE などの大規模なデータ型を持つインターフェイス テーブルとビューで操作を実行できるようにします。  
  
- BLOB、CLOB、NCLOB、アダプター型の列を読み取り、データを更新するクライアントを使用できます。 アダプター公開 Read_\<LOBColName\>と Update_\<LOBColName\>を読み取って、データを更新する操作、 \<LOBColName\>大規模な列の名前を指定しますデータを入力します。 大規模なデータ型は、1 つのインターフェイス テーブルでは、複数の列がある場合、アダプターは、多くの読み取りし、そのインターフェイス テーブルに対して操作を更新を公開します。  
  
- BFILE の型の列は、アダプター クライアントは、データを読み取るだけことができます。 アダプター公開 Read_\<LOBColName\> BFILE 型の列からデータを読み取る操作。 大規模なデータ型は、1 つのインターフェイス テーブルでは、複数の列がある場合、アダプターは、インターフェイス テーブルに対する操作の読み取りの多くを公開します。  
  
  これらの操作の詳細については、次を参照してください。[インターフェイス テーブル、インターフェイス ビュー、テーブル、ビューを含む LOB データを操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)します。 これらの操作を実行するためのメッセージ スキーマの詳細については、次を参照してください。[特殊な LOB 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)します。  
  
## <a name="how-to-perform-operations-on-columns-with-large-data-types"></a>大規模なデータ型の列に対して操作を実行する方法  
 使用して Oracle E-business Suite での操作を実行する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)します。 大規模なデータ型を含む Oracle E-business Suite のインターフェイス テーブルとインターフェイス ビューで操作を実行するには、これらのタスクは。  
  
1. BizTalk プロジェクトを作成し、操作のスキーマを生成 (Read_\<LOBColName\>または Update_\<LOBColName\>) テーブルまたはビューを起動します。  
  
2. Oracle E-business Suite からメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. インターフェイス テーブルまたはビューに対する操作を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="how-this-topic-demonstrates-reading-and-writing-data-into-columns-of-large-data-types"></a>このトピックで説明の大規模なデータ型の列にデータを読み書きする方法  
 大規模なデータ型の列にデータの読み書きを示すには、このトピックは、次のオーケストレーションを作成する手順を示します。  
  
- CUSTOMER テーブルの (BLOB のデータ型) の PHOTO 列を更新します。  
  
- 更新されたレコードの PHOTO 列の値を読み取ります。  
  
  このオーケストレーションは実行時に、更新操作の要求メッセージを指定のみことように設計されています。 操作に含まれる読み取り操作のメッセージが構築されます。  
  
> [!NOTE]
>  このトピックの「オーケストレーションの読み取りとサンプルに付属のスクリプトを実行して作成された基本データベース テーブルでは、CUSTOMER テーブルからデータを更新。 読み取りを実行またはインターフェイスの任意のテーブルまたはインターフェイス ビューでの操作を更新するには、このトピックの説明に従って、同じような手順を実行する必要があります。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、基本的な読み取りを実行し、(BLOB のデータ型) の顧客テーブルの PHOTO 列に対する操作を更新する方法を示します。 このテーブルは、サンプルに付属のスクリプトを実行して作成されます。  
  
 大規模なデータ型の列にデータを読み書きする方法を示すためには、スキーマを生成、 **Update_PHOTO**と**Read_PHOTO**顧客テーブルに対する操作。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 オーケストレーションでは、メッセージを作成し、前の手順で生成したスキーマにリンクする必要がありますようになりました。  
  
 このオーケストレーションでは、4 つのメッセージを作成する必要があります: 1 つの受信-応答の設定を**Update_PHOTO**操作とその他の受信-応答の設定、 **Read_PHOTO**操作。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  
  
2.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`UpdateMessage`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *LOBOperations.OracleEBSBinding.Update_PHOTO*LOBOperations は、BizTalk プロジェクトの名前です。 OracleEBSBindingSchema が呼び出すために生成されたスキーマ、 **Update_PHOTO**顧客テーブルに対する操作。|  
  
6.  次の 3 つの新しいメッセージを作成する手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |識別子を設定するには|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |UpdateResponse|*LOBOperations.OracleEBSBinding.Update_PHOTOResponse*|  
    |ReadMessage|*LOBOperations.OracleEBSBinding1.Read_PHOTO*|  
    |ReadResponse|*LOBOperations.OracleEBSBinding1.Read_PHOTOResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 このオーケストレーションでは、アダプターは、顧客テーブル Update_PHOTO 操作を実行する要求メッセージを受信します。 通知メッセージは、ファイルの場所で受信されます。 アダプターは、このメッセージを使用し、Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。 応答が受信されると、オーケストレーションは Update_PHOTO 操作によって更新、PHOTO 列の値を読み取り、Read_PHOTO 操作の実行にメッセージを構築します。 このメッセージの応答を同じファイルの場所で受信もします。  
  
 そのため、オーケストレーションは、次に含める必要があります。  
  
- ファイル受信ポートの要求メッセージをドロップする**Update_PHOTO**操作。  
  
- 双方向の Wcf-custom または Wcf-oracleebs の送信を実行するメッセージを送信するポート、 **Update_PHOTO**操作。  
  
- 双方向の Wcf-custom または Wcf-oracleebs の送信を実行するメッセージを送信するポート、 **Read_PHOTO**操作。 両方を実行することもできます**Read_PHOTO**と**Update_PHOTO**同じ Wcf-custom または Wcf-oracleebs を使用して送信ポート。 このトピックでは、両方の操作の単一の送信ポートを使用します。  
  
- A**メッセージの構築**図形をオーケストレーション内でメッセージを構築します。  
  
- ファイル送信ポートの応答メッセージを保存する**Update_PHOTO**と**Read_PHOTO**操作。  
  
- 受信図形と送信図形。  
  
  サンプル オーケストレーションでは、次の項目に似ています。  
  
  ![大規模なデータ型の列で使用するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/1976ab27-94c3-4039-a1ca-8790e8897ad5.gif "1976ab27-94c3-4039-a1ca-8790e8897ad5")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
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
 使用することができます、**メッセージの構築**図形をオーケストレーション内で実行する要求メッセージを生成、 **Read_PHOTO**操作。 これを行うには、追加する必要があります、**メッセージの構築**図形し、その中を**メッセージの割り当て**図形をオーケストレーションにします。 この例で、**メッセージの割り当て**図形が実行する Oracle E-business Suite に送信されるメッセージを生成するコードを呼び出す、 **Read_PHOTO**操作。 **メッセージの割り当て**図形も、Oracle E-business Suite に送信するメッセージに対するアクションを設定します。  
  
 メッセージの構築図形で、設定、**メッセージ構築**プロパティを**ReadMessage**します。  
  
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
  
 要求メッセージを生成できる上記のコード例の XML 要求メッセージがあります (用、 **Read_PHOTO**操作) の指定した場所に、`XmlFileLocation`変数。  
  
> [!NOTE]
>  プロジェクトをビルドした後に MessageCreator.dll がプロジェクト ディレクトリに作成されます。 この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。 また、BizTalk プロジェクトに参照として、MessageCreator.dll を追加する必要があります。  
  
 次のコードを呼び出すには、次の式を追加、**メッセージの割り当て**図形とメッセージのアクションを設定します。 式を追加するには、ダブルクリック、**メッセージの割り当て**図形式エディターを開きます。  
  
```  
ReadMessage = MessageCreator.MessageCreator.XMLMessageCreator();  
ReadMessage(WCF.Action) = "Tables/ReadLOB/SCOTT/CUSTOMER/PHOTO ";  
```  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*<br />-作成操作*Read_LOB*します。 この操作は、大量のデータ型の列から値を読み取るメッセージに使用されます。<br />-作成操作*Update_LOB*します。 この操作は、大量のデータ型の列に値を更新するメッセージに使用されます。|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*<br />-作成操作*Read_LOB*します。 この操作は、大量のデータ型の列から値を読み取るメッセージに使用されます。<br />-作成操作*Update_LOB*します。 この操作は、大量のデータ型の列に値を更新するメッセージに使用されます。|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveUpdateMessage|-設定**メッセージ**に*UpdateMessage*<br />-設定**操作**に*MessageIn.Update_LOB します。要求*|  
|SendUpdateMessage|-設定**メッセージ**に*UpdateMessage*<br />-設定**操作**に*LOBPort.Update_LOB します。要求*|  
|ReceiveUpdateResponse|-設定**メッセージ**に*UpdateResponse*<br />-設定**操作**に*LOBPort.Update_LOB します。応答*|  
|SendUpdateResponse|-設定**メッセージ**に*UpdateResponse*<br />-設定**操作**に*ResponseOut.Update_LOB します。要求*|  
|SendReadMessage|-設定**メッセージ**に*ReadMessage*<br />-設定**操作**に*LOBPort.Read_LOB します。要求*|  
|ReceiveReadResponse|-設定**メッセージ**に*ReadResponse*<br />-設定**操作**に*LOBPort.Read_LOB します。応答*|  
|SendReadResponse|-設定**メッセージ**に*ReadResponse*<br />-設定**操作**に*ResponseOut.Read_LOB します。要求*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、Oracle データベースに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracleebs 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、次を参照してください。 [、Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)します。 WCF カスタムを構成するときに、以下の点を行う必要があります。 または Wcf-oracleebs 送信ポート。  
  
    -   `Update_<LOBColName>`操作は、トランザクションの一部として実行する必要があります。 これは、確実に、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**True**します。  
  
    -   Wcf-custom または Wcf-oracleebs では、送信するポートは、送信し 1 つ以上のスキーマに準拠してメッセージを受信し、2 つの操作を実行しますが、ためには、両方の操作のための動的アクションを設定する必要があります。 アクションの詳細については、次を参照してください。 [for Oracle E-business Suite の SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)します。 このオーケストレーションでは、アクションをよう設定する必要があります。  
  
        ```  
        <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
          <Operation Name="Update_LOB" Action="Tables/UpdateBlob/SCOTT/CUSTOMER/PHOTO" />  
          <Operation Name="Read_LOB" Action="Tables/ReadLOB/SCOTT/CUSTOMER/PHOTO" />  
        </BtsActionMapping>  
        ```  
  
        > [!IMPORTANT]
        >  動的アクション内の操作名を BizTalk オーケストレーションを作成するときに、論理ポートで指定した操作名と同じでなければならないことに注意してください。  
  
    > [!NOTE]
    >  インターフェイス テーブルまたはビューのインターフェイスで操作を実行するには、アプリケーションのコンテキストを設定することも必要があります。 アダプターがアプリケーションのコンテキストの設定がサポートする方法の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。 アプリケーションのコンテキストを設定するには、バインドのプロパティを指定するか、メッセージによって公開されるコンテキスト プロパティを設定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 バインドのプロパティを設定する方法については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)します。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定する方法については、次を参照してください。 [Oracle E-business Suite でのアプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)します。  
    > 
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。 詳細については、次を参照してください。 [Oracle E-business Suite へのポートのバインド ファイルを物理ポートのバインドを使用して、を構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)します。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 BizTalk オーケストレーションを開始する前に要求を行うことを確認して、XML を呼び出す、 **Read_PHOTO**操作が C:\TestLocation\MessageIn でご利用いただけます。 XML 要求には、次のようになる必要があります。  
  
```  
<Read_PHOTO xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <FILTER>WHERE NAME='Mindy Martin'</FILTER>  
</Read_PHOTO>  
```  
  
> [!NOTE]
>  要求メッセージが特定の名前でフィルターに要求メッセージで**Update_PHOTO**操作、PHOTO 列の値が同じ名前を更新します。 そのため、読み取り操作では、挿入、更新操作を使用して、同じ値を読み取ります。  
  
 Oracle データベースからの大量のデータ型の値を読み取ったり書き込んだりする BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。  
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Wcf-custom または Wcf-oracleebs、Oracle データベースが実行中にメッセージを送信ポートを送信します。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 削除する必要があります、アプリケーションを開始した後、ファイルに要求メッセージを受信場所を使用します。 要求メッセージのスキーマが用のスキーマに従う必要があります、 **Update_PHOTO**以前に生成する操作。 たとえば、次のよう、CUSTOMER テーブルの PHOTO 列を更新する要求メッセージ。  
  
```  
<Update_PHOTO xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <FILTER>WHERE Name='Mindy Martin'</FILTER>  
  <DATA>U2FtcGxlIERhdGE=</DATA>  
</Update_PHOTO>  
```  
  
> [!NOTE]
>  BLOB 列を更新するときに、データ要素は常に base64 でエンコードされた値を含める必要があります。 CLOB、NCLOB データ要素は、文字列値を持つことができます。  
  
 前の要求メッセージは、WHERE 句に一致するレコードの PHOTO 列の値を更新します。 要求メッセージ スキーマを使用して大規模なデータ型に対する演算を実行するための詳細については、大きなデータ型に対する操作のメッセージ スキーマを参照してください、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
 オーケストレーションはメッセージを使用し、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、前の要求メッセージ用の Oracle データベースからの応答は、次するようになります。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Update_PHOTOResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER" />  
```  
  
 これで、オーケストレーションの要求メッセージを構築します、 **Read_PHOTO** C:\TestLocation\MessageIn で使用可能な要求メッセージを使用して操作します。 Oracle データベースに要求メッセージを送信し、応答は同じファイルの場所に保存します。 PHOTO 列に対する読み取り操作の応答には、次のようになります。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Read_PHOTOResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <Read_PHOTOResult>U2FtcGxlIERhdGE=</Read_PHOTOResult>  
</Read_PHOTOResponse>  
```  
  
> [!NOTE]
>  渡される PHOTO 列に対して同じ値が応答に含まれることに注意してください、 **Update_PHOTO**操作。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business suite アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)します。  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)