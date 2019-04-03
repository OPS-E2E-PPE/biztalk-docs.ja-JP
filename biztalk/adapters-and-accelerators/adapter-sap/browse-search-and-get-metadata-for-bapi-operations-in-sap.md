---
title: 参照、検索、および SAP の BAPI 操作のメタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI operations
- WCF client, generating for BAPI operations
- BAPIs, browsing
- searching, BAPIs
- browsing, BAPIs
- BAPIs, searching
- BAPI operations, generating schema
ms.assetid: 2884215a-ddba-40c7-bf9f-bfc7831f90bb
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97a043c08cf8d7ef258ceb2a2f311d2a86302881
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978955"
---
# <a name="browse-search-and-get-metadata-for-bapi-operations-in-sap"></a>参照、検索、および SAP の BAPI 操作のメタデータの取得
このセクションでは、参照、検索、および SAP の BAPI を使用して操作のメタデータを取得する方法の説明[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 手順のほとんどは、すべての 3 つのユーザー インターフェイスで同じです。 任意の場所、関連するユーザー インターフェイスに適用される場合、別の手順が提供されます。  
  
 次のセクションで説明する手順を実行する前にいる必要があります。  
  
- 作成、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
- 使用して SAP システムに接続されている[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 手順を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)します。  
  
## <a name="browsing-bapis-in-an-sap-system"></a>SAP システムでの Bapi の参照  
 使用してメタデータを閲覧中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Bapi の Rfc およびビジネス オブジェクトとして明らかになります。 Rfc と Bapi の参照は、SAP システムでの RFC の参照に似ています。 このような場合は、Bapi は Rfc として使用できます、 **RFC**します。 Rfc の参照の詳細については、[参照、検索、および SAP の RFC 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)を参照してください。  
  
 このセクションでは、ビジネス オブジェクトとしての Bapi の参照についてを説明します。 SAP メタデータの参照の詳細については、次を参照してください[SAP メタデータには、アダプターの画面はどのようにですか?。](https://msdn.microsoft.com/library/dd788039.aspx)  
  
 次の手順を使用した SAP システム内の Bapi の参照を実行、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
 
  
#### <a name="to-browse-bapis-in-an-sap-system"></a>SAP システムでの Bapi の参照  
  
1. 使用して SAP サーバーに接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**ドロップダウン リストで、かどうかを実行するアダプターを使用して、受信または送信の操作に基づく契約の種類を選択します。  
  
3. **カテゴリを選択**ボックスに、BAPI ノードでの BAPI の機能領域を参照してください。 をクリックして、**利用可能なカテゴリと操作**ボックス。 またはも確認できます BAPI の機能領域 BAPI ノードを展開します。  
  
   > [!TIP]
   >  ツリー ビューでのフォーカスがある状態で成果物の名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、**制御**BAPI の機能領域にフォーカスを保持、 **BAPI**ノード、および入力し、 `Controlling`。  
  
    次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BAPI の機能領域を一覧表示します。  
  
    ![BAPI の機能領域の参照](../../adapters-and-accelerators/adapter-sap/media/d4b03725-44d2-449d-a035-491cd7415139.gif "d4b03725-44d2-449d-a035-491cd7415139")  
  
4. BAPI の機能領域のさらに分類して BAPI の機能領域をクリックします。  
  
5. BAPI の機能領域にその機能領域でサポート関連の操作を参照してください をクリックします。 次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]で特定の機能領域でサポートされる操作。  
  
    ![BAPI の参照操作](../../adapters-and-accelerators/adapter-sap/media/1a9be42e-1f9e-4cf6-a555-c4e755fcc0ea.gif "1a9be42e-1f9e-4cf6-a555-c4e755fcc0ea")  
  
## <a name="searching-bapis-in-an-sap-system"></a>SAP システムでの Bapi の検索  
 中 Bapi のメタデータを使用して SAP システム内で検索[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- 検索式では、ワイルドカード文字をサポートしています。  
  
- 検索操作を実行するノードのすぐ下にある検索を有効にします。  
  
  次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|+ (プラス)|1 つだけの文字と一致します。<br /><br /> たとえば、A + と一致する AB、AC、AD|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB ABC に一致します。|  
  
 アダプターでサポートされている特殊文字の詳細については、次を参照してください[SAP メタデータには、アダプターの画面はどのようにですか?。](https://msdn.microsoft.com/library/dd788039.aspx)  
  
 次の手順を使用して SAP システムでの Bapi の検索を実行、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-search-bapis-in-an-sap-system"></a>SAP システムでの Bapi の検索  
  
1. 使用して SAP サーバーに接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**ドロップダウン リストで、アダプターを使用して、受信または送信の操作を検索対象かどうかに基づいてコントラクトの型を選択します。  
  
3. **カテゴリを選択**ボックスで検索する BAPI を含む BAPI の機能領域をクリックします。  
  
   > [!NOTE]
   >  Bapi のルート レベルでのみを検索することができます。  
  
4. **カテゴリで検索**テキスト ボックスに、特定の BAPI を検索する検索式を入力します。 たとえば、名前に「アカウント」を持つ Bapi を検索するに次のように入力します。 * アカウント\*、テキスト ボックスにします。  
  
5. 検索を開始する右矢印アイコンのボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスは、検索条件を満たす Bapi を一覧表示されます。  
  
6. 次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]検索結果を BAPI を一覧表示します。  
  
    ![SAP システムでの Bapi の検索](../../adapters-and-accelerators/adapter-sap/media/82771a47-b656-473e-a96d-998bced38b35.gif "82771a47-b656-473e-a96d-998bced38b35")  
  
## <a name="generating-schema-for-biztalk-projects"></a>BizTalk プロジェクトのスキーマを生成します。  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SAP アイテムを選択したスキーマを生成します。 参照を呼び出したいアーティファクトの検索し、それらの成果物のスキーマを生成し、SAP システムに、スキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  そのカテゴリのサブツリー内のすべての操作を返すカテゴリ ノードを選択することができます: 全体を選択するなど、BAPI のサブ機能が (そのグループ内のすべての Bapi のスキーマの生成) をまたはそれらの Bapi のスキーマを生成する特定の Bapi を選択します。 ノードの詳細については、[メタデータ ノード IDs4](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)を参照してください。  
  
#### <a name="to-retrieve-metadata-for-bapis"></a>Bapi のメタデータを取得するには  
  
1. 使用して SAP サーバーに接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**ドロップダウン リストで、かどうかを実行するアダプターを使用して、受信または送信の操作に基づく契約の種類を選択します。  
  
3. **カテゴリを選択**ボックスに、メタデータを生成する BAPI を含む BAPI の機能グループをクリックします。  
  
4. **利用可能なカテゴリと操作**ボックスで、機能領域またはメタデータを生成し、をクリックする操作を選択**追加**します。 選択した機能領域または操作に表示されます、**カテゴリと操作を追加**ボックス。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]選択 Bapi を一覧表示します。  
  
    ![BAPI のメタデータ取得](../../adapters-and-accelerators/adapter-sap/media/74170978-aef0-46c9-a6e2-36d6e9c2aefc.gif "74170978-aef0-46c9-a6e2-36d6e9c2aefc")  
  
    複数の操作のスキーマを生成する場合は、いくつかで BizTalk プロジェクトのコンパイル エラーを引き起こす可能性のあるこれらのスキーマ間で重複する要素の定義である可能性があります。 たとえば、"Op1"操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、複雑なデータ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も複雑なデータ型"CT1"のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているため、コンパイル エラーが発生します。 このような状況には、次のお勧めします。  
  
   - 1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 これにより、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] "CT1"複雑なデータ型の 1 つだけ定義が生成されます。  
  
   - 複数の異なる実行で複数の操作のスキーマを生成するかどうか[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意のスキーマ型を生成**生成された XSD ファイルには、複雑な一意の名前空間が含まれるように、チェック ボックスデータは、"CT1"を入力します。  
  
5. **[OK]** をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
   > [!NOTE]
   >  使用する場合[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、名前付け規則で既定では、ファイルの作成"SAPBinding\<n\>.xsd"ここで、' n '、1 を指定できます、2 などによって作成されたスキーマ ファイルの数にします。 または、スキーマ ファイルにカスタム名を提供の名前を入力、**ファイル名のプレフィックス**テキスト ボックス。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]名前付け規則で今すぐスキーマ ファイルを作成します\<ファイル名のプレフィックス\>\<n\>.xsd。  
   > 
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中に指定したバインドのプロパティを含むバインド ファイル (XML ファイル) も作成操作と操作を呼び出すための SOAP アクション。 接続 URI、バインドのプロパティを持つ WCF カスタム ポートを作成する BizTalk Server 管理コンソールでこのバインド ファイルをインポートして、SOAP アクションを設定します。 詳細については、[sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)を参照してください。
  
6. **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
## <a name="generating-a-wcf-client-for-bapi-operations-using-the-add-adapter-service-reference-plug-in"></a>BAPI の操作を使用して WCF クライアントの生成、プラグインのアダプター サービス参照の追加  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] BAPI の操作 (Bapi は、受信操作はサポートされていません) の WCF クライアント コードを生成します。  
  
#### <a name="to-generate-a-wcf-client-for-bapis"></a>Bapi の WCF クライアントを生成するには  
  
1. [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**コントラクト型を選択します**ドロップダウン リスト、選択**クライアント (送信操作)** します。  
  
2. **カテゴリを選択**ボックスで、展開、 **BAPI**ノードし参照または BAPI のカテゴリまたは WCF クライアントを生成する操作を検索します。  
  
3. **利用可能なカテゴリと操作**ボックスに、操作は、カテゴリ (BAPI の機能グループ) をクリックして、WCF クライアントを生成する選択**追加**します。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。 記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリのノードを選択した場合は、すべてのノードとそのサブ ノードで使用可能な操作が選択されます。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]各ビジネス オブジェクトの一意の WCF クライアント クラスが生成されます。 によって、カテゴリと、選択した操作は、複数の WCF クライアント クラスが生成されます。 詳細については、[WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)を参照してください。  
  
4. ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
   1. をクリックして**詳細オプション**を開く、**詳細オプション**ボックス。  
  
   2. **オプションの高度な**ボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、非同期メソッドは、WCF クライアントの生成または構成ファイルの生成を無効にするかどうかを選択できます。  
  
   3. **シリアライザー**使用されるシリアライザーを選択します。  
  
      次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーとしないその他のオプションが選択されているため)。  
  
      ![高度なオプションが既定の設定をボックス](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      オプションで構成できる、**詳細オプション**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスはいくつかの使用可能なオプションに相当します。 これらのオプションの詳細については、[ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)を参照してください。 
  
5. **[OK]** をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]選択した操作とカテゴリのプロジェクト ディレクトリ内の WCF クライアント クラスとヘルパー コードを保存します。 既定では、構成ファイルも保存されます。 詳細については、[WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [Visual Studio で SAP 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)