---
title: 参照、検索、および Siebel 操作のメタデータを取得 |Microsoft Docs
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a5edfbf9a5f1433721b3ce11a63d38aa259a4c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371979"
---
# <a name="browse-search-and-get-metadata-for-siebel-operations"></a>参照、検索、および Siebel 操作のメタデータを取得
このセクションを使用する方法について説明します、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 これらを使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ことができます、コンポーネント。  
  
- メタデータを取得する対象の操作を参照します。  
  
- メタデータを取得する対象の操作を検索します。  
  
- 選択した操作のメッセージ スキーマを追加し、ポートのバインドの構成ファイル、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトを使用する場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
- 使用する場合に、BizTalk 以外のプログラミング プロジェクトに WCF クライアント クラスまたは選択した操作と構成ファイル (app.config) の WCF サービス コントラクト (インターフェイス) を追加、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、3 つすべてのコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 次の参照、検索、またはターゲットの操作のメタデータを取得する前に、Siebel システムに接続する必要があります。 使用する場合は、Siebel システムに接続する方法については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio で Siebel システムへの接続](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)します。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 使用してメタデータを閲覧中に、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェス。  
  
-   挿入、クエリ、更新、および削除するなどの Siebel ビジネス コンポーネントで実行できる操作にします。  
  
-   アダプターのクライアントで呼び出すことができるビジネス サービス メソッド。  
  
> [!NOTE]
>  使用して、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、Windows インターフェイスを使用して、カテゴリと操作のノードを参照することができます。  
  
 Siebel メタデータの参照の詳細については、次を参照してください[参照、検索、および Siebel メタデータの取得。](../../adapters-and-accelerators/adapter-siebel/browse-search-and-get-siebel-metadata.md) 
  
 使用して Siebel システムのメタデータを参照する次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-browse-metadata-in-a-siebel-system"></a>Siebel システムでメタデータを参照するには  
  
1. 使用して Siebel システムへの接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio で Siebel システムへの接続](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**ドロップダウン リストで、かどうかを実行するアダプターを使用して、受信または送信の操作に基づく契約の種類を選択します。  
  
3. **カテゴリを選択**リスト ボックス、**ビジネス オブジェクト**と**ビジネス サービス**ノード。 をクリックして、**ビジネス オブジェクト**でビジネス オブジェクトの一覧を表示するノード、**利用可能なカテゴリと操作**ボックス。 またはを展開してビジネス オブジェクトの一覧を表示、**ビジネス オブジェクト**ノード。  
  
   > [!TIP]
   >  ツリー ビューでのフォーカスがある状態で成果物の名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、**アカウント**ビジネス オブジェクトにフォーカスを保持、**ビジネス オブジェクト**ノード、および入力し、 `Account`。  
  
4. 特定のビジネス オブジェクトのビジネス コンポーネントの一覧を表示するビジネス オブジェクトをクリックします。 また、ビジネス オブジェクトを展開して、ビジネス コンポーネントの一覧を確認できます。  
  
5. 特定のビジネス コンポーネントでサポートされる操作の一覧を表示するビジネス コンポーネントをクリックします。  
  
    次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、ビジネス オブジェクト、ビジネス コンポーネント、およびサポート対象の操作が一覧表示されます。  
  
    ![Siebel ビジネス コンポーネントの参照](../../adapters-and-accelerators/adapter-siebel/media/11c63383-4269-4ba0-909b-e2cbec7eae04.gif "11c63383-4269-4ba0-909b-e2cbec7eae04")  
  
6. をクリックして、**ビジネス サービス**のビジネス サービスの一覧を表示するノード、**利用可能なカテゴリと操作**ボックス。 またはを展開してテーブルの一覧を表示、**ビジネス サービス**ノード。  
  
7. 対応するビジネス サービス メソッドの一覧を表示するビジネス サービスをクリックします。  
  
    次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、ビジネス サービスと対応するビジネス サービス メソッドが一覧表示されます。  
  
    ![Siebel ビジネス サービスの参照](../../adapters-and-accelerators/adapter-siebel/media/60405c18-6035-42a5-851f-a0ed6d0570d6.gif "60405c18-6035-42a5-851f-a0ed6d0570d6")  
  
## <a name="searching-metadata"></a>メタデータの検索  
 使用して Siebel メタデータの検索中に[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]:  
  
- ワイルドカードとエスケープ文字をサポートしています。  
  
- 検索操作を実行するノードのすぐ下にある検索を有効にします。 たとえば、ビジネス サービスを検索するをする必要があります検索する \Business サービス。  
  
  次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|? (疑問符)|1 文字と一致します。<br /><br /> たとえば、A か。AB、AC、AD と一致します。|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB ABC に一致します。|  
  
 使用して Siebel システム メタデータを検索する次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-search-metadata-in-a-siebel-system"></a>Siebel システムでメタデータを検索するには  
  
1. 使用して Siebel システムへの接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio で Siebel システムへの接続](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)手順についてはします。  
  
2. **選択コントラクト型**ドロップダウン リスト、選択、**クライアント (送信操作)** コントラクト。  
  
3. **カテゴリを選択**ボックスで、、**ビジネス オブジェクト**ノード。  
  
4. 特定のビジネス オブジェクトを検索するには、クリックして、**ビジネス オブジェクト**内のノード、**カテゴリで検索**テキスト検索式を入力します。 たとえば、「アカウント」で始まる名前を持つビジネス オブジェクトを検索するに次のように入力します。**アカウント\\***、テキスト ボックスにします。  
  
5. 検索を開始する右矢印アイコンのボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件に適合するビジネス オブジェクトが一覧表示されます。  
  
6. ビジネス オブジェクトをクリックして、ビジネス オブジェクトの下の特定のビジネス コンポーネントとで検索する、**カテゴリで検索**検索式がテキスト ボックスに入力してください。 たとえば、「アカウント」で始まる名前を持つビジネス コンポーネントを検索する次のように入力します。**アカウント\\***、テキスト ボックスにします。  
  
7. 検索を開始する右矢印アイコンのボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件に適合するビジネス コンポーネントが一覧表示されます。  
  
8. ビジネス コンポーネントの特定の操作を検索するには、ビジネス コンポーネントをクリックし、、**カテゴリで検索**検索式がテキスト ボックスに入力してください。 たとえば、"Query"で始まる名前を持つ操作を検索するに次のように入力します。**クエリ\\***、テキスト ボックスにします。  
  
9. 検索を開始する右矢印アイコンのボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件に適合するビジネス コンポーネントが一覧表示されます。  
  
     次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、検索結果が一覧表示されます。  
  
     ![ビジネス コンポーネントを検索](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-04-search.gif "SIEBEL-ADPT-Lesson1-Step3-04-search")  
  
     検索するのと同様の手順を実行、**ビジネス サービス**ノード。  
  
## <a name="generating-schema-for-biztalk-projects"></a>BizTalk プロジェクトのスキーマを生成します。  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]Siebel 成果物を選択したスキーマを生成します。 参照を呼び出したいアーティファクトの検索し、それらの成果物のスキーマを生成し、Siebel に、スキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  そのカテゴリのサブ-ツリー内のすべての操作を取得するカテゴリ ノードを選択することができます: たとえば、ビジネス コンポーネント (ビジネス コンポーネントのすべての操作のスキーマの生成) をまたは (ビジネス コンポーネントで特定の操作を選択を選択できます例、Insert および Delete) これらの操作のスキーマを生成します。 ノードの詳細については、次を参照してください。[メタデータ ノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)します。  
  
#### <a name="to-generate-schema-for-siebel-artifacts"></a>Siebel の成果物のスキーマを生成するには  
  
1. 使用して Siebel システムへの接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 参照してください[Visual Studio で Siebel システムへの接続](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)手順についてはします。  
  
2. **選択コントラクト型**ドロップダウン リスト、選択、**クライアント (送信操作)** コントラクト。  
  
3. **カテゴリを選択**ボックスに、ビジネス オブジェクトまたはビジネス サービス ノードを展開します。  
  
4. **利用可能なカテゴリと操作**ボックスで、ビジネス コンポーネントまたはビジネス サービスをクリックして、メタデータを生成する、対応する操作を選択**追加**します。 選択した機能領域または操作に表示されます、**カテゴリと操作を追加**ボックス。  
  
    次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、選択した操作が一覧表示されます。  
  
    ![ビジネス オブジェクトのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-05-get.gif "SIEBEL-ADPT-Lesson1-Step3-05-get")  
  
    複数の操作のスキーマを生成する場合は、いくつかで BizTalk プロジェクトのコンパイル エラーを引き起こす可能性のあるこれらのスキーマ間で重複する要素の定義である可能性があります。 たとえば、"Op1"操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、複雑なデータ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も複雑なデータ型"CT1"のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているため、コンパイル エラーが発生します。 このような状況には、次のお勧めします。  
  
   - 1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 これにより、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] "CT1"複雑なデータ型の 1 つだけ定義が生成されます。  
  
   - 複数の異なる実行で複数の操作のスキーマを生成するかどうか[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意のスキーマ型を生成**生成された XSD ファイルには、複雑な一意の名前空間が含まれるように、チェック ボックスデータは、"CT1"を入力します。  
  
5. **[OK]** をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
    既定では、名前付け規則で、ファイルが作成"SiebelBindingSchema\<n\>.xsd"ここで、' n ' 1、2、およびでは、作成されたスキーマ ファイルの数によってにすることができます。 または、スキーマ ファイルにカスタム名を提供の名前を入力、**ファイル名のプレフィックス**テキスト ボックス。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]名前付け規則で今すぐスキーマ ファイルを作成します\<ファイル名のプレフィックス\>スキーマ\<n\>.xsd。  
  
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ときに指定されたバインドのプロパティを含むバインド ファイル (XML ファイル) も作成操作と操作を呼び出すための SOAP アクションのスキーマを生成します。 接続 URI、バインドのプロパティを持つ WCF カスタム ポートを作成する BizTalk Server 管理コンソールでこのバインド ファイルをインポートして、SOAP アクションを設定します。 詳細については、次を参照してください。 [Siebel にポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)します。  
  
6. **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
## <a name="generating-a-wcf-client-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF クライアントの生成、プラグインのアダプター サービス参照の追加  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] Siebel システムに対する送信操作の WCF クライアント コードを生成します。  
  
#### <a name="to-generate-a-wcf-client"></a>WCF クライアントを生成するには  
  
1. [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**コントラクト型を選択します**ドロップダウン リスト、選択**クライアント (送信操作)** します。  
  
2. **カテゴリを選択**ボックスに、ビジネス オブジェクトまたはビジネス サービス ノードを展開します。  
  
3. **利用可能なカテゴリと操作**ボックスで、ビジネス コンポーネント、ビジネス サービス、またはをクリックして、WCF クライアントを生成する、対応する操作を選択**追加**します。 選択した機能領域または操作に表示されます、**カテゴリと操作を追加**ボックス。 記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリのノードを選択した場合は、すべてのノードとそのサブ ノードで使用可能な操作が選択されます。  
  
   > [!IMPORTANT]
   >  によって、カテゴリと、選択した操作は、複数の WCF クライアント クラスが生成されます。 詳細については、次を参照してください。 [WCF クライアントまたは Siebel ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)します。  
  
4. ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
   1. 開くには、**オプションの高度な**ボックスで、**オプションの高度な**します。  
  
   2. **オプションの高度な**ボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、WCF クライアントは、非同期メソッドが生成または構成ファイルの生成を無効にできるかどうかを選択できます。  
  
   3. **シリアライザー**、使用するシリアライザーを選択します。  
  
      次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーとしないその他のオプションが選択されているため)。  
  
      ![高度なオプションが既定の設定をボックス](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      オプションで構成できる、**詳細オプション**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスはいくつかの使用可能なオプションに相当します。 これらのオプションの詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)します。
  
5. **[OK]** をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントの操作と、プロジェクト ディレクトリに選択したカテゴリのクラスとヘルパー コードを保存します。 既定では、構成ファイルも保存されます。 詳細については、次を参照してください。 [WCF クライアントまたは Siebel ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)します。  
  
## <a name="see-also"></a>参照  
 [Visual Studio で Siebel 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)