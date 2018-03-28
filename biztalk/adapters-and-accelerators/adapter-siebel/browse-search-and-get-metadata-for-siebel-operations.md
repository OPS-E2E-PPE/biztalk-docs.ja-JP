---
title: 参照、検索、および Siebel 操作のメタデータを取得 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving
- how to, browse metadata
- how to, retrieve metadata
- retrieving, metadata
- metadata, browsing
- browsing, metadata
- metadata, searching
- how to, seach metadata
- searching, metadata
ms.assetid: 7e474d8e-b030-47ea-b1b6-8048cddbba8a
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68e7d8dc1b067096f118eb1145554edf0b11f605
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="browse-search-and-get-metadata-for-siebel-operations"></a>参照、検索、および Siebel 操作のメタデータを取得
このセクションで説明を使用する方法については、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。 これらを使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネント、することができます。  
  
-   メタデータを取得する対象の操作を参照します。  
  
-   メタデータを取得する対象の操作を検索します。  
  
-   選択した操作のメッセージ スキーマを追加し、ポートのバインドの構成ファイル、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトを使用する場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
-   WCF クライアント クラスまたは WCF サービス コントラクト (インターフェイス) を選択した操作と構成ファイル (app.config) を使用する場合、BizTalk 以外のプログラミング プロジェクトを追加、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、3 つすべてのコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 次の参照、検索、または操作を指定のメタデータを取得する前に、Siebel システムに接続する必要があります。 使用すると、Siebel システムに接続する方法については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Siebel システムへの接続](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)です。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 使用してメタデータの参照中に、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェス。  
  
-   挿入、クエリ、更新、および削除するなど、Siebel ビジネス コンポーネントで実行できる操作にします。  
  
-   アダプターのクライアントから呼び出すことができるビジネス サービスのメソッドです。  
  
> [!NOTE]
>  使用して、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Windows のインターフェイスを使用して、カテゴリと操作のノードを参照することができます。  
  
 Siebel メタデータの参照の詳細については、次を参照してください[参照、検索、および Siebel メタデータの取得。](../../adapters-and-accelerators/adapter-siebel/browse-search-and-get-siebel-metadata.md) 
  
 次の手順を使用して Siebel システムのメタデータの参照を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-browse-metadata-in-a-siebel-system"></a>Siebel システムでメタデータを参照するには  
  
1.  使用して Siebel システムへの接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Siebel システムへの接続](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行するアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**リスト ボックス、**ビジネス オブジェクト**と**ビジネス サービス**ノード。 クリックして、**ビジネス オブジェクト**でビジネス オブジェクトの一覧を表示するノード、**利用可能なカテゴリと操作**ボックス。 または、ビジネス オブジェクトの一覧を表示を展開して、**ビジネス オブジェクト**ノード。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、アイテムの名前を入力して、**カテゴリを選択**ボックス。 例についてに移動すること、**アカウント**ビジネス オブジェクトにフォーカスを保持、**ビジネス オブジェクト**ノード、および入力`Account`です。  
  
4.  特定のビジネス オブジェクトのビジネス コンポーネントの一覧を表示するビジネス オブジェクトをクリックします。 また、ビジネス オブジェクトを展開して、ビジネス コンポーネントの一覧を表示できます。  
  
5.  特定のビジネス コンポーネントのサポートされている操作の一覧を表示するビジネス コンポーネントをクリックします。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、ビジネス オブジェクト、ビジネス コンポーネント、およびサポートされている操作を一覧表示します。  
  
     ![Siebel ビジネス コンポーネントの参照](../../adapters-and-accelerators/adapter-siebel/media/11c63383-4269-4ba0-909b-e2cbec7eae04.gif "11c63383-4269-4ba0-909b-e2cbec7eae04")  
  
6.  クリックして、**ビジネス サービス**のビジネス サービスの一覧を表示するノード、**利用可能なカテゴリと操作**ボックス。 または、テーブルの一覧を表示を展開して、**ビジネス サービス**ノード。  
  
7.  対応するビジネス サービス メソッドの一覧を表示するビジネス サービス をクリックします。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、ビジネス サービスおよびビジネス サービスの対応するメソッドを一覧表示します。  
  
     ![Siebel ビジネス サービスの参照](../../adapters-and-accelerators/adapter-siebel/media/60405c18-6035-42a5-851f-a0ed6d0570d6.gif "60405c18-6035-42a5-851f-a0ed6d0570d6")  
  
## <a name="searching-metadata"></a>メタデータの検索  
 使用して Siebel メタデータの検索中に[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]:  
  
-   ワイルドカードおよびエスケープ文字をサポートしています。  
  
-   検索操作を実行するノードのすぐ下にある検索を有効にします。 たとえば、ビジネス サービスを検索するにする必要があります検索する \Business サービス の下。  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|? (疑問符 (?))|1 文字と一致します。<br /><br /> たとえば、A か。AB、AC、AD と一致します。|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB、ABC に一致します。|  
  
 Siebel システムを使用して、メタデータを検索する次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-search-metadata-in-a-siebel-system"></a>Siebel システムでメタデータを検索するには  
  
1.  使用して Siebel システムへの接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Siebel システムへの接続](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リスト、選択、**クライアント (送信操作)**コントラクト。  
  
3.  **カテゴリを選択**ボックスで、クリックして、**ビジネス オブジェクト**ノード。  
  
4.  特定のビジネス オブジェクトを検索する をクリックして、**ビジネス オブジェクト**内のノード、**カテゴリで検索**テキスト ボックスし、検索式を入力します。 たとえば、「アカウント」で始まる名前のあるビジネス オブジェクトの検索は、次のように入力します。**アカウント\*** 、テキスト ボックスにします。  
  
5.  検索を開始する右矢印アイコンが付いたボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件に適合するビジネス オブジェクトが一覧表示されます。  
  
6.  ビジネス オブジェクトの下の特定のビジネス コンポーネント ビジネス オブジェクトと内を検索するには、**カテゴリで検索**テキスト ボックスに、検索式を入力してください。 たとえば、「アカウント」で始まる名前のあるビジネス コンポーネントの検索は、次のように入力します。**アカウント\*** 、テキスト ボックスにします。  
  
7.  検索を開始する右矢印アイコンが付いたボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件に適合するビジネス コンポーネントが一覧表示されます。  
  
8.  ビジネス コンポーネントの特定の操作を検索するには、ビジネス コンポーネントをクリックし、、**カテゴリで検索**テキスト ボックスに、検索式を入力してください。 たとえば、"Query"で始まる名前を持つ操作の検索は、次のように入力します。**クエリ\*** 、テキスト ボックスにします。  
  
9. 検索を開始する右矢印アイコンが付いたボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件に適合するビジネス コンポーネントが一覧表示されます。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、検索結果の一覧を表示します。  
  
     ![ビジネス コンポーネントを検索](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-04-search.gif "SIEBEL-ADPT-Lesson1-Step3-04-search")  
  
     検索するのと同様の手順を実行、**ビジネス サービス**ノード。  
  
## <a name="generating-schema-for-biztalk-projects"></a>BizTalk プロジェクトのスキーマを生成します。  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]Siebel の選択した成果物のためのスキーマを生成します。 参照して、呼び出し先のアイテムの検索し、それらの成果物のスキーマを生成し、Siebel に、スキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  そのカテゴリのサブツリー内のすべての操作を返すカテゴリ ノードを選択することができます: などのビジネス コンポーネント (スキーマを生成するすべての操作、ビジネス コンポーネントで) または (用ビジネス コンポーネントで特定の select 操作を選択できます例で挿入および削除) 操作だけスキーマを生成します。 ノードの詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)です。  
  
#### <a name="to-generate-schema-for-siebel-artifacts"></a>Siebel の成果物のためのスキーマを生成するには  
  
1.  使用して Siebel システムへの接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 参照してください[Visual Studio での Siebel システムへの接続](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リスト、選択、**クライアント (送信操作)**コントラクト。  
  
3.  **カテゴリを選択**ボックスで、ビジネス オブジェクトまたはビジネス サービス ノードを展開します。  
  
4.  **利用可能なカテゴリと操作**ボックスで、ビジネス コンポーネントまたはビジネス サービスをメタデータを生成し、をクリックする、対応する操作を選択**追加**です。 選択した機能領域または操作に表示されます、**カテゴリと操作を追加**ボックス。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、選択した操作を一覧表示します。  
  
     ![ビジネス オブジェクトのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-05-get.gif "SIEBEL-ADPT-Lesson1-Step3-05-get")  
  
     複数の操作のスキーマを生成する場合は、BizTalk プロジェクトのコンパイルに失敗する可能性がありますをこれらのスキーマ間で重複する要素定義である可能性があります。 たとえば、"Op1"、操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、複雑なデータ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も複雑なデータ型"CT1"のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているために、コンパイル エラーが表示されます。 このような場合に、次のお勧めします。  
  
    -   1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 これにより、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]複雑なデータ型"CT1"の定義は 1 つだけが生成されます。  
  
    -   複数の異なる実行で複数の操作のスキーマを生成するかどうかは[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意なスキーマ型を生成**生成される XSD ファイルには、複雑な一意の名前空間が含まれるように、チェック ボックスデータは、"CT1"を入力します。  
  
5.  **[OK]**をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
     既定では、ファイルを作成して、名前付け規則"SiebelBindingSchema\<n\>.xsd"ここで、' n ' 1、2、および作成したスキーマ ファイルの数によってを指定できます。 名前を入力して、スキーマ ファイルにカスタムの名前を指定する代わりに、**ファイル名のプレフィックス**テキスト ボックス。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、命名規則で今すぐスキーマ ファイルが作成されます\<ファイル名のプレフィックス\>スキーマ\<n\>.xsd です。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]時に指定されたバインディングのプロパティを含むバインド ファイル (XML ファイル) も作成操作と、操作を呼び出す SOAP アクションのスキーマを生成します。 BizTalk Server 管理コンソールで、接続 URI、バインドのプロパティで WCF カスタム ポートを作成するには、このバインド ファイルをインポートして、SOAP アクションを設定します。 詳細については、次を参照してください。 [Siebel するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)です。  
  
6.  **[ファイル]** メニューの **[すべてを保存]**をクリックします。  
  
## <a name="generating-a-wcf-client-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF クライアントを生成する、プラグイン アダプター サービス参照の追加  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] Siebel システムに対する送信操作の WCF クライアント コードを生成します。  
  
#### <a name="to-generate-a-wcf-client"></a>WCF クライアントを生成するには  
  
1.  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**選択コントラクト型**ドロップダウン リスト、選択**クライアント (送信操作)**です。  
  
2.  **カテゴリを選択**ボックスで、ビジネス オブジェクトまたはビジネス サービス ノードを展開します。  
  
3.  **利用可能なカテゴリと操作**ボックスで、ビジネス コンポーネント、ビジネス サービス、または WCF クライアントを生成し、をクリックする、対応する操作を選択**追加**です。 選択した機能領域または操作に表示されます、**カテゴリと操作を追加**ボックス。 記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリ ノードを選択する場合は、すべてのノードとそのサブ ノードで使用可能な操作が選択します。  
  
    > [!IMPORTANT]
    >  カテゴリと選択した操作では、によっては、1 つ以上の WCF クライアント クラスが生成される可能性があります。 詳細については、次を参照してください。 [WCF クライアントまたは Siebel ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)です。  
  
4.  ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
    1.  開くには、**オプションの高度な**ボックスで、クリックして**詳細オプション**です。  
  
    2.  **オプションの高度な**下にあるボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、WCF クライアントは、非同期メソッドが生成または構成ファイルの生成を無効にすることができるかどうかを選択できます。  
  
    3.  **シリアライザー**、ために使用されるシリアライザーを選択します。  
  
     次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーしない他のオプションが選択されているため)。  
  
     ![高度なオプション ボックスの既定の設定](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     構成できるオプション、**オプションの高度な**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスが使用可能なオプションの一部に相当します。 これらのオプションの詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)です。
  
5.  **[OK]**をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントの操作と、プロジェクト ディレクトリに選択したカテゴリのクラスとヘルパー コードを保存します。 既定では、構成ファイルも保存されます。 詳細については、次を参照してください。 [WCF クライアントまたは Siebel ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)です。  
  
## <a name="see-also"></a>参照  
 [Visual Studio で Siebel 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)