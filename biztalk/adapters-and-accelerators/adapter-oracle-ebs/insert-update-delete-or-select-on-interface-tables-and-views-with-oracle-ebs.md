---
title: 挿入、更新、削除、またはインターフェイス テーブルと Oracle E-business suite のインターフェイス ビューの選択 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85f42431-80fb-49be-86d1-bb21eee5e4f5
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3ea88118efa8ef3585ff1386d613ce527b1959
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375470"
---
# <a name="insert-update-delete-or-select-on-interface-tables-and-interface-views-with-oracle-e-business-suite"></a>挿入、更新、削除、またはインターフェイス テーブルと Oracle E-business suite のインターフェイス ビューに対する select
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェス Insert などの標準的な操作のセットをインターフェイス上の Update、Delete、Select のテーブルし、ビューします。 このトピックでは、アダプターを使用してこれらの操作を実行する方法について説明します。 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。[インターフェイス テーブルとインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)します。 これらの操作用の SOAP メッセージの構造については、次を参照してください。 [Insert、Update、Delete、および選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)します。  

> [!NOTE]
>  アダプターでは、テーブルおよび BLOB、CLOB、NCLOB、BFILE などの大規模なデータ型を含むビューの特定の操作も公開します。 このような操作の詳細については、次を参照してください。[インターフェイス テーブル、インターフェイス ビュー、テーブル、ビューを含む LOB データを操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)します。 BizTalk Server を使用して大規模なデータ型を持つテーブルおよび列に対する操作を実行する方法の詳細については、次を参照してください。 [WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルに対する操作を完了](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)します。  

## <a name="how-to-perform-basic-operations-on-oracle-e-business-suite"></a>Oracle E-business Suite に対する基本操作を実行する方法  
 使用して Oracle E-business Suite での操作を実行する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)します。 これらのタスクは Oracle E-business Suite で Insert、Update、Delete、またはテーブルとビューに対する Select 操作を実行するのには。  

1. BizTalk プロジェクトを作成し、インターフェイス テーブルまたはビューを起動する操作のスキーマを生成します。  

2. Oracle E-business Suite からメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  

3. インターフェイス テーブルまたはビューに対する操作を呼び出すオーケストレーションを作成します。  

4. ビルドし、BizTalk プロジェクトを配置します。  

5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  

6. BizTalk アプリケーションを起動します。  

   このトピックでは、これらのタスクを実行する手順を説明します。  

## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、Oracle E-business Suite で AR_ARCHIVE_PURGE_INTERIM インターフェイス テーブルにレコードを挿入して基本的な Insert、Update、Delete、または Select 操作を実行する方法を示します。 このインターフェイスのテーブルが表示されます、 **Receivables** Oracle E-business Suite でのアプリケーション。  

 レコードを挿入する方法を示すためには、AR_ARCHIVE_PURGE_INTERIM テーブルの挿入操作のスキーマが生成されます。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  

## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは通常、対応するスキーマによって定義された型の変数です。 オーケストレーションのメッセージを作成し、前の手順で生成したスキーマにリンクする必要がありますようになりました。  

#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  

1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  

2.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  

3.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  

4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  

5.  **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *InsertInterfaceTable.OracleEBSBinding.Insert*InsertInterfaceTable は、BizTalk プロジェクトの名前です。 OracleEBSBinding は AR_ARCHIVE_PURGE_INTERIM テーブルに対する挿入操作の生成されたスキーマを示します。|  

6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *InsertInterfaceTable.OracleEBSBinding.InsertResponse*します。|  

## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle E-business Suite での操作を実行するためです。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]がこのメッセージを使用して、Oracle E-business Suite に渡します。 Oracle E-business Suite からの応答は、別の場所に保存されます。 Oracle データベースでの基本的なテーブルの操作を実行するための一般的なオーケストレーションが含まれます。  

- Oracle データベースにメッセージを送信し、応答を受信する図形を送受信します。  

- Oracle データベースに送信する要求メッセージを受信するポートは一方向の受信します。  

- 双方向の送信要求メッセージを Oracle データベースし、応答の受信を送信するポート。  

- フォルダーに Oracle データベースからの応答を送信する一方向の送信ポート。  

  選択操作のサンプルのオーケストレーションには、次のようになります。  

  ![インターフェイス テーブルにデータを挿入するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/8a4508c5-9949-4043-9de5-d1226db8117b.gif "8a4508c5-9949-4043-9de5-d1226db8117b")  

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
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  

### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形は、メッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  

|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.Insert.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Insert.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Insert.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.Insert.Request*|  

 これらのプロパティを指定したら、メッセージの構築図形とポートを接続すると、し、オーケストレーションが完了します。  

 BizTalk ソリューションをビルドし、BizTalk Server に展開する必要がありますようになりました。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。  

## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。  

 アプリケーションを構成する必要があります。  

- アプリケーションのホストを選択します。  

- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  

  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、Oracle E-business Suite に送信します。  

  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが Oracle E-business Suite からの応答を含む応答メッセージをドロップする場所の場所を定義します。  

  - Oracle E-business Suite にメッセージを送信する物理 Wcf-custom または Wcf-oracleebs 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、次を参照してください[、Oracle E-business アダプターを物理ポート バインドを手動で構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)  

     インターフェイス テーブル、またはインターフェイスで操作を実行するビューを使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]操作が呼び出される適切なアプリケーションのコンテキストを設定する必要があります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストのいずれかの操作を指定するには、特定のバインド プロパティを提供します。 インターフェイス テーブルで演算を実行するために使用する Wcf-custom または Wcf-oracleebs ポートでは、これらのバインド プロパティを設定する必要があります。  

    - 場合、 **ClientCredentialType**に設定されているプロパティのバインド**データベース**アプリケーションのコンテキストを設定するのには、次のバインド プロパティを指定する必要があります。  


      |        プロパティのバインド         |                                                                                                                                                                                                                                                                                     値                                                                                                                                                                                                                                                                                     |
      |---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |       **OracleUserName**        | Oracle E-business Suite ユーザーの名前を指定します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力した値の大文字と小文字は保持されません、 **OracleUserName** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準の規則を使用して Oracle E-business Suite にユーザー名が渡される\*とします。 ただし、保持するユーザー名の大文字と小文字の場合、または特殊文字を含むユーザー名を入力する場合は、二重引用符で囲まれた値を指定する必要があります。 |
      |       **OraclePassword**        |   Oracle E-business Suite ユーザーのパスワード。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力した値の大文字と小文字は保持されません、 **OraclePassword** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準の規則を使用して Oracle E-business Suite にパスワードが渡される\*とします。 ただし、保持するパスワードの大文字と小文字の場合、または特殊文字を含むパスワードを入力する場合は、二重引用符で囲まれた値を指定する必要があります。    |
      | **OracleEBSResponsibilityName** |                                                                                                                                                                                                                                                     Oracle E-business Suite ユーザーに関連付けられた役割。                                                                                                                                                                                                                                                      |


    - 場合、 **ClientCredentialType**に設定されているプロパティのバインド**EBusiness**、する必要がありますを指定していない Oracle E-business 資格情報の接続を確立中にします。 このような場合、値を指定する必要がありますのみ、 **OracleEBSResponsibilityName**プロパティをバインドします。  

      異なるバインディング プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。 アダプターがアプリケーションのコンテキストの設定がサポートする方法の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  

    > [!NOTE]
    >  アプリケーションのコンテキストを設定するには、バインドのプロパティを指定するか、メッセージによって公開されるコンテキスト プロパティを設定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 バインドのプロパティを設定する方法については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)します。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定する方法については、次を参照してください。 [Oracle E-business Suite でのアプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)します。  
    > 
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。 詳細については、次を参照してください。 [Oracle E-business Suite へのポートのバインド ファイルを物理ポートのバインドを使用して、を構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)します。  

## <a name="starting-the-application"></a>アプリケーションの起動  
 AR_ARCHIVE_PURGE_INTERIM インターフェイス テーブルにレコードを挿入するための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。  

 この段階で、ことを確認します。  

-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  

-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  

-   Wcf-custom または Wcf-oracleebs Oracle E-business Suite へのメッセージが実行されている送信ポートを送信します。  

-   操作の BizTalk オーケストレーションが実行されています。  

## <a name="executing-the-operation"></a>操作の実行  
 ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。 要求メッセージのスキーマは、以前に生成する挿入操作のスキーマに準拠する必要があります。 たとえば、AR_ARCHIVE_PURGE_INTERIM インターフェイス テーブルからすべてのレコードを選択する要求メッセージには。  

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

 この要求メッセージは AR_ARCHIVE_PURGE_INTERIM インターフェイス テーブルにレコードを挿入します。 参照してください[Insert、Update、Delete、および選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)Oracle E-business Suite の使用に関する基本的な DML 操作を実行するための要求メッセージ スキーマの詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  

 単純なデータ列の場合のように、前の要求メッセージで使用することも、 **InlineValue**属性。 InlineValue 属性の詳細については、挿入操作の説明を参照してください。[インターフェイス テーブルとインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)します。  

 たとえば、インラインの値を持つ前の要求メッセージは、次のようになります。  

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

 この要求メッセージで TRX_ID 列の値は、別のテーブルから取得されます。 そのため、TRX_ID の値として「001」を指定すると、場合でも、InlineValue 属性の指定した SELECT ステートメントの値はテーブルに挿入を取得します。  

 オーケストレーションはメッセージを使用し、Oracle E-business Suite に送信します。 Oracle E-business Suite からの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、前の要求メッセージの Oracle E-business Suite からの応答には。  

```  
<?xml version="1.0" encoding="utf-8" ?>   
<InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR/AR_ARCHIVE_PURGE_INTERIM">  
  <InsertResult>1</InsertResult>   
</InsertResponse>  
```  

 応答には、テーブルに挿入される行の数が含まれています。  

## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business suite アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)します。  

## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)