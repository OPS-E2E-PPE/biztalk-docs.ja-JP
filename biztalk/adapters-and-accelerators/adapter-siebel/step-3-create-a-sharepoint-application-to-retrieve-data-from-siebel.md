---
title: "手順 3: Siebel からデータを取得する SharePoint アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86bde531-2daf-452b-b3e6-5481d66f72e7
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94537b57a731e5d71459518fcbb0a528b6240d19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel"></a>手順 3: Siebel からデータを取得する SharePoint アプリケーションを作成します。
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 15 分です。  
  
 **目標:**今すぐアプリケーション定義ファイルをエディターを使用して、ビジネス データ カタログの定義を作成して、Office SharePoint Server にインポートする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
  
-   必要がありますが作成した、アプリケーション定義ファイル」の説明に従って[手順 2: Siebel ビジネス コンポーネント操作のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)です。  
  
-   Microsoft シングル サインオン サービスを実行する必要があります。  
  
## <a name="how-to-create-a-sharepoint-application"></a>SharePoint アプリケーションを作成する方法  
 SharePoint アプリケーションを作成するには、次の手順が含まれます。  
  
-   SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。  
  
-   共有サービス プロバイダー (SSP) を作成します。  
  
-   アプリケーション定義ファイルをインポートします。  
  
-   Web パーツ ページを作成し、Web パーツを追加  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>SharePoint での SSO アプリケーションの作成  
 SharePoint アプリケーションからの Siebel システム データにアクセスするには、Siebel のユーザーに、SharePoint ユーザーにマップする SSO アプリケーションを設定する必要があります。 SharePoint で SSO アプリケーションを作成するには、次の手順が含まれます。  
  
1.  **シングル サインオンの設定をサーバー管理**です。 このステップでは、管理、シングル サインオン サービスを設定したりできるユーザー アカウントを指定します。 サーバー設定の管理ページから行うことができます。 このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。 この手順の詳細についてで「構成に対するシングル サインオン - Office SharePoint Server 2007」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。  
  
2.  **エンタープライズ アプリケーション定義の設定を管理**です。 このステップでは、エンタープライズ アプリケーション定義の設定を構成します。 エンタープライズ アプリケーション定義 ページの設定の管理から行うことができます。 このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。  
  
    1.  サーバーの全体管理で、上部のナビゲーション バーで、をクリックして**Operations**です。  
  
    2.  [操作] ページで、**セキュリティの構成**セクションで、をクリックして**でのシングル サインオンの設定を管理**です。  
  
    3.  シングル サインオン] ページの設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、[**企業アプリケーション定義の設定を管理**です。  
  
    4.  [エンタープライズ アプリケーション定義の管理] ページで、値を指定して、**表示名**、**アプリケーション名**、および**連絡先の電子メール アドレス**フィールドです。  
  
        > [!IMPORTANT]
        >  **アプリケーション名**フィールドに、指定した同じ SSO アプリケーション名を指定するかどうかを確認、 **SecondarySsoApplicationId**として、アプリケーション定義ファイルの作成中に変数説明されている[手順 2: Siebel ビジネス コンポーネント操作のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)です。  
  
    5.  既定では、他のフィールドのままにし、をクリックして**OK**です。  
  
3.  **エンタープライズ アプリケーション定義のアカウント情報を管理する**です。 このステップでは SharePoint からエンタープライズ アプリケーションに接続するには、個々 のユーザーまたはグループを有効にします。 基本的には、この手順でマップする個々 のユーザーまたはグループのユーザーに LOB システムに。 また、LOB システムへの接続に資格情報を指定します。 そのため操作は、エンタープライズ アプリケーション定義 ページのアカウント情報の管理から実行できます。 このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。 この手順の詳細についてで「エンタープライズ アプリケーション定義のアカウント情報の管理」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。  
  
## <a name="creating-a-shared-services-provider"></a>共有サービス プロバイダーを作成します。  
 SSP は、共有サービスとその関連リソースの論理グループです。 SharePoint サーバーの全体管理コンソールを使用して SSP を作成することができます。  
  
 SSP の作成中に Web サイトを定義する必要があります。 ポート番号および作成するサイトのアドレスに注意してください。 このサイトには、ビジネス データ カタログ アプリケーション定義をインポートします。  
  
 SSP の作成の詳細については、次を参照してください。"章の概要: を作成し、共有サービス プロバイダーを構成する"で[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)です。  
  
## <a name="importing-the-application-definition-file"></a>アプリケーション定義ファイルのインポート  
 SSP にアプリケーション定義ファイルをインポートする必要があります。  
  
#### <a name="to-import-the-application-definition-file"></a>アプリケーション定義ファイルをインポートするには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。  
  
3.  **ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**です。  
  
4.  Siebel_Account.xml、[参照] を開くと、アプリケーション定義のインポート ページで、ファイルを選択し、をクリックして**開く**です。  
  
5.  **[インポート]**をクリックします。  
  
6.  **[OK]**をクリックします。  
  
 アプリケーションをインポートした後に移動して、アプリケーションを表示できます、**ビュー アプリケーション**リンクします。 アプリケーション内のエンティティを表示するのには、アプリケーション名をクリックします。  
  
## <a name="creating-web-parts"></a>Web パーツを作成します。  
 SharePoint サイトの表示し、Siebel システムから抽出するビジネス データを管理する Web パーツを作成する必要があります。 Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含むおよびデータベース情報が使用できる再利用可能なコンポーネントです。  
  
 このチュートリアルでは、Web パーツは、ビジネス データ カタログ定義エディターで作成されたメソッドのインスタンスに対して作成されます。 Office SharePoint Server では、特定の使用の Web パーツのさまざまな種類を提供します。 Finder メソッド インスタンスは、使用、**ビジネス データ一覧**Web パーツ。 この Web パーツでは、アカウントのビジネス コンポーネントでクエリを実行する検索文字列を指定することができます。 このチュートリアルを呼び出してこの、**クエリ アカウント**Web パーツ。  
  
 このセクションでは、これらの Web パーツを作成する手順を説明します。 Web パーツの作成の詳細についてを参照してください (「ビジネス データ リストのカスタマイズ、Web パーツ、およびサイト」)、Microsoft Office SharePoint Server 2007 ドキュメント[http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)です。  
  
 Web パーツは、1 つの Web パーツ ページに追加されます。 Web パーツを追加する前に、Web パーツ ページを作成する必要があります。 このチュートリアルでは、Web パーツ ページと呼ばれる**Siebel アカウント**です。  
  
### <a name="creating-a-web-part-page"></a>Web パーツ ページを作成します。  
 このセクションでは、Web パーツ ページを作成する手順を説明します。  
  
##### <a name="to-create-a-web-part-page"></a>Web パーツ ページを作成するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリック**SharePoint 3.0 サーバーの全体管理**です。  
  
2.  左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。  
  
3.  共有サービスの管理 ページで、右上隅から**サイトの操作**、クリックして**作成**です。  
  
     ![Web パーツを作成するにはメニュー](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  作成 ページで、 **Web ページ**セクションで、 **Web パーツ ページ**です。  
  
5.  新しい Web パーツ ページで、次の操作を行います。  
  
    1.  **名前**フィールドに、ページの名前を指定します。 このチュートリアルでは、名前を指定、として`Siebel Account`です。  
  
    2.  選択、**ファイルが既に存在する場合に上書き**チェック ボックスを作成するページと同じ名前で古いページを上書きする場合。  
  
    3.  **レイアウト** セクションから、**レイアウト テンプレートを選択して**ボックスで、Web パーツ ページのレイアウトを選択します。 このチュートリアルでは、次のように選択します。**ページ全体を垂直方向**です。  
  
    4.  **保存場所**セクションで、**ドキュメント ライブラリ**一覧で、**フォーム テンプレート**です。  
  
    5.  **[作成]**をクリックします。 次の図は、作成した後、Web パーツ ページを示します。  
  
         ![空の Web パーツ ページ](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")  
  
     このページを別の Web パーツを追加する必要があります。  
  
### <a name="adding-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加します。  
 ビジネス データ一覧 Web パーツを Web パーツ ページに追加する必要があります。 この Web パーツを使用して、検索式を使用してアカウントのビジネス コンポーネントは照会します。 この Web パーツは、ビジネス データ カタログ定義エディターで作成した Finder メソッド インスタンス (QueryAccount) に対応します。  
  
##### <a name="to-add-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加するには  
  
1.  **Siebel アカウント** ページの 、**ヘッダー**セクションで、 **Web パーツの追加**です。  
  
2.  **Web パーツの追加** ダイアログ ボックスで、**ビジネス データ** セクションで、選択、**ビジネス データ一覧**チェック ボックスをクリックして**追加**です。  
  
     ![ビジネス データ Web パーツを作成するオプションを](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  新しく追加されたビジネス データ一覧 Web パーツ、クリックして、**ツール ウィンドウを開いて**リンクします。  
  
     ![Web パーツのツール ウィンドウを開いて](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  ビジネス データ一覧のツール ウィンドウは、右側のウィンドウで開きます。 **ビジネス データ一覧** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。  
  
     ![ビジネス データ一覧のツール ウィンドウ](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")  
  
5.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **Siebel_Account_Instance**クリックしてアプリケーションでは、 **OK**です。  
  
     ![アプリケーション インスタンスの選択](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")  
  
6.  展開、**外観**ノード、および、**タイトル**フィールドに、Web パーツのタイトルを指定します。 この Web パーツを指定する**アカウント一覧**です。  
  
7.  ビジネス データ一覧のツール ウィンドウで、をクリックして**適用**、クリックして**OK**です。 ビジネス データ一覧 Web パーツは、次のようになります。  
  
     ![ビジネス データ一覧 Web パーツ](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")  
  
    > [!NOTE]
    >  パラメーターの列の順序を変更することもできます。 これを行う をクリックして、**ビューの編集**Web パーツの右上隅にあるリンクします。  
  
8.  をクリックして**編集モードの終了**ページの右上隅にあるからです。  
  
## <a name="next-steps"></a>次の手順  
 Siebel システムからデータを取得することによって、SharePoint アプリケーションをテストします。 参照してください[手順 4: SharePoint アプリケーションをテスト](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SharePoint サイト上の Siebel システムからのデータの表示](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)