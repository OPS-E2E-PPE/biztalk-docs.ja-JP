---
title: "参照、検索、および SQL アダプターを使用して SQL 操作のメタデータを取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdd5ca6f-30ff-4d32-a656-bbd54b9d072e
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a8d82a69b342c278e7cb17de8759d4986a71cd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter"></a>参照、検索、および SQL アダプターを使用して SQL 操作のメタデータを取得
このセクションで説明を使用する方法については、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。 これらを使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネント、することができます。  
  
-   メタデータを取得する対象の操作を参照します。  
  
-   メタデータを取得する対象の操作を検索します。  
  
-   選択した操作のメッセージ スキーマを追加し、ポートのバインドの構成ファイル、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトを使用する場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
-   WCF クライアント クラスまたは WCF サービス コントラクト (インターフェイス) を選択した操作と構成ファイル (app.config) を使用する場合、BizTalk 以外のプログラミング プロジェクトを追加、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、3 つすべてのコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 参照、検索、または操作を指定のメタデータを取得する前に、SQL Server に接続する必要があります。 使用すると、SQL Server に接続する方法については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[アダプター サービスのアドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)です。  
  
## <a name="browsing-for-operations"></a>操作の参照  
 使用することができます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を SQL Server で実行できる送信および受信操作の参照を使用して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
### <a name="outbound-operations"></a>送信操作  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]により、クライアントは、次の送信操作を実行します。  
  
-   Insert、Select、Update、およびテーブルとビューでの Delete 操作。  
  
-   テーブルやビュー上の < column_name > の操作を設定します。 Varchar (max)、nvarchar (max)、または varbinary (max) の列を持つテーブルには、この操作が公開します。 このような操作は、ラージ オブジェクトのストリーミングを有効にします。  
  
-   ストアド プロシージャ、弱いと厳密に型指定された操作としての両方です。  
  
-   スカラーおよびテーブルの操作として関数を値です。  
  
 アダプターも公開ジェネリック バウンド操作など**ExecuteReader**、 **ExecuteScalar**、および**ExecuteNonQuery**ルート レベルにします。  
  
### <a name="inbound-operations"></a>受信操作  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]により、クライアントは、次の受信操作を実行します。  
  
-   **ポーリング**SQL Server からデータの変更のポーリングに基づいたメッセージを受信する操作。 この操作で受信したメッセージがない厳密に型指定します。  
  
-   **TypedPolling** SQL Server からデータの変更のポーリングに基づいたメッセージを受信する操作。 この操作で受信したメッセージは、厳密型指定されます。  
  
-   **通知**から SQL Server クエリ通知を受信する操作。  
  
> [!NOTE]
>  アダプターもサポートしています、 **XmlPolling**を SELECT ステートメントおよび FOR XML 句を含むストアド プロシージャを使用してデータベースを SQL Server 上でのポーリングを有効にする操作を受信します。 ただし、アダプターは、この特定の受信操作を公開しません。 XmlPolling の詳細については、次を参照してください。 [BizTalk Server を使用して SQL から FOR XML 句で SELECT ステートメントを使用してポーリング メッセージを受信](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)です。  
  
 これらの操作の詳細については、次を参照してください。[アダプターを使用して SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)です。  
  
> [!NOTE]
>  使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Windows のインターフェイスを使用して、カテゴリと操作のノードを参照することができます。  
  
 参照メタデータの詳細については、次を参照してください。 [SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)です。  
  
##### <a name="to-browse-outbound-operations-on-sql-server"></a>SQL Server に対する送信操作を参照するには  
  
1.  SQL Server への接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[アダプター サービスのアドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)手順についてはします。  
  
2.  **選択コントラクト型**を一覧表示、送信操作を選択**クライアント (送信操作)**です。  
  
3.  **カテゴリを選択**ボックスに、使用できる成果物に接続する SQL Server データベースが一覧表示されます。 そのアイテムに使用できる操作を表示するアイテムをクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、アイテムの名前を入力して、**カテゴリを選択**ボックス。 例についてに移動すること、**従業員**テーブル ノードにフォーカスを保持、**テーブル**ノード、および入力`Employee`です。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 ルート ノード (/) が選択されているし、ルート ノードで使用可能な一般カテゴリのノードで表示されます、**利用可能なカテゴリと操作**ボックス。  
  
     ![ルート レベルの操作とカテゴリで利用可能な](../../adapters-and-accelerators/adapter-sql/media/3eef7b99-da8e-4b98-8b14-8e48fd7b3801.gif "3eef7b99-da8e-4b98-8b14-8e48fd7b3801")  
  
    > [!NOTE]
    >  ExecuteReader、ExecuteScalar、ExecuteNonQuery など標準の SQL Server の操作は、ルート レベルでも使用できます。 これらの操作の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。  
  
4.  SQL Server データベースで使用できる手順を表示するをクリックして、**プロシージャ**ノード。 次の図に、**プロシージャ**でノードを選択、**カテゴリを選択** ボックスと対応する手順を次に、**ボックスの利用可能なカテゴリと操作**.  
  
     ![SQL Server でのプロシージャの参照](../../adapters-and-accelerators/adapter-sql/media/e3b1a070-4077-4e4d-bfc7-558df9b8b9d5.gif "e3b1a070-4077-4e4d-bfc7-558df9b8b9d5")  
  
    > [!NOTE]
    >  下に表示するプロシージャの同じセット、**プロシージャ**で使用可能なノードも、 **Strongly-Typed プロシージャ**ノード。 スキーマを生成する方法が違います。 下にある手順については、**プロシージャ**ノード、スキーマは、弱い型指定します。 ただし、下にある手順について、 **Strongly-Typed プロシージャ**ノード、スキーマを厳密に型指定します。 厳密に型指定されたスキーマは、1 つの操作のスキーマを BizTalk プロジェクトの作成中にスキーマがデザイン時に使用するために BizTalk マッパーを使用して別の操作にマップする場合に便利です。 弱い型指定の手順では、プロシージャのスキーマは実行時に、応答メッセージの一部として受信されます。  
  
5.  SQL Server データベース内のテーブルを表示するをクリックして、**テーブル**ノード。 また、展開、**テーブル**ノード。  
  
6.  テーブルでサポートされる操作を表示するには、テーブル名をクリックします。  
  
     次の図は、テーブルの一覧を示します、**カテゴリを選択**ボックス。 **利用可能なカテゴリと操作**ボックスには、選択したテーブルのサポートされる操作が一覧表示されます。  
  
     ![SQL Server データベース テーブルの参照](../../adapters-and-accelerators/adapter-sql/media/3966f3b9-85a0-4354-8ed4-da5ae74c9885.gif "3966f3b9-85a0-4354-8ed4-da5ae74c9885")  
  
    > [!NOTE]
    >  SQL Server テーブルの型 varchar (max)、nvarchar (max)、および varbinary (max) 列が含まれている場合、アダプターはその列のデータを更新する特定の操作も公開します。 この操作の名前には、< column_name > が設定されます。 たとえば、テーブルに列型 varchar (max) の"Job_Description"がある場合、操作の名前は"SetJob_Description"です。  
  
7.  SQL Server データベースのビューを表示するをクリックして、**ビュー**ノード。 また、展開、**ビュー**ノード。  
  
8.  ビューでサポートされる操作を表示するには、ビュー名をクリックします。  
  
     次の図のビューの一覧を示しています、**カテゴリを選択**ボックス。 **利用可能なカテゴリと操作**ボックスに、選択したビューのサポートされる操作が一覧表示されます。  
  
     ![SQL Server データベース ビューの参照](../../adapters-and-accelerators/adapter-sql/media/67362fb2-35fb-4afb-8ff6-e519b26bd187.gif "67362fb2-35fb-4afb-8ff6-e519b26bd187")  
  
    > [!NOTE]
    >  ビューの型 varchar (max)、nvarchar (max)、および varbinary (max) 列が含まれている場合、アダプターはその列のデータを更新する特定の操作も公開します。 この操作の名前には、< column_name > が設定されます。 たとえば、テーブルに列型 varchar (max) の"Job_Description"がある場合、操作の名前は"SetJob_Description"です。  
  
9. SQL Server データベースで定義されているスカラー関数の一覧を表示する、**利用可能なカテゴリと操作**ボックスで、クリックして、**スカラー関数**ノード。  
  
     次の図に、**スカラー関数**でノードを選択、**カテゴリを選択** ボックスと対応する関数を次に、**利用可能なカテゴリと操作**ボックス。  
  
     ![SQL Server のスカラー関数参照](../../adapters-and-accelerators/adapter-sql/media/78b9f720-2cb2-44a8-b8cc-49e4fb608a1f.gif "78b9f720-2cb2-44a8-b8cc-49e4fb608a1f")  
  
10. テーブルの一覧を表示する値に SQL Server データベースで定義されている関数、**利用可能なカテゴリと操作**ボックスで、クリックして、**テーブル値関数**ノード。  
  
     次の図に、**テーブル値関数**でノードを選択、**カテゴリを選択** ボックスと対応する関数を次に、**利用可能なカテゴリとoperations**ボックス。  
  
     ![SQL Server でのテーブル値関数の参照](../../adapters-and-accelerators/adapter-sql/media/b007059f-280e-40d7-9553-eca4216296f4.gif "b007059f-280e-40d7-9553-eca4216296f4")  
  
##### <a name="to-browse-inbound-operations-on-sql-server"></a>SQL Server での受信操作を参照するには  
  
1.  SQL Server への接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[アダプター サービスのアドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)手順についてはします。  
  
2.  **選択コントラクト型**一覧で、受信操作は、選択**サービス (入力方向の操作)**です。  
  
3.  サポートされているすべての受信操作、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]はルート ノードで使用可能です。 使用可能な受信操作を表示するには、ルート ノード (/) をクリックします。  
  
     ![受信アダプターでサポートされている操作](../../adapters-and-accelerators/adapter-sql/media/133732c0-ca8f-4e57-8a70-ba4fb561a37b.gif "133732c0-ca8f-4e57-8a70-ba4fb561a37b")  
  
## <a name="searching-for-operations"></a>操作の検索  
 使用することができます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]SQL Server データベース内の特定の成果物を検索します。 SQL Server のメタデータを検索するときに、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
-   検索式では、ワイルドカードとエスケープ文字をサポートしています。  
  
-   検索操作を実行するノードのすぐ下にある検索を有効にします。 たとえば、テーブルを検索するをする必要があります検索する \Table です。 複数レベルの検索がサポートされていません。  
  
 次の表に、成果物とその解釈してを検索するために使用できる特殊文字、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
|特殊文字|解釈|例|  
|-----------------------|--------------------|-------------|  
|_ (アンダースコア)|1 文字と一致します。|「A _」は、AB、AC、AD と一致します。|  
|%|0 個以上の文字と一致します。|「%」では、A、AB AC と一致します。|  
|[ ]|-% と _ の特別な意味をエスケープします。<br />-範囲または存在する文字のセットを指定します。|-% [%] % 記号を含むすべての名前に一致します。<br />-一致する間 (およびなど) 文字を含むすべての名前を [a ~ f] 'a' と 'f' です。<br />-一致する文字を含む 'a', 'b' すべての名前を [abc] と 'c' です。|  
|[^]|範囲または存在しているが文字のセットを指定します|-[^ a ~ f] が付いていない文字間 (を含めて) すべての名前と一致する 'a' と 'f' です。<br />-[^ abc] 一致するすべての名前を持たない文字 'a', 'b' および 'c' です。|  
  
> [!NOTE]
>  エスケープ文字は、通常の文字とは、ワイルドカードとしてではなくにワイルドカードを解釈することを示すためにワイルドカード文字の前に配置する文字です。  
  
 詳細については、次を参照してください。 [SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)です。  
  
 SQL Server を使用してメタデータを検索するには、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、次の手順を実行します。  
  
#### <a name="to-search-metadata-in-sql-server"></a>SQL Server でメタデータを検索するには  
  
1.  SQL Server への接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[アダプター サービスのアドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)手順についてはします。  
  
2.  **選択コントラクト型**一覧で、受信または送信操作を検索するかどうかに基づいてコントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、対象を検索する特定の成果物のカテゴリ ノードをクリックします。 たとえば、テーブルの検索は、次のようにクリックします。、**テーブル**ノード。  
  
4.  **カテゴリで検索**ボックスに、特定の成果物を検索する検索式を入力します。 たとえば、名前に"Customer"を格納するテーブルの検索は、次のように入力します。`%Customer%`です。  
  
    > [!NOTE]
    >  検索文字列では大文字小文字を区別します。  
  
5.  検索を開始するには、右矢印アイコンが付いたボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件に適合するアイテムが一覧表示されます。  
  
     次の図は、名前に"Customer"を含む SQL Server テーブルを示します。  
  
     ![SQL Server でのメタデータの検索](../../adapters-and-accelerators/adapter-sql/media/62c24ed3-f4e5-47de-8e8d-35af96e6c5ec.gif "62c24ed3-f4e5-47de-8e8d-35af96e6c5ec")  
  
## <a name="generating-schema-for-biztalk-projects"></a>BizTalk プロジェクトのスキーマを生成します。  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]選択した SQL Server の成果物のためのスキーマを生成します。 参照して、呼び出し先のアイテムの検索し、それらの成果物のスキーマを生成し、SQL Server に、スキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  そのカテゴリのサブツリー内のすべての操作を返すカテゴリ ノードを選択することができます: たとえばを選択 (テーブルのすべての操作のスキーマの生成) をテーブル全体またはテーブル (Insert や Delete など) で特定の操作を選択するテーブルに対する操作のみのスキーマを生成します。 ノードの詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)です。  
  
#### <a name="to-generate-schema-for-sql-server-artifacts"></a>SQL Server の成果物のためのスキーマを生成するには  
  
1.  SQL Server への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 参照してください[アダプター サービスのアドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)手順についてはします。  
  
    > [!IMPORTANT]
    >  使用して操作を実行するためのスキーマを生成する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]設定する必要があります、 **EnableBizTalkCompatibilityMode**にプロパティのバインド**True**です。 SQL Server データベースへの接続を確立中にこのバインドのプロパティを設定する必要があります。  
  
2.  **選択コントラクト型**一覧で、受信または送信操作のスキーマを生成しているかどうかに基づいてコントラクトの型を選択します。  
  
3.  メタデータを生成するカテゴリ ノードをクリックします。 たとえば、テーブルのメタデータを生成する場合は、クリックして**テーブル**です。  
  
4.  カテゴリのノードを展開し、メタデータを生成する、そのノード内の特定の項目を選択します。 たとえば、"CustomerTable"テーブルでの操作のメタデータを生成するには、展開、**テーブル**ノードをクリックして**CustomerTable**です。  
  
5.  **利用可能なカテゴリと操作**ボックスで、SQL Server を実行し、をクリックする操作を選択**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。 たとえば、Insert および"CustomerTable"テーブルに対する Select 操作を実行する操作名をクリック**追加**です。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、選択した操作を一覧表示します。  
  
     ![SQL Server からメタデータを取得](../../adapters-and-accelerators/adapter-sql/media/a6a95291-f6ed-46d1-bacc-2dfc27638117.gif "a6a95291-f6ed-46d1-bacc-2dfc27638117")  
  
     複数の操作のスキーマを生成する場合は、BizTalk プロジェクトのコンパイルに失敗する可能性がありますをこれらのスキーマ間で重複する要素定義である可能性があります。 たとえば、"Op1"、操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、データ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"が"CT1"のデータ型のパラメーターにはも含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているために、コンパイル エラーが表示されます。 このような場合に、次のお勧めします。  
  
    -   1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 これにより、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]複雑なデータ型"CT1"の定義は 1 つだけが生成されます。  
  
    -   複数の異なる実行で複数の操作のスキーマを生成するかどうか[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意なスキーマ型を生成** チェック ボックスを生成される XSD ファイルの一意の名前空間に含まれるように、複雑なデータは、"CT1"を入力します。  
  
6.  **[OK]**をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
    > [!NOTE]
    >  使用している場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータを生成する SQL Server の成果物の既定では、ファイルは、特定の名前付け規則で作成します。 生成された WSDL が含まれています、 **fileNameHint** XSD ファイルに割り当てられる名前を含む注釈タグ。 たとえば、テーブル操作のスキーマ ファイルのファイル名のヒントには、規約 TableOperation が次に示します。\<スキーマ >。\<tablename >。 生成された XSD ファイルの名前をカスタマイズする場合でプレフィックスを入力することができます、**ファイル名のプレフィックス**ボックス。 最後に、XSD ファイルの名前に到達する時にファイル名のプレフィックス + fileNameHint + (必要な場合、ファイル名が一意であることを確認する) の一意の整数。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]時に指定されたバインディングのプロパティを含むバインド ファイル (XML ファイル) も作成操作と、操作を呼び出す SOAP アクションのスキーマを生成します。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを WCF カスタム ポートまたは BizTalk SQL アダプターのポート、接続 URI をバインディング プロパティ、および作成 SOAP アクションを設定します。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。
  
     SQL Server のアイテムのメタデータが正常に生成されました。 メタデータを使用すると、特定の操作を実行するのに SQL Server にメッセージを送信します。 参照してください[SQL アダプタを使用する開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)これらの操作を実行する方法に関する詳細についてはします。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>WCF クライアントまたは WCF サービス コントラクトを使用して、生成する、プラグイン アダプター サービス参照の追加  
 使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]いずれかの送信操作用の WCF クライアント コードまたは受信操作のための WCF サービス コードを生成します。  
  
#### <a name="to-generate-wcf-client-class-or-service-contract-for-sql-server-operations"></a>SQL Server 操作用の WCF クライアント クラスまたはサービス コントラクトを生成するには  
  
1.  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行する受信または送信操作コントラクトの型を選択します。  
  
2.  参照またはまたは WCF クライアント (または WCF サービス コントラクト) を生成する特定の操作 (データベース テーブルなど) のカテゴリを検索します。   
    たとえば、従業員テーブル内の操作用に参照するため、**カテゴリを選択**ボックス。  
  
    1.  ルート ノードを展開 (**/**) を SQL Server データベースの操作が表示されるカテゴリを表示します。  
  
    2.  [ルート] ノードで、展開、**テーブル**ノードを使用できるテーブルを参照してください。  
  
3.  クリックして、**従業員**テーブル ノードし、、**利用可能なカテゴリと操作**ボックスで、操作または WCF クライアント (または WCF サービス コントラクト) を生成するカテゴリを選択し、をクリックして**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
     次に示します、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] Insert と選択した Employee テーブルに対して Select 操作を使用します。  
  
     ![WCF クライアントまたはサービス コントラクトの生成](../../adapters-and-accelerators/adapter-sql/media/sql-adap-add-adap-serv-ref.gif "sql_adap_add_adap_serv_ref")  
  
    > [!IMPORTANT]
    >  によって送信操作 (またはカテゴリ) を選択、複数の 1 つの WCF クライアント クラスが生成されます。 詳細については、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
4.  ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
    1.  をクリックして**オプションの高度な**を開くには、**オプションの高度な**ボックス。  
  
    2.  **オプションの高度な**下にあるボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、非同期メソッドは、WCF クライアントの生成または構成ファイルの生成を無効にするかどうかを選択することができます。  
  
    3.  **シリアライザー**のために使用されるシリアライザーを選択します。  
  
     次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーしない他のオプションが選択されているため)。  
  
     ![高度なオプション ボックスの既定の設定](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     構成できるオプション、**オプションの高度な**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスが使用可能なオプションの一部に相当します。 これらのオプションの詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)です。 
  
5.  **[OK]**をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアント クラス (または WCF サービスのインターフェイス) を保存し、操作と、プロジェクト ディレクトリに選択したカテゴリのヘルパー コード。 既定では、構成ファイルも保存されます。 受信と送信操作です。 わずかに異なるファイルが生成されます。詳細については、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
 記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリ ノードを選択する場合は、すべてのノードとそのサブ ノードで使用可能な操作が選択します。 たとえば、Employee テーブルに対して表示される操作のすべての WCF クライアントを生成するには、従業員ノードを選択できます。  
  
## <a name="see-also"></a>参照  
 [SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)