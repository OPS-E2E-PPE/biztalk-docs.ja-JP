---
title: 手順 2:SAP アイテム用のアプリケーション定義ファイルの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- application definition file, creating a
- Business Data Catalog Definition Editor
- Business Data Catalog
ms.assetid: d254b00e-dbeb-4167-ad57-6f0aa2e7a563
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1d2953775a948aa20009cf419bd253cafc9a5e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372821"
---
# <a name="step-2-create-an-application-definition-file-for-the-sap-artifacts"></a>手順 2:SAP アイテム用のアプリケーション定義ファイルを作成します。
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 15 分  
  
 **目標:** Microsoft SharePoint Server のビジネス データ カタログ機能は、公開し、基幹業務 (LOB) アプリケーションからのデータがポータルに組み込まれています。 ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用するアプリケーション定義ファイルをビルドする必要があります。  
  
 Microsoft Office SharePoint Server 2007 SDK で使用可能なビジネス データ カタログ定義エディター ツールでは、ビジネス データ カタログ アプリケーション定義ファイルを作成することができます。 このツールでは、手動でファイルを作成するには、XML エディター必要はありませんので、定義ファイルの XML ファイルが自動的に生成されます。  
  
 作成している Microsoft Office SharePoint Server アプリケーションの目的には。  
  
- 顧客名に基づいて、SAP システムの顧客を検索します。  
  
- フェッチされた顧客の一覧から顧客を選択し、顧客の詳細を取得します。  
  
- フェッチされた顧客の一覧から顧客を選択し、顧客の注文を取得します。  
  
  これらの要件ごとに、一連のビジネス データ カタログ定義エディター ツールでタスクを完了する必要があります。 このトピックでは、これらのタスクを実行する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされているビジネス データ カタログ定義エディターであることを確認します。 SDK をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)します。  
  
-   WCF サービスに発行する」の説明に従って[手順 1。SAP アイテムを WCF サービスとして発行](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)します。  
  
## <a name="creating-an-application-definition-file"></a>アプリケーション定義ファイルを作成します。  
 このトピックでは、WCF サービスのアプリケーション定義ファイルを作成する手順を提供します。  
  
### <a name="connect-to-the-wcf-lob-service-and-create-entities"></a>WCF LOB サービスに接続して、エンティティを作成します。  
 Web サービス記述言語 (WSDL) サービスを抽出する WCF サービスに接続する必要があります。 ビジネス データ カタログ定義エディターでは、WSDL からメソッドを抽出します。 エンティティを作成するのには、これらのメソッドを使用できます。 この例では、2 つのエンティティが作成、顧客と販売注文に対して 1 つずつされます。  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>WCF サービスに接続し、エンティティを作成するには  
  
1. ビジネス データ カタログ定義エディターを起動します。 **開始** メニューのをクリックして**Microsoft ビジネス データ カタログ定義エディター**します。  
  
2. ツールバーの**LOB システムの追加**します。  
  
3. LOB システムの追加 ウィンドウで、次のようにクリックします。 **web サービスへの接続**します。  
  
4. **URL**ボックスに、WCF サービスの URL を入力します。 URL は、次の形式である必要があります。  
  
   ```  
   https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
   ```  
  
    Rfc.svc は、Rfc コントラクト用に作成されたファイルです。  
  
    WCF サービスが、トピックの説明に従って、正常に発行されるかどうかをテストするときに、URL が使用可能な[手順 1。SAP アイテムを WCF サービスとして発行](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)します。  
  
5. **[接続]** をクリックします。  
  
6. WCF アダプター サービス開発ウィザードで選択した操作を表示するには、クリックして、 **Web メソッドの追加**タブ。次の方法が表示されます。  
  
   - SD_RFC_CUSTOMER_GET  
  
   - BAPI_SALESORDER_GETLIST  
  
      ![BDC アプリケーションへの web メソッドの追加](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")  
  
     メソッドは、デザイン画面にドラッグします。 両方の操作をさまざまなエンティティにドラッグすることを確認します。  
  
     ![Web メソッドのエンティティを作成する](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")  
  
7. **[OK]** をクリックします。  
  
8. **LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。 この例では、呼び出す**Customer_Order**、順にクリックします**OK**します。  
  
9. ビジネス データ カタログ定義エディターで 2 つのエンティティとして一覧表示。 **Entity0**と**Entity1**します。 これらのエンティティにわかりやすい名前を付けます。 SD_RFC_CUSTOMER_GET のエンティティの名前変更**顧客**に BAPI_SALESORDER_GETLIST のエンティティの名前変更と**SalesOrder**します。 エンティティの名前を変更するには、次の手順に従います。  
  
    1.  展開、 **Customer_Order**ノードの順に展開し、**エンティティ**ノード。  
  
    2.  選択、 **Entity0**ノード。  
  
    3.  プロパティ ペインで次のように入力します。**顧客**で、**名前**ボックス。  
  
         ![エンティティの名前変更](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")  
  
    4.  選択、 **Entity1**ノード。  
  
    5.  プロパティ ペインで次のように入力します。 **SalesOrder**で、**名前**ボックス。  
  
### <a name="specify-user-name-and-password-headers-for-the-methods"></a>メソッドのユーザー名とパスワードのヘッダーを指定します。  
 SAP システムで、選択した Rfc の WCF サービスを作成するときに、エンドポイント動作の構成の一部としてユーザー名とパスワードのヘッダーを指定します。 このトピックの「[手順 1:SAP アイテムを WCF サービスとして発行](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)します。 メソッドのプロパティの同じ値を指定する必要があります。  
  
##### <a name="to-specify-user-name-and-password-headers"></a>ユーザー名とパスワードのヘッダーを指定するには  
  
1.  SD_RFC_CUSTOMER_GET メソッドのユーザー名とパスワード ヘッダーを追加します。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。  
  
    2.  SD_RFC_CUSTOMER_GET ノードをクリックし、プロパティ ペインで、に対して省略記号 (...) ボタンをクリックします。、**プロパティ**ボックス。  
  
    3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **HttpHeaderUserName**の、**名前**ボックス。 同様に、入力**MyUserHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
         ![プロパティを追加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")  
  
    4.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **HttpHeaderPassword**の、**名前**ボックス。 同様に、入力**MyPassHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
    5.  **[OK]** をクリックします。  
  
2.  BAPI_SALESORDER_GETLIST メソッドのユーザー名とパスワード ヘッダーを追加します。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、 **SalesOrder**ノードの順に展開し、**メソッド**ノード。  
  
    2.  BAPI_SALESORDER_GETLIST ノードをクリックし、プロパティ ペインで、に対して省略記号 (...) ボタンをクリックします。、**プロパティ**ボックス。  
  
    3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **HttpHeaderUserName**の、**名前**ボックス。 同様に、入力**MyUserHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
    4.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **HttpHeaderPassword**の、**名前**ボックス。 同様に、入力**MyPassHeader**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
    5.  **[OK]** をクリックします。  
  
### <a name="set-up-single-sign-on-for-connecting-to-the-sap-system"></a>SAP システムに接続するためのシングル サインオンの設定します。  
 このトピックのすべての手順を実行した後は、SharePoint アプリケーションにインポートできるアプリケーション定義ファイルが作成されます。 アプリケーションからは、SAP システムから関連するデータを取得する SAP メソッドを呼び出します。 これを有効にするには、SharePoint アプリケーションで SAP システムのユーザーとユーザー間のマッピングを作成する必要があります。 アプリケーション定義ファイルをインポートした後は、SharePoint サーバーの全体管理コンソールでこのマッピングを作成します。  
  
 ただし、マッピングを作成する必要がありますプロパティを設定する**SecondarySsoApplicationId**ビジネス データ カタログ定義エディターでします。  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a>SecondarySsoApplicationId のプロパティを設定するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、 **Customer_Order**ノードの順に展開し、**インスタンス**ノード。  
  
2.  をクリックして**Customer_Order_Instance**、プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**ボックス。  
  
3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **SecondarySsoApplicationId**の、**名前**ボックス。 同様に、入力**SAPSSO**の**PropertyValue**ボックス。 選択**System.String**の**型**ボックス。  
  
     ![SSO プロパティの追加](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")  
  
4.  **[OK]** をクリックします。  
  
### <a name="requirement-1-search-for-customers-based-on-customer-name"></a>要件 1:顧客名に基づいて顧客の検索  
 顧客名に基づいて顧客の検索に使用できるアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。  
  
-   SD_RFC_CUSTOMER_GET メソッドでは、フィルターを作成し、顧客名を格納するパラメーターにマップします。  
  
-   作成、 **Finder** SD_RFC_CUSTOMER_GET メソッドのメソッドのインスタンス。 A **Finder**メソッドは、フィルターに基づくレコードの一覧を取得します。  
  
##### <a name="to-create-a-filter-and-map-it-to-the-customer-name-parameter"></a>フィルターを作成して、顧客の name パラメーターにマップするには  
  
1.  フィルターを作成します。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。  
  
    2.  SD_RFC_CUSTOMER_GET メソッドを展開し、右クリックして**フィルター**、 をクリックし、**フィルターの追加**します。  
  
         ![メソッドにフィルターを追加](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")  
  
    3.  プロパティ ペインで次のように入力します。 **CustomerName**で、**名前**ボックス。  
  
         ![フィルターの名前を指定](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")  
  
    4.  **FilterType**プロパティで、 **WildcardFilter**します。  
  
2.  マップをフィルター、 **NAME1** SD_RFC_CUSTOMER_GET メソッドのパラメーター。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。  
  
    2.  SD_RFC_CUSTOMER_GET メソッドを展開し、展開、**パラメーター**ノード。  
  
    3.  展開、 **NAME1**ノード、2 つ目のクリックと**NAME1**ノード。 **NAME1**パラメーターには、顧客の名前が含まれています。  
  
    4.  プロパティ ペインで選択**CustomerName**から、 **FilterDescriptor**一覧。  
  
         ![フィルターをメソッド パラメーターにマップ](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")  
  
##### <a name="to-create-a-finder-method-instance-for-the-sdrfccustomerget-method"></a>SD_RFC_CUSTOMER_GET メソッドの Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **SD_RFC_CUSTOMER_GET**ノードを右クリックして**インスタンス**、順にクリックします**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。  
  
     ![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")  
  
3.  メソッド インスタンスの作成 ウィンドウで、次のようにクリックします。 **Finder**の**メソッド インスタンスの型**します。 選択**CUSTOMER_T**の**TypeDescriptor を返す**します。  
  
     ![Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")  
  
4.  **[OK]** をクリックします。  
  
5.  プロパティ ペインで次のように入力します。 **GetCustomerByName_Instance**で、**名前**ボックス。  
  
     ![メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")  
  
### <a name="requirement-2-retrieve-details-for-a-specific-customer-from-the-list-of-customers"></a>要件 2:顧客の一覧から特定の顧客の詳細を取得します。  
 顧客名に基づいて顧客の検索に使用できるアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。  
  
-   SD_RFC_CUSTOMER_GET メソッドでは、識別子を作成し、顧客番号を格納するパラメーターにマップします。  
  
-   作成、 **Specificfinder** SD_RFC_CUSTOMER_GET メソッドのメソッドのインスタンス。 A **Specificfinder**メソッド識別子に基づいて特定のレコードを検索します。  
  
##### <a name="to-create-an-identifier-and-map-it-to-the-customer-number-parameter"></a>識別子を作成し、顧客番号パラメーターにマップするには  
  
1.  識別子を作成、**顧客**エンティティ。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**顧客**ノード。  
  
    2.  右クリックし、**識別子**ノードをクリックして**追加識別子**します。  
  
         ![メソッドへの識別子の追加](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")  
  
    3.  プロパティ ペインで次のように入力します。 **CustomerID**で、**名前**ボックス。  
  
    4.  選択**System.String**の**型**ボックス。  
  
         ![識別子の名前を指定](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")  
  
2.  識別子をキー SD_RFC_CUSTOMER_GET メソッドのパラメーターにマップします。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。  
  
    2.  SD_RFC_CUSTOMER_GET メソッドを展開し、展開、**パラメーター**ノード。  
  
    3.  展開、 **KUNNR**パラメーターを 2 つ目のクリックして**KUNNR**ノード。  
  
    4.  プロパティ ペインで選択**CustomerID [Customer]** から、**識別子**一覧。  
  
         ![識別子をパラメーターにマップ](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")  
  
3.  入力パラメーターと戻り値パラメーター間の関連付けを設定します。  
  
    1.  メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。  
  
    2.  SD_RFC_CUSTOMER_GET メソッドを展開し、展開、**パラメーター**ノード。  
  
    3.  展開、 **CUSTOMER_T** ] ノードの [2 番目の**CUSTOMER_T**ノード、**項目**ノードをクリック、 **KUNNR**ノード。  
  
    4.  プロパティ ペインで選択**CustomerID [Customer]** から、**識別子**一覧。  
  
##### <a name="to-create-a-specific-finder-method-instance-for-the-sdrfccustomerget-method"></a>SD_RFC_CUSTOMER_GET メソッド Specific Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードをクリックし、**メソッド**ノード。  
  
2.  展開、 **SD_RFC_CUSTOMER_GET**ノードを右クリックして**インスタンス**、し、[**メソッド インスタンスの追加**メソッド インスタンスの作成] ウィンドウを開きます。  
  
     ![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")  
  
3.  メソッド インスタンスの作成 ウィンドウで、次のように選択します。 **Specificfinder**の**メソッド インスタンスの型**します。 同様に、選択**CUSTOMER_T**の**戻り値の TypeDescriptor**します。  
  
     ![Specific Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")  
  
4.  **[OK]** をクリックします。  
  
5.  プロパティ ペインで次のように入力します。 **GetCustomerByNumber_Instance**の、**名前**ボックス。  
  
     ![メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")  
  
### <a name="requirement-3-retrieve-sales-order-details-for-a-specific-customer-from-the-list-of-customers"></a>要件 3:顧客の一覧から特定の顧客の販売注文の詳細を取得します。  
 特定の顧客の販売注文の詳細を取得するために使用するアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。  
  
-   間の関連付けを設定、**顧客**と**SalesOrder**エンティティ。  
  
-   作成、**アソシエーション**BAPI_SALESORDER_GETLIST メソッドのメソッド。  
  
##### <a name="to-create-an-association-between-the-customer-and-salesorder-entities"></a>顧客と SalesOrder エンティティ間のアソシエーションを作成するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、 **SalesOrder**ノードの順に展開し、**メソッド**ノード。  
  
2.  BAPI_SALESORDER_GETLIST メソッドを展開し、展開、**パラメーター**ノード。  
  
3.  展開、 **CUSTOMER_NUMBER**ノード、2 つ目のクリックと**CUSTOMER_NUMBER**ノード。  
  
4.  プロパティ ペインで選択**CustomerID [Customer]** から、**識別子**一覧。  
  
     ![2 つのエンティティ間の関連付け作成](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")  
  
##### <a name="to-create-an-association-method-instance-for-the-bapisalesordergetlist-method"></a>BAPI_SALESORDER_GETLIST メソッドの Association メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、 **SalesOrder**ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **BAPI_SALESORDER_GETLIST**ノードを右クリックして**インスタンス**、し、[**メソッド インスタンスの追加**メソッド インスタンスの作成] ウィンドウを開きます。  
  
     ![Association メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")  
  
3.  メソッド インスタンスの作成 ウィンドウで、次のように選択します。**アソシエーション**の**メソッド インスタンスの型**します。  
  
4.  **ソース エンティティ**一覧で、**顧客**します。  
  
5.  **戻り値の TypeDescriptor**一覧で、 **SALES_ORDERS**.  
  
     ![Association メソッド インスタンスの作成](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")  
  
6.  **[OK]** をクリックします。  
  
7.  プロパティ ペインで次のように入力します。 **SalesOrderForCustomer_Instance**の、**名前**ボックス。  
  
     ![Association メソッドの名前を指定](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")  
  
### <a name="remove-parameters-of-systemnullable-type"></a>'System.nullable(of 型のパラメーターを削除します。  
 作成するときに、**アソシエーション**メソッド インスタンス SALES_ORDERS として戻り値の型を選択した BAPI_SALESORDER_GETLIST 方法の場合。 SALES_ORDER パラメーターを展開する場合、いくつかのパラメーターは System.Nullable 型がわかります。 ビジネス データ カタログ定義エディターで、パラメーターを選択しの値を調べて、入力パラメーターを確認できます、 **TypeName**プロパティ。  
  
 このようなパラメーターでは、ビジネス データ カタログ定義エディターは、"Specified"サフィックスを持つが、同じ名前の別のパラメーターを作成します。 たとえば、パラメーターを見て*ITM_NUMBER*と*ITM_NUMBERSpecified*します。 Microsoft Office SharePoint Server は System.Nullable パラメーターをサポートしていません。 そのため、System.Nullable パラメーターの型を含むレコードをしようとすると、例外をスローします。 そのため、削除する必要あります (必要に応じて、「指定された」サフィックスと同じ名前を持つ)、両方のパラメーターからビジネス データ カタログ定義エディター  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type"></a>'System.nullable(of 型のパラメーターを削除する  
  
1.  メタデータ オブジェクト ウィンドウで、展開、 **SalesOrder**ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **BAPI_SALESORDER_GETLIST**ノードの順に展開し、**パラメーター**ノード。  
  
3.  展開**SALES_ORDERS**、2 つ目の展開**SALES_ORDERS**、順に展開**項目**します。  
  
4.  名前に"Specified"サフィックスを含むパラメーターを右クリックし、**削除**します。  
  
5.  サフィックスが付いて、削除するパラメーターと同じ名前を持つパラメーターを右クリックし、**削除**します。 通常、このパラメーターは、「指定された」サフィックスを持つパラメーターの前に適切なです。  
  
### <a name="set-default-parameters"></a>既定のパラメーターを設定します。  
 BAPI_SALESORDER_GETLIST は 2 つのパラメーターを受け取ります。 TRANSACTION_GROUP、これらのパラメーターの 1 つは、既定のパラメーターです。 そのため、このパラメーターの既定値を設定する必要があります。  
  
##### <a name="to-set-the-default-value-for-transactiongroup"></a>TRANSACTION_GROUP の既定値を設定するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、 **SalesOrder**ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **BAPI_SALESORDER_GETLIST**ノードの順に展開し、**インスタンス**ノード。  
  
3.  選択、 **SalesOrderForCustomer_Instance**メソッド インスタンス、およびプロパティ ペインで、に対して省略記号ボタン (…) をクリックします。、 **DefaultValues**ボックス。  
  
4.  編集ウィンドウで  **TRANSACTION_GROUP**ノード、および、 **TRANSACTION_GROUP**ボックスで、既定値 0 を指定します。  
  
     ![メソッド インスタンスの既定値を指定](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")  
  
5.  **[閉じる]** をクリックします。  
  
### <a name="export-the-application-definition-to-a-file"></a>アプリケーション定義をファイルにエクスポートします。  
 SAP システム インスタンスのメタデータを含むアプリケーション定義が作成されました。 Microsoft Office SharePoint Server にインポートできる XML ファイルには、この定義をエクスポートする必要があります。  
  
##### <a name="to-export-the-application-definition-to-a-file"></a>アプリケーション定義をファイルにエクスポートするには  
  
1.  メタデータ オブジェクトのウィンドウで右クリックし、 **Customer_Order**ノード、およびクリック**エクスポート**します。  
  
2.  Customer_Order.xml として保存します。  
  
## <a name="next-steps"></a>次の手順  
 SAP システムからデータを取得する SharePoint アプリケーションを作成する必要がありますようになりました。 参照してください[手順 3。SAP からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)手順についてはします。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1:SAP システムからのデータを SharePoint サイトに表示する](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)