---
title: "手順 2: Oracle E-business Suite 成果物のためのアプリケーション定義ファイルの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2665afde-0337-4795-ab4c-6223d39fdf9c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ed4340893d351d8406212b585e6216de19c634c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-an-application-definition-file-for-the-oracle-e-business-suite-artifacts"></a>手順 2: Oracle E-business Suite 成果物のためのアプリケーション定義ファイルを作成します。
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 15 分  
  
 **目標:** Microsoft SharePoint Server でビジネス データ カタログの機能を公開し、ポータルに基幹業務 (LOB) アプリケーションからのデータが組み込まれています。 ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用できるアプリケーション定義ファイルをビルドする必要があります。  
  
 Microsoft Office SharePoint Server 2007 SDK で利用可能なビジネス データ カタログ定義エディター ツールでは、ビジネス データ カタログ アプリケーション定義ファイルを作成することができます。 手動で作成、ファイル、XML エディター必要はありませんので、このツールは自動的に定義ファイルの XML ファイルを生成します。  
  
 作成している Microsoft Office SharePoint Server アプリケーションの目的には。  
  
-   ビジネス データ一覧 Web パーツを使用して MS_SAMPLE_EMPLOYEE インターフェイス テーブル内の従業員のクエリは、従業員の名前に基づいています。  
  
-   Microsoft Office SharePoint Server から MS_SAMPLE_EMPLOYEE インターフェイス テーブルにフルテキスト検索を実行します。  
  
 これらの要件ごとに、一連のビジネス データ カタログ定義エディター ツールでタスクを完了する必要があります。 このトピックでは、これらのタスクを実行する方法についてを説明します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   ビジネス データ カタログの定義を Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされているエディターを行ったことを確認します。 SDK をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)です。  
  
-   」の説明に従って、WCF サービスを発行[手順 1: create Oracle E-business アダプターを使用し、WCF サービスを発行](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)です。  
  

  
##  <a name="Connect"></a>WCF LOB サービスに接続し、エンティティの作成  
 Web サービス記述言語 (WSDL) サービスを抽出する WCF サービスに接続する必要があります。 ビジネス データ カタログ定義エディターは、WSDL からメソッドを抽出します。 これらのメソッドは、エンティティの作成に使用できます。 このチュートリアルでは、エンティティが作成されます。  
  
#### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>WCF サービスに接続し、エンティティを作成するには  
  
1.  ビジネス データ カタログ定義エディターを起動します。 **開始** メニューのをクリックして**Microsoft ビジネス データ カタログ定義エディター**です。  
  
2.  ツールバーで、をクリックして**LOB システムの追加**です。  
  
3.  LOB システムの追加] ウィンドウで、[ **web サービスへの接続**です。  
  
4.  **URL**ボックスには、WCF サービスの URL を入力します。 このチュートリアルでは、URL になります。  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc  
    ```  
  
     WCF サービスが」の説明に従って、正常に発行されるかどうかをテストするときに、URL が使用可能な[手順 1: create Oracle E-business アダプターを使用し、WCF サービスを発行](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)です。  
  
5.  **[接続]**をクリックします。  
  
6.  WCF アダプター サービス開発ウィザードで選択した操作を表示するをクリックして、 **Web メソッドの追加**タブです。次のメソッドが表示されます:**選択**です。  
  
7.  ドラッグ、**選択**デザイン画面にメソッドです。 メソッドをデザイン画面にドラッグするとエンティティが作成され、メソッドがそのエンティティの一部になります。  
  
     ![デザイン画面に Select メソッドの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05 _ add_lob_system")  
  
8.  **[OK]**をクリックします。  
  
9. **LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。 この例では、呼び出すこと**MS_SAMPLE_EMPLOYEE**、順にクリック**OK**です。  
  
10. ビジネス データ カタログ定義エディターで、新しく作成されたエンティティと表示されている**Entity0**です。 エンティティの名前を変更**従業員**です。 エンティティの名前を変更する次の手順に従います。  
  
    1.  展開、 **MS_SAMPLE_EMPLOYEE**  ノードの順に展開し、**エンティティ**ノード。  
  
    2.  選択、 **Entity0**ノード。  
  
    3.  プロパティ ウィンドウで、次のように入力します。**従業員**で、**名前**ボックス。  
  
         ![エンティティの名前変更](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06 _ entity_name")  
  
##  <a name="Headers"></a>メソッドのユーザー名とパスワードのヘッダーを指定します。  
 内のエンドポイント動作の構成の一部としてユーザー名とパスワードのヘッダーを指定した Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する Select 操作の WCF サービスの作成、ときに[手順 1: Oracle の使用作成し、WCF サービスを発行 E-business アダプター](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)です。 Select メソッドのプロパティに同じ値を指定する必要があります。  
  
#### <a name="to-specify-user-name-and-password-headers-for-the-select-method"></a>Select メソッドのユーザー名とパスワードのヘッダーを指定するには  
  
1.  メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。  
  
2.  をクリックして、**選択**ノード、プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**ボックス。  
  
3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **HttpHeaderUserName**の、**名前**ボックス。 型**MyUserHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
4.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **HttpHeaderPassword**の、**名前**ボックス。 同様に、入力**MyPasswordHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
     ![プロパティを追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07 _ propertviewcollection_editor")  
  
5.  **[OK]**をクリックします。  
  
##  <a name="Scenario1"></a>ビジネス データ一覧 Web パーツを使用している従業員のシナリオ 1: クエリ  
 従業員がビジネス データ一覧 Web パーツを検索するために使用して従業員の名前に基づくできるアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。  
  
1.  **選択**メソッド、フィルターを作成し、マップ、**フィルター**パラメーター。  
  
2.  作成、 **Finder**メソッド インスタンスの**選択**メソッドです。 A **Finder**メソッドはフィルターに基づくレコードの一覧を取得します。  
  
#### <a name="to-create-a-filter-and-map-it-to-the-filter-parameter"></a>フィルターを作成して、フィルター パラメーターにマップするには  
  
1.  フィルターを作成します。  
  
    1.  メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。  
  
    2.  展開、**選択**メソッドを右クリックして**フィルター**、順にクリック**フィルターの追加**です。  
  
         ![SELECT メソッドにフィルターを追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08 _ add_filter")  
  
    3.  プロパティ ペインでの**FilterType**プロパティで、 **Equals**です。  
  
    4.  プロパティ ウィンドウで、次のように入力します。 **EmployeeName**で、**名前**ボックス。  
  
         ![フィルター プロパティを指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09 _ filter_properties")  
  
2.  マップをフィルター、**フィルター**内のパラメーター、**選択**メソッドです。  
  
    1.  メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。  
  
    2.  展開、**選択**メソッドの順に展開し、**パラメーター**ノード。  
  
    3.  展開、**フィルター**ノード、2 つ目のクリックと**フィルター**ノード。  
  
    4.  プロパティ ウィンドウで、次のように選択します。 **EmployeeName**から、 **FilterDescriptor**  ボックスの一覧です。  
  
         ![フィルターを Select メソッド パラメーターにマップ](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")  
  
#### <a name="to-create-a-finder-method-instance-for-the-select-method"></a>Select メソッドの Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、**を選択** ノードを右クリックして**インスタンス**、順にクリック**メソッド インスタンスの追加**です。  
  
     ![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11 _ add_method_instance")  
  
3.  メソッド インスタンスの作成 ウィンドウで、をクリックして**Finder**の**メソッド インスタンスの型**です。 選択**返す**の**TypeDescriptor を返す**です。  
  
     ![Finder メソッド インスタンスの作成](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12 _ create_method_instance")  
  
4.  **[OK]**をクリックします。  
  
5.  プロパティ ウィンドウで、次のように入力します。 **Finder_Instance**で、**名前**ボックス。  
  
     ![Finder メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13 _ instance_property")  
  
##  <a name="Scenario2"></a>Microsoft Office SharePoint Server から MS_SAMPLE_EMPLOYEE インターフェイス テーブルのシナリオ 2: フル テキスト検索  
 Microsoft Office SharePoint Server から MS_SAMPLE_EMPLOYEE インターフェイス テーブルでフルテキスト検索を実行するために使用するアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。  
  
-   **選択**メソッドを識別子を作成し、フィルター パラメーターおよび従業員の名前を格納する戻り値にマップします。  
  
-   作成、 **Specific Finder**メソッド インスタンスの**選択**です。 **Specific Finder**メソッドは、特定のレコードの識別子に基づいて、つまり、従業員の名前を検索します。  
  
-   ID Enumerator メソッド インスタンスを作成します。  
  
#### <a name="to-create-an-identifier-and-map-it-to-the-filter-parameter-and-employee-name-return-value"></a>識別子を作成し、フィルター パラメーターと従業員の名前の戻り値にマップするには  
  
1.  識別子を作成、**従業員**エンティティです。  
  
    1.  メタデータ オブジェクト ペインで、展開、**従業員**ノード。  
  
    2.  右クリックし、**識別子**ノードをクリックして**識別子の追加**です。  
  
         ![識別子の作成](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14 _ create_identifier")  
  
    3.  プロパティ ウィンドウで、次のように入力します。 **EmployeeName**で、**名前**ボックス。  
  
    4.  選択**System.String**の**型**ボックス。  
  
         ![識別子のプロパティを指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")  
  
2.  フィルター パラメーターに、id を割り当てる、**選択**メソッドです。  
  
    1.  メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。  
  
    2.  展開、**選択**メソッドの順に展開し、**パラメーター**ノード。  
  
    3.  展開して、**フィルター**パラメーター、もう 1 つをクリックして**フィルター**ノード。  
  
    4.  プロパティ ウィンドウで、次のように選択します。 **EmployeeName [Employee]**から、**識別子** ボックスの一覧です。  
  
         ![フィルターのパラメーターの識別子を設定](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16 _ set_identifier")  
  
3.  従業員の名前の戻り値に識別子をマップします。  
  
    1.  メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。  
  
    2.  展開、**選択**メソッドの順に展開し、**パラメーター**ノード。  
  
    3.  展開、**を返す**] ノードの [2 番目**返す**ノード、**項目**ノードをクリックして、**名前**ノード。  
  
    4.  プロパティ ウィンドウで、次のように選択します。 **EmployeeName [Employee]**から、**識別子** ボックスの一覧です。  
  
#### <a name="to-create-a-specific-finder-method-instance-for-the-select-method"></a>Select メソッドの Specific Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ペインで、展開、**従業員**ノード、し、**メソッド**ノード。  
  
2.  展開、**選択** ノードを右クリックして**インスタンス**、し、**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。  
  
     ![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11 _ add_method_instance")  
  
3.  メソッド インスタンスの作成 ウィンドウで、次のように選択します。 **Specific Finder**の**メソッド インスタンスの型**です。 選択**返す**の**TypeDescriptor を返す**です。  
  
     ![Specific Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17 _ specific_finder")  
  
4.  **[OK]**をクリックします。  
  
5.  プロパティ ウィンドウで、次のように入力します。 **SpeciFinder_Instance**の、**名前**ボックス。  
  
#### <a name="to-create-an-id-enumerator-method-instance-for-the-select-method"></a>Select メソッドの Id Enumerator メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ペインで、展開、**従業員**ノード、し、**メソッド**ノード。  
  
2.  展開、**選択** ノードを右クリックして**インスタンス**、し、**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。  
  
     ![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11 _ add_method_instance")  
  
3.  メソッド インスタンスの作成 ウィンドウで、次のように選択します。 **Id Enumerator**の**メソッド インスタンスの型**です。 選択**返す**の**TypeDescriptor を返す**です。  
  
     ![Id Enumerator メソッド インスタンスの作成](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18 _ id_enumerator")  
  
4.  **[OK]**をクリックします。  
  
5.  プロパティ ウィンドウで、次のように入力します。 **IDEnumerator_Instance**の、**名前**ボックス。  
  
##  <a name="Defaults"></a>メソッド インスタンスの既定のパラメーターを設定します。  
 Select メソッドでは、列名を指定する必要があります。 したがって、既定値を指定する必要があります、**それら**Finder、固有の検索、および Id Enumerator メソッド インスタンスのパラメーターが以前に作成します。 既定値を指定するはもさらに、**フィルター** Id Enumerator メソッド インスタンスのパラメーターです。  
  
#### <a name="to-set-the-default-parameters-for-the-method-instances"></a>メソッド インスタンスの既定のパラメーターを設定するには  
  
1.  メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、**選択**ノードの順に展開し、**パラメーター**ノード。  
  
3.  展開して、**それら**ノードをクリックし、**それら**パラメーター。  
  
4.  プロパティ ウィンドウで、に対して省略記号ボタン (...) をクリックして、 **DefaultValues**ボックス。  
  
5.  **DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**追加**、プロパティ ウィンドウで、をクリックして**Finder_Instance**で、 **SelectMethodInstance**  ボックスの一覧です。  
  
     ![Finder インスタンスの既定値を指定する](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19 _ finderinstance_defaults")  
  
6.  型`*`で、**値**ボックス。  
  
7.  同様に、手順 5. と 6. の既定値を追加、 **SpecificFinder_Instance**と**IDEnumerator_Instance**メソッドのインスタンス。  
  
8.  **DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**OK**です。  
  
9. 既定値を次に、追加、**フィルター**のパラメーター、 **IDEnumerator_Instance**メソッド インスタンス。 展開して、**フィルター**ノードをクリックし、**フィルター**パラメーター。  
  
10. プロパティ ウィンドウで、に対して省略記号ボタン (...) をクリックして、 **DefaultValues**ボックス。  
  
11. **DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**追加**、プロパティ ウィンドウで、をクリックして**IDEnumerator_Instance**で、 **SelectMethodInstance**  ボックスの一覧です。  
  
12. 型`%`で、**値**ボックス。  
  
     ![Id Enumerator インスタンスの既定値](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20 _ idenumeratorinstance_defaults")  
  
13. **DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**OK**です。  
  
##  <a name="SSO"></a>Oracle E-business Suite に接続するためのシングル サインオンの設定します。  
 このトピックのすべてのプロシージャの実行が完了したら後、は、SharePoint アプリケーションにインポートできるアプリケーション定義ファイルが作成されます。 アプリケーションから Oracle E-business Suite から関連データを取得するメソッドを呼び出します。 これを有効にするには、SharePoint アプリケーションで Oracle E-business Suite でのユーザーとユーザー間のマッピングを作成する必要があります。 アプリケーション定義ファイルをインポートした後は、SharePoint サーバーの全体管理コンソールの このマッピングを作成します。  
  
 ただし、マッピングを作成する必要がありますプロパティを設定する**SecondarySsoApplicationId**ビジネス データ カタログ定義エディターにします。  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a>SecondarySsoApplicationId のプロパティを設定するには  
  
1.  メタデータ オブジェクト ペインで、展開、 **MS_SAMPLE_EMPLOYEE**  ノードの順に展開し、**インスタンス**ノード。  
  
2.  をクリックして**MS_SAMPLE_EMPLOYEE_Instance**、プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**ボックス。  
  
3.  **PropertyView コレクション エディター**ダイアログ ボックスで、をクリックして**追加**、プロパティ ウィンドウで、次のように入力します**SecondarySsoApplicationId**の、**名前。**ボックス。 同様に、入力**OracleSSO**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
     ![SSO プロパティの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21 _ sso")  
  
4.  **[OK]**をクリックします。  
  
##  <a name="Export"></a>アプリケーション定義をファイルにエクスポートします。  
 Oracle E-business Suite インスタンスのメタデータを含んでいるアプリケーション定義が作成されました。 Microsoft Office SharePoint Server にインポートできる XML ファイルにこの定義をエクスポートする必要があります。  
  
#### <a name="to-export-the-application-definition-to-a-file"></a>アプリケーション定義をファイルにエクスポートするには  
  
1.  メタデータ オブジェクト ペインで右クリックし、 **MS_SAMPLE_EMPLOYEE**ノードをクリックして**エクスポート**です。  
  
2.  Employee.xml としてファイルを保存します。  
  
## <a name="next-steps"></a>次の手順  
 Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成する必要がありますようになりました。 手順については、次を参照してください。[手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)