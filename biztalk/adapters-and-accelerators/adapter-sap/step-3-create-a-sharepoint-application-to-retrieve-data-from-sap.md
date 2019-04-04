---
title: '手順 3: SAP からデータを取得する SharePoint アプリケーションの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346dcf24e1440717e111a1ae146521d887054cd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983483"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-sap"></a>手順 3: SAP からデータを取得する SharePoint アプリケーションを作成します。
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 15 分  
  
 **目標:** 今すぐビジネス データ カタログ定義エディター ツールを使用して作成したアプリケーション定義ファイルを取得し、Microsoft Office SharePoint Server にインポートする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
  
-   作成済みアプリケーション定義ファイル」の説明に従って[手順 2: SAP アイテム用のアプリケーション定義ファイルの作成](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)です。  
  
-   Microsoft シングル サインオン サービスを実行する必要があります。  
  
## <a name="how-to-create-a-sharepoint-application"></a>SharePoint アプリケーションを作成する方法  
 SharePoint アプリケーションを作成するには、次の手順が含まれます。  
  
- SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。  
  
- 共有サービス プロバイダーを作成します。  
  
- アプリケーション定義ファイルをインポートします。  
  
- Web パーツ ページを作成し、Web パーツを追加  
  
  このトピックでは、次の手順を実行する方法を示します。  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>SharePoint での SSO アプリケーションの作成  
 SharePoint アプリケーションから SAP システムで、データにアクセスするには、ユーザーが SAP、SharePoint ユーザーにマップする SSO アプリケーションを設定する必要があります。 SharePoint での SSO アプリケーションを作成するには、次の手順が含まれます。  
  
1.  **シングル サインオンの設定をサーバー管理**します。 この手順では、管理、シングル サインオン サービスを設定しているユーザー アカウントを指定します。 管理サーバーの設定 ページで行うことができます。 このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。 この手順の詳細については、ある「構成でシングル サインオン Office SharePoint Server 2007 の」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)します。  
  
2.  **エンタープライズ アプリケーション定義の設定を管理する**します。 この手順では、エンタープライズ アプリケーション定義の設定を構成します。 エンタープライズ アプリケーション定義 ページの設定の管理から行うことができます。 このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。  
  
    1.  サーバーの全体管理で、上部のナビゲーション バーでクリックして**操作**します。  
  
    2.  操作 ページで、**セキュリティの構成**セクションで、**でシングル サインオンの設定を管理**。  
  
    3.  シングル サインオン ページで、設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、**企業アプリケーション定義の設定を管理する**します。  
  
    4.  エンタープライズ アプリケーション定義の管理 ページで、値を指定、**表示名**、**アプリケーション名**、および**連絡先の電子メール アドレス**フィールド。  
  
        > [!IMPORTANT]
        >  **アプリケーション名**フィールドに、指定したのと同じ SSO アプリケーション名を指定するかどうかを確認、 **SecondarySsoApplicationId**として、アプリケーション定義ファイルを作成するときに変数説明されている[手順 2: SAP アイテム用のアプリケーション定義ファイルの作成](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)です。  
  
    5.  既定では、他のフィールドのままにし、クリックして**OK**します。  
  
3.  **エンタープライズ アプリケーション定義のアカウント情報の管理**します。 この手順では SharePoint からエンタープライズ アプリケーションに接続するには、個々 のユーザーまたはグループを有効にします。 基本的には、この手順でマップするか、個々 のユーザーまたはグループをユーザーに、LOB システムに。 また、LOB システムへの接続に資格情報を指定します。 エンタープライズ アプリケーション定義 ページのアカウント情報の管理から行うことができます。 このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。 この手順の詳細については、ある「エンタープライズ アプリケーション定義のアカウント情報の管理」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)します。  
  
## <a name="creating-a-shared-services-provider"></a>共有サービス プロバイダーを作成します。  
 共有サービス プロバイダーは、共有サービスとその関連リソースの論理的なグループです。 SSP は、SharePoint サーバーの全体管理コンソールを使用して作成できます。  
  
 SSP を作成するときに、Web サイトを定義する必要があります。 ポート番号とを作成するサイトのアドレスに注意してください。 このサイトには、ビジネス データ カタログ アプリケーション定義をインポートします。  
  
 SSP の作成の詳細については、"」の章の概要: を作成し、共有サービス プロバイダーを構成する"で[ http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)を参照してください。  
  
## <a name="importing-the-application-definition-file"></a>アプリケーション定義ファイルのインポート  
 SSP に今すぐアプリケーション定義ファイルをインポートする必要があります。  
  
#### <a name="to-import-the-application-definition-file"></a>アプリケーション定義ファイルをインポートするには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーションの定義をインポートする SSP の名前をクリックします。  
  
3.  **ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**します。  
  
4.  Customer_Orders.xml、[参照] を開くと、アプリケーション定義のインポート ページで、ファイルを選択し、**オープン**します。  
  
5.  **[インポート]** をクリックします。  
  
6.  **[OK]** をクリックします。  
  
     アプリケーションをインポートした後に移動して、アプリケーションを表示することができます、**アプリケーションの表示**リンク。 アプリケーション内のエンティティを表示するのには、アプリケーション名をクリックします。  
  
## <a name="creating-web-parts"></a>Web パーツの作成  
 SharePoint サイトの表示および SAP システムから抽出するビジネス データを管理する Web パーツを作成する必要があります。 Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含めることができ、データベース情報を再利用可能なコンポーネントです。  
  
 このチュートリアルでは、ビジネス データ カタログ定義エディター内に作成されたメソッド インスタンスの Web パーツが作成されます。 Office SharePoint Server では、特定の用途の場合は、さまざまな種類の Web パーツを提供します。 ここでは、次の Web パーツを使用します。  
  
- **ビジネス データ一覧**用の Web パーツ、 **Finder**メソッドのインスタンス。 この Web パーツでは、SAP システムから顧客の一覧を取得する検索文字列を指定することができます。 このチュートリアルでは、この検索のお客様の Web パーツは呼び出されます。  
  
- **ビジネス データ項目**用の Web パーツ、 **Specificfinder**メソッドのインスタンス。 この Web パーツは、検索のお客様の Web パーツから選択した特定の顧客の詳細を表示します。 この Web パーツは、検索の顧客の Web パーツにマップされます。  このチュートリアルでは、この顧客の詳細の Web パーツは呼び出されます。  
  
- **ビジネス データ関連一覧**用の Web パーツ、**アソシエーション**メソッドのインスタンス。 この Web パーツには、検索のお客様の Web パーツから選択した特定の顧客の販売注文が一覧表示します。 この Web パーツは、検索の顧客の Web パーツに関連付けられます。  このチュートリアルでは、この販売注文の詳細の Web パーツは呼び出されます。  
  
  ここでは、これらの Web パーツを作成し、それらの間の関連付けを作成する手順について説明します。 Web パーツの作成の詳細についてを参照してください「ビジネス データ リストのカスタマイズ、Web パーツ、およびサイト」 [ http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)します。  
  
  Web パーツは、1 つの Web パーツ ページに追加されます。 Web パーツを追加する前に、Web パーツ ページを作成する必要があります。 このチュートリアルでは、この Web パーツ ページには Customer_SalesOrders が呼び出されます。  
  
### <a name="creating-a-web-part-page"></a>Web パーツ ページの作成  
 ここでは、Web パーツ ページを作成する手順について説明します。  
  
##### <a name="to-create-a-web-part-page"></a>Web パーツ ページを作成するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリック**SharePoint 3.0 サーバーの全体管理**します。  
  
2.  左側のナビゲーション ウィンドウで、アプリケーションの定義をインポートする SSP の名前をクリックします。  
  
3.  共有サービス管理 ページで、右上隅にある**サイトの操作**、 をクリックし、**作成**です。  
  
     ![Web パーツを作成するにはメニュー](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  作成 ページで、 **Web ページ**セクションで、 **Web パーツ ページ**します。  
  
5.  新しい Web パーツ ページで、次の操作を行います。  
  
    1.  **名前**フィールドに、ページの名前を入力します。 このチュートリアルでは、入力として名前**Customer_SalesOrders**します。  
  
    2.  選択、**ファイルが既に存在する場合に上書き**チェック ボックスで、古いページを作成する新しいページと同じ名前で上書きする場合。  
  
    3.  **レイアウト**セクションから、**レイアウト テンプレートの選択**ボックスに、Web パーツ ページのレイアウトを選択します。 このチュートリアルでは、次のように選択します。**ヘッダー、左の列、本文**します。  
  
    4.  **保存場所**セクションで、**ドキュメント ライブラリ**一覧で、**フォーム テンプレート**します。  
  
    5.  **[作成]** をクリックします。 次の図は、作成した後、Web パーツ ページを示します。  
  
         ![空の Web パーツ ページ](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")  
  
    6.  このページを別の Web パーツを追加する必要があります。  
  
### <a name="adding-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加します。  
 Web パーツ ページに、ビジネス データ一覧 Web パーツを追加する必要がありますようになりました。 この Web パーツを使用して検索式に一致する SAP システムから顧客の一覧が取得されます。 この Web パーツに対応する、 **Finder**メソッド インスタンス (*GetCustomerByName_Instance*) でビジネス データ カタログ定義エディターを作成します。  
  
##### <a name="to-add-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加するには  
  
1.  Customer_SalesOrders] ページで、**ヘッダー**セクションで、[ **Web パーツの追加**。  
  
2.  **Web パーツの追加** ダイアログ ボックスで、**ビジネス データ**セクションで、**ビジネス データ一覧**チェック ボックスをオンにして**追加**します。  
  
     ![ビジネス データ Web パーツを作成するオプション](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  新しく追加されたビジネス データ一覧 Web パーツ、クリックして、**ツール ウィンドウを開く**リンク。  
  
     ![Web パーツのツール ウィンドウを開く](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  ビジネス データ一覧のツール ウィンドウが右側のウィンドウで開きます。 **ビジネス データ一覧**セクションの**型**フィールドに、をクリックして、**参照**ボタン。  
  
     ![ビジネス データ一覧のツール ウィンドウ](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")  
  
5.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **Customer_Order_Instance**アプリケーション、およびクリック**OK**します。  
  
     ![アプリケーション インスタンスの選択](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")  
  
6.  展開、**外観**ノード、および、**タイトル**ボックスに、Web パーツのタイトルを入力します。 この Web パーツでは、入力**顧客リスト**します。  
  
7.  ビジネス データ一覧のツール ウィンドウで、次のようにクリックします。**適用**、 をクリックし、 **OK**します。 ビジネス データ一覧 Web パーツは、次のようになります。  
  
     ![ビジネス データ一覧 Web パーツ](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")  
  
8.  Web パーツには、SD_RFC_CUSTOMER_GET RFC を実行することによって返されるフィールドが一覧表示します。 SharePoint ポータルに表示しないフィールドを削除することができます。 フィールドを削除する をクリックして、**ビューの編集**Web パーツの右上隅にリンクします。  
  
9. ビューの編集 ページで、列 セクションを表示しない列に対してチェック ボックスをオフにします。  
  
     ![SharePoint で特定の列を表示](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")  
  
10. **[OK]** をクリックします。  
  
### <a name="adding-a-business-data-item-web-part"></a>ビジネス データ項目の Web パーツを追加します。  
 Web パーツ ページに、ビジネス データ項目の Web パーツを追加する必要がありますようになりました。 この Web パーツは、作成したビジネス データ一覧 Web パーツにも接続されます。 これにより、ビジネス データ一覧 Web パーツで選択した顧客の詳細を表示することができます。 この Web パーツに対応する、 **Specificfinder**メソッド インスタンス (*GetCustomerByNumber_Instance*) でビジネス データ カタログ定義エディターを作成します。  
  
##### <a name="to-add-a-business-data-item-web-part"></a>ビジネス データ項目の Web パーツを追加するには  
  
1.  Customer_SalesOrders ページで、右上隅にある**サイトの操作**、 をクリックし、**ページの編集**します。  
  
2.  Customer_SalesOrders] ページで、**左列**セクションで、[ **Web パーツの追加**します。  
  
3.  **Web パーツの追加** ダイアログ ボックスで、**ビジネス データ**セクションで、**ビジネス データ項目**チェック ボックスをオンにして**追加**します。  
  
4.  新しく追加されたビジネス データ項目 Web パーツ、クリックして、**ツール ウィンドウを開く**リンク。  
  
5.  ビジネス データ項目のツール ウィンドウが右側のウィンドウで開きます。 **ビジネス データ項目**セクションの**型**フィールドに、をクリックして、**参照**ボタン。  
  
     ![ビジネス データ項目のツール ウィンドウ](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")  
  
6.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **Customer_Order_Instance**アプリケーション、およびクリック**OK**します。  
  
7.  **ビュー**一覧で、**既定**します。  
  
8.  ままに、**項目**リストが空です。  
  
    > [!NOTE]
    >  **項目**フィールドに、顧客名または詳細を表示する顧客番号を指定する必要があります。 入力パラメーターとして機能するには、「この Web パーツ。 ビジネス データ一覧 Web パーツに接続して、入力パラメーターを取得するため、項目を明示的に指定すること必要がありますできません。  
  
9. **フィールド**セクションで、**選択**ページに表示するフィールドを選択します。  
  
10. 展開、**外観**ノード、および、**タイトル**フィールドに、Web パーツのタイトルを指定します。 この Web パーツでは、指定**特定の顧客詳細**します。  
  
11. クリックして**適用**、順にクリックします**OK**します。  
  
12. Web パーツを接続、**顧客リスト**Web パーツ。 そのためには次を行います。  
  
    1.  クリックして**編集**Web パーツの右上隅にします。  
  
    2.  コンテキスト メニューをポイント**接続**、 をポイント**から項目を取得**、 をクリック**顧客リスト**します。  
  
         ![2 つの Web パーツの接続](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")  
  
### <a name="adding-a-business-data-related-list-web-part"></a>リスト Web パーツに関連のビジネス データの追加  
 Web パーツ ページに、ビジネス データ関連一覧 Web パーツを追加する必要がありますようになりました。 先ほど作成したビジネス データ一覧 Web パーツをこの Web パーツを接続することもされます。 これにより、ビジネス データ一覧 Web パーツで選択した顧客の販売注文を表示することができます。 この Web パーツに対応する、**アソシエーション**メソッド インスタンス (*SalesOrderForCustomer_Instance*) でビジネス データ カタログ定義エディターを作成します。  
  
##### <a name="to-add-a-business-data-related-list-web-part"></a>ビジネス データ関連一覧 Web パーツを追加するには  
  
1.  Customer_SalesOrders] ページで、**本文**セクションで、[ **Web パーツの追加**。  
  
2.  **Web パーツの追加** ダイアログ ボックスで、**ビジネス データ**セクションで、**ビジネス データ関連一覧**チェック ボックスをオンにして**追加**します。  
  
3.  新しく追加されたビジネス データ関連一覧 Web パーツで、をクリックして、**ツール ウィンドウを開く**リンク。  
  
4.  ビジネス データ関連一覧のツール ウィンドウが右側のウィンドウで開きます。 **ビジネス データ関連一覧**セクションの**型**フィールドに、をクリックして、**参照**ボタン。  
  
     ![ビジネス データ関連一覧](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")  
  
5.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **Customer_Order_Instance**アプリケーション、およびクリック**OK**します。 **リレーションシップ**リストの名前を設定します、**アソシエーション**メソッド インスタンス (*SalesOrderForCustomer_Instance*)。  
  
6.  展開、**外観**ノード、および、**タイトル**ボックスに、Web パーツのタイトルを入力します。 この Web パーツでは、入力**特定の顧客の販売注文**します。  
  
7.  クリックして**適用**、順にクリックします**OK**します。  
  
8.  Web パーツには、BAPI_SALESORDER_GETLIST RFC を実行することによって返されるフィールドが一覧表示します。 SharePoint ポータルに表示しないフィールドを削除することができます。 フィールドを削除する をクリックして、**ビューの編集**Web パーツの右上隅にリンクします。  
  
9. ビューの編集 ページで、**列**セクションで、表示しない列に対してテキスト ボックスをオフにします。  
  
10. **[OK]** をクリックします。  
  
11. Web パーツを接続、**顧客リスト**Web パーツ。 そのためには次を行います。  
  
    1.  クリックして**編集**の右上隅に向かって、**特定の顧客の販売注文**Web パーツ。  
  
    2.  コンテキスト メニューをポイント**接続**、 をポイント**関連項目を取得**、順にクリックします**顧客リスト**します。  
  
12. をクリックして**編集モードを終了**ページの右上隅にあるからです。  
  
## <a name="next-steps"></a>次の手順  
 SAP システムからデータを取得することによって、SharePoint アプリケーションをテストします。 参照してください[手順 4: SharePoint アプリケーションをテスト](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SAP システムからのデータを SharePoint サイトに表示する](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)