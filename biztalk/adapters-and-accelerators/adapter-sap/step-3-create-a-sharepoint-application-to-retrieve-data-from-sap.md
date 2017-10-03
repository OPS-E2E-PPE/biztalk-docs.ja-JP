---
title: "手順 3: SAP からデータを取得する SharePoint アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO application, creating an
- Business Data Catalog Definition Editor
- application definition file, importing
- Web Part
- SSP
- Web Part page, creating a
- Shared Services Provider, creating a
ms.assetid: 7158caec-9dc0-477c-9db3-179e634e5196
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 879a4b48da7645471e53db357f7c0a6260117f99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-sap"></a>手順 3: SAP からデータを取得する SharePoint アプリケーションを作成します。
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 15 分  
  
 **目標:**今すぐビジネス データ カタログ定義エディター ツールを使用して作成したアプリケーション定義ファイルを実行し、Microsoft Office SharePoint Server にインポートする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
  
-   必要がありますがファイルを作成したアプリケーションの定義」の説明に従って[手順 2: SAP 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)です。  
  
-   Microsoft シングル サインオン サービスを実行する必要があります。  
  
## <a name="how-to-create-a-sharepoint-application"></a>SharePoint アプリケーションを作成する方法  
 SharePoint アプリケーションを作成するには、次の手順が含まれます。  
  
-   SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。  
  
-   共有サービス プロバイダーを作成します。  
  
-   アプリケーション定義ファイルをインポートします。  
  
-   Web パーツ ページを作成し、Web パーツを追加  
  
 このトピックでは、次の手順を実行する方法を示します。  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>SharePoint での SSO アプリケーションの作成  
 SharePoint アプリケーションから SAP システムでデータにアクセスするには、SAP のユーザーに、SharePoint ユーザーにマップする SSO アプリケーションを設定する必要があります。 SharePoint で SSO アプリケーションを作成するには、次の手順が含まれます。  
  
1.  **シングル サインオンの設定をサーバー管理**です。 このステップでは、管理、シングル サインオン サービスを設定したりできるユーザー アカウントを指定します。 サーバー設定の管理 ページで、これを行うことができます。 このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。 この手順の詳細についてで「構成に対するシングル サインオン - Office SharePoint Server 2007」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。  
  
2.  **エンタープライズ アプリケーション定義の設定を管理**です。 このステップでは、エンタープライズ アプリケーション定義の設定を構成します。 エンタープライズ アプリケーション定義 ページの設定の管理から行うことができます。 このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。  
  
    1.  サーバーの全体管理で、上部のナビゲーション バーで、をクリックして**Operations**です。  
  
    2.  [操作] ページで、**セキュリティの構成**セクションで、をクリックして**でのシングル サインオンの設定を管理**です。  
  
    3.  シングル サインオン] ページの設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、[**企業アプリケーション定義の設定を管理**です。  
  
    4.  [エンタープライズ アプリケーション定義の管理] ページで、値を指定して、**表示名**、**アプリケーション名**、および**連絡先の電子メール アドレス**フィールドです。  
  
        > [!IMPORTANT]
        >  **アプリケーション名**フィールドに、指定した同じ SSO アプリケーション名を指定するかどうかを確認、 **SecondarySsoApplicationId**として、アプリケーション定義ファイルの作成中に変数説明されている[手順 2: SAP 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)です。  
  
    5.  既定では、他のフィールドのままにし、をクリックして**OK**です。  
  
3.  **エンタープライズ アプリケーション定義のアカウント情報を管理する**です。 このステップでは SharePoint からエンタープライズ アプリケーションに接続するには、個々 のユーザーまたはグループを有効にします。 基本的には、この手順でマップする個々 のユーザーまたはグループのユーザーに LOB システムに。 また、LOB システムへの接続に資格情報を指定します。 エンタープライズ アプリケーション定義 ページのアカウント情報の管理から行うことができます。 このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。 この手順の詳細についてで「エンタープライズ アプリケーション定義のアカウント情報の管理」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。  
  
## <a name="creating-a-shared-services-provider"></a>共有サービス プロバイダーを作成します。  
 共有サービス プロバイダーは、共有サービスとその関連リソースの論理的なグループです。 SSP は、SharePoint サーバーの全体管理コンソールを使用して作成できます。  
  
 SSP を作成するときに、Web サイトを定義する必要があります。 ポート番号と、サイト アドレスを作成することに注意してください。 このサイトには、ビジネス データ カタログ アプリケーション定義をインポートします。  
  
 SSP の作成の詳細については、次を参照してください。"章の概要: を作成し、共有サービス プロバイダーを構成する"で[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)です。  
  
## <a name="importing-the-application-definition-file"></a>アプリケーション定義ファイルのインポート  
 SSP にアプリケーション定義ファイルをインポートする必要があります。  
  
#### <a name="to-import-the-application-definition-file"></a>アプリケーション定義ファイルをインポートするには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。  
  
3.  **ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**です。  
  
4.  Customer_Orders.xml、[参照] を開くと、アプリケーション定義のインポート ページで、ファイルを選択し、をクリックして**開く**です。  
  
5.  **[インポート]**をクリックします。  
  
6.  **[OK]**をクリックします。  
  
     アプリケーションをインポートした後に移動して、アプリケーションを表示することができます、**ビュー アプリケーション**リンクします。 アプリケーション内のエンティティを表示するのには、アプリケーション名をクリックします。  
  
## <a name="creating-web-parts"></a>Web パーツを作成します。  
 SharePoint サイトの表示および SAP システムから抽出するビジネス データを管理する Web パーツを作成する必要があります。 Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含むおよびデータベース情報が使用できる再利用可能なコンポーネントです。  
  
 このチュートリアルでは、Web パーツは、ビジネス データ カタログ定義エディターで作成されたメソッドのインスタンスに対して作成されます。 Office SharePoint Server では、特定の使用の Web パーツのさまざまな種類を提供します。 次の Web パーツは、ここで使用されます。  
  
-   **ビジネス データ一覧**用の Web パーツ、 **Finder**メソッド インスタンス。 この Web パーツでは、SAP システムから顧客の一覧を取得する検索文字列を指定することができます。 このチュートリアルでは、これには、検索の顧客の Web パーツを呼び出されます。  
  
-   **ビジネス データ項目**用の Web パーツ、 **Specific Finder**メソッド インスタンス。 この Web パーツは、検索の顧客の Web パーツから選択した特定の顧客の詳細を表示します。 この Web パーツは、検索の顧客の Web パーツにマップされます。  このチュートリアルでは、これには、顧客の詳細の Web パーツを呼び出されます。  
  
-   **ビジネス データ関連一覧**用の Web パーツ、**アソシエーション**メソッド インスタンス。 この Web パーツには、検索の顧客の Web パーツから選択した特定の顧客の販売注文が一覧表示します。 この Web パーツは、検索の顧客の Web パーツに関連付けられます。  このチュートリアルでは、これには、販売注文の詳細の Web パーツを呼び出されます。  
  
 このセクションでは、これらの Web パーツを作成して、それらの間の関連付けを作成する手順を示します。 Web パーツの作成の詳細についてを参照してください「ビジネス データ リストのカスタマイズ、Web パーツ、およびサイト」で[http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)です。  
  
 Web パーツは、1 つの Web パーツ ページに追加されます。 Web パーツを追加する前に、Web パーツ ページを作成する必要があります。 このチュートリアルでは、この Web パーツ ページを Customer_SalesOrders と呼びます。  
  
### <a name="creating-a-web-part-page"></a>Web パーツ ページを作成します。  
 このセクションでは、Web パーツ ページを作成する手順を説明します。  
  
##### <a name="to-create-a-web-part-page"></a>Web パーツ ページを作成するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリック**SharePoint 3.0 サーバーの全体管理**です。  
  
2.  左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。  
  
3.  共有サービスの管理 ページの右上隅で、をクリックして**サイトの操作**、クリックして**作成**です。  
  
     ![Web パーツを作成するにはメニュー](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  作成 ページで、 **Web ページ**セクションで、 **Web パーツ ページ**です。  
  
5.  新しい Web パーツ ページには、次の操作を行います。  
  
    1.  **名前**フィールドに、ページの名前を入力します。 このチュートリアルでは、名前を入力しますとして**Customer_SalesOrders**です。  
  
    2.  選択、**ファイルが既に存在する場合に上書き**チェック ボックスを作成する新しいページと同じ名前の古いページを上書きする場合。  
  
    3.  **レイアウト** セクションから、**レイアウト テンプレートを選択して**ボックスで、Web パーツ ページのレイアウトを選択します。 このチュートリアルでは、次のように選択します。**ヘッダー、左の列、本文**です。  
  
    4.  **保存場所**セクションで、**ドキュメント ライブラリ**一覧で、クリックして**フォーム テンプレート**です。  
  
    5.  **[作成]**をクリックします。 次の図は、作成した後、Web パーツ ページを示します。  
  
         ![空の Web パーツ ページ](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")  
  
    6.  このページを別の Web パーツを追加する必要があります。  
  
### <a name="adding-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加します。  
 ビジネス データ一覧 Web パーツを Web パーツ ページに追加する必要があります。 この Web パーツを使用して、検索式に一致する SAP システムから顧客の一覧が取得されます。 この Web パーツに対応する、 **Finder**メソッド インスタンス (*GetCustomerByName_Instance*) で、ビジネス データ カタログ定義エディターを作成しました。  
  
##### <a name="to-add-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加するには  
  
1.  Customer_SalesOrders ページで、、**ヘッダー**セクションで、 **Web パーツの追加**です。  
  
2.  **Web パーツの追加** ダイアログ ボックスで、**ビジネス データ** セクションで、選択、**ビジネス データ一覧**チェック ボックスをクリックして**追加**です。  
  
     ![ビジネス データ Web パーツを作成するオプションを](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  新しく追加されたビジネス データ一覧 Web パーツ、クリックして、**ツール ウィンドウを開いて**リンクします。  
  
     ![Web パーツのツール ウィンドウを開いて](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  ビジネス データ一覧のツール ウィンドウは、右側のウィンドウで開きます。 **ビジネス データ一覧** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。  
  
     ![ビジネス データ一覧のツール ウィンドウ](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")  
  
5.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **Customer_Order_Instance**クリックしてアプリケーションでは、 **OK**です。  
  
     ![アプリケーション インスタンスの選択](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")  
  
6.  展開、**外観**ノード、および、**タイトル**ボックスで、Web パーツのタイトルを入力します。 この Web パーツの次のように入力します。**顧客リスト**です。  
  
7.  ビジネス データ一覧のツール ウィンドウで、をクリックして**適用**、クリックして**OK**です。 ビジネス データ一覧 Web パーツは、次のようになります。  
  
     ![ビジネス データ一覧 Web パーツ](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")  
  
8.  Web パーツには、SD_RFC_CUSTOMER_GET RFC を実行することによって返されるフィールドが一覧表示します。 SharePoint ポータルに表示したくないフィールドを削除することができます。 削除するには、フィールドをクリックして、**ビューの編集**Web パーツの右上隅にリンクします。  
  
9. ビューの編集 ページの 列 セクションで、表示しない列に対して、チェック ボックスをオフにします。  
  
     ![SharePoint 内の特定の列の表示](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")  
  
10. **[OK]**をクリックします。  
  
### <a name="adding-a-business-data-item-web-part"></a>ビジネス データ項目の Web パーツを追加します。  
 ビジネス データ項目の Web パーツを Web パーツ ページに追加する必要があります。 この Web パーツは、先ほど作成したビジネス データ一覧 Web パーツに接続します。 これにより、ビジネス データ一覧 Web パーツで選択した顧客の詳細を表示することができます。 この Web パーツに対応する、 **Specific Finder**メソッド インスタンス (*GetCustomerByNumber_Instance*) で、ビジネス データ カタログ定義エディターを作成しました。  
  
##### <a name="to-add-a-business-data-item-web-part"></a>ビジネス データ項目の Web パーツを追加するには  
  
1.  Customer_SalesOrders ページの右上隅で、をクリックして**サイトの操作**、クリックして**ページの編集**です。  
  
2.  Customer_SalesOrders] ページで、**左列**セクションで、[ **Web パーツの追加**です。  
  
3.  **Web パーツの追加** ダイアログ ボックスで、**ビジネス データ** セクションで、選択、**ビジネス データ項目**チェック ボックスをクリックして**追加**です。  
  
4.  新しく追加されたビジネス データ項目 Web パーツをクリックして、**ツール ウィンドウを開く**リンクします。  
  
5.  ビジネス データ項目のツール ウィンドウは、右側のウィンドウで開きます。 **ビジネス データ項目** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。  
  
     ![ビジネス データ項目のツール ウィンドウ](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")  
  
6.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **Customer_Order_Instance**クリックしてアプリケーションでは、 **OK**です。  
  
7.  **ビュー**一覧で、**既定**です。  
  
8.  ままにして、**項目**リストが空です。  
  
    > [!NOTE]
    >  **項目**フィールドに、顧客名または詳細を表示する顧客番号を指定する必要があります。 入力パラメーターとして機能するにはこの Web パーツ。 ビジネス データ一覧 Web パーツに接続して、入力パラメーターを取得するため項目を明示的に指定することが必要ありません。  
  
9. **フィールド**セクションで、**選択**ページに表示するフィールドを選択します。  
  
10. 展開、**外観**ノード、および、**タイトル**フィールドに、Web パーツのタイトルを指定します。 この Web パーツを指定する**、特定の顧客の詳細**です。  
  
11. をクリックして**適用**、順にクリック**OK**です。  
  
12. Web パーツを接続、**顧客リスト**Web パーツ。 そのためには次を行います。  
  
    1.  をクリックして**編集**Web パーツの右上寄りです。  
  
    2.  コンテキスト メニューのをポイント**接続**、 をポイント**から項目を取得**、 をクリック**顧客リスト**です。  
  
         ![2 つの Web パーツを接続](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")  
  
### <a name="adding-a-business-data-related-list-web-part"></a>リスト Web パーツに関連するビジネス データの追加  
 Web パーツ ページに、ビジネス データ関連一覧 Web パーツを追加する必要があります。 この Web パーツは、先ほど作成したビジネス データ一覧 Web パーツに接続します。 これにより、ビジネス データ一覧 Web パーツで選択した顧客の販売注文を表示することができます。 この Web パーツに対応する、**アソシエーション**メソッド インスタンス (*SalesOrderForCustomer_Instance*) で、ビジネス データ カタログ定義エディターを作成しました。  
  
##### <a name="to-add-a-business-data-related-list-web-part"></a>ビジネス データ関連一覧 Web パーツを追加するには  
  
1.  Customer_SalesOrders] ページで、**本文**セクションで、[ **Web パーツの追加**です。  
  
2.  **Web パーツの追加** ダイアログ ボックスで、**ビジネス データ** セクションで、select、**ビジネス データ関連一覧**チェック ボックスをオンし、をクリックして**追加**です。  
  
3.  新しく追加されたビジネス データ関連一覧 Web パーツで、をクリックして、**ツール ウィンドウを開いて**リンクします。  
  
4.  ビジネス データ関連一覧のツール ウィンドウは、右側のウィンドウで開きます。 **ビジネス データ関連一覧** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。  
  
     ![ビジネス データ関連一覧](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")  
  
5.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **Customer_Order_Instance**クリックしてアプリケーションでは、 **OK**です。 **リレーションシップ**一覧の設定の名前を持つ、**アソシエーション**メソッド インスタンス (*SalesOrderForCustomer_Instance*)。  
  
6.  展開、**外観**ノード、および、**タイトル**ボックスで、Web パーツのタイトルを入力します。 この Web パーツの次のように入力します。**特定の顧客の販売注文**です。  
  
7.  をクリックして**適用**、順にクリック**OK**です。  
  
8.  Web パーツには、BAPI_SALESORDER_GETLIST RFC を実行することによって返されるフィールドが一覧表示します。 SharePoint ポータルに表示したくないフィールドを削除することができます。 削除するには、フィールドをクリックして、**ビューの編集**Web パーツの右上隅にリンクします。  
  
9. [ビューの編集] ページで、**列**セクションで、表示しない列に対して、テキスト ボックスをオフにします。  
  
10. **[OK]**をクリックします。  
  
11. Web パーツを接続、**顧客リスト**Web パーツ。 そのためには次を行います。  
  
    1.  をクリックして**編集**の右上寄り、**特定の顧客の販売注文**Web パーツ。  
  
    2.  コンテキスト メニューのをポイント**接続**、 をポイント**関連項目を取得**、順にクリック**顧客リスト**です。  
  
12. をクリックして**編集モードの終了**ページの右上隅からです。  
  
## <a name="next-steps"></a>次の手順  
 SAP システムからデータを取得することによって、SharePoint アプリケーションをテストします。 参照してください[手順 4: SharePoint アプリケーションをテスト](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SharePoint サイト上の SAP システムからのデータの表示](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)