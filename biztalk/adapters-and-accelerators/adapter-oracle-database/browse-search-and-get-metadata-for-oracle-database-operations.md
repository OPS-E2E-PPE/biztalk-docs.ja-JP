---
title: "参照、検索、および Oracle データベースの操作のメタデータを取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF client, generating a
- operations, browsing for
- metadata, browsing
- browse, for operations
- schema, generating
- metadata, retrieving
- browse, metadata
- retrieve, metadata
- operations, searching for
- WCF service contract, generating a
- metadata, browsing, searching, and retrieving
ms.assetid: 65bd59e0-771d-40fe-966c-8cc8a629ce47
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8735040dd1cad2df59e18dbb572dad322ec46fcf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-metadata-for-oracle-database-operations"></a>参照、検索、および Oracle データベースの操作のメタデータを取得
このセクションの使用方法に関する情報が[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。 これらを使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネント、することができます。  
  
-   メタデータを取得する対象の操作を参照します。  
  
-   メタデータを取得する対象の操作を検索します。  
  
-   選択した操作のメッセージ スキーマを追加し、ポートのバインド構成ファイルを BizTalk server プロジェクトを使用する場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
-   WCF クライアント クラスまたは WCF サービス コントラクト (インターフェイス) を選択した操作と構成ファイル (app.config) を使用する場合、BizTalk 以外のプログラミング プロジェクトを追加、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
 参照、検索、または操作を指定のメタデータを取得する前に、Oracle データベースに接続する必要があります。 データベースを使用するときに、Oracle に接続する方法については[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)です。  
  
> [!NOTE]
>  -   [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]参照操作については、検索するため、3 つすべてのコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
> -   そのカテゴリのサブツリー内のすべての操作を返すカテゴリ ノードを選択することができます: たとえば、テーブル全体またはスキーマ (または、スキーマ内のすべてのテーブル)。  
  
## <a name="browsing-for-operations"></a>操作の参照  
 使用してメタデータの参照中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス。  
  
-   テーブル、ビュー、ストアド プロシージャ、関数、およびパッケージで実行できる操作。  
  
-   SQLEXECUTE 操作により、Oracle データベースで任意の汎用的なデータ操作言語 (DML) またはストアド プロシージャを実行するクライアントはアダプターです。  
  
-   POLLINGSTMT および Notification の操作、Oracle データベースからの受信データを取得するアダプターのクライアントを有効にします。 ストアド プロシージャ、関数およびポーリングの操作として公開されているそれぞれのスキーマの下にあるパッケージの一覧も公開します。  
  
> [!NOTE]
>  -   使用して、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Windows のインターフェイスを使用して、カテゴリと操作のノードを参照することができます。  
> -   SQLEXECUTE、POLLINGSTMT、および通知の操作は、カテゴリ ツリーのルート ノードのすぐ下に表示されます。 これらの送信および受信操作を表示するルート ノードを選択する必要があります。  
  
 参照メタデータの詳細については、次を参照してください[Visual Studio での Oracle データベース操作のメタデータを取得。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)  
  
 次の手順を使用して Oracle データベース内の各アイテムの公開操作の参照を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
#### <a name="to-browse-metadata-in-an-oracle-database"></a>Oracle データベースでのメタデータを参照するには  
  
1.  使用して Oracle データベースへの接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行するアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスに、Oracle データベースでスキーマが一覧表示されます。 テーブル、プロシージャ、関数、パッケージ、およびスキーマにアクセスできるビューを表示するスキーマ をクリックして、**利用可能なカテゴリと操作**ボックス。 また、スキーマ ノードを展開して、カテゴリ化を確認できます。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、アイテムの名前を入力して、**カテゴリを選択**ボックス。 たとえばに移動すること、 **SCOTT**ノード、ルート ノードにフォーカスを保持し、入力`SCOTT`です。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 SCOTT スキーマ ノードが選択され、SCOTT ノードで使用可能な一般カテゴリのノードで表示されます、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのユーザーの参照](../../adapters-and-accelerators/adapter-oracle-database/media/c6e02d12-278b-4419-8c8d-d12d0d64f325.gif "c6e02d12-278b-4419-8c8d-d12d0d64f325")  
  
4.  クリックして、**テーブル**SCOTT 内のテーブルを表示するノード、**利用可能なカテゴリと操作**ボックス。 または、テーブルの一覧を表示を展開して、**テーブル**ノード。  
  
5.  テーブルでサポートされる操作を表示するテーブル名をクリックします。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 SCOTT スキーマで使用できるテーブルが記載されて、**カテゴリを選択**ボックス。 EMP テーブルの使用可能な操作が表示されている、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベース テーブルの参照](../../adapters-and-accelerators/adapter-oracle-database/media/6df61a2f-3cd9-486c-9bf5-7968f8f1ce8d.gif "6df61a2f-3cd9-486c-9bf5-7968f8f1ce8d")  
  
6.  クリックして、**プロシージャ**スキーマ SCOTT にアクセス可能な手順を一覧表示するノードで、**利用可能なカテゴリと操作**ボックス。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 SCOTT スキーマで使用できる [全般] カテゴリのノードで表示されます、**カテゴリを選択**ボックス。 SCOTT スキーマで使用できる手順が記載されて、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-database/media/9826e160-5295-4fdc-bd82-ccd456d89242.gif "9826e160-5295-4fdc-bd82-ccd456d89242")  
  
7.  クリックして、**関数**SCOTT スキーマの関数を表示するノードで、**利用可能なカテゴリと操作**ボックス。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 SCOTT スキーマで使用できる [全般] カテゴリのノードで表示されます、**カテゴリを選択**ボックス。 SCOTT スキーマで使用できる関数の一覧は、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでの関数参照](../../adapters-and-accelerators/adapter-oracle-database/media/ae02731e-7f26-4552-8e40-db797885af01.gif "ae02731e-7f26-4552-8e40-db797885af01")  
  
8.  クリックして、**パッケージ**SCOTT スキーマ用のパッケージを表示するノードで、**利用可能なカテゴリと操作**ボックス。 または、パッケージの一覧を表示を展開して、**パッケージ**ノード。  
  
9. パッケージでサポートされる操作を表示するパッケージ名をクリックします。  
  
     次に示します[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、パッケージ、および SCOTT スキーマに対して、特定のパッケージでサポートされている操作を一覧表示します。  
  
     ![Oracle データベースでのパッケージの参照](../../adapters-and-accelerators/adapter-oracle-database/media/bts-r2-net-adapter-oracle-tut1-browse-pckgs.gif "bts_R2_NET_Adapter_Oracle_Tut1_Browse_Pckgs")  
  
10. クリックして、**ビュー** SCOTT スキーマのビューを表示するノードで、**利用可能なカテゴリと操作**ボックス。 またはを展開してビューの一覧を表示できます、**ビュー**ノード。  
  
11. ビューでサポートされる操作を表示するビューの名前をクリックします。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ビュー、および SCOTT スキーマに対して、特定のビューのサポートされている操作を一覧表示します。  
  
     ![Oracle データベースでビューの参照](../../adapters-and-accelerators/adapter-oracle-database/media/cc1079bc-c1ca-4c2b-a291-abf87bf1ac4d.gif "cc1079bc-c1ca-4c2b-a291-abf87bf1ac4d")  
  
    > [!NOTE]
    >  アダプターのクライアントは、WCF チャネルとサービス モデルを使用して、メタデータのバッチの取得を実行するバッチ サイズを指定できます。  
  
## <a name="searching-for-operations"></a>操作の検索  
 使用して Oracle メタデータを検索中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
-   検索式では、ワイルドカードとエスケープ文字をサポートしています。  
  
-   検索操作を実行するノードのすぐ下にある検索を有効にします。 たとえば、関数を検索するにする必要がありますを検索できる\\[Schema] \Functions です。 複数レベルの検索がサポートされていません。  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|_ (アンダースコア)|1 文字と一致します。<br /><br /> たとえば、a _ は、AB、AC、AD と一致します。|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、%a、AB、ABC に一致します。|  
|\ (エスケープ)|% と _ の特別な意味をエスケープします。<br /><br /> たとえば、A\\_B A_B に一致します。|  
  
> [!NOTE]
>  エスケープ文字は、通常の文字とは、ワイルドカードとしてではなくにワイルドカードを解釈することを示すためにワイルドカード文字の前に挿入されている文字です。  
  
 詳細については、次を参照してください[Visual Studio での Oracle データベース操作のメタデータを取得。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)  
  
#### <a name="to-search-metadata-in-an-oracle-database"></a>Oracle データベースでメタデータを検索するには  
  
1.  使用して Oracle データベースへの接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)手順についてはします。  
  
2.  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から、**選択コントラクト型**ドロップダウン リストで、基にするかどうかを検索対象のアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、テーブル、プロシージャ、関数、パッケージ、および検索するビューが含まれているスキーマ をクリックします。 をクリックするスキーマがない場合は、ルート ノードをクリックします。  
  
4.  **カテゴリで検索**テキスト ボックスに、特定のスキーマを検索する検索式を入力します。 たとえば、名前に"SC"を含むスキーマの検索は、次のように入力します。 **% SC** 、テキスト ボックスにします。  
  
5.  検索を開始する右矢印アイコンが付いたボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件を満たすためのスキーマが一覧表示されます。  
  
6.  **カテゴリを選択**ボックスで、スキーマに対応するノードを展開し をクリックし、データベース アイテムの内で検索する文字列。 **カテゴリで検索**テキスト ボックスに、特定のデータベースのアイテムを検索する検索式を入力します。  
  
     たとえば、検索を名前に"EMP"を持つテーブルを次のように選択します**テーブル**、型**% EMP**で、**カテゴリで検索**テキスト ボックスとボタンをクリックし、。右側の下矢印アイコン。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、検索結果の一覧を表示します。  
  
     ![Oracle データベースでメタデータを検索](../../adapters-and-accelerators/adapter-oracle-database/media/1ee912f8-896e-4b45-ba98-1bbd36b56574.gif "1ee912f8-896e-4b45-ba98-1bbd36b56574")  
  
    > [!NOTE]
    >  アダプターのクライアントは、WCF チャネルとサービス モデルを使用して、メタデータの batch-wise 検索を実行するバッチ サイズを指定できます。  
  
## <a name="generating-schema-using-the-consume-adapter-service-add-in-or-add-adapter-metadata-wizard"></a>使用してスキーマを生成する、アダプターを使用する追加のサービスまたはアダプター メタデータのウィザードの追加  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]選択されている Oracle データベース アイテムのスキーマを生成します。 参照して、呼び出し先のアイテムの検索し、それらの成果物のスキーマを生成し、Oracle データベースに、スキーマに準拠したメッセージを送信できます。 使用して Oracle データベースからメタデータを取得する次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
> [!NOTE]
>  そのカテゴリのサブツリー内のすべての操作を返すカテゴリ ノードを選択することができます: たとえばを選択 (テーブルのすべての操作のスキーマの生成) をテーブル全体またはテーブル (Insert や Delete など) で特定の操作を選択するテーブルに対する操作のみのスキーマを生成します。 ノードの詳細については、次を参照してください。[メタデータ ノード IDs3](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)です。  
  
#### <a name="to-retrieve-metadata-from-an-oracle-database"></a>Oracle データベースからメタデータを取得するには  
  
1.  使用して Oracle データベースへの接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 参照してください[Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行するアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、スキーマのノードを展開します。  
  
4.  メタデータを生成するカテゴリを選択します。 たとえば、テーブルのメタデータを生成する場合は、選択**テーブル**です。  
  
5.  その特定のカテゴリ ノードを展開し、メタデータを生成する、そのノード内の特定の項目を選択します。  
  
     たとえば、特定のテーブルのメタデータを生成する展開、**テーブル**ノードを展開し、特定のテーブル名を選択します。  
  
    > [!NOTE]
    >  前の手順」の説明に従って、特定のデータベースのアイテムの検索もできます。  
  
6.  **利用可能なカテゴリと操作**ボックスで、前の手順で選択したデータベースのアイテムに関連する操作を選択し、をクリックして**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、選択した操作を一覧表示します。  
  
     ![Oracle データベースからメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/media/d3950566-8720-4c15-8a16-4ade14bf6221.gif "d3950566-8720-4c15-8a16-4ade14bf6221")  
  
     複数の操作のスキーマを生成する場合は、BizTalk プロジェクトのコンパイルに失敗する可能性がありますをこれらのスキーマ間で重複する要素定義である可能性があります。 たとえば、"Op1"、操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、複雑なデータ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も複雑なデータ型"CT1"のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているために、コンパイル エラーが表示されます。 このような場合に、次のお勧めします。  
  
    -   1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 これにより、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]複雑なデータ型"CT1"の定義は 1 つだけが生成されます。  
  
    -   複数の異なる実行で複数の操作のスキーマを生成するかどうかは[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意なスキーマ型を生成**生成される XSD ファイルには、複雑な一意の名前空間が含まれるように、チェック ボックスデータは、"CT1"を入力します。  
  
7.  **[OK]**をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
     既定では、ファイルを作成して、名前付け規則"OracleDBBindingSchema\<n > .xsd"ここで、' n ' 1、2、および作成したスキーマ ファイルの数によってを指定できます。 名前を入力して、スキーマ ファイルにカスタムの名前を指定する代わりに、**ファイル名のプレフィックス**テキスト ボックス。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、命名規則で今すぐスキーマ ファイルが作成されます\<ファイル名のプレフィックス > スキーマ\<n > .xsd です。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]時に指定されたバインディングのプロパティを含むバインド ファイル (XML ファイル) も作成操作と、操作を呼び出す SOAP アクションのスキーマを生成します。 BizTalk Server 管理コンソールで、接続 URI、バインドのプロパティで WCF カスタム ポートを作成するには、このバインド ファイルをインポートして、SOAP アクションを設定します。 詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。  
  
    > [!IMPORTANT]
    >  使用して、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]バインド ファイルを生成しません。  
  
8.  **[ファイル]** メニューの **[すべてを保存]**をクリックします。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>WCF クライアントまたは WCF サービス コントラクトを使用して、生成する、プラグイン アダプター サービス参照の追加  
 使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]いずれかの送信操作用の WCF クライアント コードまたは受信操作のための WCF サービス コードを生成します。  
  
#### <a name="to-retrieve-metadata-from-an-oracle-database"></a>Oracle データベースからメタデータを取得するには  
  
1.  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行する (POLLINGSTMT) の受信または送信操作コントラクトの型を選択します。  
  
2.  参照または WCF クライアント (または WCF サービス コントラクト) を生成する特定の操作または Oracle データベース テーブルの場合) などのカテゴリを検索します。   
    たとえば、SCOTT に含まれる操作を参照するには、です。EMP テーブルで、**カテゴリを選択**ボックス。  
  
    1.  ルート ノードを展開 (**/**) に、Oracle データベースに公開されるスキーマを参照してください。  
  
    2.  [ルート] ノードで、展開、 **SCOTT** SCOTT スキーマの公開されているカテゴリを表示するノードです。  
  
    3.  下にある、 **SCOTT**  ノードを展開、**テーブル**SCOTT スキーマのテーブルを表示するノードが示されます。  
  
    4.  下にある、**テーブル**ノードを選択、 **EMP**ノード。 表示、EMP テーブルの操作が記載されて、**利用可能なカテゴリと操作**ボックス。  
  
3.  **利用可能なカテゴリと操作**ボックスで、操作は、WCF クライアント (または WCF サービス コントラクト) を生成し、をクリックする項目の選択**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
     次の図に示しています、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] SCOTT Insert および Update 操作とします。選択された EMP テーブル。  
  
     ![Select および Update 操作が選択されます。] (../../adapters-and-accelerators/adapter-oracle-database/media/4c41ac7b-784a-494c-ac82-c007e22a4fdf.gif "4c41ac7b-784a-494c-ac82-c007e22a4fdf")  
  
    > [!IMPORTANT]
    >  によって送信操作 (またはカテゴリ) を選択、複数の 1 つの WCF クライアント クラスが生成されます。 詳細については、次を参照してください。 [WCF クライアントまたは Oracle データベース ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。  
  
4.  ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
    1.  をクリックして**オプションの高度な**を開くには、**オプションの高度な**ボックス。  
  
    2.  **オプションの高度な**下にあるボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、非同期メソッドは、WCF クライアントの生成または構成ファイルの生成を無効にするかどうかを選択することができます。  
  
    3.  **シリアライザー**のために使用されるシリアライザーを選択します。  
  
     次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーしない他のオプションが選択されているため)。  
  
     ![高度なオプション ボックスの既定の設定](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     構成できるオプション、**オプションの高度な**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスが使用可能なオプションの一部に相当します。 これらのオプションの詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)です。
  
5.  **[OK]**をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアント クラス (または WCF サービスのインターフェイス) を保存し、操作と、プロジェクト ディレクトリに選択したカテゴリのヘルパー コード。 既定では、構成ファイルも保存されます。 受信と送信操作です。 わずかに異なるファイルが生成されます。詳細については、次を参照してください。 [WCF クライアントまたは Oracle データベース ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。  
  
 記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリ ノードを選択する場合は、すべてのノードとそのサブ ノードで使用可能な操作が選択します。 たとえば、すべての操作を EMP テーブルの表示用の WCF クライアントを生成することができますノードを選択する、EMP;SCOTT スキーマ内のすべてのテーブルの WCF クライアントを生成するには、テーブル ノード; を選択することができます。などなど。  
  
## <a name="see-also"></a>参照  
[Visual Studio での Oracle データベース操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)