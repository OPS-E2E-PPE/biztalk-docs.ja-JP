---
title: 参照、検索、および SQL アダプターを使用して SQL 操作のメタデータを取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdd5ca6f-30ff-4d32-a656-bbd54b9d072e
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30f76d18f79206fff217ab080c9e2b052aa4f73b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971099"
---
# <a name="browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter"></a>参照、検索、および SQL アダプターを使用して SQL 操作のメタデータを取得
このセクションを使用する方法について説明します、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 これらを使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ことができます、コンポーネント。  
  
- メタデータを取得する対象の操作を参照します。  
  
- メタデータを取得する対象の操作を検索します。  
  
- 選択した操作のメッセージ スキーマを追加し、ポートのバインドの構成ファイル、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトを使用する場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
- 使用する場合に、BizTalk 以外のプログラミング プロジェクトに WCF クライアント クラスまたは選択した操作と構成ファイル (app.config) の WCF サービス コントラクト (インターフェイス) を追加、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、3 つすべてのコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 参照、検索、またはターゲットの操作のメタデータを取得する前に、SQL Server に接続する必要があります。 使用する場合は、SQL Server に接続する方法については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Consume Adapter Service アドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)します。  
  
## <a name="browsing-for-operations"></a>操作の参照  
 使用することができます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を SQL Server で実行できる操作を送信および受信の参照を使用して、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
### <a name="outbound-operations"></a>送信操作  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]により、クライアントは、次の送信操作を実行します。  
  
- 挿入、更新プログラムを選択およびテーブルとビューで操作を削除します。  
  
- テーブルとビューで < column_name > の操作を設定します。 この操作は、varchar (max)、nvarchar (max)、または varbinary (max) 列を含むテーブルで公開されます。 このような操作は、ラージ オブジェクトのストリーミングを有効にします。  
  
- ストアド プロシージャ、弱いと厳密に型指定された操作としての両方。  
  
- スカラーおよびテーブルの操作として関数を値です。  
  
  アダプターで、汎用的な送信操作をなど、公開も**ExecuteReader**、 **ExecuteScalar**、および**ExecuteNonQuery**ルート レベルにします。  
  
### <a name="inbound-operations"></a>受信操作  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]により、クライアントは、次の受信操作を実行します。  
  
-   **ポーリング**SQL Server からのポーリング ベースのデータ変更メッセージを受信する操作。 この操作で受信したメッセージは厳密に型指定されません。  
  
-   **TypedPolling** SQL Server からのポーリング ベースのデータ変更メッセージを受信する操作。 この操作で受信したメッセージは厳密に型指定します。  
  
-   **通知**から SQL Server クエリ通知を受信する操作。  
  
> [!NOTE]
>  アダプターもサポートしています、 **XmlPolling** SELECT ステートメントと FOR XML 句を含むストアド プロシージャを使用して SQL Server データベースでのポーリングを有効にする操作を受信します。 ただし、アダプターは、この特定の受信操作を公開しません。 XmlPolling の詳細については、[と FOR XML 句から BizTalk Server を使用した SQL SELECT ステートメントを使用してポーリング メッセージを受信](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)を参照してください。  
  
 これらの操作の詳細については、[アダプターを使用して SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)を参照してください。  
  
> [!NOTE]
>  使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、Windows インターフェイスを使用して、カテゴリと操作のノードを参照することができます。  
  
 参照メタデータの詳細については、[SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)を参照してください。  
  
##### <a name="to-browse-outbound-operations-on-sql-server"></a>SQL Server に対する送信操作を参照するには  
  
1. SQL Server に接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Consume Adapter Service アドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)手順についてはします。  
  
2. **コントラクト型を選択します**リスト、送信操作の選択の**クライアント (送信操作)** します。  
  
3. **カテゴリを選択**ボックスに接続する SQL Server データベースで使用できる成果物を一覧表示されます。 そのアーティファクトを使用可能な操作を表示するアイテムをクリックして、**利用可能なカテゴリと操作**ボックス。  
  
   > [!TIP]
   >  ツリー ビューにフォーカスがあるときに、アイテムの名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、**従業員**テーブル ノードを常にフォーカスを**テーブル**ノード、および入力`Employee`。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 ルート ノード (/) が選択されているし、ルート ノードの下で利用できる一般カテゴリ ノードが記載されて、**利用可能なカテゴリと操作**ボックス。  
  
    ![ルート レベルの操作とカテゴリで利用可能な](../../adapters-and-accelerators/adapter-sql/media/3eef7b99-da8e-4b98-8b14-8e48fd7b3801.gif "3eef7b99-da8e-4b98-8b14-8e48fd7b3801")  
  
   > [!NOTE]
   >  ルート レベルでは、ExecuteReader、ExecuteScalar、ExecuteNonQuery などの標準の SQL Server 操作を入手できます。 これらの操作の詳細については、[ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)を参照してください。  
  
4. SQL Server データベースで使用できる手順を表示するには、クリックして、**プロシージャ**ノード。 次の図に、**プロシージャ**でノードを選択、**カテゴリを選択** ボックスと対応する手順を次に、**ボックスの利用可能なカテゴリと操作**.  
  
    ![SQL Server でプロシージャの参照](../../adapters-and-accelerators/adapter-sql/media/e3b1a070-4077-4e4d-bfc7-558df9b8b9d5.gif "e3b1a070-4077-4e4d-bfc7-558df9b8b9d5")  
  
   > [!NOTE]
   >  同じ一覧にある手順のセット、**プロシージャ**で使用可能なノードも、 **Strongly-Typed プロシージャ**ノード。 違いはスキーマの生成方法にあります。 下の手順については、**プロシージャ**ノード、スキーマが弱い型指定されました。 ただし、対象のプロシージャの**Strongly-Typed プロシージャ**ノード、スキーマが厳密に型指定します。 厳密に型指定されたスキーマは、1 つの操作のスキーマを BizTalk プロジェクトを作成するときに、スキーマがデザイン時に使用可能なため、BizTalk マッパーを使用して別の操作にマップする場合に便利です。 厳密に型指定の手順では、プロシージャのスキーマは、応答メッセージの一部として実行時に受信されます。  
  
5. SQL Server データベース内のテーブルを表示するには、クリックして、**テーブル**ノード。 また、展開、**テーブル**ノード。  
  
6. テーブルでサポートされる操作を表示するには、テーブル名をクリックします。  
  
    次の図は、テーブルの一覧、**カテゴリを選択**ボックス。 **利用可能なカテゴリと操作**ボックスが選択されているテーブルでサポートされる操作を一覧表示されます。  
  
    ![SQL Server データベース テーブルの参照](../../adapters-and-accelerators/adapter-sql/media/3966f3b9-85a0-4354-8ed4-da5ae74c9885.gif "3966f3b9-85a0-4354-8ed4-da5ae74c9885")  
  
   > [!NOTE]
   >  SQL Server テーブルに列の型 varchar (max)、nvarchar (max)、および varbinary (max) が含まれている場合、アダプターには、列のデータを更新する特定の操作も公開します。 この操作の名前には、< column_name > が設定されます。 たとえば、テーブルの列の型 varchar (max)"Job_Description"の場合、操作の名前は"SetJob_Description"。  
  
7. SQL Server データベースのビューを表示する をクリックして、**ビュー**ノード。 また、展開、**ビュー**ノード。  
  
8. ビューでサポートされる操作を表示するには、ビュー名をクリックします。  
  
    次の図のビューの一覧を示しています、**カテゴリを選択**ボックス。 **利用可能なカテゴリと操作**ボックスは、選択したビューでサポートされる操作を一覧表示されます。  
  
    ![SQL Server データベース ビューの参照](../../adapters-and-accelerators/adapter-sql/media/67362fb2-35fb-4afb-8ff6-e519b26bd187.gif "67362fb2-35fb-4afb-8ff6-e519b26bd187")  
  
   > [!NOTE]
   >  ビューに列の型 varchar (max)、nvarchar (max)、および varbinary (max) が含まれている場合、アダプターには、列のデータを更新する特定の操作も公開します。 この操作の名前には、< column_name > が設定されます。 たとえば、テーブルの列の型 varchar (max)"Job_Description"の場合、操作の名前は"SetJob_Description"。  
  
9. SQL Server データベースで定義されているスカラー関数の一覧を表示する、**利用可能なカテゴリと操作**ボックスで、、**スカラー関数**ノード。  
  
     次の図に、**スカラー関数**でノードを選択、**カテゴリを選択** ボックスと対応する関数を次に、**利用可能なカテゴリと操作**ボックス。  
  
     ![SQL Server でのスカラー関数の参照](../../adapters-and-accelerators/adapter-sql/media/78b9f720-2cb2-44a8-b8cc-49e4fb608a1f.gif "78b9f720-2cb2-44a8-b8cc-49e4fb608a1f")  
  
10. テーブルの一覧を表示する値で SQL Server データベースで定義されている関数、**利用可能なカテゴリと操作**ボックスで、、**テーブル値関数**ノード。  
  
     次の図に、**テーブル値関数**でノードを選択、**カテゴリを選択** ボックスと対応する関数を次に、**利用可能なカテゴリと操作**ボックス。  
  
     ![SQL Server でのテーブル値関数の参照](../../adapters-and-accelerators/adapter-sql/media/b007059f-280e-40d7-9553-eca4216296f4.gif "b007059f-280e-40d7-9553-eca4216296f4")  
  
##### <a name="to-browse-inbound-operations-on-sql-server"></a>SQL Server での受信操作を参照するには  
  
1. SQL Server に接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Consume Adapter Service アドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)手順についてはします。  
  
2. **コントラクト型を選択します**一覧で、受信操作は、選択**サービス (受信操作)** します。  
  
3. サポートされているすべての受信操作、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]はルート ノードで利用できます。 使用可能な受信操作を表示するには、ルート ノード (/) をクリックします。  
  
    ![受信アダプターでサポートされている操作](../../adapters-and-accelerators/adapter-sql/media/133732c0-ca8f-4e57-8a70-ba4fb561a37b.gif "133732c0-ca8f-4e57-8a70-ba4fb561a37b")  
  
## <a name="searching-for-operations"></a>操作の検索  
 使用することができます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]SQL Server データベース内の特定の成果物を検索します。 SQL Server のメタデータを検索するときに、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
- 検索式では、ワイルドカードとエスケープ文字をサポートしています。  
  
- 検索操作を実行するノードのすぐ下にある検索を有効にします。 たとえば、テーブルを検索するをする必要があります検索する \Table 下。 複数レベルの検索がサポートされていません。  
  
  次の表に、成果物と、その解釈を検索するために使用できる特殊文字、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
|特殊文字|解釈|例|  
|-----------------------|--------------------|-------------|  
|_ (アンダースコア)|1 文字と一致します。|「A _」は、AB、AC、AD と一致します。|  
|%|0 個以上の文字と一致|「%」では、A、AB AC と一致します。|  
|[ ]|-% と _ の特別な意味をエスケープします。<br />-範囲または存在する文字のセットを指定します。|-[%] % が、"%"記号を含むすべての名前と一致します。<br />-[a ~ f] が間に (およびなど) に文字を含むすべての名前と一致する 'a' と 'f'。<br />-[abc] と 'a'、'b' 文字を含むすべての名前を一致して、'c'。|  
|[^]|範囲または存在しない文字のセットを指定します|-[^ a ~ f] 間 (およびなど) の文字が存在しないすべての名前と一致する 'a' と 'f'。<br />-[^ abc] 一致するすべての名前がない文字 'a '、'b'、'c' とします。|  
  
> [!NOTE]
>  エスケープ文字は、ワイルドカードではなく、通常の文字として、ワイルドカードを解釈することを示すために、ワイルドカード文字の前に配置する文字です。  
  
 詳細については、[SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)を参照してください。  
  
 SQL Server を使用してメタデータを検索する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、次の手順に従います。  
  
#### <a name="to-search-metadata-in-sql-server"></a>SQL Server でメタデータを検索するには  
  
1. SQL Server に接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Consume Adapter Service アドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)手順についてはします。  
  
2. **選択コントラクト型**一覧で、受信または送信の操作を検索するかどうかに基づく契約の種類を選択します。  
  
3. **カテゴリを選択**ボックスを検索する特定の成果物のカテゴリ ノードをクリックします。 たとえば、テーブルを検索するに次のようにクリックします。、**テーブル**ノード。  
  
4. **カテゴリで検索**ボックスに、特定の成果物を検索する検索式を入力します。 たとえば、名前に"Customer"を持つテーブルを検索するに次のように入力します。`%Customer%`します。  
  
   > [!NOTE]
   >  検索文字列が大文字小文字を区別します。  
  
5. 検索を開始するには、右矢印アイコンのボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件を満たすアイテムが一覧表示されます。  
  
    次の図には、名前に"Customer"が含まれている SQL Server テーブルが表示されます。  
  
    ![SQL Server でメタデータを検索](../../adapters-and-accelerators/adapter-sql/media/62c24ed3-f4e5-47de-8e8d-35af96e6c5ec.gif "62c24ed3-f4e5-47de-8e8d-35af96e6c5ec")  
  
## <a name="generating-schema-for-biztalk-projects"></a>BizTalk プロジェクトのスキーマを生成します。  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SQL Server のアイテムの選択したスキーマを生成します。 参照を呼び出したいアーティファクトの検索し、それらの成果物のスキーマを生成し、SQL Server に、スキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  そのカテゴリのサブ-ツリー内のすべての操作を取得するカテゴリ ノードを選択するなどを選択 (テーブルのすべての操作のスキーマの生成) をテーブル全体またはテーブル (たとえば、Insert および Delete) の特定の操作を選択にテーブルに対する操作のみのスキーマを生成します。 ノードの詳細については、[メタデータ ノード Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)を参照してください。  
  
#### <a name="to-generate-schema-for-sql-server-artifacts"></a>SQL Server のアイテムのスキーマを生成するには  
  
1. SQL Server に接続する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 参照してください[Consume Adapter Service アドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)手順についてはします。  
  
   > [!IMPORTANT]
   >  使用して操作を実行するためのスキーマを生成する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]設定する必要があります、 **EnableBizTalkCompatibilityMode**プロパティをバインド**True**します。 SQL Server データベースへの接続を確立中には、このバインドのプロパティを設定する必要があります。  
  
2. **選択コントラクト型**一覧で、受信または送信操作のスキーマを生成するかどうかに基づく契約の種類を選択します。  
  
3. メタデータを生成するカテゴリ ノードをクリックします。 たとえば、テーブルのメタデータを生成する場合は、クリックして**テーブル**します。  
  
4. カテゴリのノードを展開し、メタデータを生成する、そのノード内の特定の項目を選択します。 たとえば、"CustomerTable"テーブルに対する操作のメタデータを生成するには、展開、**テーブル**ノードをクリック**CustomerTable**します。  
  
5. **利用可能なカテゴリと操作**ボックスをクリックして、SQL Server で実行する操作を選択します。**追加**します。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。 たとえば、Insert と"CustomerTable"テーブルに対する Select 操作を実行する操作名をクリック**追加**します。  
  
    次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、選択した操作が一覧表示されます。  
  
    ![SQL Server からメタデータを取得](../../adapters-and-accelerators/adapter-sql/media/a6a95291-f6ed-46d1-bacc-2dfc27638117.gif "a6a95291-f6ed-46d1-bacc-2dfc27638117")  
  
    複数の操作のスキーマを生成する場合は、いくつかで BizTalk プロジェクトのコンパイル エラーを引き起こす可能性のあるこれらのスキーマ間で重複する要素の定義である可能性があります。 たとえば、"Op1"操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、データ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も"CT1"のデータ型のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているため、コンパイル エラーが発生します。 このような状況には、次のお勧めします。  
  
   - 1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 これにより、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] "CT1"複雑なデータ型の 1 つだけ定義が生成されます。  
  
   - 複数の異なる実行で複数の操作のスキーマを生成する[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意のスキーマ型を生成**生成された XSD ファイルの一意の名前空間に含まれるようにチェック ボックスをオン、複雑なデータは、"CT1"を入力します。  
  
6. **[OK]** をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
   > [!NOTE]
   >  使用する場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]既定では、ファイルが特定の名前付け規則を作成、SQL Server アーティファクトのメタデータを生成します。 生成された WSDL が含まれています、 **fileNameHint** XSD ファイルに割り当てる必要がある名前を含む注釈タグ。 たとえば、テーブル操作のスキーマ ファイルのファイル名のヒントは TableOperation 規則に従います。\<スキーマ\>.\<tablename\>します。 生成される XSD ファイルの名前をカスタマイズする場合は、プレフィックスを行うことができます、**ファイル名のプレフィックス**ボックス。 最後に、XSD ファイルの名前はファイル名のプレフィックス + fileNameHint + (必要な場合、ファイル名が一意であることを確認する) の一意の整数に到着します。  
   > 
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ときに指定されたバインドのプロパティを含むバインド ファイル (XML ファイル) も作成操作と操作を呼び出すための SOAP アクションのスキーマを生成します。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接続 URI のアダプターのポート、バインドのプロパティおよび SOAP アクションは、WCF カスタム ポートまたは BizTalk SQL を作成する管理コンソールで設定します。 詳細については、[SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)を参照してください。
  
    SQL Server のアイテムのメタデータが正常に生成されました。 メタデータを使用すると、特定の操作を実行するのに SQL Server にメッセージを送信します。 参照してください[SQL アダプターを使用して開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)これらの操作を実行する方法の詳細について。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>WCF クライアントまたは WCF サービス コントラクトを使用して、生成、プラグインのアダプター サービス参照の追加  
 使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]いずれかの送信操作の WCF クライアント コードまたは受信操作のための WCF サービス コードを生成します。  
  
#### <a name="to-generate-wcf-client-class-or-service-contract-for-sql-server-operations"></a>SQL Server 操作用の WCF クライアント クラスまたはサービス コントラクトを生成するには  
  
1. [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**コントラクト型を選択します**ドロップダウン リストで、かどうかを実行する受信または送信の操作に基づく契約の種類を選択します。  
  
2. 参照またはまたは WCF クライアント (または WCF サービス コントラクト) を生成する特定の操作 (データベース テーブル) などのカテゴリを検索します。   
   たとえば、従業員テーブル内の操作で参照する、**カテゴリを選択**ボックス。  
  
   1.  ルート ノードを展開 (**/**) を SQL Server データベースの操作が表示されるカテゴリを表示します。  
  
   2.  [ルート] ノードで、展開、**テーブル**ノードを使用できるテーブルを参照してください。  
  
3. をクリックして、**従業員**テーブル ノード、および、**利用可能なカテゴリと操作**ボックスで、操作または WCF クライアント (または WCF サービス コントラクト) を生成するカテゴリを選択し、クリックして**追加**します。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
    次に示します、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] Insert と Select 操作の従業員テーブルを選択します。  
  
    ![WCF クライアントまたはサービス コントラクトの生成](../../adapters-and-accelerators/adapter-sql/media/sql-adap-add-adap-serv-ref.gif "sql_adap_add_adap_serv_ref")  
  
   > [!IMPORTANT]
   >  によって送信操作 (またはカテゴリ) を選択で、複数の 1 つの WCF クライアント クラスを生成できます。 詳細については、[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)を参照してください。  
  
4. ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
   1. をクリックして**詳細オプション**を開く、**詳細オプション**ボックス。  
  
   2. **オプションの高度な**ボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、非同期メソッドは、WCF クライアントの生成または構成ファイルの生成を無効にするかどうかを選択できます。  
  
   3. **シリアライザー**使用されるシリアライザーを選択します。  
  
      次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーとしないその他のオプションが選択されているため)。  
  
      ![高度なオプションが既定の設定をボックス](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      オプションで構成できる、**詳細オプション**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスはいくつかの使用可能なオプションに相当します。 これらのオプションの詳細については、[ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)を参照してください。 
  
5. **[OK]** をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアント クラス (または WCF サービスのインターフェイス) を保存し、操作と、プロジェクト ディレクトリで選択したカテゴリのヘルパー コード。 既定では、構成ファイルも保存されます。 受信と送信操作の若干異なるファイルが生成されます。詳細については、[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)を参照してください。  
  
   記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリ ノードを選択する場合は、すべてのノードとそのサブ ノードで使用可能な操作が選択されます。 たとえば、Employee テーブルの表示操作のすべての WCF クライアントを生成するには、従業員ノードを選択できます。  
  
## <a name="see-also"></a>参照  
 [SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)