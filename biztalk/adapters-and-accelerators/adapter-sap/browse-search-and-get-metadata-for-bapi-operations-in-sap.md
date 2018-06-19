---
title: 参照、検索、および SAP の BAPI 操作のメタデータを取得 |Microsoft ドキュメント
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
ms.openlocfilehash: aaf2145bd288d844a3ad02e222a8d8193f32b7de
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25962392"
---
# <a name="browse-search-and-get-metadata-for-bapi-operations-in-sap"></a>参照、検索、および SAP の BAPI 操作のメタデータを取得
このセクションでは、参照、検索、および SAP からの BAPI の操作を使用してメタデータを取得する方法の手順を説明[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 手順のほとんどは、すべての 3 つのユーザー インターフェイスで同じです。 任意の場所、別の該当する手順は、該当するユーザー インターフェイスの提供されます。  
  
 次のセクションで説明する手順を実行する前にする必要があります。  
  
-   作成された、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
-   使用して SAP システムに接続されている[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 手順を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)です。  
  
## <a name="browsing-bapis-in-an-sap-system"></a>SAP システムでの Bapi の参照  
 使用してメタデータの参照中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスの Bapi の Rfc およびビジネス オブジェクトとして。 Rfc として Bapi の参照は、SAP システムでの RFC の参照に似ています。 このような場合は、Bapi、Rfc として利用可能な**RFC**です。 Rfc の参照の詳細については、次を参照してください。[参照、検索、および get 操作のメタデータの RFC に SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)です。  
  
 このセクションでは、ビジネス オブジェクトとしての Bapi の参照についてを説明します。 SAP メタデータの参照の詳細については、次を参照してください[SAP メタデータには、アダプターの画面をどのようにしますか?。](https://msdn.microsoft.com/library/dd788039.aspx)  
  
 以下の手順に従って SAP システムを使用してでの Bapi の参照を[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
 
  
#### <a name="to-browse-bapis-in-an-sap-system"></a>SAP システムでの Bapi の参照  
  
1.  使用して SAP サーバーに接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行するアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスでの BAPI の機能領域を参照してください BAPI ノードをクリックして、**利用可能なカテゴリと操作**ボックス。 また、BAPI の機能領域には、BAPI ノードを展開しても確認できます。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、アイテムの名前を入力して、**カテゴリを選択**ボックス。 例についてに移動すること、**制御**BAPI の機能領域にフォーカスを保持、 **BAPI**ノード、および入力`Controlling`です。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BAPI の機能領域を一覧表示します。  
  
     ![BAPI の機能領域の参照](../../adapters-and-accelerators/adapter-sap/media/d4b03725-44d2-449d-a035-491cd7415139.gif "d4b03725-44d2-449d-a035-491cd7415139")  
  
4.  BAPI の機能領域のさらに分類を表示する BAPI の機能領域をクリックします。  
  
5.  その機能領域のサポートされている関連する操作を表示する BAPI の機能領域をクリックします。 次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]特定の機能領域でサポートされる操作とします。  
  
     ![BAPI の参照操作](../../adapters-and-accelerators/adapter-sap/media/1a9be42e-1f9e-4cf6-a555-c4e755fcc0ea.gif "1a9be42e-1f9e-4cf6-a555-c4e755fcc0ea")  
  
## <a name="searching-bapis-in-an-sap-system"></a>SAP システムでの Bapi の検索  
 SAP システムを使用してでの Bapi のメタデータを検索中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   検索式では、ワイルドカード文字をサポートしています。  
  
-   検索操作を実行するノードのすぐ下にある検索を有効にします。  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|+ (プラス)|1 文字と一致します。<br /><br /> たとえば、A + 一致 AB、AC、AD|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB、ABC に一致します。|  
  
 詳細について、アダプターによってサポートされる、特殊文字は、次を参照してください[SAP メタデータには、アダプターの画面をどのようにしますか?。](https://msdn.microsoft.com/library/dd788039.aspx)  
  
 SAP システムを使用してでの Bapi の検索に次の手順、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-search-bapis-in-an-sap-system"></a>SAP システムでの Bapi の検索するには  
  
1.  使用して SAP サーバーに接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを検索対象のアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、検索する BAPI を含む BAPI の機能領域をクリックします。  
  
    > [!NOTE]
    >  Bapi のルート レベルでのみを検索することができます。  
  
4.  **カテゴリで検索**テキスト ボックスに、特定の BAPI の検索検索式を入力します。 たとえばを名前に「アカウント」を持つ Bapi の検索は、次のように入力します。 * アカウント\*、テキスト ボックスにします。  
  
5.  検索を開始する右矢印アイコンが付いたボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスの Bapi の検索条件に適合するが一覧表示されます。  
  
6.  次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]検索結果を BAPI を一覧表示します。  
  
     ![SAP システムでの Bapi の検索](../../adapters-and-accelerators/adapter-sap/media/82771a47-b656-473e-a96d-998bced38b35.gif "82771a47-b656-473e-a96d-998bced38b35")  
  
## <a name="generating-schema-for-biztalk-projects"></a>BizTalk プロジェクトのスキーマを生成します。  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SAP アイテムを選択したスキーマを生成します。 参照して、呼び出し先のアイテムの検索し、それらの成果物のスキーマを生成し、SAP システムへのスキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  そのカテゴリのサブツリー内のすべての操作を返すカテゴリ ノードを選択することができます: 全体を選択するなど、BAPI のサブ機能が、(そのグループ内のすべての Bapi のスキーマの生成) またはそれらの Bapi のスキーマを生成する特定の Bapi を選択します。 ノードの詳細については、次を参照してください。[メタデータ ノード IDs4](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。  
  
#### <a name="to-retrieve-metadata-for-bapis"></a>Bapi のメタデータを取得するには  
  
1.  使用して SAP サーバーに接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行するアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、メタデータを生成する BAPI を含む BAPI の機能グループをクリックします。  
  
4.  **利用可能なカテゴリと操作**ボックスで、機能領域やメタデータを生成し、をクリックする操作を選択**追加**です。 選択した機能領域または操作に表示されます、**カテゴリと操作を追加**ボックス。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Bapi の選択を一覧表示します。  
  
     ![BAPI のメタデータの取得](../../adapters-and-accelerators/adapter-sap/media/74170978-aef0-46c9-a6e2-36d6e9c2aefc.gif "74170978-aef0-46c9-a6e2-36d6e9c2aefc")  
  
     複数の操作のスキーマを生成する場合は、BizTalk プロジェクトのコンパイルに失敗する可能性がありますをこれらのスキーマ間で重複する要素定義である可能性があります。 たとえば、"Op1"、操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、複雑なデータ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も複雑なデータ型"CT1"のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているために、コンパイル エラーが表示されます。 このような場合に、次のお勧めします。  
  
    -   1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 これにより、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]複雑なデータ型"CT1"の定義は 1 つだけが生成されます。  
  
    -   複数の異なる実行で複数の操作のスキーマを生成するかどうかは[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意なスキーマ型を生成**生成される XSD ファイルには、複雑な一意の名前空間が含まれるように、チェック ボックスデータは、"CT1"を入力します。  
  
5.  **[OK]** をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
    > [!NOTE]
    >  使用している場合[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、名前付け規則に既定では、ファイルの作成"SAPBinding\<n\>.xsd"ここで、' n ' 1 にすることができます、2 などによって作成されたスキーマ ファイルの数。 名前を入力して、スキーマ ファイルにカスタムの名前を指定する代わりに、**ファイル名のプレフィックス**テキスト ボックス。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、命名規則で今すぐスキーマ ファイルが作成されます\<ファイル名のプレフィックス\>\<n\>.xsd です。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中に指定されているバインド プロパティを含むバインド ファイル (XML ファイル) も作成操作と操作を呼び出すための SOAP アクション。 BizTalk Server 管理コンソールで、接続 URI、バインドのプロパティで WCF カスタム ポートを作成するには、このバインド ファイルをインポートして、SOAP アクションを設定します。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)です。
  
6.  **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
## <a name="generating-a-wcf-client-for-bapi-operations-using-the-add-adapter-service-reference-plug-in"></a>BAPI の操作を使用して WCF クライアントを生成する、プラグイン アダプター サービス参照の追加  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] (Bapi は、受信操作はサポートされていません)、BAPI 操作のための WCF クライアント コードを生成します。  
  
#### <a name="to-generate-a-wcf-client-for-bapis"></a>Bapi の WCF クライアントを生成するには  
  
1.  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**選択コントラクト型**ドロップダウン リスト、選択**クライアント (送信操作)** です。  
  
2.  **カテゴリを選択**ボックスで、展開、 **BAPI**ノード、およびしを参照または BAPI カテゴリまたは WCF クライアントを生成する操作を検索します。  
  
3.  **利用可能なカテゴリと操作**ボックスで、操作は、WCF クライアントを生成し、をクリックする項目 (BAPI の機能グループ) 選択**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。 記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリ ノードを選択する場合は、すべてのノードとそのサブ ノードで使用可能な操作が選択します。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]各ビジネス オブジェクトの一意の WCF クライアント クラスが生成されます。 カテゴリと選択した操作では、によっては、1 つ以上の WCF クライアント クラスが生成される可能性があります。 詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
4.  ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
    1.  をクリックして**オプションの高度な**を開くには、**オプションの高度な**ボックス。  
  
    2.  **オプションの高度な**下にあるボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、非同期メソッドは、WCF クライアントの生成または構成ファイルの生成を無効にするかどうかを選択することができます。  
  
    3.  **シリアライザー**のために使用されるシリアライザーを選択します。  
  
     次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーしない他のオプションが選択されているため)。  
  
     ![高度なオプション ボックスの既定の設定](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     構成できるオプション、**オプションの高度な**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスが使用可能なオプションの一部に相当します。 これらのオプションの詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)です。 
  
5.  **[OK]** をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアント クラスとヘルパー コードを選択した操作とカテゴリのプロジェクト ディレクトリに保存します。 既定では、構成ファイルも保存されます。 詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
## <a name="see-also"></a>参照  
 [Visual Studio で SAP 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)