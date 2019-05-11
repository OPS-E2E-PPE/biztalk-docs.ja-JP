---
title: 手順 2:Oracle E-business Suite の成果物のアプリケーション定義ファイルの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2665afde-0337-4795-ab4c-6223d39fdf9c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad908429c8daccef990377c953fda334558440aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374565"
---
# <a name="step-2-create-an-application-definition-file-for-the-oracle-e-business-suite-artifacts"></a>手順 2:Oracle E-business Suite の成果物のアプリケーション定義ファイルを作成します。
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 15 分  
  
 **目標:** Microsoft SharePoint Server のビジネス データ カタログ機能は、公開し、基幹業務 (LOB) アプリケーションからのデータがポータルに組み込まれています。 ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用するアプリケーション定義ファイルをビルドする必要があります。  
  
 Microsoft Office SharePoint Server 2007 SDK で使用可能なビジネス データ カタログ定義エディター ツールでは、ビジネス データ カタログ アプリケーション定義ファイルを作成することができます。 このツールでは、手動でファイルを作成するには、XML エディター必要はありませんので、定義ファイルの XML ファイルが自動的に生成されます。  
  
 作成している Microsoft Office SharePoint Server アプリケーションの目的には。  
  
- クエリ、ビジネス データ一覧 Web パーツを使用して MS_SAMPLE_EMPLOYEE インターフェイス テーブルに従業員の従業員の名前に基づいています。  
  
- Microsoft Office SharePoint Server から MS_SAMPLE_EMPLOYEE インターフェイス テーブルのフルテキスト検索を実行します。  
  
  これらの要件ごとに、一連のビジネス データ カタログ定義エディター ツールでタスクを完了する必要があります。 このトピックでは、これらのタスクを実行する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされているビジネス データ カタログ定義エディターであることを確認します。 SDK をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)します。  
  
-   WCF サービスに発行する」の説明に従って[手順 1。Oracle E-business アダプターを使用して作成および WCF サービス発行](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)します。  
  

  
##  <a name="Connect"></a> WCF LOB サービスに接続し、エンティティの作成  
 Web サービス記述言語 (WSDL) サービスを抽出する WCF サービスに接続する必要があります。 ビジネス データ カタログ定義エディターでは、WSDL からメソッドを抽出します。 エンティティを作成するのには、これらのメソッドを使用できます。 このチュートリアルでは、エンティティが作成されます。  
  
#### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>WCF サービスに接続し、エンティティを作成するには  
  
1.  ビジネス データ カタログ定義エディターを起動します。 **開始** メニューのをクリックして**Microsoft ビジネス データ カタログ定義エディター**します。  
  
2.  ツールバーの**LOB システムの追加**します。  
  
3.  LOB システムの追加 ウィンドウで、次のようにクリックします。 **web サービスへの接続**します。  
  
4.  **URL**ボックスに、WCF サービスの URL を入力します。 このチュートリアルでは、URL になります。  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc  
    ```  
  
     WCF サービスが」の説明に従って、正常に発行されるかどうかをテストするときに、URL が使用可能な[手順 1。Oracle E-business アダプターを使用して作成および WCF サービス発行](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)します。  
  
5.  **[接続]** をクリックします。  
  
6.  WCF アダプター サービス開発ウィザードで選択した操作を表示するには、クリックして、 **Web メソッドの追加**タブ。次のメソッドが表示されます。**選択**します。  
  
7.  ドラッグ、**選択**メソッドは、デザイン サーフェイスにします。 メソッドをデザイン サーフェイスにドラッグすると、エンティティを作成して、メソッドがそのエンティティの一部になります。  
  
     ![デザイン画面に Select メソッドの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05 _ add_lob_system")  
  
8.  **[OK]** をクリックします。  
  
9. **LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。 この例では、呼び出す**MS_SAMPLE_EMPLOYEE**、順にクリックします**OK**します。  
  
10. ビジネス データ カタログ定義エディターで、新しく作成されたエンティティ になっている**Entity0**します。 エンティティの名前を変更**従業員**します。 エンティティの名前を変更するには、次の手順に従います。  
  
    1.  展開、 **MS_SAMPLE_EMPLOYEE**ノードの順に展開し、**エンティティ**ノード。  
  
    2.  選択、 **Entity0**ノード。  
  
    3.  プロパティ ペインで次のように入力します。**従業員**で、**名前**ボックス。  
  
         ![エンティティの名前変更](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06 _ entity_name")  
  
##  <a name="Headers"></a> メソッドのユーザー名とパスワードのヘッダーを指定します。  
 Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブルの選択操作の WCF サービスを作成するときにユーザー名とパスワードのヘッダーを指定したでエンドポイント動作の構成の一部として[手順 1。Oracle E-business アダプターを使用して作成および WCF サービス発行](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)します。 Select メソッドのプロパティの同じ値を指定する必要があります。  
  
#### <a name="to-specify-user-name-and-password-headers-for-the-select-method"></a>Select メソッドのユーザー名とパスワードのヘッダーを指定するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、**従業員**ノードの順に展開し、**メソッド**ノード。  
  
2.  をクリックして、**選択**ノード、プロパティ ペインで、に対して省略記号 (...) ボタンをクリックします。、**プロパティ**ボックス。  
  
3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **HttpHeaderUserName**の、**名前**ボックス。 型**MyUserHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
4.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **HttpHeaderPassword**の、**名前**ボックス。 同様に、入力**MyPasswordHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
     ![プロパティを追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07 _ propertviewcollection_editor")  
  
5.  **[OK]** をクリックします。  
  
##  <a name="Scenario1"></a> シナリオ 1:ビジネス データ一覧 Web パーツを使用している従業員のクエリ  
 ビジネス データ一覧 Web パーツから従業員を検索するために使用して従業員の名前に基づくできるアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。  
  
1.  **選択**メソッド フィルターを作成し、マップ、**フィルター**パラメーター。  
  
2.  作成、 **Finder**メソッド インスタンスの**選択**メソッド。 A **Finder**メソッドは、フィルターに基づくレコードの一覧を取得します。  
  
#### <a name="to-create-a-filter-and-map-it-to-the-filter-parameter"></a>フィルターを作成して、フィルター パラメーターにマップするには  
  
1.  フィルターを作成します。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**従業員**ノードの順に展開し、**メソッド**ノード。  
  
    2.  展開、**選択**メソッドを右クリックして**フィルター**、順にクリックします**フィルターの追加**。  
  
         ![SELECT メソッドにフィルターを追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08 _ add_filter")  
  
    3.  プロパティ ペインでの**FilterType**プロパティで、 **Equals**します。  
  
    4.  プロパティ ペインで次のように入力します。 **EmployeeName**で、**名前**ボックス。  
  
         ![フィルター プロパティを指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09 _ filter_properties")  
  
2.  マップをフィルター、**フィルター**パラメーター、**選択**メソッド。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**従業員**ノードの順に展開し、**メソッド**ノード。  
  
    2.  展開、**選択**メソッドを順に展開し、**パラメーター**ノード。  
  
    3.  展開、**フィルター**ノード、2 つ目のクリックと**フィルター**ノード。  
  
    4.  プロパティ ペインで選択**EmployeeName**から、 **FilterDescriptor**一覧。  
  
         ![Select メソッド パラメーターにフィルターをマップ](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")  
  
#### <a name="to-create-a-finder-method-instance-for-the-select-method"></a>Select メソッドの Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、**従業員**ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、**選択**ノードを右クリックして**インスタンス**、順にクリックします**メソッド インスタンスの追加**します。  
  
     ![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11 _ add_method_instance")  
  
3.  メソッド インスタンスの作成 ウィンドウで、次のようにクリックします。 **Finder**の**メソッド インスタンスの型**します。 選択**返す**の**TypeDescriptor を返す**します。  
  
     ![Finder メソッド インスタンスの作成](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12 _ create_method_instance")  
  
4.  **[OK]** をクリックします。  
  
5.  プロパティ ペインで次のように入力します。 **Finder_Instance**で、**名前**ボックス。  
  
     ![Finder メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13 _ instance_property")  
  
##  <a name="Scenario2"></a> シナリオ 2:Microsoft Office SharePoint Server から MS_SAMPLE_EMPLOYEE インターフェイス テーブルでフルテキスト検索  
 Microsoft Office SharePoint Server MS_SAMPLE_EMPLOYEE インターフェイスのテーブルに対してフルテキスト検索を実行するために使用するアプリケーション定義ファイルを作成するには、次の一連のタスクを実行する必要があります。  
  
-   **選択**メソッドは、識別子を作成し、フィルター パラメーターと従業員の名前を格納する戻り値にマップします。  
  
-   作成、 **Specificfinder**メソッド インスタンスの**選択**します。 **Specificfinder**メソッドは特定のレコードの識別子に基づいて、つまり、従業員の名前を検索します。  
  
-   ID Enumerator メソッド インスタンスを作成します。  
  
#### <a name="to-create-an-identifier-and-map-it-to-the-filter-parameter-and-employee-name-return-value"></a>識別子を作成し、フィルター パラメーターと従業員名戻り値にマップするには  
  
1.  識別子を作成、**従業員**エンティティ。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**従業員**ノード。  
  
    2.  右クリックし、**識別子**ノードをクリックして**追加識別子**します。  
  
         ![識別子作成](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14 _ create_identifier")  
  
    3.  プロパティ ペインで次のように入力します。 **EmployeeName**で、**名前**ボックス。  
  
    4.  選択**System.String**の**型**ボックス。  
  
         ![識別子のプロパティを指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")  
  
2.  フィルター パラメーターに、id を割り当てる、**選択**メソッド。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**従業員**ノードの順に展開し、**メソッド**ノード。  
  
    2.  展開、**選択**メソッドを順に展開し、**パラメーター**ノード。  
  
    3.  展開、**フィルター**パラメーターを 2 つ目のクリックして**フィルター**ノード。  
  
    4.  プロパティ ペインで選択**EmployeeName [Employee]** から、**識別子**一覧。  
  
         ![フィルター パラメーターの識別子の設定](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16 _ set_identifier")  
  
3.  識別子は、従業員名の戻り値にマップします。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**従業員**ノードの順に展開し、**メソッド**ノード。  
  
    2.  展開、**選択**メソッドを順に展開し、**パラメーター**ノード。  
  
    3.  展開、**を返す**] ノードの [2 番目の**返す**ノード、**項目**ノードをクリック、**名前**ノード。  
  
    4.  プロパティ ペインで選択**EmployeeName [Employee]** から、**識別子**一覧。  
  
#### <a name="to-create-a-specific-finder-method-instance-for-the-select-method"></a>Select メソッドの Specific Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、**従業員**ノードをクリックし、**メソッド**ノード。  
  
2.  展開、**選択**ノードを右クリックして**インスタンス**、し、[**メソッド インスタンスの追加**メソッド インスタンスの作成] ウィンドウを開きます。  
  
     ![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11 _ add_method_instance")  
  
3.  メソッド インスタンスの作成 ウィンドウで、次のように選択します。 **Specificfinder**の**メソッド インスタンスの型**します。 選択**返す**の**TypeDescriptor を返す**します。  
  
     ![Specific Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17 _ specific_finder")  
  
4.  **[OK]** をクリックします。  
  
5.  プロパティ ペインで次のように入力します。 **SpeciFinder_Instance**の、**名前**ボックス。  
  
#### <a name="to-create-an-id-enumerator-method-instance-for-the-select-method"></a>Select メソッドの Id Enumerator メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、**従業員**ノードをクリックし、**メソッド**ノード。  
  
2.  展開、**選択**ノードを右クリックして**インスタンス**、し、[**メソッド インスタンスの追加**メソッド インスタンスの作成] ウィンドウを開きます。  
  
     ![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11 _ add_method_instance")  
  
3.  メソッド インスタンスの作成 ウィンドウで、次のように選択します。 **Id Enumerator**の**メソッド インスタンスの型**します。 選択**返す**の**TypeDescriptor を返す**します。  
  
     ![Id Enumerator メソッド インスタンスの作成](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18 _ id_enumerator")  
  
4.  **[OK]** をクリックします。  
  
5.  プロパティ ペインで次のように入力します。 **IDEnumerator_Instance**の、**名前**ボックス。  
  
##  <a name="Defaults"></a> メソッド インスタンスの既定のパラメーターを設定します。  
 Select メソッドでは、列名を指定する必要があります。 そのため、既定値を指定する必要があります、**それら**Finder、固有の検索 Id Enumerator メソッド インスタンスのパラメーターが前に作成します。 既定値を指定するはもさらに、**フィルター** Id Enumerator メソッド インスタンスのパラメーター。  
  
#### <a name="to-set-the-default-parameters-for-the-method-instances"></a>メソッド インスタンスの既定のパラメーターを設定するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、**従業員**ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、**選択**ノードの順に展開し、**パラメーター**ノード。  
  
3.  展開、**それら**ノード、および選択し、**それら**パラメーター。  
  
4.  プロパティ ペインで、に対して省略記号ボタン (…) をクリックします。、 **DefaultValues**ボックス。  
  
5.  **DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**追加**、プロパティ ペインで次のようにクリックします**Finder_Instance**で、  **。SelectMethodInstance**一覧。  
  
     ![Finder インスタンスの既定値を指定する](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19 _ finderinstance_defaults")  
  
6.  型`*`で、**値**ボックス。  
  
7.  同様に、5 および 6 の既定値を追加する手順を繰り返して、 **SpecificFinder_Instance**と**IDEnumerator_Instance**メソッドのインスタンス。  
  
8.  **DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**OK**します。  
  
9. 既定値を次に、追加、**フィルター**のパラメーター、 **IDEnumerator_Instance**メソッドのインスタンス。 展開、**フィルター**ノード、および選択し、**フィルター**パラメーター。  
  
10. プロパティ ペインで、に対して省略記号ボタン (…) をクリックします。、 **DefaultValues**ボックス。  
  
11. **DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**追加**、プロパティ ペインで次のようにクリックします**IDEnumerator_Instance**で、  **。SelectMethodInstance**一覧。  
  
12. 型`%`で、**値**ボックス。  
  
     ![Id Enumerator インスタンスの既定値](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20 _ idenumeratorinstance_defaults")  
  
13. **DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**OK**します。  
  
##  <a name="SSO"></a> Oracle E-business Suite に接続するためのシングル サインオンの設定します。  
 このトピックのすべての手順を実行した後は、SharePoint アプリケーションにインポートできるアプリケーション定義ファイルが作成されます。 アプリケーションから Oracle E-business Suite から関連するデータを取得するメソッドを呼び出します。 これを有効にするには、SharePoint アプリケーションで、Oracle E-business Suite でのユーザーとユーザー間のマッピングを作成する必要があります。 アプリケーション定義ファイルをインポートした後は、SharePoint サーバーの全体管理コンソールでこのマッピングを作成します。  
  
 ただし、マッピングを作成する必要がありますプロパティを設定する**SecondarySsoApplicationId**ビジネス データ カタログ定義エディターでします。  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a>SecondarySsoApplicationId のプロパティを設定するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、 **MS_SAMPLE_EMPLOYEE**ノードの順に展開し、**インスタンス**ノード。  
  
2.  をクリックして**MS_SAMPLE_EMPLOYEE_Instance**、プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**ボックス。  
  
3.  **PropertyView コレクション エディター**ダイアログ ボックスで、をクリックして**追加**、プロパティ ペインで次のように入力します**SecondarySsoApplicationId**の、 **名。** ボックス。 同様に、入力**OracleSSO**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
     ![SSO プロパティの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21 _ sso")  
  
4.  **[OK]** をクリックします。  
  
##  <a name="Export"></a> アプリケーション定義をファイルにエクスポートします。  
 Oracle E-business Suite インスタンスのメタデータを含むアプリケーション定義が作成されました。 Microsoft Office SharePoint Server にインポートできる XML ファイルには、この定義をエクスポートする必要があります。  
  
#### <a name="to-export-the-application-definition-to-a-file"></a>アプリケーション定義をファイルにエクスポートするには  
  
1.  メタデータ オブジェクトのウィンドウで右クリックし、 **MS_SAMPLE_EMPLOYEE**ノード、およびクリック**エクスポート**します。  
  
2.  Employee.xml として保存します。  
  
## <a name="next-steps"></a>次の手順  
 Oracle E-business Suite からデータを取得する SharePoint アプリケーションが作成する必要があります。 手順については、次を参照してください。[手順 3。Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)