---
title: 手順 3:Siebel からデータを取得する SharePoint アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86bde531-2daf-452b-b3e6-5481d66f72e7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d6d70e1c2d876262ddab35720be4e6991d0374d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370533"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel"></a>手順 3:Siebel からデータを取得する SharePoint アプリケーションを作成します。
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 15 分。  
  
 **目標:** ビジネス データ カタログ定義エディターを使用して作成したアプリケーション定義ファイルを受け取り、Office SharePoint Server にインポートする必要がありますようになりました。  
  
## <a name="prerequisites"></a>前提条件  
  
-   作成済み、アプリケーション定義ファイル」の説明に従って[手順 2。Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルの作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)です。  
  
-   Microsoft シングル サインオン サービスを実行する必要があります。  
  
## <a name="how-to-create-a-sharepoint-application"></a>SharePoint アプリケーションを作成する方法  
 SharePoint アプリケーションを作成するには、次の手順が含まれます。  
  
-   SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。  
  
-   共有サービス プロバイダー (SSP) の作成します。  
  
-   アプリケーション定義ファイルをインポートします。  
  
-   Web パーツ ページを作成し、Web パーツを追加  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>SharePoint での SSO アプリケーションの作成  
 SharePoint アプリケーションからの Siebel システムのデータにアクセスするには、Siebel のユーザーに、SharePoint ユーザーにマップする SSO アプリケーションを設定する必要があります。 SharePoint での SSO アプリケーションを作成するには、次の手順が含まれます。  
  
1.  **シングル サインオンの設定をサーバー管理**します。 この手順では、管理、シングル サインオン サービスを設定しているユーザー アカウントを指定します。 サーバー設定の管理ページから行うことができます。 このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。 この手順の詳細については、ある「構成でシングル サインオン Office SharePoint Server 2007 の」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)します。  
  
2.  **エンタープライズ アプリケーション定義の設定を管理する**します。 この手順では、エンタープライズ アプリケーション定義の設定を構成します。 エンタープライズ アプリケーション定義 ページの設定の管理から行うことができます。 このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。  
  
    1.  サーバーの全体管理で、上部のナビゲーション バーでクリックして**操作**します。  
  
    2.  操作 ページで、**セキュリティの構成**セクションで、**でシングル サインオンの設定を管理**。  
  
    3.  シングル サインオン ページで、設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、**企業アプリケーション定義の設定を管理する**します。  
  
    4.  エンタープライズ アプリケーション定義の管理 ページで、値を指定、**表示名**、**アプリケーション名**、および**連絡先の電子メール アドレス**フィールド。  
  
        > [!IMPORTANT]
        >  **アプリケーション名**フィールドに、指定したのと同じ SSO アプリケーション名を指定するかどうかを確認、 **SecondarySsoApplicationId**として、アプリケーション定義ファイルを作成するときに変数説明されている[手順 2。Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルの作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)です。  
  
    5.  既定では、他のフィールドのままにし、クリックして**OK**します。  
  
3.  **エンタープライズ アプリケーション定義のアカウント情報の管理**します。 この手順では SharePoint からエンタープライズ アプリケーションに接続するには、個々 のユーザーまたはグループを有効にします。 基本的には、この手順でマップするか、個々 のユーザーまたはグループをユーザーに、LOB システムに。 また、LOB システムへの接続に資格情報を指定します。 アカウント情報の管理からのエンタープライズ アプリケーション定義 ページで、これを実行できます。 このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。 この手順の詳細については、ある「エンタープライズ アプリケーション定義のアカウント情報の管理」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)します。  
  
## <a name="creating-a-shared-services-provider"></a>共有サービス プロバイダーを作成します。  
 SSP は、共有サービスとその関連リソースの論理グループです。 SharePoint サーバーの全体管理コンソールを使用して SSP を作成できます。  
  
 SSP の作成中に Web サイトを定義する必要があります。 ポート番号とを作成するサイトのアドレスに注意してください。 このサイトには、ビジネス データ カタログ アプリケーション定義をインポートします。  
  
 SSP の作成の詳細については、次を参照してください。"」の章の概要。作成および共有サービス プロバイダーの構成"に[ http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)します。  
  
## <a name="importing-the-application-definition-file"></a>アプリケーション定義ファイルのインポート  
 SSP に今すぐアプリケーション定義ファイルをインポートする必要があります。  
  
#### <a name="to-import-the-application-definition-file"></a>アプリケーション定義ファイルをインポートするには  
  
1. SharePoint 3.0 サーバーの全体管理を開始します。 クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.  
  
2. 左側のナビゲーション ウィンドウで、アプリケーションの定義をインポートする SSP の名前をクリックします。  
  
3. **ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**します。  
  
4. Siebel_Account.xml、[参照] を開くと、アプリケーション定義のインポート ページで、ファイルを選択し、**オープン**します。  
  
5. **[インポート]** をクリックします。  
  
6. **[OK]** をクリックします。  
  
   アプリケーションをインポートした後、アプリケーションを表示して、**アプリケーションの表示**リンク。 アプリケーション内のエンティティを表示するのには、アプリケーション名をクリックします。  
  
## <a name="creating-web-parts"></a>Web パーツの作成  
 表示し、Siebel システムから抽出するビジネス データを管理する SharePoint サイト内の Web パーツを作成する必要があります。 Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含めることができ、データベース情報を再利用可能なコンポーネントです。  
  
 このチュートリアルでは、ビジネス データ カタログ定義エディター内に作成されたメソッド インスタンスの Web パーツが作成されます。 Office SharePoint Server では、特定の用途の場合は、さまざまな種類の Web パーツを提供します。 Finder メソッド インスタンスの場合は使用、**ビジネス データ一覧**Web パーツ。 この Web パーツでは、アカウントのビジネス コンポーネントにクエリを実行する検索文字列を指定することができます。 このチュートリアルを呼び出してこの、**クエリ アカウント**Web パーツ。  
  
 ここでは、これらの Web パーツを作成する手順について説明します。 Web パーツの作成の詳細についてを参照してください (「ビジネス データ リストのカスタマイズ、Web パーツ、およびサイト」) は、Microsoft Office SharePoint Server 2007 ドキュメント[ http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)します。  
  
 Web パーツは、1 つの Web パーツ ページに追加されます。 Web パーツを追加する前に、Web パーツ ページを作成する必要があります。 このチュートリアルでは、Web パーツ ページが呼び出されます**Siebel アカウント**します。  
  
### <a name="creating-a-web-part-page"></a>Web パーツ ページの作成  
 ここでは、Web パーツ ページを作成する手順について説明します。  
  
##### <a name="to-create-a-web-part-page"></a>Web パーツ ページを作成するには  
  
1. SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリック**SharePoint 3.0 サーバーの全体管理**します。  
  
2. 左側のナビゲーション ウィンドウで、アプリケーションの定義をインポートする SSP の名前をクリックします。  
  
3. 共有サービス管理 ページで、右上隅から**サイトの操作**、 をクリックし、**作成**です。  
  
    ![Web パーツを作成するにはメニュー](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4. 作成 ページで、 **Web ページ**セクションで、 **Web パーツ ページ**します。  
  
5. 新しい Web パーツ ページで、次の操作を行います。  
  
   1. **名前**フィールドに、ページの名前を指定します。 このチュートリアルと名前を指定`Siebel Account`します。  
  
   2. 選択、**ファイルが既に存在する場合に上書き**チェック ボックスで、古いページを作成するページと同じ名前で上書きする場合。  
  
   3. **レイアウト**セクションから、**レイアウト テンプレートの選択**ボックスに、Web パーツ ページのレイアウトを選択します。 このチュートリアルでは、次のように選択します。**ページ全体を垂直**します。  
  
   4. **保存場所**セクションで、**ドキュメント ライブラリ**一覧で、**フォーム テンプレート**します。  
  
   5. **[作成]** をクリックします。 次の図は、作成した後、Web パーツ ページを示します。  
  
       ![空の Web パーツ ページ](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")  
  
      このページを別の Web パーツを追加する必要があります。  
  
### <a name="adding-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加します。  
 Web パーツ ページに、ビジネス データ一覧 Web パーツを追加する必要がありますようになりました。 この Web パーツを使用して、検索式を使用して、アカウントのビジネス コンポーネントは照会します。 この Web パーツは、ビジネス データ カタログ定義エディターで作成した Finder メソッド インスタンス (QueryAccount) に対応します。  
  
##### <a name="to-add-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加するには  
  
1.  **Siebel アカウント**ページで、**ヘッダー**セクションで、 **Web パーツの追加**します。  
  
2.  **Web パーツの追加** ダイアログ ボックスで、**ビジネス データ**セクションで、**ビジネス データ一覧**チェック ボックスをオンにして**追加**します。  
  
     ![ビジネス データ Web パーツを作成するオプション](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  新しく追加されたビジネス データ一覧 Web パーツ、クリックして、**ツール ウィンドウを開く**リンク。  
  
     ![Web パーツのツール ウィンドウを開く](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  ビジネス データ一覧のツール ウィンドウが右側のウィンドウで開きます。 **ビジネス データ一覧**セクションの**型**フィールドに、をクリックして、**参照**ボタン。  
  
     ![ビジネス データ一覧のツール ウィンドウ](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")  
  
5.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **Siebel_Account_Instance**アプリケーション、およびクリック**OK**します。  
  
     ![アプリケーション インスタンスの選択](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")  
  
6.  展開、**外観**ノード、および、**タイトル**フィールドに、Web パーツのタイトルを指定します。 この Web パーツでは、指定**Account List**します。  
  
7.  ビジネス データ一覧のツール ウィンドウで、次のようにクリックします。**適用**、 をクリックし、 **OK**します。 ビジネス データ一覧 Web パーツは、次のようになります。  
  
     ![ビジネス データ一覧 Web パーツ](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")  
  
    > [!NOTE]
    >  パラメーターの列の順序を変更することもできます。 クリックして行うことができます、**ビューの編集**Web パーツの右上隅にあるリンクです。  
  
8.  をクリックして**編集モードの終了**ページの右上隅にあるからです。  
  
## <a name="next-steps"></a>次の手順  
 Siebel システムからデータを取得することによって、SharePoint アプリケーションをテストします。 参照してください[手順 4。SharePoint アプリケーションをテスト](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1:Siebel システムからのデータを SharePoint サイトに表示する](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)