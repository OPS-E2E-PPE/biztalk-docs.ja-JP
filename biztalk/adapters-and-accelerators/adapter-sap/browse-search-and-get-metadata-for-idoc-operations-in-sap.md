---
title: 参照、検索、および SAP の IDOC 操作のメタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF client, generating for IDOC operations
- IDOCs, searching
- searching, IDOCs
- IDOCs, browsing
- browsing, IDOCs
- IDOC operations, generating schema for
- IDOC operations
ms.assetid: 44d05129-ce06-4a10-bf28-9d3519a02a7a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 536a7ab77073c668378d65ffa29309a14a8159ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374135"
---
# <a name="browse-search-and-get-metadata-for-idoc-operations-in-sap"></a>参照、検索、および SAP の IDOC 操作のメタデータの取得
このセクションでは、参照、検索、および SAP の IDOC を使用して操作のメタデータを取得する方法の説明[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 手順のほとんどは、すべての 3 つのユーザー インターフェイスで同じです。 任意の場所、関連するユーザー インターフェイスに適用される場合、別の手順が提供されます。  
  
 次のセクションで説明する手順を実行する前にいる必要があります。  
  
- 作成、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
- 使用して SAP システムに接続されている[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 手順を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)スキーマまたは Idoc 用の WCF クライアントを生成する SAP システムに接続する前に特定のバインド プロパティを設定する必要がありますに注意してください。  
  
  - GenerateFlatFileCompatibleIdocSchema  
  
  - ReceiveIdocFormat  
  
  - FlatFileSegmentIndicator  
  
    これらのプロパティは、SAP システムから IDOC のメタデータを取得する方法を制御します。 これらのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。 バインドのプロパティを設定する方法の手順を参照してください[SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)します。  
  
## <a name="browsing-idocs-in-an-sap-system"></a>SAP システムでの Idoc の閲覧  
 使用してメタデータを閲覧中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスは、SAP システムから Idoc を送受信するための操作を分離します。  
  
- **送信**と**受信**します。 アダプターのクライアントは、厳密に型指定されたスキーマを使用して SAP システムから Idoc を送受信するこれらの操作を使用できます。 アダプターは、IDOC ごとに個別にこれらの操作を表示し、それぞれの IDOC のノードで使用可能な。  
  
- **SendIdoc**と**ReceiveIdoc**します。 アダプターのクライアントは、厳密に型指定のスキーマを使用して SAP システムから Idoc を送受信するこれらの操作を使用できます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスの 1 つのみ**SendIdoc**と**ReceiveIdoc** Idoc のすべての操作。 これらの操作はの直下にある使用可能な**IDOC**ノード。  
  
  Idoc を使用して SAP システムで参照する次の手順を実行、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-browse-idocs-in-an-sap-system"></a>Idoc を SAP システムで参照するには  
  
1. 使用して SAP サーバーに接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での SAP システムに接続する](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**ドロップダウン リストで、かどうかを実行するアダプターを使用して、受信または送信の操作に基づく契約の種類を選択します。  
  
3. **カテゴリを選択**ボックスに、IDOC ノード内の IDOC メッセージ型を参照してください。 をクリックして、**利用可能なカテゴリと操作**ボックス。 またはも確認できます IDOC メッセージの種類、IDOC ノードを展開します。  
  
   > [!TIP]
   >  ツリー ビューでのフォーカスがある状態で成果物の名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、 **ACC_BILLING** IDOC メッセージ型を常にフォーカスを**IDOC**ノード、および入力`ACC_BILLING`。  
  
    次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] IDOC の一覧を表示するメッセージの種類。 ルートの IDOC ノードも明らかになります、 **SendIdoc** SAP システムを厳密に型指定の Idoc を送信するオプション。  
  
    ![IDOC でのメッセージの種類の参照](../../adapters-and-accelerators/adapter-sap/media/3b8701c2-0530-4577-817c-92af0cd9a770.gif "3b8701c2-0530-4577-817c-92af0cd9a770")  
  
   > [!NOTE]
   >  受信シナリオ、IDOC のルート ノード サーフェスを**ReceiveIdoc**弱くを受信する操作が Idoc を入力します。  
  
4. 関連する IDOC の種類を表示する IDOC メッセージの種類をクリックします。 次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]特定 IDOC での IDOC タイプのメッセージの種類。  
  
    ![IDOC の種類の参照](../../adapters-and-accelerators/adapter-sap/media/fee70ed2-74c1-4c91-b2fd-3d281a335145.gif "fee70ed2-74c1-4c91-b2fd-3d281a335145")  
  
5. IDOC タイプの異なるバージョンを参照する IDOC の種類をクリックします。 次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]特定 IDOC タイプのバージョン。  
  
    ![IDOC タイプのバージョンを参照](../../adapters-and-accelerators/adapter-sap/media/35603fac-ff48-40b1-bb51-bd0548715cd3.gif "35603fac-ff48-40b1-bb51-bd0548715cd3")  
  
6. その IDOC タイプでサポートされている操作を表示する IDOC タイプのバージョンをクリックします。 次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] IDOC タイプの特定バージョンのサポートされている操作。  
  
    ![IDOC タイプの参照操作](../../adapters-and-accelerators/adapter-sap/media/f37624b4-f1f2-4d44-8708-01eb51a2d2a7.gif "f37624b4-f1f2-4d44-8708-01eb51a2d2a7")  
  
## <a name="searching-idocs-in-an-sap-system"></a>SAP システムでの Idoc の検索  
 Idoc のメタデータを使用して SAP システム内で検索中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- 検索式では、ワイルドカード文字をサポートしています。  
  
- 検索操作を実行するノードのすぐ下にある検索を有効にします。  
  
  次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|+ (プラス)|1 つだけの文字と一致します。<br /><br /> たとえば、A + と一致する AB、AC、AD|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB ABC に一致します。|  
  
 アダプターでサポートされている特殊文字の詳細については、次を参照してください。 [WCF LOB Adapter SDK を使用してバインドのプロパティとしてアダプターの設定を公開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)します。
  
 次の手順を使用した SAP システム内の Idoc の検索を実行、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-search-idocs-in-an-sap-system"></a>Idoc を SAP システムで検索するには  
  
1. 使用して SAP サーバーに接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**ドロップダウン リストで、アダプターを使用して、受信または送信の操作を検索対象かどうかに基づいてコントラクトの型を選択します。  
  
3. **カテゴリを選択**ボックスに、IDOC のノードをクリックします。  
  
   > [!IMPORTANT]
   >  Idoc のルート レベルでのみを検索することができます。  
  
4. **カテゴリで検索**テキスト ボックスに、特定の IDOC メッセージの種類を検索する検索式を入力します。 たとえば、名前に"MATMAS"のある Idoc を検索するに次のように入力します。 * MATMAS\* 、テキスト ボックスにします。  
  
5. 検索を開始する右矢印アイコンのボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件を満たす Idoc が一覧表示されます。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]検索結果の IDOC の一覧を表示します。  
  
    ![Idoc を SAP システムで検索](../../adapters-and-accelerators/adapter-sap/media/tut1-lesson3-step3-idocsearch.gif "Tut1 Lesson3 Step3 IDOCSearch")  
  
## <a name="generating-schema-for-biztalk-projects"></a>BizTalk プロジェクトのスキーマを生成します。  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SAP アイテムを選択したスキーマを生成します。 参照を呼び出したいアーティファクトの検索し、それらの成果物のスキーマを生成し、SAP システムに、スキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  そのカテゴリのサブ-ツリー内のすべての操作を取得するカテゴリ ノードを選択することができます: (そのグループ内のすべてのバージョンの Idoc のスキーマの生成) する IDOC タイプの選択など、またはそのバージョンのみのスキーマを生成するための IDOC の特定のバージョンを選択します。IDOC します。 ノードの詳細については、次を参照してください。[メタデータ ノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)します。  
  
#### <a name="to-retrieve-metadata-for-idocs"></a>Idoc のメタデータを取得するには  
  
1. 使用して SAP サーバーに接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**ドロップダウン リストで、かどうかを実行するアダプターを使用して、受信または送信の操作に基づく契約の種類を選択します。  
  
3. **カテゴリを選択**ボックスに、IDOC メッセージの種類またはメタデータを生成する IDOC の種類をクリックします。  
  
4. **利用可能なカテゴリと操作**ボックスで、IDOC の種類またはサポート対象のメタデータを生成し、をクリックする操作を選択**追加**します。 選択した IDOC の種類または操作に表示されます、**カテゴリと操作を追加**ボックス。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]選択された Idoc の一覧を表示します。  
  
    ![Idoc のメタデータ取得](../../adapters-and-accelerators/adapter-sap/media/d9765c62-68b2-4313-9292-9265ab095e2e.gif "d9765c62-68b2-4313-9292-9265ab095e2e")  
  
    複数の操作のスキーマを生成する場合は、いくつかで BizTalk プロジェクトのコンパイル エラーを引き起こす可能性のあるこれらのスキーマ間で重複する要素の定義である可能性があります。 たとえば、"Op1"操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、複雑なデータ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も複雑なデータ型"CT1"のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているため、コンパイル エラーが発生します。 このような状況には、次のお勧めします。  
  
   - 1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 これにより、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] "CT1"複雑なデータ型の 1 つだけ定義が生成されます。  
  
   - 複数の異なる実行で複数の操作のスキーマを生成するかどうか[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意のスキーマ型を生成**生成された XSD ファイルには、複雑な一意の名前空間が含まれるように、チェック ボックスデータは、"CT1"を入力します。  
  
5. **[OK]** をクリックします。 スキーマ ファイルは、IDOC プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
   > [!NOTE]
   >  使用する場合[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、名前付け規則で既定では、ファイルの作成"SAPBinding\<n\>.xsd"ここで、' n '、1 を指定できます、2 などによって作成されたスキーマ ファイルの数にします。 または、スキーマ ファイルにカスタム名を提供の名前を入力、**ファイル名のプレフィックス**テキスト ボックス。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]名前付け規則で今すぐスキーマ ファイルを作成します\<ファイル名のプレフィックス\>\<n\>.xsd。  
   > 
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中に指定したバインドのプロパティを含むバインド ファイル (XML ファイル) も作成操作と操作を呼び出すための SOAP アクション。 接続 URI、バインドのプロパティを持つ WCF カスタム ポートを作成する BizTalk Server 管理コンソールでこのバインド ファイルをインポートして、SOAP アクションを設定します。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)します。  
  
6. **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
## <a name="generating-a-wcf-client-for-idoc-operations-using-the-add-adapter-service-reference-plug-in"></a>使用して IDOC 操作の WCF クライアントの生成、プラグインのアダプター サービス参照の追加  
 使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]いずれかの SAP システムへの Idoc を送信する WCF クライアント コードまたは SAP システムから Idoc を受信する WCF サービス コントラクトを生成します。  
  
#### <a name="to-generate-a-wcf-client-or-a-wcf-service-contract-for-idocs"></a>Idoc の WCF クライアントまたは WCF サービス コントラクトを生成するには  
  
1. [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**コントラクト型を選択します**ドロップダウン リストで、かどうかを実行する (受信側の Idoc) の受信または送信 (Idoc を送信する) の操作に基づく契約の種類を選択します。  
  
2. **カテゴリを選択**ボックスで、展開、 **IDOC**ノードし参照または IDOC メッセージの種類または送信または受信する IDOC の種類を検索します。  
  
3. **利用可能なカテゴリと操作**ボックスで、IDOC の種類またはサポート対象の WCF クライアント (または WCF サービス コントラクト) を生成し をクリックする操作を選択**追加**します。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。 記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 場合は、カテゴリ ノードの すべてのノードの下で使用可能な操作を選択して、そのサブ ノードが追加されます。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] IDOC の種類ごとに一意の WCF クライアント クラス (または WCF サービス コントラクト) が生成されます。 によって、カテゴリと、選択した操作は、複数の WCF クライアント クラスが生成されます。 詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。  
  
4. ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
   1. をクリックして**詳細オプション**を開く、**詳細オプション**ボックス。  
  
   2. **オプションの高度な**ボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、非同期メソッドは、WCF クライアントの生成または構成ファイルの生成を無効にするかどうかを選択できます。  
  
   3. **シリアライザー**使用されるシリアライザーを選択します。  
  
      次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーとしないその他のオプションが選択されているため)。  
  
      ![高度なオプションが既定の設定をボックス](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      オプションで構成できる、**詳細オプション**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスはいくつかの使用可能なオプションに相当します。 これらのオプションの詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)します。
  
5. **[OK]** をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアント クラス (または WCF サービスのインターフェイス) を保存し、操作と、プロジェクト ディレクトリで選択したカテゴリのヘルパー コード。 既定では、構成ファイルも保存されます。 受信と送信操作の若干異なるファイルが生成されます。詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。  
  
## <a name="see-also"></a>参照  
 [Visual Studio で SAP 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)