---
title: BizTalk Server を使用して SQL Server からのポーリングに基づいたデータ変更メッセージを厳密に型指定の受信 |Microsoft Docs
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
ms.openlocfilehash: 5454a20e087a643acb6f2b0bc9735eae6d29b996
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976259"
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server からのポーリングに基づいたデータ変更メッセージを厳密に型指定の受信します。
構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server から厳密に型指定されたポーリング メッセージを受信します。 データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。 ポーリング ステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。  
  
 厳密に型指定されたポーリングは、ポーリング メッセージ内の要素を他の任意のスキーマにマップするシナリオで使用する必要があります。 マップするスキーマは、SQL Server で別の操作の可能性があります。 たとえば、別のテーブルで挿入操作のスキーマにポーリング メッセージの特定の要素をマップする可能性があります。 そのため、ポーリング メッセージ内の値は、挿入操作のパラメーターとして機能します。 単純なシナリオでは、だけ情報を格納するスキーマ ファイルを厳密に型指定されたポーリング メッセージのスキーマをマップする可能性があります。  
  
> [!IMPORTANT]
>  1 つの BizTalk アプリケーションでは、複数のポーリング操作を必要するかどうか、指定する必要あります、 **InboundID**接続して一意の URI の一部として接続プロパティです。 一意接続 URI を複数作成できます、同じデータベースまたはデータベースでも同じテーブルをポーリングするポートを受信します。 詳細については、[受信ポーリング メッセージ間で複数受信ポートから Biztalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)を参照してください。  
  
 アダプターが厳密に型指定されたポーリングをサポートする方法の詳細については、[のポーリング サポート](https://msdn.microsoft.com/library/dd788416.aspx)を参照してください。 メッセージのスキーマを厳密に型指定されたポーリングの詳細については、[Polling 操作と TypedPolling 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)を参照してください。  
  
## <a name="how-this-topic-demonstrates-strongly-typed-polling"></a>このトピックの「厳密に型指定されたポーリングしていますか  
 このトピックでは、厳密に型指定されたポーリングを使用してポーリング メッセージを別のスキーマにマップする方法を示します。 このトピックでは、BizTalk プロジェクトを作成し、スキーマを生成する方法を示しています。 **TypedPolling**操作。 スキーマを生成する前に**TypedPolling**操作では、次を行う必要があります。  
  
- 指定する必要があります、 **InboundID**接続 URI の一部として。  
  
- ポーリング ステートメントを指定する必要があります、 **PollingStatement**プロパティをバインドします。  
  
  ポーリング ステートメントの一部として、次の操作を実行します。  
  
- Employee テーブルからすべての行を選択します。  
  
- ストアド プロシージャ、EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。  
  
- Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。 この手順は、従業員の名前、表記、および給与をパラメーターとして受け取ります。  
  
  これらの操作を実行するは、次を指定する必要があります、 **PollingStatement**プロパティをバインドします。  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 スキーマを生成するため、 **TypedPolling**操作、スキーマは厳密に型指定され、ポーリング メッセージに含まれるすべての要素が含まれています。  
  
 同じ BizTalk プロジェクトの一環として、たとえば EmployeeDetails.xsd 別のスキーマ ファイルを追加します。 EmployeeDetails.xsd のスキーマには、次のようになります。  
  
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
  
 BizTalk マッパーは、EmployeeDetails.xsd スキーマ内の要素には、Employee テーブル (ポーリング メッセージとして受信済み) からの要素をマップするプロジェクトに追加します。 マップの一部として、ポーリング メッセージから要素を 1 つまたは複数を組み合わせるし、EmployeeDetails スキーマ内の単一の要素にマップします。 使用して行うことができます、**文字列連結**functoid。  
  
 最後に、BizTalk プロジェクトの一部として EmployeeDetails.xsd スキーマに準拠しているファイルは、ファイル送信ポートに削除されます。  
  
## <a name="configure-typed-polling-with-the-sql-adapter-binding-properties"></a>型指定されたポーリングを SQL アダプターのプロパティのバインド構成します。  
 次の表にまとめたものです、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティのデータ変更メッセージを受信するアダプターを構成するために使用します。 他にも、 **PollingStatement**バインド プロパティでは、すべて、他のバインド プロパティこのセクションに記載が必要で受信ポートを構成するときに、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 指定する必要があります、 **PollingStatement**プロパティのバインドのスキーマを生成する前に、 **TypedPolling**操作。  
  
> [!NOTE]
>  型指定されたポーリングは、指定する必要があります、 **PollingStatement**スキーマの生成中にプロパティをバインドします。 必須しないにもかかわらず、スキーマの生成中に他のバインドのプロパティもを指定することができます。 ポートのバインド ファイルをバインドのプロパティを指定する場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部にもバインドのプロパティで指定する値が含まれているが生成されます。 後でこのバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または WCF SQL を作成する管理コンソールの受信ポート。 バインド ファイルを使用してポートを作成する方法の詳細については、[SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)を参照してください。  
  
|         プロパティのバインド         |                                                                                                                                                                                                                                                                                                   説明                                                                                                                                                                                                                                                                                                    |
|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                                                  実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。 既定値は**ポーリング**します。 設定を厳密に型指定されたポーリング メッセージを受信する**TypedPolling**します。                                                                                                                                                                                                   |
| **PolledDataAvailableStatement** |                                                                                                                                                 すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。 SQL ステートメントが指定した行を使用できる場合のみ、 **PollingStatement**プロパティのバインドが実行されます。                                                                                                                                                 |
|   **PollingIntervalInSeconds**   |                                                                                   秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔は、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプターは、残りの時間間隔での待機します。                                                                                    |
|       **PollingStatement**       | SQL Server データベースのテーブルをポーリングする SQL ステートメントを指定します。 単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定することができます。 既定値は null です。 値を指定する必要があります**PollingStatement**ポーリングを有効にします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。 セミコロンで区切られた SQL ステートメントの任意の数を指定できます。<br /><br /> **重要:** の**TypedPolling**メタデータを生成する前にこのバインドのプロパティを指定する必要があります。 |
|      **PollWhileDataFound**      |                                                                                      指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**データがポーリングされるテーブルで使用できる場合は、プロパティをバインドします。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。 既定値は**false**します。                                                                                       |
  
 これらのプロパティの詳細については、[for SQL Server アダプターのバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。 使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server をポーリングするには、さらに読み進める。  
  
## <a name="how-to-receive-strongly-typed-data-change-messages-from-the-sql-server-database"></a>SQL Server データベースからデータの変化を厳密に型指定されたメッセージを受信する方法  
 SQL Server データベースを使用して、操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)します。 これらのタスクは厳密に型指定のデータ変更メッセージを受信するアダプターを構成するには。  
  
1. BizTalk プロジェクトを作成しのスキーマを生成し、 **TypedPolling**操作。 指定する必要があります、 **InboundID**接続プロパティと**PollingStatement**スキーマの生成中にプロパティをバインドします。 たとえば、次のよう受信 ID が指定された URI の接続。  
  
   ```  
   mssql://mysqlserver//mysqldatabase?InboundID=mydatabaseId  
   ```  
  
2. SQL Server データベースからメッセージを受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. SQL Server データベースからメッセージを受信して、フォルダーに保存するオーケストレーションを作成します。  
  
4. BizTalk プロジェクトで EmployeeDetails.xsd など、スキーマを追加します。  
  
5. ポーリング メッセージのスキーマをスキーマにマップ EmployeeDetails.xsd BizTalk マッパーを追加します。  
  
6. ビルドし、BizTalk プロジェクトを配置します。  
  
7. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
   > [!IMPORTANT]
   >  受信のポーリングのシナリオは、Wcf-custom の一方向常に構成する必要があります。 または WCF SQL 受信ポート。 Wcf-custom または WCF-SQL の双方向受信ポートの受信操作はサポートされていません。  
  
8. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル TypedPolling、このトピックの「に基づいてが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、[SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)を参照してください。  
  
## <a name="generate-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、 **TypedPolling**操作。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法の詳細について。 スキーマを生成するときに、次のタスクを実行します。  
  
1.  指定、 **InboundID**接続 URI を指定するときにプロパティを接続します。 このトピックでは、指定することができます、 **InboundID**として**従業員**します。 接続 URI の詳細については、[SQL Server の接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)を参照してください。  
  
2.  値を指定、 **PollingStatement**プロパティをバインドします。 このバインドのプロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。  
  
     バインドのプロパティを指定する方法については、[SQL アダプタのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)を参照してください。  
  
3.  コントラクトの種類を選択します。**サービス (受信操作)** します。  
  
4.  スキーマの生成、 **TypedPolling**操作。  
  
## <a name="define-messages-and-message-types"></a>メッセージとメッセージ定義の種類  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションからメッセージをリンクする必要があります。  
  
 このトピックでは、SQL Server データベースからメッセージを受信する 1 つのメッセージを作成する必要があります。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  
  
#### <a name="create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマへのリンク  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  
  
2.  開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。 をクリックして**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**PollingMessage**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選び*Typed_Polling.TypedPolling_Employee.TypedPolling*ここで、 *Typed_Polling* BizTalk の名前を指定しますプロジェクトです。 *TypedPolling_Employee*に対して生成されたスキーマには、 **TypedPolling**操作。|  
  
## <a name="set-up-the-orchestration"></a>オーケストレーションをセットアップします。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SQL Server データベースからのポーリング ベースのデータ変更メッセージを受信します。 このオーケストレーションでは、アダプターは、指定されたポーリング ステートメントのポーリング メッセージを受信します。 BizTalk マッパーは、ポーリングのメッセージ スキーマを EmployeeDetails.xsd スキーマにマップします。 マップされたメッセージはファイルの場所に保存されます。 SQL Server データベースから厳密に型指定されたポーリング メッセージを受信するための一般的なオーケストレーションが含まれます。  
  
- 受信図形と送信図形を SQL Server からメッセージを受信し、それぞれ、ファイルのポートに送信します。  
  
- 一方向の受信ポートを SQL Server からメッセージを受信します。  
  
  > [!IMPORTANT]
  >  常に設定する必要があります、ポーリングの受信シナリオの一方向の受信ポート。 双方向受信ポートは受信操作のサポートされていません。  
  
- SQL Server データベースからフォルダーにポーリング応答を送信する一方向の送信ポート。  
  
- ポーリング メッセージのスキーマを他の任意のスキーマにマップする BizTalk マッパー。  
  
  サンプル オーケストレーションでは、次の項目に似ています。  
  
  ![オーケストレーションの厳密に&#45;ポーリングを型指定された](../../adapters-and-accelerators/adapter-sql/media/1db03859-b7f8-470c-9158-2be4da0b45ae.gif "1db03859-b7f8-470c-9158-2be4da0b45ae")  
  
### <a name="add-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br /><br /> -設定**アクティブ**に*は True。*|  
|SaveMessage|Send|-設定**名前**に*SaveMessage*|  
  
### <a name="add-ports"></a>ポートを追加します。  
 論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|SQLReceivePort|-設定**識別子**に*SQLReceivePort*<br /><br /> -設定**型**に*SQLReceivePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|SaveMessagePort|-設定**識別子**に*SaveMessagePort*<br /><br /> -設定**型**に*SaveMessagePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
  
### <a name="enter-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを入力し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|設定**メッセージ**に*PollingMessage*<br /><br /> 設定**操作**に*SQLReceivePort.TypedPolling.Request*|  
|SaveMessage|設定**メッセージ**に*PollingMessage*<br /><br /> 設定**操作**に*SaveMessagePort.TypedPolling.Request*|  
  
 これらのプロパティを指定した後は、メッセージの構築図形とポートが接続されます。  
  
### <a name="add-a-biztalk-mapper"></a>BizTalk マッパーを追加します。  
 ポーリングのメッセージ スキーマを EmployeeDetails.xsd スキーマにマップするオーケストレーションを BizTalk マッパーを追加する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、ポーリング メッセージのスキーマを EmployeeDetails.xsd スキーマにマップするこのマッパーが使用されます。  
  

1. BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
    **新しい項目の追加**ダイアログ ボックスで、左側のウィンドウから**マップ ファイル**します。 右側のウィンドウから次のように選択します。**マップ**します。 マップの名前を指定します。`MapSchema.btm`します。 **[追加]** をクリックします。  
  
2. 送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。  
  
3. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、ポーリング メッセージのスキーマを選択します。 このトピックでは、Typed_Polling.TypedPolling_Employee を選択します。 **[OK]** をクリックします。  
  
4. **送信元スキーマのルート ノード**ダイアログ ボックスで選択 TypedPolling とクリック**OK**。  
  
5. 送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。  
  
6. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**EmployeeDetails のスキーマを選択します。 このトピックでは、Typed_Polling.EmployeeDetails を選択します。 **[OK]** をクリックします。  
  
7. ポーリングのメッセージの送信元スキーマ、TypedPollingResultSet0 ノードとポーリング メッセージで返される要素を確認する後続のノードを展開します。 送信先スキーマ ノードを展開 EmployeeDetails をスキーマ内のさまざまな要素を参照してください。 このトピックでは、このような方法でスキーマを割り当てることが必要です。  
  
   - **Employee_ID**と**名前**にマップする必要があります、ソース スキーマ**Employee_Info**送信先スキーマです。  
  
   - **指定**と**Job_Description**にマップする必要があります、ソース スキーマ**Employee_Profile**送信先スキーマです。  
  
   - **評価**と**給与**にマップする必要があります、ソース スキーマ**Employee_Performance**送信先スキーマです。  
  
     送信元スキーマの 1 つ以上のノードを結合し、送信先スキーマの 1 つのノードにマップを使用する必要があります、**文字列連結 functoid**します。 詳細[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]します。
  
8. 文字列連結 functoid を使用します。  
  
   1.  **ツールボックス**、ドラッグ、**文字列連結**functoid およびマッパー グリッドの上にドロップします。  
  
   2.  接続、 **Employee_ID**と**名前**functoid への送信元スキーマ内の要素。  
  
   3.  Functoid を接続、 **Employee_Info**送信先スキーマ内の要素。  
  
   4.  マップするすべての要素には、次の手順を繰り返します。 完成したマップは、次のようになります。  
  
        ![厳密に型指定されたポーリング スキーマ マップ](../../adapters-and-accelerators/adapter-sql/media/0a4a2608-3b84-4bac-9a16-512cf42c7525.gif "0a4a2608-3b84-4bac-9a16-512cf42c7525")  
  
   5.  マップを保存します。  
  
   マッパーに作成した後、オーケストレーションが完了しました。 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。
  
## <a name="configure-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)を参照してください。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - WCF-SQL の一方向受信ポートまたは物理 Wcf-custom を定義します。 このポートは、ポートを指定するポーリング ステートメントを使用して SQL Server データベースをポーリングします。 ポートを作成する方法については、[SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)を参照してください。 受信ポートのバインドのプロパティを指定することを確認します。  
  
    > [!IMPORTANT]
    >  指定するかどうかを確認、 **InboundID**接続 URI の一部として。 受信 ID は、スキーマの生成中に指定したものと同じである必要があります。  
    > 
    > [!IMPORTANT]
    >  デザイン時のバインドのプロパティが指定されている場合は、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または WCF-SQL によって作成されたバインド ファイルをインポートすることによって、必要なバインドのプロパティを設定すると、ポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 詳細については、[SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)を参照してください。  
  
    |プロパティのバインド|値|  
    |----------------------|-----------|  
    |**InboundOperationType**|これを設定することを確認**TypedPolling**します。|  
    |**PolledDataAvailableStatement**|これは、スキーマの生成中に指定した同じ SQL ステートメントを指定することを確認します。<br /><br /> `SELECT COUNT(*) FROM Employee`|  
    |**PollingStatement**|これは、スキーマの生成中に指定した同じポーリング ステートメントを指定することを確認します。<br /><br /> `SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000`|  
  
     異なるバインディング プロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。  
  
    > [!NOTE]
    >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧めします。、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 ように、サービスを追加することで、Wcf-custom または WCF SQL を構成するときに動作の受信ポートを行うことができます。 サービスの動作を追加する方法については、[トランザクション分離レベルの構成と SQL を使用したトランザクション タイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)を参照してください。  
  
  - アダプターがメッセージをドロップする場所の FILE 送信ポートを定義します。 この送信ポートは、ポーリング メッセージを EmployeeDetails.xsd スキーマに準拠したメッセージにマップするオーケストレーションで作成したマップを使用してもします。 マップを使用する FILE 送信ポートを構成するのには、次の手順を実行します。  
  
    1.  ファイル送信ポートを作成します。  
  
    2.  送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**送信マップ**します。 右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**MapSchema**。 **[OK]** をクリックします。  
  
         ![FILE 送信ポートの送信マップの構成](../../adapters-and-accelerators/adapter-sql/media/831c9aee-fd97-466f-9270-3b04dbccd9fe.gif "831c9aee-fd97-466f-9270-3b04dbccd9fe")  
  
## <a name="start-the-application"></a>アプリケーションを起動します  
 SQL Server データベースからメッセージを受信する BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)を参照してください。
  
 この段階で、ことを確認します。  
  
-   Wcf-custom または WCF SQL 一方向受信ポートで、指定されたステートメントを使用して SQL Server データベースをポーリングします**PollingStatement**プロパティ、バインドが実行されています。  
  
-   ポーリング メッセージを EmployeeDetails スキーマにマッピングする、ファイル送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="execute-the-operation"></a>操作を実行します  
 アプリケーションを実行した後、次の一連のアクションに、同じシーケンスを実行します。  
  
- アダプターの実行、 **PolledDataAvailableStatement**従業員テーブルし、テーブルがポーリングのレコードを決定します。  
  
- アダプターは、ポーリング ステートメントを実行します。 ポーリング ステートメントと SELECT ステートメントおよびストアド プロシージャは、アダプターは、その他の後に 1 つのすべてのステートメントを実行します。  
  
  - アダプターは、まず、従業員テーブル内のすべてのレコードを返す SELECT ステートメントを実行します。  
  
  - アダプターは、EmployeeHistory テーブルに、Employee テーブルからすべてのデータを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。 このストアド プロシージャでは、任意の値は返されません。  
  
  - アダプターは、Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。 このストアド プロシージャは、挿入されたレコードの従業員 ID を返します。  
  
    ポーリング ステートメントが実行され、メッセージの受信、ポーリング メッセージは、ファイル送信ポートに送信を取得します。 ここでは、送信マップ (**MapSchema**) EmployeeDetails スキーマにポーリング メッセージを送信ポートのマップで構成されているし、ファイルの場所にメッセージを削除します。 メッセージには、次のようになります。  
  
  ```  
  <?xml version="1.0" encoding="utf-8" ?>   
  <EmployeeDetails xmlns="http://Typed_Polling.EmployeeDetails">  
    <Employee_Info>10751John</Employee_Info>   
    <Employee_Profile>TesterManagesTesting</Employee_Profile>   
    <Employee_Performance>100000</EmployeePerformance>  
  </EmployeeDetails>  
  ```  
  
   前の応答には、従業員 ID (10751) と従業員の名前 (John) の組み合わせには Employee_Info 要素が含まれているして確認できます。 その他の要素には、オーケストレーションの一部として作成したマッパーでマップの組み合わせも含まれます。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリングからの受信ポートを明示的に無効にするまでは引き続き、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)を参照してください。
  
## <a name="see-also"></a>参照  
 [BizTalk Server を SQL アダプターを使用して SQL Server をポーリング](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)