---
title: 厳密に型指定されたポーリング ベース データが変更されてから受信 BizTalk Server を使用して SQL Server |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6e6ba7e-9e13-4e28-b57d-d24569277bbc
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b12450e87e730e3713a89350fc2a16440e4d911
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968056"
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-biztalk-server"></a>厳密に型指定されたポーリング ベース データが変更されてから受信 BizTalk Server を使用して SQL Server
構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server から厳密に型指定されたポーリング メッセージを受信します。 データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。 ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。  
  
 その他の任意のスキーマにポーリング メッセージ内の要素をマップするシナリオで、厳密に型指定されたポーリングを使用する必要があります。 マップするスキーマは、SQL Server 上の別の操作の可能性があります。 たとえば、別のテーブルに対して挿入操作用のスキーマにポーリング メッセージの特定の要素をマップする可能性があります。 そのため、ポーリング メッセージ内の値は、挿入操作のパラメーターとして機能します。 単純なシナリオでは、同様の情報を格納するスキーマ ファイルをポーリングの厳密に型指定されたメッセージのスキーマをマップする可能性があります。  
  
> [!IMPORTANT]
>  かどうかは 1 つの BizTalk アプリケーションに複数のポーリング操作を必要がありますを指定する、 **InboundID**接続一意にする URI の一部として接続プロパティです。 一意の接続 URI の場合を複数作成できます、同じデータベースまたはデータベースでも同じテーブルをポーリングするポートを受信します。 詳細については、次を参照してください。[受信ポーリング メッセージ間で複数の受信ポートから Biztalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)です。  
  
 アダプターが厳密に型指定されたポーリングをサポートする方法の詳細については、次を参照してください。[ポーリングのサポート](https://msdn.microsoft.com/library/dd788416.aspx)です。 メッセージのスキーマを厳密に型指定されたポーリングの詳細については、次を参照してください。[ポーリングと TypedPolling 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)です。  
  
## <a name="how-this-topic-demonstrates-strongly-typed-polling"></a>このトピックの内容が厳密に型指定されたポーリングを示しています  
 このトピックでは、厳密に型指定されたポーリングを使用してポーリング メッセージを別のスキーマにマップする方法を示します。 このトピックは、BizTalk プロジェクトを作成しのスキーマを生成する方法を示しています。 **TypedPolling**操作します。 スキーマを生成する前に**TypedPolling**操作で、次を実行する必要があります。  
  
-   指定する必要があります、 **InboundID**接続 URI の一部として。  
  
-   ポーリング ステートメントを指定する必要があります、 **PollingStatement**プロパティをバインドします。  
  
 ポーリング ステートメントの一部として、次の操作を実行します。  
  
-   Employee テーブルからすべての行を選択します。  
  
-   ストアド プロシージャ、EmployeeHistory テーブルには Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。  
  
-   Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。 この手順は、従業員名、指定、および給与をパラメーターとして受け取ります。  
  
 これらの操作を実行するは、次を指定する必要があります、 **PollingStatement**プロパティをバインドします。  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 スキーマを生成するため、 **TypedPolling**操作、スキーマは、厳密に型指定され、ポーリング メッセージに含まれるすべての要素が含まれています。  
  
 同じ BizTalk プロジェクトの一部として、たとえば EmployeeDetails.xsd 別のスキーマ ファイルを追加します。 EmployeeDetails.xsd のスキーマには、次のようになります。  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://Typed_Polling.EmployeeDetails" elementFormDefault="qualified" targetNamespace="http://Typed_Polling.EmployeeDetails" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="EmployeeDetails">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Employee_Info" type="xs:string" />   
        <xs:element name="Employee_Profile" type="xs:string" />   
        <xs:element name="Employee_Performance" type="xs:string" />   
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 BizTalk マッパーは、EmployeeDetails.xsd スキーマ内の要素には Employee テーブル (ポーリング メッセージとして受信済み) から要素をマップするプロジェクトに追加します。 マップの一部として、ポーリング メッセージから 1 つまたは複数の要素を組み合わせるし、EmployeeDetails スキーマ内の単一要素にマップします。 これを行うを使用して、**文字列連結**functoid です。  
  
 最後に、BizTalk プロジェクトの一部として EmployeeDetails.xsd スキーマに準拠したファイルは、ファイル送信ポートには削除されます。  
  
## <a name="configure-typed-polling-with-the-sql-adapter-binding-properties"></a>SQL アダプターのプロパティをバインドに型指定されたポーリングを構成します。  
 次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ データの変更メッセージを受信するアダプターを構成するために使用します。 以外の場合、 **PollingStatement**バインディング プロパティ バインディング プロパティをすべてここで示した必要なの受信ポートを構成するときに、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 指定する必要があります、 **PollingStatement**プロパティのバインドのスキーマを生成する前に、 **TypedPolling**操作します。  
  
> [!NOTE]
>  型指定されたポーリングは、指定する必要があります、 **PollingStatement**スキーマの生成中にプロパティをバインドします。 その他のバインディング プロパティの指定も、スキーマの生成中は必須ではない場合でもメッセージが表示できます。 バインドのプロパティを指定すると、ポートのバインド ファイル、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成され、メタデータの生成の一部では、バインドのプロパティを指定する値も含まれます。 このバインド ファイルを後でインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または WCF SQL を作成する管理コンソールの受信ポート。 詳細については、バインド ファイルを使用するポートを作成する、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。  
  
|プロパティのバインド|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。 既定値は**ポーリング**です。 厳密に型指定されたポーリング メッセージを受信するには、これを設定**TypedPolling**です。|  
|**PolledDataAvailableStatement**|すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。 SQL ステートメントが指定した行がある場合のみ、 **PollingStatement**プロパティのバインドが実行されます。|  
|**PollingIntervalInSeconds**|秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔では、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプターは、間隔の残り時間を待機します。|  
|**PollingStatement**|SQL Server データベース テーブルをポーリングする SQL ステートメントを指定します。 単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定できます。 既定値は null です。 値を指定する必要があります**PollingStatement**ポーリングを有効にします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。 セミコロンで区切られた SQL ステートメントの任意の数を指定できます。<br /><br /> **重要:** の**TypedPolling**メタデータを生成する前にこのバインドのプロパティを指定する必要があります。|  
|**PollWhileDataFound**|指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**をポーリングするテーブルにデータがある場合、プロパティをバインドします。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。 既定値は**false**です。|  
  
 これらのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for SQL Server アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 使用する方法の詳細については、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL サーバーのポーリングを読みます。  
  
## <a name="how-to-receive-strongly-typed-data-change-messages-from-the-sql-server-database"></a>SQL Server データベースからデータの変化を厳密に型指定されたメッセージを受信する方法  
 SQL Server データベースを使用して、操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明する手順のタスクでは、 [SQL アダプターと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)です。 これらのタスクはデータの変化を厳密に型指定されたメッセージを受信するアダプターを構成するのには。  
  
1.  BizTalk プロジェクトを作成しのスキーマを生成、 **TypedPolling**操作します。 指定する必要があります、 **InboundID**接続プロパティと**PollingStatement**スキーマの生成中にプロパティをバインドします。 たとえば、次のよう受信 ID が指定された URI の接続。  
  
    ```  
    mssql://mysqlserver//mysqldatabase?InboundID=mydatabaseId  
    ```  
  
2.  SQL Server データベースからメッセージを受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  SQL Server データベースからメッセージを受信して、フォルダーに保存するオーケストレーションを作成します。  
  
4.  BizTalk プロジェクトに EmployeeDetails.xsd など、スキーマを追加します。  
  
5.  ポーリングのメッセージのスキーマをスキーマにマップ EmployeeDetails.xsd BizTalk マッパーを追加します。  
  
6.  構築し、BizTalk プロジェクトを展開します。  
  
7.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
    > [!IMPORTANT]
    >  受信ポーリングのシナリオは、一方向の WCF カスタム常に構成する必要があります。 または WCF SQL 受信ポート。 双方向の WCF カスタムまたは WCF SQL 受信ポートの受信操作はサポートされていません。  
  
8.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、TypedPolling、このトピックの内容に基づいてが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。  
  
## <a name="generate-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、 **TypedPolling**操作します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。 スキーマを生成するときに、次のタスクを実行します。  
  
1.  指定して、 **InboundID**接続 URI を指定する際に、接続プロパティです。 このトピックの内容を指定できます、 **InboundID**として**従業員**です。 接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
2.  値を指定、 **PollingStatement**プロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
     バインドのプロパティを指定する方法については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。  
  
3.  コントラクトの種類を選択して**サービス (入力方向の操作)** です。  
  
4.  スキーマを生成、 **TypedPolling**操作します。  
  
## <a name="define-messages-and-message-types"></a>メッセージおよびメッセージの定義の種類  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションの種類からのメッセージをリンクする必要があります。  
  
 このトピックのメッセージを受信する SQL Server データベースから 1 つのメッセージを作成する必要があります。  
  
 メッセージを作成し、それらのスキーマにリンクするには、次の手順を実行します。  
  
#### <a name="create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマへのリンク  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**PollingMessage**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*Typed_Polling.TypedPolling_Employee.TypedPolling*ここで、 *Typed_Polling* BizTalk の名前を指定しますプロジェクトです。 *TypedPolling_Employee*に対して生成されたスキーマは、 **TypedPolling**操作します。|  
  
## <a name="set-up-the-orchestration"></a>オーケストレーションをセットアップします。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SQL Server データベースからデータの変更のポーリングに基づいたメッセージを受信します。 このオーケストレーションでは、アダプターは、指定されたポーリング ステートメントのポーリング メッセージを受信します。 BizTalk マッパーは、ポーリング メッセージ スキーマを EmployeeDetails.xsd スキーマにマップします。 マップされたメッセージはファイルの場所に保存されます。 SQL Server データベースから厳密に型指定されたポーリング メッセージを受信するための一般的なオーケストレーションにが含まれます。  
  
-   受信図形と送信図形を SQL Server からメッセージを受信し、それぞれ、FILE ポートに送信します。  
  
-   一方向の受信ポートを SQL Server からメッセージを受信します。  
  
    > [!IMPORTANT]
    >  受信のポーリングのシナリオが常に設定する必要がありますの一方向の受信ポート。 双方向受信ポートが受信操作のサポートされていません。  
  
-   SQL Server データベースからフォルダーにポーリング応答を送信する一方向の送信ポートです。  
  
-   ポーリングのメッセージのスキーマを他の任意のスキーマにマップする BizTalk マッパー。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![オーケストレーションを強く &#45;以外の型指定されたポーリング](../../adapters-and-accelerators/adapter-sql/media/1db03859-b7f8-470c-9158-2be4da0b45ae.gif "1db03859-b7f8-470c-9158-2be4da0b45ae")  
  
### <a name="add-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br /><br /> -設定**アクティブ**に*は True。*|  
|SaveMessage|Send|-設定**名前**に*SaveMessage*|  
  
### <a name="add-ports"></a>ポートを追加します。  
 論理ポートごとに、次のプロパティを指定することを確認してください。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|SQLReceivePort|-設定**識別子**に*SQLReceivePort*<br /><br /> -設定**型**に*SQLReceivePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|SaveMessagePort|-設定**識別子**に*SaveMessagePort*<br /><br /> -設定**型**に*SaveMessagePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
  
### <a name="enter-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを入力し、ポートに接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|設定**メッセージ**に*PollingMessage*<br /><br /> 設定**操作**に*SQLReceivePort.TypedPolling.Request*|  
|SaveMessage|設定**メッセージ**に*PollingMessage*<br /><br /> 設定**操作**に*SaveMessagePort.TypedPolling.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されます。  
  
### <a name="add-a-biztalk-mapper"></a>BizTalk マッパーを追加します。  
 ポーリング メッセージ スキーマをスキーマにマップ、EmployeeDetails.xsd オーケストレーションには、BizTalk マッパーを追加する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを使用してこのマッパー EmployeeDetails.xsd スキーマにポーリング メッセージのスキーマをマップします。  
  

1.  BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
     **新しい項目の追加**ダイアログ ボックスで、左ペインで、**マップ ファイル**です。 右側のウィンドウから次のように選択します。**マップ**です。 など、マップの名前を指定`MapSchema.btm`です。 **[追加]** をクリックします。  
  
2.  送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
3.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、ポーリング メッセージのスキーマを選択します。 このトピックでは、Typed_Polling.TypedPolling_Employee を選択します。 **[OK]** をクリックします。  
  
4.  **送信元スキーマのルート ノード**ダイアログ ボックスで選択 TypedPolling とクリック**OK**です。  
  
5.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
6.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**EmployeeDetails のスキーマを選択します。 このトピックでは、Typed_Polling.EmployeeDetails を選択します。 **[OK]** をクリックします。  
  
7.  ポーリングのメッセージの送信元スキーマ、TypedPollingResultSet0 ノードとポーリング メッセージで返される要素を参照する後続のノードを展開します。 送信先スキーマのスキーマ内の異なる要素を参照してください EmployeeDetails ノードを展開してください。 このトピックのようにスキーマを割り当てることが必要です。  
  
    -   **Employee_ID**と**名前**ソース内のスキーマにマップする必要があります**Employee_Info**送信先スキーマです。  
  
    -   **Designation**と**Job_Description**ソース内のスキーマにマップする必要があります**Employee_Profile**送信先スキーマです。  
  
    -   **評価**と**給与**ソース内のスキーマにマップする必要があります**Employee_Performance**送信先スキーマです。  
  
     結合送信元スキーマ内の 1 つ以上のノードを送信先スキーマの 1 つのノードにマップするには、使用する必要があります、**文字列連結 functoid**です。 詳細[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]です。
  
8.  文字列連結 functoid を使用します。  
  
    1.  **ツールボックス**、ドラッグ、**文字列連結**functoid およびマッパー グリッドの上にドロップします。  
  
    2.  接続、 **Employee_ID**と**名前**functoid への送信元スキーマ内の要素。  
  
    3.  Functoid への接続、 **Employee_Info**送信先スキーマ内の要素。  
  
    4.  すべての要素をマップするには、この手順を繰り返します。 完成したマップは、次のようになります。  
  
         ![厳密に型指定されたポーリング スキーマ マップ](../../adapters-and-accelerators/adapter-sql/media/0a4a2608-3b84-4bac-9a16-512cf42c7525.gif "0a4a2608-3b84-4bac-9a16-512cf42c7525")  
  
    5.  マップを保存します。  
  
 オーケストレーションは、マッパーを作成する時点後で完了します。 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configure-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   物理 Wcf-custom を定義するか、WCF SQL 一方向の受信ポートです。 このポートは、ポートを指定するポーリング ステートメントを使用して SQL Server データベースをポーリングします。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。 受信ポートのバインドのプロパティを指定することを確認してください。  
  
        > [!IMPORTANT]
        >  指定するかどうかを確認、 **InboundID**接続 URI の一部として。 受信 ID は、スキーマの生成中に指定したものと同じである必要があります。  
  
        > [!IMPORTANT]
        >  デザイン時のバインドのプロパティを指定した場合、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または WCF SQL 受信ポート、必要なバインド プロパティを設定、によって作成されたバインド ファイルをインポートすることによって、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。  
  
        |プロパティのバインド|値|  
        |----------------------|-----------|  
        |**InboundOperationType**|これを設定するかどうかを確認**TypedPolling**です。|  
        |**PolledDataAvailableStatement**|これは、スキーマの生成中に指定した同じ SQL ステートメントを指定することを確認します。<br /><br /> `SELECT COUNT(*) FROM Employee`|  
        |**PollingStatement**|これは、スキーマの生成中に指定した同じポーリング ステートメントを指定することを確認します。<br /><br /> `SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000`|  
  
         異なるバインディングのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
        > [!NOTE]
        >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧め、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 サービスを追加することで、Wcf-custom または WCF SQL の構成中に動作の受信ポートを行うことができます。 サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクションのタイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)です。  
  
    -   アダプターがメッセージをドロップする場所の FILE 送信ポートを定義します。 この送信ポートは、ポーリング メッセージをマッピングする EmployeeDetails.xsd スキーマに準拠したメッセージをオーケストレーションで作成したマップを使用してもします。 マップを使用する FILE 送信ポートを構成するのには、次の手順を実行します。  
  
        1.  FILE 送信ポートを作成します。  
  
        2.  送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**送信マップ**です。 右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**MapSchema**です。 **[OK]** をクリックします。  
  
             ![FILE 送信ポートの送信マップを構成する](../../adapters-and-accelerators/adapter-sql/media/831c9aee-fd97-466f-9270-3b04dbccd9fe.gif "831c9aee-fd97-466f-9270-3b04dbccd9fe")  
  
## <a name="start-the-application"></a>アプリケーションを開始します。  
 SQL Server データベースからメッセージを受信する BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   Wcf-custom または WCF SQL 一方向受信ポートを指定されたステートメントを使用して SQL Server データベースをポーリングする、 **PollingStatement**バインディング プロパティが実行されています。  
  
-   ポーリング メッセージを EmployeeDetails スキーマにマップされます、FILE 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="execute-the-operation"></a>操作を実行します。  
 アプリケーションを実行した後、次の一連のアクションが実行と同じ順序で。  
  
-   アダプターの実行、 **PolledDataAvailableStatement**従業員のテーブルが表示され、テーブルにポーリングのレコードがあることを決定します。  
  
-   アダプターでは、ポーリング ステートメントを実行します。 ポーリング ステートメントと SELECT ステートメントおよびストアド プロシージャは、アダプターは、他の後に 1 つのすべてのステートメントを実行します。  
  
    -   アダプターは、最初は Employee テーブルのすべてのレコードを返す SELECT ステートメントを実行します。  
  
    -   アダプターは、EmployeeHistory テーブルには Employee テーブルからすべてのデータを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。 このストアド プロシージャは、任意の値を返しません。  
  
    -   アダプターは、Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。 このストアド プロシージャでは、挿入したレコードの従業員 ID を返します。  
  
     ポーリング ステートメントが実行され、メッセージを受信した、ポーリング メッセージは、ファイル送信ポートに送信を取得します。 ここでは、送信マップ (**MapSchema**) EmployeeDetails スキーマにポーリング メッセージを送信ポートのマップのように構成し、ファイルの場所にメッセージを削除します。 メッセージには、次のようになります。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <EmployeeDetails xmlns="http://Typed_Polling.EmployeeDetails">  
      <Employee_Info>10751John</Employee_Info>   
      <Employee_Profile>TesterManagesTesting</Employee_Profile>   
      <Employee_Performance>100000</EmployeePerformance>  
    </EmployeeDetails>  
    ```  
  
     前の応答で Employee_Info 要素に従業員 ID (10751) と従業員の名前 (John) の組み合わせが含まれていることがわかります。 その他の要素には、オーケストレーションの一部として作成したマッパーでマップの組み合わせも含まれます。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]はポーリングから受信ポートを明示的に無効にするまで引き続き、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
 [BizTalk Server と SQL アダプタを使用して SQL サーバーにポーリング](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)