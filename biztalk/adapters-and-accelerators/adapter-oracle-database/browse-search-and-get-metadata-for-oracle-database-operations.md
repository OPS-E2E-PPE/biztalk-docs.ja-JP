---
title: 参照、検索、および Oracle データベース操作のメタデータを取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab8c821f489a510d87fa06546f45a319608b5065
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005355"
---
# <a name="browse-search-and-get-metadata-for-oracle-database-operations"></a>参照、検索、および Oracle データベース操作のメタデータを取得
このセクションでは、使用する方法についての情報を提供します。 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 これらを使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ことができます、コンポーネント。  
  
- メタデータを取得する対象の操作を参照します。  
  
- メタデータを取得する対象の操作を検索します。  
  
- 選択した操作のメッセージ スキーマを追加し、ポートのバインドの構成ファイルを BizTalk server プロジェクトを使用する場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  
  
- 使用する場合に、BizTalk 以外のプログラミング プロジェクトに WCF クライアント クラスまたは選択した操作と構成ファイル (app.config) の WCF サービス コントラクト (インターフェイス) を追加、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
  参照、検索、またはターゲットの操作のメタデータを取得する前に、Oracle データベースに接続する必要があります。 使用する時に、データベース、Oracle に接続する方法については[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)します。  
  
> [!NOTE]
> - [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]参照操作については、検索するため、3 つすべてのコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
>   -   そのカテゴリのサブツリー内のすべての操作を返すカテゴリ ノードを選択することができます: たとえば、テーブル全体またはスキーマ (または、スキーマ内のすべてのテーブル)。  
  
## <a name="browsing-for-operations"></a>操作の参照  
 使用してメタデータを閲覧中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス。  
  
-   テーブル、ビュー、ストアド プロシージャ、関数、およびパッケージで実行できる操作。  
  
-   SQLEXECUTE 操作、アダプター クライアントが Oracle データベースで任意の汎用的なデータ操作言語 (DML) またはストアド プロシージャを実行できるようにします。  
  
-   POLLINGSTMT と通知操作、Oracle データベースからの受信データを取得するアダプターのクライアントを有効にします。 ストアド プロシージャ、関数およびポーリングするための操作として公開されているそれぞれのスキーマの下のパッケージの一覧も公開します。  
  
> [!NOTE]
> - 使用して、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、Windows インターフェイスを使用して、カテゴリと操作のノードを参照することができます。  
>   -   SQLEXECUTE、POLLINGSTMT、および通知の操作は、カテゴリ ツリーのルート ノードのすぐ下に表示されます。 これらの送信および受信操作を表示するルート ノードを選択する必要があります。  
  
 参照メタデータの詳細については、次を参照してください[Visual Studio での Oracle データベース操作のメタデータを取得。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)  
  
 次の手順を使用して Oracle データベース内の各アイテムの公開されている操作の参照を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
#### <a name="to-browse-metadata-in-an-oracle-database"></a>Oracle データベースでのメタデータを参照するには  
  
1. 使用して Oracle データベース接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**ドロップダウン リストで、かどうかを実行するアダプターを使用して、受信または送信の操作に基づく契約の種類を選択します。  
  
3. **カテゴリを選択**ボックスには、Oracle データベースでスキーマが一覧表示されます。 テーブル、プロシージャ、関数、パッケージ、およびスキーマにアクセスできるビューを表示するスキーマ をクリックして、**利用可能なカテゴリと操作**ボックス。 または、スキーマのノードを展開して、カテゴリ化を確認できます。  
  
   > [!TIP]
   >  ツリー ビューでのフォーカスがある状態で成果物の名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、 **SCOTT**ノードは、ルート ノードにフォーカスを保持し、入力`SCOTT`します。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 SCOTT のスキーマ ノードを選択すると、および SCOTT ノードの下で利用できる一般カテゴリ ノードが記載されて、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle データベースでユーザーの参照](../../adapters-and-accelerators/adapter-oracle-database/media/c6e02d12-278b-4419-8c8d-d12d0d64f325.gif "c6e02d12-278b-4419-8c8d-d12d0d64f325")  
  
4. をクリックして、**テーブル**scott でテーブルを表示するノード、**利用可能なカテゴリと操作**ボックス。 またはを展開してテーブルの一覧を表示、**テーブル**ノード。  
  
5. テーブルでサポートされる操作を表示するテーブル名をクリックします。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 SCOTT スキーマで使用できるテーブルが記載されて、**カテゴリを選択**ボックス。 EMP テーブルの使用可能な操作が記載されて、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle データベースのテーブルの参照](../../adapters-and-accelerators/adapter-oracle-database/media/6df61a2f-3cd9-486c-9bf5-7968f8f1ce8d.gif "6df61a2f-3cd9-486c-9bf5-7968f8f1ce8d")  
  
6. をクリックして、**プロシージャ**SCOTT のスキーマにアクセスできるプロシージャの一覧表示するノードで、**利用可能なカテゴリと操作**ボックス。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 SCOTT スキーマで使用できる一般カテゴリのノードが記載されて、**カテゴリを選択**ボックス。 SCOTT スキーマで使用できる手順が記載されて、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle データベースでプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-database/media/9826e160-5295-4fdc-bd82-ccd456d89242.gif "9826e160-5295-4fdc-bd82-ccd456d89242")  
  
7. をクリックして、**関数**SCOTT スキーマの関数を表示するノードで、**利用可能なカテゴリと操作**ボックス。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 SCOTT スキーマで使用できる一般カテゴリのノードが記載されて、**カテゴリを選択**ボックス。 SCOTT スキーマで使用可能な関数の一覧は、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle データベースで関数の参照](../../adapters-and-accelerators/adapter-oracle-database/media/ae02731e-7f26-4552-8e40-db797885af01.gif "ae02731e-7f26-4552-8e40-db797885af01")  
  
8. をクリックして、**パッケージ**SCOTT スキーマ用のパッケージを表示するノードで、**利用可能なカテゴリと操作**ボックス。 または、展開パッケージの一覧を表示、**パッケージ**ノード。  
  
9. パッケージでサポートされる操作を表示するパッケージ名をクリックします。  
  
     次に示します[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、パッケージ、および SCOTT スキーマに対して、特定のパッケージでサポートされている操作が一覧表示されます。  
  
     ![Oracle データベースでパッケージの参照](../../adapters-and-accelerators/adapter-oracle-database/media/bts-r2-net-adapter-oracle-tut1-browse-pckgs.gif "bts_R2_NET_Adapter_Oracle_Tut1_Browse_Pckgs")  
  
10. をクリックして、**ビュー** SCOTT スキーマのビューを表示するノードで、**利用可能なカテゴリと操作**ボックス。 またはを展開してビューの一覧を表示、**ビュー**ノード。  
  
11. ビューでサポートされる操作を表示するビューの名前をクリックします。  
  
     次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ビュー、および SCOTT スキーマに対して、特定のビューのサポートされている操作が一覧表示されます。  
  
     ![Oracle データベースでビューの参照](../../adapters-and-accelerators/adapter-oracle-database/media/cc1079bc-c1ca-4c2b-a291-abf87bf1ac4d.gif "cc1079bc-c1ca-4c2b-a291-abf87bf1ac4d")  
  
    > [!NOTE]
    >  アダプター クライアントは、WCF チャネルとサービス モデルを使用して、メタデータのバッチの取得を実行するバッチ サイズを指定できます。  
  
## <a name="searching-for-operations"></a>操作の検索  
 使用して Oracle メタデータを検索中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
- 検索式では、ワイルドカードとエスケープ文字をサポートしています。  
  
- 検索操作を実行するノードのすぐ下にある検索を有効にします。 たとえば、関数を検索するをする必要があります検索する\\[Schema] \Functions します。 複数レベルの検索がサポートされていません。  
  
  次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|_ (アンダースコア)|1 文字と一致します。<br /><br /> たとえば、<curses.h は AB、AC、AD と一致します。|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、%a、AB ABC に一致します。|  
|\ (エスケープ)|% と _ の特別な意味でのエスケープします。<br /><br /> たとえば、A\\_B A_B に一致します。|  
  
> [!NOTE]
>  エスケープ文字は、ワイルドカードではなく、通常の文字として、ワイルドカードを解釈することを示すワイルドカード文字の前に挿入されている文字です。  
  
 詳細については、次を参照してください[Visual Studio での Oracle データベース操作のメタデータを取得。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)  
  
#### <a name="to-search-metadata-in-an-oracle-database"></a>Oracle データベースのメタデータを検索するには  
  
1. 使用して Oracle データベース接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)手順についてはします。  
  
2. [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から、**コントラクト型を選択します**ドロップダウン リストで、アダプターを使用して、受信または送信の操作を検索対象かどうかに基づいてコントラクトの型を選択します。  
  
3. **カテゴリを選択**ボックスに、テーブル、プロシージャ、関数、パッケージ、および検索するビューを含むスキーマをクリックします。 をクリックするスキーマがない場合は、ルート ノードをクリックします。  
  
4. **カテゴリで検索**テキスト ボックスに、特定のスキーマを検索する検索式を入力します。 たとえば、名前に"SC"のスキーマを検索するに次のように入力します。 **% SC** 、テキスト ボックスにします。  
  
5. 検索を開始する右矢印アイコンのボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件を満たすスキーマが一覧表示されます。  
  
6. **カテゴリを選択**ボックスで、スキーマに対応するノードを展開し、データベース項目をクリックし をクリックします内で検索します。 **カテゴリで検索**テキスト ボックスに、特定のデータベースのアイテムを検索する検索式を入力します。  
  
    などを検索し、名前に"EMP"を持つテーブルを次のように選択します**テーブル**、型 **% EMP**で、**カテゴリで検索**テキスト ボックスとボタンをクリックし、。右矢印アイコン。  
  
    次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、検索結果が一覧表示されます。  
  
    ![Oracle データベースのメタデータを検索](../../adapters-and-accelerators/adapter-oracle-database/media/1ee912f8-896e-4b45-ba98-1bbd36b56574.gif "1ee912f8-896e-4b45-ba98-1bbd36b56574")  
  
   > [!NOTE]
   >  アダプター クライアントは、WCF チャネルとサービス モデルを使用して、メタデータの batch-wise 検索を実行するバッチ サイズを指定できます。  
  
## <a name="generating-schema-using-the-consume-adapter-service-add-in-or-add-adapter-metadata-wizard"></a>使用してスキーマを生成する、アダプターを使用する追加のサービスまたはアダプター メタデータのウィザードの追加  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]Oracle データベース アイテムを選択したスキーマを生成します。 参照を呼び出したいアーティファクトの検索し、それらの成果物のスキーマを生成し、Oracle データベース、スキーマに準拠したメッセージを送信できます。 使用して Oracle データベースからメタデータを取得する次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
> [!NOTE]
>  そのカテゴリのサブ-ツリー内のすべての操作を取得するカテゴリ ノードを選択するなどを選択 (テーブルのすべての操作のスキーマの生成) をテーブル全体またはテーブル (たとえば、Insert および Delete) の特定の操作を選択にテーブルに対する操作のみのスキーマを生成します。 ノードの詳細については、[メタデータ ノード IDs3](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)を参照してください。  
  
#### <a name="to-retrieve-metadata-from-an-oracle-database"></a>Oracle データベースからメタデータを取得するには  
  
1. 使用して Oracle データベース接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 参照してください[Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**ドロップダウン リストで、かどうかを実行するアダプターを使用して、受信または送信の操作に基づく契約の種類を選択します。  
  
3. **カテゴリを選択**ボックスに、スキーマのノードを展開します。  
  
4. メタデータを生成するカテゴリを選択します。 たとえば、テーブルのメタデータを生成する場合は、選択**テーブル**します。  
  
5. その特定のカテゴリ ノードを展開し、メタデータを生成する、そのノード内の特定の項目を選択します。  
  
    たとえば、特定のテーブルのメタデータを生成する展開、**テーブル**ノード、および特定のテーブル名を選択します。  
  
   > [!NOTE]
   >  前の手順」の説明に従って、特定のデータベースのアイテムの検索もできます。  
  
6. **利用可能なカテゴリと操作**ボックスで、前の手順で選択したデータベースのアイテムに関連する操作を選択し、をクリックし、**追加**します。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
    次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、選択した操作が一覧表示されます。  
  
    ![Oracle データベースからメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/media/d3950566-8720-4c15-8a16-4ade14bf6221.gif "d3950566-8720-4c15-8a16-4ade14bf6221")  
  
    複数の操作のスキーマを生成する場合は、いくつかで BizTalk プロジェクトのコンパイル エラーを引き起こす可能性のあるこれらのスキーマ間で重複する要素の定義である可能性があります。 たとえば、"Op1"操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、複雑なデータ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も複雑なデータ型"CT1"のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているため、コンパイル エラーが発生します。 このような状況には、次のお勧めします。  
  
   - 1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 これにより、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] "CT1"複雑なデータ型の 1 つだけ定義が生成されます。  
  
   - 複数の異なる実行で複数の操作のスキーマを生成するかどうか[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意のスキーマ型を生成**生成された XSD ファイルには、複雑な一意の名前空間が含まれるように、チェック ボックスデータは、"CT1"を入力します。  
  
7. **[OK]** をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
    既定では、名前付け規則で、ファイルが作成"OracleDBBindingSchema\<n\>.xsd"ここで、' n ' 1、2、およびでは、作成されたスキーマ ファイルの数によってにすることができます。 または、スキーマ ファイルにカスタム名を提供の名前を入力、**ファイル名のプレフィックス**テキスト ボックス。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]名前付け規則で今すぐスキーマ ファイルを作成します\<ファイル名のプレフィックス\>スキーマ\<n\>.xsd。  
  
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ときに指定されたバインドのプロパティを含むバインド ファイル (XML ファイル) も作成操作と操作を呼び出すための SOAP アクションのスキーマを生成します。 接続 URI、バインドのプロパティを持つ WCF カスタム ポートを作成する BizTalk Server 管理コンソールでこのバインド ファイルをインポートして、SOAP アクションを設定します。 詳細については、[Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)を参照してください。  
   > 
   > [!IMPORTANT]
   >  使用して、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]バインド ファイルを生成しません。  
  
8. **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>WCF クライアントまたは WCF サービス コントラクトを使用して、生成、プラグインのアダプター サービス参照の追加  
 使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]いずれかの送信操作の WCF クライアント コードまたは受信操作のための WCF サービス コードを生成します。  
  
#### <a name="to-retrieve-metadata-from-an-oracle-database"></a>Oracle データベースからメタデータを取得するには  
  
1. [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**コントラクト型を選択します**ドロップダウン リストで、かどうかを実行する (POLLINGSTMT) の受信または送信操作に基づく契約の種類を選択します。  
  
2. 参照または (Oracle データベース テーブルの場合) などのカテゴリまたは特定の WCF クライアント (または WCF サービス コントラクト) を生成する操作を検索します。   
   たとえば、参照、SCOTT に含まれる操作です。EMP テーブルに、**カテゴリを選択**ボックス。  
  
   1.  ルート ノードを展開 (**/**) に Oracle データベースの表示、スキーマを参照してください。  
  
   2.  [ルート] ノードで、展開、 **SCOTT** SCOTT スキーマの公開されているカテゴリを表示するノード。  
  
   3.  下、 **SCOTT**ノード、展開、**テーブル**SCOTT スキーマ、テーブルを表示するノードが登場してきました。  
  
   4.  で、**テーブル**ノードの選択、 **EMP**ノード。 EMP テーブルの表示操作が記載されて、**利用可能なカテゴリと操作**ボックス。  
  
3. **利用可能なカテゴリと操作**ボックスに、操作は、カテゴリをクリックして、WCF クライアント (または WCF サービス コントラクト) を生成する選択**追加**します。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
    次に示します、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] scott Insert および Update 操作とします。EMP テーブルを選択します。  
  
    ![Select および Update 操作が選択されます。](../../adapters-and-accelerators/adapter-oracle-database/media/4c41ac7b-784a-494c-ac82-c007e22a4fdf.gif "4c41ac7b-784a-494c-ac82-c007e22a4fdf")  
  
   > [!IMPORTANT]
   >  によって送信操作 (またはカテゴリ) を選択で、複数の 1 つの WCF クライアント クラスを生成できます。 詳細については、[WCF クライアントまたは Oracle データベース ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)を参照してください。  
  
4. ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
   1. をクリックして**詳細オプション**を開く、**詳細オプション**ボックス。  
  
   2. **オプションの高度な**ボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、非同期メソッドは、WCF クライアントの生成または構成ファイルの生成を無効にするかどうかを選択できます。  
  
   3. **シリアライザー**使用されるシリアライザーを選択します。  
  
      次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーとしないその他のオプションが選択されているため)。  
  
      ![高度なオプションが既定の設定をボックス](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      オプションで構成できる、**詳細オプション**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスはいくつかの使用可能なオプションに相当します。 これらのオプションの詳細については、[ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)を参照してください。
  
5. **[OK]** をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアント クラス (または WCF サービスのインターフェイス) を保存し、操作と、プロジェクト ディレクトリで選択したカテゴリのヘルパー コード。 既定では、構成ファイルも保存されます。 受信と送信操作の若干異なるファイルが生成されます。詳細については、[WCF クライアントまたは Oracle データベース ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)を参照してください。  
  
   記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリ ノードを選択する場合は、すべてのノードとそのサブ ノードで使用可能な操作が選択されます。 たとえば、すべての EMP テーブルの表示操作用の WCF クライアントを生成するにはノードを選択、EMP;SCOTT スキーマ内のテーブルのすべての WCF クライアントを生成するには、テーブル ノード; を選択しますなどなど。  
  
## <a name="see-also"></a>参照  
[Visual Studio での Oracle データベース操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)