---
title: 参照、検索、および SAP RFC 操作のメタデータを取得 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- browsing, RFCs
- RFCs, searching
- RFCs, browsing
- RFC operations, generating schema
- RFC operations
- searching, RFCs
- WCF client, generating a
ms.assetid: 68d9e7b2-b8ab-47f5-afda-2811f68e834b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aae3cb0963b4ccbc5c3e891af70706587f8e4b9
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="browse-search-and-get-metadata-for-rfc-operations-in-sap"></a>参照、検索、および SAP RFC 操作のメタデータを取得
このセクションでは、参照、検索、および RFC を使用して操作の SAP からのメタデータを取得する方法の手順を説明[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 手順のほとんどは、すべての 3 つのユーザー インターフェイスで同じです。 任意の場所、別の該当する手順は、該当するユーザー インターフェイスの提供されます。  
  
 次のセクションで説明する手順を実行する前にする必要があります。  
  
-   作成された、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
-   使用して SAP システムに接続されている[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 手順を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)です。  
  
## <a name="browsing-rfcs-in-an-sap-system"></a>SAP システムでの Rfc の参照  
 使用してメタデータの参照中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェス。  
  
-   SAP システムで呼び出すことができる操作として Rfc です。  
  
-   RfcGetAttributes 操作には、アダプター クライアントが RFC 接続パラメーターに関する情報を取得できるようにします。  
  
 SAP メタデータの参照の詳細については、次を参照してください。 [WCF LOB Adapter SDK を使用してバインド プロパティとしてアダプターの設定を公開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)です。
  
 SAP システムを使用してでの Rfc を参照する次の手順を実行、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-browse-rfcs-in-an-sap-system"></a>SAP システムでの Rfc を参照するには  
  
1.  使用して SAP サーバーに接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行するアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、RFC 機能グループを参照してください。 RFC ノードをクリックして、**利用可能なカテゴリと操作**ボックス。 またも表示できます RFC 機能グループ RFC ノードを展開します。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、アイテムの名前を入力して、**カテゴリを選択**ボックス。 例についてに移動すること、**ごと**RFC 機能グループにフォーカスを保持、 **RFC**ノード、および入力`Basis`です。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] RFC 機能グループを一覧表示します。  
  
     ![RFC 機能グループの参照](../../adapters-and-accelerators/adapter-sap/media/958cba26-1644-4700-a647-9eeb0273ebd1.gif "958cba26-1644-4700-a647-9eeb0273ebd1")  
  
4.  関連 Rfc を参照してくださいに RFC 機能グループをクリックします。 次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Rfc 特定 RFC 機能グループの下にあるとします。  
  
     ![機能グループでの Rfc の参照](../../adapters-and-accelerators/adapter-sap/media/bf725aa9-a547-4f20-8246-d9c8fedadb40.gif "bf725aa9-a547-4f20-8246-d9c8fedadb40")  
  
## <a name="searching-rfcs-in-an-sap-system"></a>SAP システムでの Rfc の検索  
 SAP システムを使用してでの Rfc のメタデータを検索中に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   検索式では、ワイルドカード文字をサポートしています。  
  
-   検索操作を実行するノードのすぐ下にある検索を有効にします。  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|+ (プラス)|1 文字と一致します。<br /><br /> たとえば、A + 一致 AB、AC、AD|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB、ABC に一致します。|  
  
 詳細について、アダプターによってサポートされる、特殊文字は、次を参照してください。 [WCF LOB Adapter SDK を使用してバインド プロパティとしてアダプターの設定を公開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)です。
  
 次の手順を使用した SAP システム内の Rfc の検索を実行、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-search-rfcs-in-an-sap-system"></a>SAP システムでの Rfc を検索するには  
  
1.  使用して SAP サーバーに接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを検索対象のアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、検索する RFC を格納している RFC 機能グループをクリックします。 検索するには、どの機能グループがない場合は、RFC のルート ノードをクリックします。  
  
4.  **カテゴリで検索**テキスト ボックスに、特定の RFC の検索検索式を入力します。 たとえば、検索を名前に"RFC_CUST"を持つ Rfc を次のように入力します。 * RFC_CUST\* 、テキスト ボックスにします。  
  
5.  検索を開始する右矢印アイコンが付いたボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに、Rfc の検索条件に適合するが一覧表示されます。  
  
     次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]検索結果の RFC を一覧表示します。  
  
     ![SAP システムでの RFC の検索](../../adapters-and-accelerators/adapter-sap/media/2cf0b262-bbc7-4d0f-a9cf-5b090fb744b6.gif "2cf0b262-bbc7-4d0f-a9cf-5b090fb744b6")  
  
## <a name="generating-schema-for-biztalk-projects"></a>BizTalk プロジェクトのスキーマを生成します。  
 使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SAP アイテムを選択したスキーマを生成します。 参照して、呼び出し先のアイテムの検索し、それらの成果物のスキーマを生成し、SAP システムへのスキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  そのカテゴリのサブツリー内のすべての操作を返すカテゴリ ノードを選択することができます: たとえば、全体の RFC 機能グループにそのグループ内のすべての Rfc のスキーマの生成) を選択できますか、これらの Rfc のみにスキーマを生成する特定の Rfc を選択します。 ノードの詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。  
  
#### <a name="to-retrieve-metadata-for-rfcs"></a>Rfc のメタデータを取得するには  
  
1.  使用して SAP サーバーに接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行するアダプターを使用して、受信または送信の操作コントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、メタデータを生成する RFC を格納している RFC 機能グループをクリックします。  
  
     特定の Rfc の検索することもできます。 例については、その名前に"RFC_CUST"を含んでいる Rfc RFC ノードをクリックしておよびで検索する、**カテゴリで検索**テキスト ボックスに「 \*RFC_CUST\*です。 検索を開始する右矢印アイコンが付いたボタンをクリックします。 **利用可能なカテゴリと操作**ボックスは、名前に"RFC_CUST"があるすべての Rfc を一覧表示されます。  
  
4.  **利用可能なカテゴリと操作**ボックスで、選択、Rfc のメタデータを生成し、をクリックする**追加**です。 選択した Rfc が記載されて、**カテゴリと操作を追加**ボックス。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]選択した Rfc を一覧表示します。  
  
     ![RFC のメタデータの取得](../../adapters-and-accelerators/adapter-sap/media/f7c89882-e2d7-409b-af2e-e35c7268c137.gif "f7c89882-e2d7-409b-af2e-e35c7268c137")  
  
     複数の操作のスキーマを生成する場合は、BizTalk プロジェクトのコンパイルに失敗する可能性がありますをこれらのスキーマ間で重複する要素定義である可能性があります。 たとえば、"Op1"、操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、複雑なデータ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も複雑なデータ型"CT1"のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているために、コンパイル エラーが表示されます。 このような場合に、次のお勧めします。  
  
    -   1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 これにより、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]複雑なデータ型"CT1"の定義は 1 つだけが生成されます。  
  
    -   複数の異なる実行で複数の操作のスキーマを生成するかどうかは[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意なスキーマ型を生成**生成される XSD ファイルには、複雑な一意の名前空間が含まれるように、チェック ボックスデータは、"CT1"を入力します。  
  
5.  **[OK]**をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
    > [!NOTE]
    >  使用している場合[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、名前付け規則に既定では、ファイルの作成"SAPBinding\<n > .xsd"ここで、' n ' 1 にすることができます、2 などによって作成されたスキーマ ファイルの数。 名前を入力して、スキーマ ファイルにカスタムの名前を指定する代わりに、**ファイル名のプレフィックス**テキスト ボックス。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、命名規則で今すぐスキーマ ファイルが作成されます\<ファイル名のプレフィックス >\<n > .xsd です。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマの生成中に指定されているバインド プロパティを含むバインド ファイル (XML ファイル) も作成操作と操作を呼び出すための SOAP アクション。 BizTalk Server 管理コンソールで、接続 URI、バインドのプロパティで WCF カスタム ポートを作成するには、このバインド ファイルをインポートして、SOAP アクションを設定します。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)です。
  
6.  **[ファイル]** メニューの **[すべてを保存]**をクリックします。  
  
## <a name="generating-a-wcf-client-for-rfc-operations-using-the-add-adapter-service-reference-plug-in"></a>RFC を使用して操作用の WCF クライアントを生成する、プラグイン アダプター サービス参照の追加  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] Rfc を SAP に送信する、WCF クライアント コードを生成するシステムまたは WCF サービス コントラクトとコード (RFC サーバー) の Rfc を SAP システムから受信します。  
  
#### <a name="to-generate-a-wcf-client-or-a-wcf-service-contract-for-rfcs"></a>Rfc に WCF クライアントまたは WCF サービス コントラクトを生成するには  
  
1.  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行する (RFC サーバー) を受信または送信操作コントラクトの型を選択します。  
  
2.  **カテゴリを選択**ボックスで、展開、 **RFC**ノード、WCF クライアントまたは WCF サービス コントラクトを生成する RFC を含む RFC 機能グループをクリックします。  
  
     Rfc の検索することもできます。 たとえば、名前に"RFC_CUST"を含む Rfc の検索は、次のようにクリックします。、 **RFC**ノードし、、**カテゴリで検索**テキスト ボックスに「 \*RFC_CUST\*です。 検索を開始する右矢印アイコンが付いたボタンをクリックします。 **利用可能なカテゴリと操作**ボックスは、名前に"RFC_CUST"があるすべての Rfc を一覧表示されます。  
  
3.  **利用可能なカテゴリと操作**ボックスで、操作は、WCF クライアント (または WCF サービス コントラクト) を生成し、をクリックする項目 (RFC 機能グループ) 選択**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。 記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリ ノードを選択する場合、すべての操作は、そのノードとそのサブ ノードで使用可能な追加されます。  
  
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