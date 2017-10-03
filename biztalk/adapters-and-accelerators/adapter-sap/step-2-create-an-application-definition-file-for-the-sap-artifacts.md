---
title: "手順 2: SAP アイテム用のアプリケーション定義ファイルの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application definition file, creating a
- Business Data Catalog Definition Editor
- Business Data Catalog
ms.assetid: d254b00e-dbeb-4167-ad57-6f0aa2e7a563
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d334b885b1135fb429655200090671a2a750ec0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-an-application-definition-file-for-the-sap-artifacts"></a>手順 2: SAP 成果物のため、アプリケーション定義ファイルを作成します。
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 15 分  
  
 **目標:** Microsoft SharePoint Server でビジネス データ カタログの機能を公開し、ポータルに基幹業務 (LOB) アプリケーションからのデータが組み込まれています。 ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用できるアプリケーション定義ファイルをビルドする必要があります。  
  
 Microsoft Office SharePoint Server 2007 SDK で利用可能なビジネス データ カタログ定義エディター ツールでは、ビジネス データ カタログ アプリケーション定義ファイルを作成することができます。 手動で作成、ファイル、XML エディター必要はありませんので、このツールは自動的に定義ファイルの XML ファイルを生成します。  
  
 作成している Microsoft Office SharePoint Server アプリケーションの目的には。  
  
-   顧客名に基づく SAP システム内の顧客を検索します。  
  
-   フェッチされた顧客の一覧から顧客を選択し、顧客の詳細を取得します。  
  
-   フェッチされた顧客の一覧から顧客を選択し、顧客の販売注文を取得します。  
  
 これらの要件ごとに、一連のビジネス データ カタログ定義エディター ツールでタスクを完了する必要があります。 このトピックでは、これらのタスクを実行する方法についてを説明します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   ビジネス データ カタログの定義を Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされているエディターを行ったことを確認します。 SDK をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)です。  
  
-   」の説明に従って、WCF サービスを発行[手順 1: WCF サービスとして SAP アイテムをパブリッシュ](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)です。  
  
## <a name="creating-an-application-definition-file"></a>アプリケーション定義ファイルを作成します。  
 このトピックでは、WCF サービスのアプリケーション定義ファイルを作成する手順を説明します。  
  
### <a name="connect-to-the-wcf-lob-service-and-create-entities"></a>WCF LOB サービスに接続し、エンティティの作成  
 Web サービス記述言語 (WSDL) サービスを抽出する WCF サービスに接続する必要があります。 ビジネス データ カタログ定義エディターは、WSDL からメソッドを抽出します。 これらのメソッドは、エンティティの作成に使用できます。 この例では、2 つのエンティティが作成、顧客および販売注文の 1 つずつされます。  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>WCF サービスに接続し、エンティティを作成するには  
  
1.  ビジネス データ カタログ定義エディターを起動します。 **開始** メニューのをクリックして**Microsoft ビジネス データ カタログ定義エディター**です。  
  
2.  ツールバーで、をクリックして**LOB システムの追加**です。  
  
3.  LOB システムの追加] ウィンドウで、[ **web サービスへの接続**です。  
  
4.  **URL**ボックスには、WCF サービスの URL を入力します。 URL は、次の形式である必要があります。  
  
    ```  
    https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
    ```  
  
     Rfc.svc は、Rfc コントラクト用に作成されたファイルです。  
  
     WCF サービスが、トピックの説明に従って、正常に発行されるかどうかをテストするときに、URL が使用可能な[手順 1: WCF サービスとして SAP アイテムをパブリッシュ](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)です。  
  
5.  **[接続]**をクリックします。  
  
6.  WCF アダプター サービス開発ウィザードで選択した操作を表示するをクリックして、 **Web メソッドの追加**タブです。次の方法が表示されます。  
  
    -   SD_RFC_CUSTOMER_GET  
  
    -   BAPI_SALESORDER_GETLIST  
  
         ![BDC アプリケーションへの web メソッドの追加](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")  
  
     メソッドは、デザイン画面にドラッグします。 両方の操作を別のエンティティにドラッグすることを確認してください。  
  
     ![Web メソッドのエンティティを作成](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")  
  
7.  **[OK]**をクリックします。  
  
8.  **LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。 この例では、呼び出すこと**Customer_Order**、順にクリック**OK**です。  
  
9. ビジネス データ カタログ定義エディターで、2 つのエンティティとしてリストされて**Entity0**と**Entity1**です。 これらのエンティティのわかりやすい名前を付けます。 SD_RFC_CUSTOMER_GET のエンティティの名前変更**顧客**に BAPI_SALESORDER_GETLIST のエンティティの名前変更および**SalesOrder**です。 エンティティの名前を変更する次の手順に従います。  
  
    1.  展開、 **Customer_Order**  ノードの順に展開し、**エンティティ**ノード。  
  
    2.  選択、 **Entity0**ノード。  
  
    3.  プロパティ ウィンドウで、次のように入力します。**顧客**で、**名前**ボックス。  
  
         ![エンティティの名前変更](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")  
  
    4.  選択、 **Entity1**ノード。  
  
    5.  プロパティ ウィンドウで、次のように入力します。 **SalesOrder**で、**名前**ボックス。  
  
### <a name="specify-user-name-and-password-headers-for-the-methods"></a>メソッドのユーザー名とパスワードのヘッダーを指定します。  
 SAP システムで、選択した Rfc の WCF サービスの作成、エンドポイント動作の構成の一部としてユーザー名とパスワードのヘッダーが指定されています。 参照してください[手順 1: WCF サービスとして SAP アイテムをパブリッシュ](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)です。 メソッドのプロパティの同じ値を指定する必要があります。  
  
##### <a name="to-specify-user-name-and-password-headers"></a>ユーザー名とパスワードのヘッダーを指定するには  
  
1.  SD_RFC_CUSTOMER_GET メソッドのユーザー名とパスワード ヘッダーを追加します。  
  
    1.  メタデータ オブジェクト ペインで、展開、**顧客** ノードの順に展開し、**メソッド**ノード。  
  
    2.  SD_RFC_CUSTOMER_GET ノードをクリックし、[プロパティ] ウィンドウでに対して省略記号 (...) ボタンをクリックして、**プロパティ**ボックス。  
  
    3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **HttpHeaderUserName**の、**名前**ボックス。 同様に、入力**MyUserHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
         ![プロパティを追加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")  
  
    4.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **HttpHeaderPassword**の、**名前**ボックス。 同様に、入力**MyPassHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
    5.  **[OK]**をクリックします。  
  
2.  BAPI_SALESORDER_GETLIST メソッドのユーザー名とパスワード ヘッダーを追加します。  
  
    1.  メタデータ オブジェクト ペインで、展開、 **SalesOrder**  ノードの順に展開し、**メソッド**ノード。  
  
    2.  BAPI_SALESORDER_GETLIST ノードをクリックし、[プロパティ] ウィンドウでに対して省略記号 (...) ボタンをクリックして、**プロパティ**ボックス。  
  
    3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **HttpHeaderUserName**の、**名前**ボックス。 同様に、入力**MyUserHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
    4.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **HttpHeaderPassword**の、**名前**ボックス。 同様に、入力**MyPassHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
    5.  **[OK]**をクリックします。  
  
### <a name="set-up-single-sign-on-for-connecting-to-the-sap-system"></a>SAP システムに接続するためのシングル サインオンを設定します。  
 このトピックのすべてのプロシージャの実行が完了したら後、は、SharePoint アプリケーションにインポートできるアプリケーション定義ファイルが作成されます。 アプリケーションからは、SAP システムから関連データを取得する SAP メソッドを呼び出します。 これを有効にするには、SharePoint アプリケーションで、SAP システム内のユーザーとユーザー間のマッピングを作成する必要があります。 アプリケーション定義ファイルをインポートした後は、SharePoint サーバーの全体管理コンソールの このマッピングを作成します。  
  
 ただし、マッピングを作成する必要がありますプロパティを設定する**SecondarySsoApplicationId**ビジネス データ カタログ定義エディターにします。  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a>SecondarySsoApplicationId のプロパティを設定するには  
  
1.  メタデータ オブジェクト ペインで、展開、 **Customer_Order**  ノードの順に展開し、**インスタンス**ノード。  
  
2.  をクリックして**Customer_Order_Instance**、プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**ボックス。  
  
3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **SecondarySsoApplicationId**の、**名前**ボックス。 同様に、入力**SAPSSO**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
     ![SSO プロパティの追加](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")  
  
4.  **[OK]**をクリックします。  
  
### <a name="requirement-1-search-for-customers-based-on-customer-name"></a>顧客名に基づいて顧客の要件 1: 検索  
 顧客名に基づいて顧客を検索するために使用するアプリケーション定義ファイルを作成するには、次の一連のタスクを実行する必要があります。  
  
-   SD_RFC_CUSTOMER_GET メソッドでフィルターを作成し、顧客名を格納するパラメーターにマップします。  
  
-   作成、 **Finder** SD_RFC_CUSTOMER_GET メソッドのメソッドのインスタンス。 A **Finder**メソッドはフィルターに基づくレコードの一覧を取得します。  
  
##### <a name="to-create-a-filter-and-map-it-to-the-customer-name-parameter"></a>フィルターを作成して、customer name パラメーターにマップするには  
  
1.  フィルターを作成します。  
  
    1.  メタデータ オブジェクト ペインで、展開、**顧客** ノードの順に展開し、**メソッド**ノード。  
  
    2.  SD_RFC_CUSTOMER_GET メソッドを展開しを右クリックして**フィルター**、クリックして**フィルターの追加**です。  
  
         ![メソッドにフィルターを追加](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")  
  
    3.  プロパティ ウィンドウで、次のように入力します。 **CustomerName**で、**名前**ボックス。  
  
         ![フィルターの名前を指定](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")  
  
    4.  **FilterType**プロパティで、 **WildcardFilter**です。  
  
2.  マップをフィルター、 **NAME1** SD_RFC_CUSTOMER_GET メソッドのパラメーターです。  
  
    1.  メタデータ オブジェクト ペインで、展開、**顧客** ノードの順に展開し、**メソッド**ノード。  
  
    2.  SD_RFC_CUSTOMER_GET メソッドを展開し、展開、**パラメーター**ノード。  
  
    3.  展開、 **NAME1**ノード、2 つ目のクリックと**NAME1**ノード。 **NAME1**パラメーターには、顧客の名前が含まれています。  
  
    4.  プロパティ ウィンドウで、次のように選択します。 **CustomerName**から、 **FilterDescriptor**  ボックスの一覧です。  
  
         ![フィルターをメソッド パラメーターにマップ](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")  
  
##### <a name="to-create-a-finder-method-instance-for-the-sdrfccustomerget-method"></a>SD_RFC_CUSTOMER_GET メソッドの Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ペインで、展開、**顧客** ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **SD_RFC_CUSTOMER_GET**  ノードを右クリックして**インスタンス**、順にクリック**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。  
  
     ![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")  
  
3.  メソッド インスタンスの作成 ウィンドウで、をクリックして**Finder**の**メソッド インスタンスの型**です。 選択**CUSTOMER_T**の**TypeDescriptor を返す**です。  
  
     ![Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")  
  
4.  **[OK]**をクリックします。  
  
5.  プロパティ ウィンドウで、次のように入力します。 **GetCustomerByName_Instance**で、**名前**ボックス。  
  
     ![メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")  
  
### <a name="requirement-2-retrieve-details-for-a-specific-customer-from-the-list-of-customers"></a>要件 2: 顧客の一覧から特定の顧客の詳細を取得します。  
 顧客名に基づいて顧客を検索するために使用するアプリケーション定義ファイルを作成するには、次の一連のタスクを実行する必要があります。  
  
-   SD_RFC_CUSTOMER_GET メソッドで、識別子を作成し、顧客番号を格納するパラメーターにマップします。  
  
-   作成、 **Specific Finder** SD_RFC_CUSTOMER_GET メソッドのメソッドのインスタンス。 A **Specific Finder**メソッドは、識別子に基づく特定のレコードを検索します。  
  
##### <a name="to-create-an-identifier-and-map-it-to-the-customer-number-parameter"></a>識別子を作成し、顧客番号パラメーターにマップするには  
  
1.  識別子を作成、**顧客**エンティティです。  
  
    1.  メタデータ オブジェクト ペインで、展開、**顧客**ノード。  
  
    2.  右クリックし、**識別子**ノードをクリックして**識別子の追加**です。  
  
         ![メソッドへの識別子の追加](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")  
  
    3.  プロパティ ウィンドウで、次のように入力します。 **CustomerID**で、**名前**ボックス。  
  
    4.  選択**System.String**の**型**ボックス。  
  
         ![識別子の名前を指定](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")  
  
2.  識別子をキー SD_RFC_CUSTOMER_GET メソッドのパラメーターにマップします。  
  
    1.  メタデータ オブジェクト ペインで、展開、**顧客** ノードの順に展開し、**メソッド**ノード。  
  
    2.  SD_RFC_CUSTOMER_GET メソッドを展開し、展開、**パラメーター**ノード。  
  
    3.  展開して、 **KUNNR**パラメーター、もう 1 つをクリックして**KUNNR**ノード。  
  
    4.  プロパティ ウィンドウで、次のように選択します。 **CustomerID [Customer]**から、**識別子** ボックスの一覧です。  
  
         ![識別子をパラメーターにマップ](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")  
  
3.  入力パラメーターと戻り値パラメーター間の関連付けを設定します。  
  
    1.  メタデータ オブジェクト ペインで、展開、**顧客** ノードの順に展開し、**メソッド**ノード。  
  
    2.  SD_RFC_CUSTOMER_GET メソッドを展開し、展開、**パラメーター**ノード。  
  
    3.  展開、 **CUSTOMER_T**  ノードの 2 番目**CUSTOMER_T**  ノード、**項目**ノードをクリックして、 **KUNNR**ノード。  
  
    4.  プロパティ ウィンドウで、次のように選択します。 **CustomerID [Customer]**から、**識別子** ボックスの一覧です。  
  
##### <a name="to-create-a-specific-finder-method-instance-for-the-sdrfccustomerget-method"></a>SD_RFC_CUSTOMER_GET メソッドの Specific Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ペインで、展開、**顧客**ノード、し、**メソッド**ノード。  
  
2.  展開、 **SD_RFC_CUSTOMER_GET**  ノードを右クリックして**インスタンス**、し、**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。  
  
     ![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")  
  
3.  メソッド インスタンスの作成 ウィンドウで、次のように選択します。 **Specific Finder**の**メソッド インスタンスの型**です。 同様に、選択**CUSTOMER_T**の**戻り値の TypeDescriptor**です。  
  
     ![Specific Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")  
  
4.  **[OK]**をクリックします。  
  
5.  プロパティ ウィンドウで、次のように入力します。 **GetCustomerByNumber_Instance**の、**名前**ボックス。  
  
     ![メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")  
  
### <a name="requirement-3-retrieve-sales-order-details-for-a-specific-customer-from-the-list-of-customers"></a>要件 3: 顧客の一覧から特定の顧客の販売注文の詳細を取得します。  
 特定の顧客の販売注文の詳細を取得するために使用するアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。  
  
-   間の関連付けを設定、**顧客**と**SalesOrder**エンティティです。  
  
-   作成、**アソシエーション**BAPI_SALESORDER_GETLIST メソッドのメソッドです。  
  
##### <a name="to-create-an-association-between-the-customer-and-salesorder-entities"></a>顧客と SalesOrder のエンティティ間の関連付けを作成するには  
  
1.  メタデータ オブジェクト ペインで、展開、 **SalesOrder**  ノードの順に展開し、**メソッド**ノード。  
  
2.  BAPI_SALESORDER_GETLIST メソッドを展開し、展開、**パラメーター**ノード。  
  
3.  展開、 **CUSTOMER_NUMBER**ノード、2 つ目のクリックと**CUSTOMER_NUMBER**ノード。  
  
4.  プロパティ ウィンドウで、次のように選択します。 **CustomerID [Customer]**から、**識別子** ボックスの一覧です。  
  
     ![2 つのエンティティ間の関連付けを作成する](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")  
  
##### <a name="to-create-an-association-method-instance-for-the-bapisalesordergetlist-method"></a>BAPI_SALESORDER_GETLIST メソッドの Association メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ペインで、展開、 **SalesOrder**  ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **BAPI_SALESORDER_GETLIST**  ノードを右クリックして**インスタンス**、し、**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。  
  
     ![Association メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")  
  
3.  メソッド インスタンスの作成 ウィンドウで、次のように選択します。**アソシエーション**の**メソッド インスタンスの型**です。  
  
4.  **参照元エンティティ**一覧で、**顧客**です。  
  
5.  **戻り値の TypeDescriptor**一覧で、 **SALES_ORDERS**.  
  
     ![Association メソッド インスタンスの作成](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")  
  
6.  **[OK]**をクリックします。  
  
7.  プロパティ ウィンドウで、次のように入力します。 **SalesOrderForCustomer_Instance**の、**名前**ボックス。  
  
     ![Association メソッドの名前を指定](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")  
  
### <a name="remove-parameters-of-systemnullable-type"></a>'System.nullable(of 型のパラメーターを削除します。  
 作成中に、**アソシエーション**メソッド インスタンス SALES_ORDERS として戻り値の型を選択した BAPI_SALESORDER_GETLIST メソッドです。 SALES_ORDER パラメーターを展開すると、いくつかのパラメーターは 'system.nullable(of 型がわかります。 ビジネス データ カタログ定義エディターで、パラメーターを選択しの値を入力パラメーターを参照することができます、 **TypeName**プロパティです。  
  
 このようなパラメーターのビジネス データ カタログ定義エディターは、名前が同じ名前が"Specified"サフィックスを持つ別のパラメーターを作成します。 たとえば、パラメーターを見て*ITM_NUMBER*と*ITM_NUMBERSpecified*です。 Microsoft Office SharePoint Server は 'system.nullable(of パラメーターをサポートしていません。 そのため、'system.nullable(of パラメーターの型を含むレコードをしようとすると、例外をスローします。 そのため、削除する必要あります (となし"Specified"サフィックスと同じ名前を持つ)、両方のパラメーターから、ビジネス データ カタログ定義エディター  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type"></a>'System.nullable(of 型のパラメーターを削除する  
  
1.  メタデータ オブジェクト ペインで、展開、 **SalesOrder**  ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **BAPI_SALESORDER_GETLIST**  ノードの順に展開し、**パラメーター**ノード。  
  
3.  展開**SALES_ORDERS**、2 つ目の展開**SALES_ORDERS**、順に展開**項目**です。  
  
4.  名前に"Specified"サフィックスを含むパラメーターを右クリックし、**削除**です。  
  
5.  削除、サフィックスなし、パラメーターと同じ名前を持つパラメーターを右クリックし、**削除**です。 通常、このパラメーターは、"Specified"サフィックスが、パラメーターの前に適切です。  
  
### <a name="set-default-parameters"></a>既定のパラメーターを設定します。  
 BAPI_SALESORDER_GETLIST は、次の 2 つのパラメーターを受け取ります。 TRANSACTION_GROUP、これらのパラメーターの 1 つは、既定のパラメーターです。 そのため、このパラメーターの既定値を設定する必要があります。  
  
##### <a name="to-set-the-default-value-for-transactiongroup"></a>TRANSACTION_GROUP の既定値を設定するには  
  
1.  メタデータ オブジェクト ペインで、展開、 **SalesOrder**  ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **BAPI_SALESORDER_GETLIST**  ノードの順に展開し、**インスタンス**ノード。  
  
3.  選択、 **SalesOrderForCustomer_Instance**メソッドをインスタンス化、およびプロパティ ウィンドウで、に対して省略記号ボタン (...) をクリックして、 **DefaultValues**ボックス。  
  
4.  編集ウィンドウで  **TRANSACTION_GROUP**ノード、および、 **TRANSACTION_GROUP**ボックスで、既定値 0 を指定します。  
  
     ![メソッド インスタンスの既定値を指定して](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")  
  
5.  **[閉じる]**をクリックします。  
  
### <a name="export-the-application-definition-to-a-file"></a>アプリケーション定義をファイルにエクスポートします。  
 SAP システムのインスタンスのメタデータを含んでいるアプリケーション定義が作成されました。 Microsoft Office SharePoint Server にインポートできる XML ファイルにこの定義をエクスポートする必要があります。  
  
##### <a name="to-export-the-application-definition-to-a-file"></a>アプリケーション定義をファイルにエクスポートするには  
  
1.  メタデータ オブジェクト ペインで右クリックし、 **Customer_Order**ノードをクリックして**エクスポート**です。  
  
2.  Customer_Order.xml としてファイルを保存します。  
  
## <a name="next-steps"></a>次の手順  
 SAP システムからデータを取得する SharePoint アプリケーションを作成する必要がありますようになりました。 参照してください[手順 3: SAP からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)手順についてはします。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SharePoint サイト上の SAP システムからのデータの表示](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)