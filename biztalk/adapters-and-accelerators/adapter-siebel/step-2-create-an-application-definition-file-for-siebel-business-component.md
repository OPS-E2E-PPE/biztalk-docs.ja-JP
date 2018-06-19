---
title: '手順 2: Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75d34c48-0f2a-42e4-a60b-e04bcf2404e1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bd1eaac434f4fc6bda55f6ab290740147d91997
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227034"
---
# <a name="step-2-create-an-application-definition-file-for-siebel-business-component-operations"></a>手順 2: Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルを作成します。
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 15 分  
  
 **目標:** ビジネス データ カタログを公開し、ポータルに基幹業務 (LOB) アプリケーションからのデータが組み込まれています。 ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用できるアプリケーション定義ファイルをビルドする必要があります。  
  
 ビジネス データ カタログ定義エディター ツールでは、ビジネス データ カタログのアプリケーション定義ファイルを作成することができます。 このツールには、XML 定義ファイルを自動的に生成されます。 そのため、手動でエディターを作成するファイル、XML ではありません。  
  
 作成している Microsoft Office SharePoint Server アプリケーションの目的は、レコードの一覧を取得するアカウントのビジネス コンポーネントでクエリ操作の実行を開始します。 これを実現するには、一連のビジネス データ カタログ定義エディターでのタスクを完了する必要があります。 このトピックでは、これらのタスクを実行する方法についてを説明します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされているビジネス データ カタログ定義エディターが必要です。 SDK をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)です。  
  
-   公開した WCF サービス」の説明に従って[手順 1: WCF サービスとしての Siebel ビジネス コンポーネント操作の公開](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)です。  
  
## <a name="creating-an-application-definition-file"></a>アプリケーション定義ファイルを作成します。  
 このセクションでは、WCF サービスのアプリケーション定義ファイルを作成する手順を説明します。  
  
### <a name="connect-to-the-wcf-service-and-create-entities"></a>WCF サービスに接続し、エンティティの作成  
 Web サービス記述言語 (WSDL) サービスを抽出する WCF サービスに接続する必要があります。 ビジネス データ カタログ定義エディターは、WSDL からメソッドを抽出します。 これらのメソッドは、エンティティの作成に使用できます。 この例では、アカウントのビジネス コンポーネント上でクエリ操作の 1 つのエンティティを作成する必要があります。  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>WCF サービスに接続し、エンティティを作成するには  
  
1.  ビジネス データ カタログ定義エディターを起動します。 **開始** メニューのをクリックして**Microsoft ビジネス データ カタログ定義エディター**です。  
  
2.  ツールでは、をクリックして**LOB システムの追加**です。  
  
3.  LOB システムの追加] ウィンドウで、[ **web サービスへの接続**です。  
  
4.  [URL] ボックスには、WCF サービスの URL を入力します。 URL は、次の形式である必要があります。  
  
    ```  
    https://<computer_name>/Siebel_Account/BusinessObjects_Account_Account_Operation.svc?wsdl  
    ```  
  
     ここで、BusinessObjects_Account_Account_Operation.svc は、Siebel コントラクト用に作成されたサービス ファイルです。  
  
     URL を入力する必要がありますが、WCF サービスが」の説明に従って、正常に発行されるかどうかをテストするときに使用可能な[手順 1: WCF サービスとしての Siebel ビジネス コンポーネント操作の公開](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)です。  
  
5.  **[接続]** をクリックします。  
  
6.  クリックして、 **Web メソッドの追加** タブに、WCF アダプター サービス開発ウィザードで選択した操作を参照してください。 表示されます、**クエリ**メソッドです。  
  
     ![BDC アプリケーションへの web メソッドの追加](../../adapters-and-accelerators/adapter-siebel/media/f9505cd3-67e3-4f99-b189-d010322a3137.gif "f9505cd3-67e3-4f99-b189-d010322a3137")  
  
7.  ドラッグ、**クエリ**メソッドをクリックしてデザイン サーフェイス**OK**です。  
  
8.  **LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。 この例では、「 `Siebel_Account`、クリックしてして**OK**です。 エンティティ、 **Entity0**、ビジネス データ カタログ定義エディターで作成します。  
  
    > [!IMPORTANT]
    >  ビジネス データ カタログ定義エディター ツールでは、列挙データ型は処理されません。 そのため、ビジネス データ カタログ定義エディター ツールは、その列挙型を検出し、その他のフィールドを無視するまで、フィールドをインポートします。 ビジネス データ カタログ定義エディター ツールでは、エラーも提供されます。 このエラーを無視し、[ok] をクリックして続行できます。 後の段階で、アプリケーション定義ファイルで、必要なフィールドを手動で追加することができます。  
  
9. 複数のフレンドリ名を使用するエンティティの名前を変更します。 この例では、変更**Entity0**に**アカウント**です。  
  
    1.  展開、 **Siebel_Account**  ノードの順に展開し、**エンティティ**ノード。  
  
    2.  選択、 **Entity0**ノード。  
  
    3.  プロパティ ウィンドウで、次のように入力します。**アカウント**で、**名前**フィールドです。  
  
         ![エンティティの名前変更](../../adapters-and-accelerators/adapter-siebel/media/44eda1de-b348-4421-9c51-0355b51f4a90.gif "44eda1de-b348-4421-9c51-0355b51f4a90")  
  
### <a name="specify-user-name-and-password-headers-for-methods"></a>メソッドのユーザー名とパスワードのヘッダーを指定します。  
 ユーザー名とパスワードのヘッダーを指定したエンドポイント動作の構成の一部として、Siebel システムでを選択したビジネス コンポーネント操作のための WCF サービスを作成する場合 ([手順 1: Siebel ビジネス コンポーネント操作の公開WCF サービスとして](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md))。 メソッドのプロパティの同じ値を指定する必要があります。  
  
##### <a name="to-specify-user-name-and-password-headers-for-the-query-method"></a>クエリ メソッドのユーザー名とパスワードのヘッダーを指定するには  
  
1.  メタデータ オブジェクト ペインで、展開、**アカウント** ノードの順に展開し、**メソッド**ノード。  
  
2.  クリックして、**クエリ**ノード、プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**フィールドです。  
  
3.  PropertyView コレクション エディター] ダイアログ ボックスで、[**追加**、プロパティ ウィンドウで、次のように入力します。`HttpHeaderUserName`の、**名前**フィールドです。 同様に、入力`MyUserHeader`の**PropertyValue**フィールドです。 選択**System.String**の**型**フィールドです。  
  
     ![プロパティを追加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")  
  
4.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。`HttpHeaderPassword`の、**名前**フィールドです。 同様に、入力`MyPassHeader`の**PropertyValue**フィールドです。 選択**System.String**の**型**フィールドです。  
  
5.  **[OK]** をクリックします。  
  
### <a name="set-up-single-sign-on-for-connecting-to-a-siebel-system"></a>Siebel システムに接続するためのシングル サインオンを設定します。  
 このトピックのすべてのプロシージャの実行が完了したら後、は、アプリケーション定義、SharePoint アプリケーションにインポートできる XML が作成されます。 アプリケーションからは、Siebel システムの関連するデータを取得する (Web メソッドとして公開) Siebel ビジネス コンポーネント操作を呼び出します。 これを有効にするには、SharePoint アプリケーションで Siebel システムのユーザーとユーザー間のマッピングを作成する必要があります。 アプリケーション定義の XML をインポートした後は、SharePoint サーバーの全体管理 Web サイトでこのマッピングを作成します。  
  
 ただし、マッピングを作成する必要がありますプロパティを設定する**SecondarySsoApplicationId**ビジネス データ カタログ定義エディターにします。  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a>SecondarySsoApplicationId のプロパティを設定するには  
  
1.  メタデータ オブジェクト ペインで、展開、 **Siebel_Account**  ノードの順に展開し、**インスタンス**ノード。  
  
2.  をクリックして**Siebel_Account_Instance**プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**フィールドです。  
  
3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **SecondarySsoApplicationId**の、**名前**フィールドです。 同様に、入力**SiebelSSO**の**PropertyValue**フィールドです。 選択**System.String**の**型**フィールドです。  
  
     ![SSO プロパティの追加](../../adapters-and-accelerators/adapter-siebel/media/59ce70eb-498f-406b-965d-c273c2d6ed14.gif "59ce70eb-498f-406b-965d-c273c2d6ed14")  
  
4.  **[OK]** をクリックします。  
  
### <a name="requirement-perform-a-query-operation-on-the-account-business-component"></a>アカウントのビジネス コンポーネントでクエリ操作を実行する要件。  
 この例の最初の要件では、アカウントのビジネス コンポーネントでクエリ操作の実行に使用できるアプリケーション定義を作成します。 この要件を達成するのには、次の一連のタスクを行う必要があります。  
  
-   メソッドでは、クエリ、フィルターを作成して、クエリ操作が実行されるパラメーターにマップします。 アカウント ビジネス コンポーネントを使用してクエリを実行は、 **SearchExpr**パラメーター。 そのため、フィルターをマップする、 **SearchExpr**パラメーター。  
  
-   クエリ メソッドの Finder メソッド インスタンスを作成します。 Finder メソッドは、フィルターに基づくレコードの一覧を取得します。  
  
##### <a name="to-create-a-filter-and-map-it-to-the-searchexpr-parameter"></a>フィルターを作成して、SearchExpr パラメーターにマップするには  
  
1.  クエリ メソッドにフィルターを作成します。  
  
    1.  メタデータ オブジェクト ペインで、展開、**アカウント** ノードの順に展開し、**メソッド**ノード。  
  
    2.  クエリ メソッドを展開しを右クリックして**フィルター**、クリックして**フィルターの追加**です。  
  
         ![メソッドにフィルターを追加](../../adapters-and-accelerators/adapter-siebel/media/9cf7ccfd-6da0-44b7-b522-df327a74e7a2.gif "9cf7ccfd-6da0-44b7-b522-df327a74e7a2")  
  
    3.  プロパティ ウィンドウで、次のように入力します。`SearchExpression`の、**名前**フィールドです。  
  
    4.  **FilterType**プロパティで、 **Equals**です。  
  
         ![フィルターの名前と種類の指定](../../adapters-and-accelerators/adapter-siebel/media/9faa18e1-4d27-4ee4-960a-458f978812a7.gif "9faa18e1-4d27-4ee4-960a-458f978812a7")  
  
2.  マップをフィルター、 **SearchExpr**クエリ メソッドのパラメーターです。  
  
    1.  メタデータ オブジェクト ペインで、展開、**アカウント** ノードの順に展開し、**メソッド**ノード。  
  
    2.  クエリ メソッドを展開し、展開、**パラメーター**ノード。  
  
    3.  展開、 **AccountQueryInputRecord**ノード、2 番目の順に展開および**AccountQueryInputRecord**ノード。  
  
    4.  をクリックして、 **SearchExpr**ノードのプロパティ ウィンドウで選択および**SearchExpression**から、 **FilterDescriptor** ボックスの一覧です。  
  
         ![フィルターにパラメーターをマップ](../../adapters-and-accelerators/adapter-siebel/media/199c8ba7-d0e8-4fb4-9d73-9cf548512498.gif "199c8ba7-d0e8-4fb4-9d73-9cf548512498")  
  
        > [!IMPORTANT]
        >  **AccountQueryInputRecord**も含まれています、 **QueryFields** 、ノードが含まれています、**項目**ノード。 削除する必要があります、**項目**ノード、それ以外の場合、アカウントのビジネス コンポーネントでクエリ操作が得られない、目的の結果。 削除する、**項目**ノード、ノードを右クリックし、**削除**です。  
  
##### <a name="to-create-a-finder-method-instance-for-query-method"></a>クエリ メソッドの Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ペインで、展開、**アカウント** ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、**クエリ** ノードを右クリックして**インスタンス**、順にクリック**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。  
  
     ![Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-siebel/media/c90e7784-4fb7-4eb5-baf5-efbefba4bb1f.gif "c90e7784-4fb7-4eb5-baf5-efbefba4bb1f")  
  
3.  メソッド インスタンスの作成 ウィンドウで、をクリックして**Finder**の**メソッド インスタンスの型**です。  
  
4.  をクリックして**返す**から**戻り値の TypeDescriptor**セクションです。  
  
     ![Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-siebel/media/e8343988-d7c1-4b04-85b0-ca7d07097490.gif "e8343988-d7c1-4b04-85b0-ca7d07097490")  
  
5.  **[OK]** をクリックします。  
  
6.  プロパティ ウィンドウで、次のように入力します。`QueryAccount`の、**名前**フィールドです。  
  
     ![メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-siebel/media/401223f3-806f-4010-8646-d5ac0c0e9f67.gif "401223f3-806f-4010-8646-d5ac0c0e9f67")  
  
### <a name="remove-the-parameters-of-systemnullable-type"></a>'System.nullable(of 型のパラメーターを削除します。  
 クエリ関数の戻り値パラメーターは 'system.nullable(of 型のパラメーターを含めることがあります。 アプリケーション定義でこれらのパラメーターが存在する、ため SharePoint ポータル上で Siebel データの表示中にエラーが発生した可能性があります。 そのため、アプリケーションの定義から 'system.nullable(of 型のパラメーターを削除する必要があります。  
  
 また、'system.nullable(of 型の各パラメーターのビジネス データ カタログ定義エディターは System.Boolean 型の別のパラメーターを作成し、パラメーター名に"Specified"を追加します。 たとえば、パラメーター AccountRole は 'system.nullable(of 型です。 そのため、ビジネス データ カタログ定義エディターは、パラメーターの一覧に AccountRoleSpecified パラメーターを追加します。 同様に、このようなパラメーターを削除する必要があります。  
  
> [!NOTE]
>  ビジネス データ カタログ定義エディターで、パラメーターを選択しの値を入力パラメーターを参照することができます、 **TypeName**プロパティ ペインでプロパティです。  
  
> [!NOTE]
>  アプリケーションに 'system.nullable(of 型のパラメーターが含まれていない場合は、この手順を省略できます。  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type-for-the-query-method"></a>'System.nullable(of メソッドの型をクエリのパラメーターを削除する  
  
1.  メタデータ オブジェクト ペインで、展開、**アカウント** ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、**クエリ** ノードの順に展開し、**パラメーター**ノード。  
  
3.  展開、**返す**ノード、2 番目の順に展開し、**返す**ノード。  
  
4.  クリックして、削除するパラメーターを右クリックして**削除**です。  
  
5.  ダイアログ ボックスで、 **OK**です。  
  
### <a name="export-the-application-definition-to-a-file"></a>アプリケーション定義をファイルにエクスポートします。  
 Siebel システムのインスタンスのメタデータを含んでいるアプリケーション定義が作成されました。 Microsoft Office SharePoint Server にインポートできる XML ファイルにこの定義をエクスポートする必要があります。  
  
##### <a name="to-export-the-application-definition-to-a-file"></a>アプリケーション定義をファイルにエクスポートするには  
  
1.  右クリックし、 **Siebel_Account**ノードをクリックしてメタデータ オブジェクト ウィンドウで**エクスポート**です。  
  
2.  Siebel_Account.xml としてファイルを保存します。  
  
### <a name="modify-the-application-definition-file-to-include-specific-parameters"></a>特定のパラメーターを含めるアプリケーション定義ファイルを変更します。  
 前述したこのトピックの前に、ビジネス データ カタログ定義エディター ツールは、列挙データ型を処理しません。 ビジネス データ カタログ定義エディター ツールは、その列挙型を検出し、その他のフィールドを無視するまでに、フィールドをインポートします。 そのため、アプリケーションで使用する特定のフィールドを省略する場合があります。 これらのフィールドを含めるアプリケーション定義ファイルを手動で編集することができます。  
  
> [!NOTE]
>  追加するパラメーターがの WCF アダプター サービス開発ウィザードによって生成された .cs ファイルに存在する必要があります[手順 1: WCF サービスとしての Siebel ビジネス コンポーネント操作の公開](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)です。  
  
 このアプリケーション定義ファイルにする、追加または削除の戻り値パラメーター、 **QueryAccount**メソッドです。  
  
##### <a name="to-modify-the-application-definition-file"></a>アプリケーション定義ファイルを変更するには  
  
1.  使用して、Siebel_Account.xml、アプリケーション定義ファイルを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]またはその他の任意のエディターです。  
  
2.  パラメーターを置き換えるアプリケーション定義ファイルの変更、 **QueryAccount**メソッドです。  
  
    1.  アプリケーション定義ファイル内では、次を検索します。  
  
        ```  
        <TypeDescriptor TypeName="BDC.AccountQueryRecord,Siebel_Account" Name="Item">  
        ```  
  
    2.  内で、`<TypeDescriptors>`タグ、既存の置換`<TypeDescriptor>`を次の要素。  
  
        ```  
  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Id" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Country" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Name" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Location" />  
        ```  
  
    3.  ファイルを保存して閉じます。  
  
    > [!TIP]
    >  新しく追加されたフィールドを表示するビジネス データ カタログ定義エディター ツールに戻り、更新されたアプリケーション定義ファイルをインポートすることができます。 ただし、インポートする前に、ビジネス データ カタログ定義エディター ツールから既存の"Siebel_Account"アプリケーションを削除する必要があります。  
  
## <a name="next-steps"></a>次の手順  
 Siebel システムからデータを取得する SharePoint アプリケーションを作成する必要がありますようになりました。 参照してください[手順 3: Siebel からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)手順についてはします。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SharePoint サイト上の Siebel システムからのデータの表示](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)