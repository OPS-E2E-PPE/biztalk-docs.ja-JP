---
title: 参照、検索、および SAP IDOC 操作のメタデータを取得 |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4c82ecf945e85c8e4c9b5f365c808598fcbbf3a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="browse-search-and-get-metadata-for-idoc-operations-in-sap"></a>参照、検索、および SAP IDOC 操作のメタデータを取得
このセクションでは、参照、検索、および SAP から IDOC を使用して操作のメタデータを取得する方法の手順を説明[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 手順のほとんどは、すべての 3 つのユーザー インターフェイスで同じです。 任意の場所、別の該当する手順は、該当するユーザー インターフェイスの提供されます。  
  
 次のセクションで説明する手順を実行する前にする必要があります。  
  
-   作成された、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
-   使用して SAP システムに接続されている[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 手順を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)スキーマまたは Idoc 用の WCF クライアントを生成する SAP システムへの接続をする前に特定のバインディング プロパティを設定する必要がありますに注意してください。  
  
    -   GenerateFlatFileCompatibleIdocSchema  
  
    -   ReceiveIdocFormat  
  
    -   FlatFileSegmentIndicator  
  
     これらのプロパティは、SAP システムから IDOC のメタデータを取得する方法を制御します。 これらのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。 バインドのプロパティを設定する方法の手順を参照してください[SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)です。  
  
## <a name="browsing-idocs-in-an-sap-system"></a>SAP システムでの Idoc の参照  
 使用してメタデータの参照中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスが SAP システムから Idoc を送受信するための操作を分離します。  
  
-   **送信**と**受信**です。 アダプターのクライアントは、厳密に型指定されたスキーマを使用して SAP システムから Idoc を送受信するこれらの操作を使用できます。 アダプターは、IDOC ごとに個別にこれらの操作を表示し、それぞれの IDOC ノードの 利用します。  
  
-   **SendIdoc**と**ReceiveIdoc**です。 アダプターのクライアントは、弱い型指定のスキーマを使用して SAP システムから Idoc を送受信するこれらの操作を使用できます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]のみサーフェスのいずれかの**SendIdoc**と**ReceiveIdoc** Idoc のすべての操作です。 これらの操作は直下にある使用可能な**IDOC**ノード。  
  
 Idoc を SAP システムを使用して、参照する次の手順を実行、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-browse-idocs-in-an-sap-system"></a>Idoc を SAP システムで参照するには  
  
1.  使用して SAP サーバーに接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での SAP システムに接続する](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行するアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、IDOC ノードでの IDOC メッセージの種類を参照してください。 をクリックして、**利用可能なカテゴリと操作**ボックス。 また、IDOC メッセージの種類には、IDOC ノードを展開しても確認できます。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、アイテムの名前を入力して、**カテゴリを選択**ボックス。 たとえばに移動すること、 **ACC_BILLING** IDOC メッセージの種類にフォーカスを保持、 **IDOC**ノード、および入力`ACC_BILLING`です。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] IDOC の一覧を表示するメッセージの種類。 IDOC のルート ノードも明らかな**SendIdoc**弱い型指定の Idoc を SAP システムに送信するにはオプションです。  
  
     ![IDOC でのメッセージの種類の参照](../../adapters-and-accelerators/adapter-sap/media/3b8701c2-0530-4577-817c-92af0cd9a770.gif "3b8701c2-0530-4577-817c-92af0cd9a770")  
  
    > [!NOTE]
    >  シナリオについては、受信、ルート IDOC ノード サーフェス、 **ReceiveIdoc**弱くを受信する操作が Idoc を入力します。  
  
4.  関連する IDOC の種類を表示する IDOC メッセージの種類をクリックします。 次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]特定 IDOC IDOC タイプのメッセージの種類。  
  
     ![IDOC の種類の参照](../../adapters-and-accelerators/adapter-sap/media/fee70ed2-74c1-4c91-b2fd-3d281a335145.gif "fee70ed2-74c1-4c91-b2fd-3d281a335145")  
  
5.  IDOC タイプの異なるバージョンを参照する IDOC の種類をクリックします。 次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]特定 IDOC タイプのバージョンとします。  
  
     ![IDOC タイプのバージョンを参照](../../adapters-and-accelerators/adapter-sap/media/35603fac-ff48-40b1-bb51-bd0548715cd3.gif "35603fac-ff48-40b1-bb51-bd0548715cd3")  
  
6.  その IDOC タイプでサポートされている操作を表示する IDOC タイプのバージョンをクリックします。 次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] IDOC タイプの特定バージョンのサポートされている操作にします。  
  
     ![IDOC タイプの参照操作](../../adapters-and-accelerators/adapter-sap/media/f37624b4-f1f2-4d44-8708-01eb51a2d2a7.gif "f37624b4-f1f2-4d44-8708-01eb51a2d2a7")  
  
## <a name="searching-idocs-in-an-sap-system"></a>SAP システムでの Idoc の検索  
 SAP システムを使用してでの Idoc のメタデータを検索中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   検索式では、ワイルドカード文字をサポートしています。  
  
-   検索操作を実行するノードのすぐ下にある検索を有効にします。  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|+ (プラス)|1 文字と一致します。<br /><br /> たとえば、A + 一致 AB、AC、AD|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB、ABC に一致します。|  
  
 詳細について、アダプターによってサポートされる、特殊文字は、次を参照してください。 [WCF LOB Adapter SDK を使用してバインド プロパティとしてアダプターの設定を公開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)です。
  
 Idoc を SAP システムを使用して、検索する次の手順を実行、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-search-idocs-in-an-sap-system"></a>Idoc を SAP システムで検索するには  
  
1.  使用して SAP サーバーに接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを検索対象のアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、IDOC ノードをクリックします。  
  
    > [!IMPORTANT]
    >  Idoc のルート レベルでのみを検索することができます。  
  
4.  **カテゴリで検索**テキスト ボックスに、特定の IDOC メッセージ型を検索する検索式を入力します。 たとえば、検索を名前に"MATMAS"を持つ Idoc を次のように入力します。 * MATMAS\* 、テキスト ボックスにします。  
  
5.  検索を開始する右矢印アイコンが付いたボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件を満たす Idoc が一覧表示されます。  
  
     次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]検索結果の IDOC の一覧表示します。  
  
     ![SAP システムでの Idoc の検索](../../adapters-and-accelerators/adapter-sap/media/tut1-lesson3-step3-idocsearch.gif "Tut1 Lesson3-手順 3 IDOCSearch")  
  
## <a name="generating-schema-for-biztalk-projects"></a>BizTalk プロジェクトのスキーマを生成します。  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SAP アイテムを選択したスキーマを生成します。 参照して、呼び出し先のアイテムの検索し、それらの成果物のスキーマを生成し、SAP システムへのスキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  そのカテゴリのサブツリー内のすべての操作を返すカテゴリ ノードを選択することができます: たとえば、(そのグループ内のすべてのバージョンの Idoc のスキーマの生成) を IDOC タイプを選択することができますか、そのバージョンのみのスキーマを生成するための IDOC の特定のバージョンを選択IDOC です。 ノードの詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。  
  
#### <a name="to-retrieve-metadata-for-idocs"></a>Idoc のメタデータを取得するには  
  
1.  使用して SAP サーバーに接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行するアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、IDOC メッセージの種類またはメタデータを生成する IDOC の種類 をクリックします。  
  
4.  **利用可能なカテゴリと操作**ボックスで、IDOC の種類またはメタデータを生成し、をクリックする、サポートされている操作を選択して**追加**です。 選択した IDOC の種類または操作に表示されます、**カテゴリと操作を追加**ボックス。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]選択された Idoc の一覧表示します。  
  
     ![Idoc のメタデータの取得](../../adapters-and-accelerators/adapter-sap/media/d9765c62-68b2-4313-9292-9265ab095e2e.gif "d9765c62-68b2-4313-9292-9265ab095e2e")  
  
     複数の操作のスキーマを生成する場合は、BizTalk プロジェクトのコンパイルに失敗する可能性がありますをこれらのスキーマ間で重複する要素定義である可能性があります。 たとえば、"Op1"、操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、複雑なデータ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も複雑なデータ型"CT1"のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているために、コンパイル エラーが表示されます。 このような場合に、次のお勧めします。  
  
    -   1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 これにより、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]複雑なデータ型"CT1"の定義は 1 つだけが生成されます。  
  
    -   複数の異なる実行で複数の操作のスキーマを生成するかどうかは[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意なスキーマ型を生成**生成される XSD ファイルには、複雑な一意の名前空間が含まれるように、チェック ボックスデータは、"CT1"を入力します。  
  
5.  **[OK]**をクリックします。 スキーマ ファイルは、IDOC プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
    > [!NOTE]
    >  使用している場合[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、名前付け規則に既定では、ファイルの作成"SAPBinding\<n\>.xsd"ここで、' n ' 1 にすることができます、2 などによって作成されたスキーマ ファイルの数。 名前を入力して、スキーマ ファイルにカスタムの名前を指定する代わりに、**ファイル名のプレフィックス**テキスト ボックス。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、命名規則で今すぐスキーマ ファイルが作成されます\<ファイル名のプレフィックス\>\<n\>.xsd です。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中に指定されているバインド プロパティを含むバインド ファイル (XML ファイル) も作成操作と操作を呼び出すための SOAP アクション。 BizTalk Server 管理コンソールで、接続 URI、バインドのプロパティで WCF カスタム ポートを作成するには、このバインド ファイルをインポートして、SOAP アクションを設定します。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)です。  
  
6.  **[ファイル]** メニューの **[すべてを保存]**をクリックします。  
  
## <a name="generating-a-wcf-client-for-idoc-operations-using-the-add-adapter-service-reference-plug-in"></a>IDOC を使用して操作用の WCF クライアントを生成する、プラグイン アダプター サービス参照の追加  
 使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を WCF クライアント コードで SAP システムへの Idoc を送信するか、SAP システムから Idoc を受信する WCF サービス コントラクトを生成します。  
  
#### <a name="to-generate-a-wcf-client-or-a-wcf-service-contract-for-idocs"></a>Idoc の WCF クライアントまたは WCF サービス コントラクトを生成するには  
  
1.  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**選択コントラクト型**ドロップダウン リストで、かどうかを実行する (受信側の Idoc) の受信または送信 (Idoc を送信する) 操作に基づくコントラクトの型を選択します。  
  
2.  **カテゴリを選択**ボックスで、展開、 **IDOC**ノード、およびを参照または IDOC メッセージの種類または送信または受信する IDOC の種類を検索します。  
  
3.  **利用可能なカテゴリと操作**ボックスで、IDOC の種類または WCF クライアント (または WCF サービス コントラクト) を生成し、をクリックする、サポートされている操作を選択して**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。 記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリ ノードを選択する場合、すべての操作は、そのノードとそのサブ ノードで使用可能な追加されます。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] IDOC の種類ごとに一意の WCF クライアント クラス (または WCF サービス コントラクト) が生成されます。 カテゴリと選択した操作では、によっては、1 つ以上の WCF クライアント クラスが生成される可能性があります。 詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
4.  ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
    1.  をクリックして**オプションの高度な**を開くには、**オプションの高度な**ボックス。  
  
    2.  **オプションの高度な**下にあるボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、非同期メソッドは、WCF クライアントの生成または構成ファイルの生成を無効にするかどうかを選択することができます。  
  
    3.  **シリアライザー**のために使用されるシリアライザーを選択します。  
  
     次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーしない他のオプションが選択されているため)。  
  
     ![高度なオプション ボックスの既定の設定](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     構成できるオプション、**オプションの高度な**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスが使用可能なオプションの一部に相当します。 これらのオプションの詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)です。
  
5.  **[OK]**をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアント クラス (または WCF サービスのインターフェイス) を保存し、操作と、プロジェクト ディレクトリに選択したカテゴリのヘルパー コード。 既定では、構成ファイルも保存されます。 受信と送信操作です。 わずかに異なるファイルが生成されます。詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
## <a name="see-also"></a>参照  
 [Visual Studio で SAP 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)