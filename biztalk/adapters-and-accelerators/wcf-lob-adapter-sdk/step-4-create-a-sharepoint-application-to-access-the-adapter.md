---
title: "手順 4: アダプターにアクセスする Sharepoint アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2d8c398-370a-4c62-961d-0eab6066ad5a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3360bbdf5ae5a6a8dde9851c544342ea6a6bc1cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-a-sharepoint-application-to-access-the-adapter"></a>手順 4: アダプターにアクセスする Sharepoint アプリケーションを作成します。
![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **所要時間:** 15 分  
  
 このステップでは、ビジネス データ カタログ定義エディター ツールを使用して作成したアプリケーション定義ファイルを実行し、Microsoft Office SharePoint Server にインポートします。  
  
## <a name="prerequisites"></a>前提条件  
  
-   必要がありますがファイルを作成したアプリケーション」の説明に従って[手順 3: アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)です。  
  
-   Microsoft シングル サインオン サービスを実行する必要があります。  
  
## <a name="how-to-create-a-sharepoint-application"></a>SharePoint アプリケーションを作成する方法  
 SharePoint アプリケーションを作成するには、次の手順が含まれます。  
  
-   SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。  
  
-   共有サービス プロバイダーを作成し、アプリケーション定義ファイルをインポートします。  
  
-   Web パーツ ページを作成し、Web パーツを追加します。  
  
 このトピックでは、次の手順を実行する方法を示します。  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>SharePoint での SSO アプリケーションの作成  
 SharePoint アプリケーションからユーザーの資格情報をエコー アダプターに渡すには、ユーザー アカウントまたはグループにマップされている SSO アプリケーションを設定する必要があります。  
  
#### <a name="manage-server-settings-for-single-sign-on"></a>シングル サインオン用のサーバー設定を管理します。  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 **開始** メニューのをポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  上部のナビゲーション バーで、をクリックして**Operations**です。  
  
3.  [操作] ページで、**セキュリティの構成**セクションで、をクリックして**でのシングル サインオンの設定を管理**です。  
  
4.  シングル サインオン] ページの設定の管理で、**サーバー設定**セクションで、[**サーバー設定の管理**です。  
  
5.  このページの情報が、シングル サインオンのインストールの正しいことを確認します。 これらの操作の詳細についてを参照してください「でのシングル サインオン (Office SharePoint Server) を構成する」で[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。  
  
#### <a name="manage-settings-for-enterprise-application-definitions"></a>エンタープライズ アプリケーション定義の設定を管理します。  
  
1.  SharePoint サーバーの全体管理で、上部のナビゲーション バーで、をクリックして**Operations**です。  
  
2.  [操作] ページで、**セキュリティの構成**セクションで、をクリックして**でのシングル サインオンの設定の管理**です。  
  
3.  シングル サインオン] ページの設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、[**企業アプリケーション定義の設定の管理**です。  
  
4.  エンタープライズ アプリケーション定義の管理 ページで、**新しい項目の**します。  
  
5.  作成エンタープライズ アプリケーション定義 ページ、設定、**表示名**フィールドを**EchoSSO**、し、設定、**アプリケーション名**フィールドを**EchoSSO**です。 この値の一致で指定した SecondarySsoApplicationId[手順 3: アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)です。  
  
6.  **連絡先の電子メール アドレス**フィールドで、お客様の電子メール アドレスを入力し、をクリックして**OK**です。  
  
#### <a name="manage-account-information-for-enterprise-application-definitions"></a>エンタープライズ アプリケーション定義のアカウント情報を管理します。  
  
1.  SharePoint サーバーの全体管理で、上部のナビゲーション バーで、をクリックして**Operations**です。  
  
2.  操作 ページで、**セキュリティ構成セクション**、 をクリックして**でのシングル サインオンの設定を管理**です。  
  
3.  シングル サインオン] ページの設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、[**管理アカウントについて、エンタープライズ アプリケーション定義**です。  
  
4.  [エンタープライズ アプリケーション定義の管理アカウント情報、選択**EchoSSO**から、**エンタープライズ アプリケーション定義**] ボックスの一覧です。  
  
5.  **グループ アカウント名**フィールドに、このアプリケーションの定義をセキュリティで保護するために使用する Windows グループを入力します。 たとえば、 **DOMAIN\Domain ユーザー**です。  
  
6.  **[設定]**をクリックします。  
  
7.  EchoSSO アカウント情報の提供 ページで、 **Username**フィールド型**testuser**、し、**パスワード**フィールド型**testpassword**.  
  
8.  をクリックして**OK**、順にクリック**完了**です。  
  
## <a name="creating-a-shared-services-provider-and-importing-the-application-definition-file"></a>共有サービス プロバイダーを作成し、アプリケーション定義ファイルをインポートします。  
 共有サービス プロバイダー (SSP) は、共有サービスとその関連リソースの論理グループです。 SSP を作成するには、SharePoint サーバーの全体管理コンソールを使用します。 この例は、SSP. で動作します。 SSP の作成の詳細については、次を参照してください。"章の概要: を作成および構成共有サービスのプロバイダー"で[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)です。  
  
### <a name="to-import-the-application-definition-file"></a>アプリケーション定義ファイルをインポートするには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 **開始** メニューのをポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。  
  
3.  **ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**です。  
  
4.  アプリケーション定義のインポート ページで、をクリックして**参照**、し EchoWS.xml ファイルを選択します。  
  
5.  をクリックして**インポート**、順にクリック**OK**です。  
  
## <a name="creating-web-parts"></a>Web パーツを作成します。  
 ビジネス データ カタログ定義エディターで作成したメソッドのインスタンスを使用するように SharePoint サイトで Web パーツを作成する必要があります。 Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含むおよびデータベース情報が使用できる再利用可能なコンポーネントです。  
  
#### <a name="to-create-a-web-part-page"></a>Web パーツ ページを作成するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 **開始** メニューのをポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーション定義ファイルをインポートした SSP の名前をクリックします。  
  
3.  共有サービスの管理 ページの右上隅で、をクリックして**サイトの操作**、クリックして**作成**です。  
  
     ![サイトの操作を作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")  
  
4.  **作成** ページの 、 **Web ページ**セクションで、 **Web パーツ ページ**です。  
  
5.  [新しい Web パーツ] ページで、**名前**フィールドに「 **EchoPart**、し、[**ページ全体を垂直方向**から、 **レイアウトテンプレートを選択した**] ボックスの一覧です。  
  
6.  **[作成]**をクリックします。  
  
#### <a name="to-add-a-business-data-web-part"></a>ビジネス データ Web パーツを追加するには  
  
1.  **[Web パーツの追加]**をクリックします。  
  
2.  **Web パーツの追加**ダイアログ ボックスで、**ビジネス データ一覧**、クリックして**追加**です。  
  
     ![ビジネス データ一覧](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")  
  
3.  をクリックして**ツール ウィンドウを開いて**です。  
  
4.  ビジネス データ一覧のツール ウィンドウは、右側のウィンドウで開きます。 **ビジネス データ一覧** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。  
  
     ![種類を選択して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")  
  
5.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **EchoWSLob_Instance**クリックしてアプリケーションでは、 **OK**です。  
  
6.  ビジネス データ一覧のツール ウィンドウで、をクリックして**OK**です。  
  
7.  EchoGreetings メソッドに渡すグリーティング値を入力できるフィールドが表示されます。 応答メッセージ フィールドにデータを入力し、クリックして**データの取得**です。 これにより、IIS でホストされている Echo アダプターの EchoGreetings メソッドを呼び出し、応答を返します。  
  
     ![EchoGreetings 一覧](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")  
  
    > [!NOTE]
    >  [名前] 列では、ユーザー情報は含まれませんが、BDC をのみ表示されます。名前です。 これは、BDC が単純なレコード構造のみを必要とし、[名前] フィールドで表される複雑な構造は表示されません。  
  
8.  をクリックして**編集モードの終了**ページの上にあるからです。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 アプリケーション定義をインポートし、この定義を使用して、操作を呼び出し、EchoGreetings エコー アダプターの Web パーツを作成する、SharePoint 3.0 サーバーの全体管理を使用しました。  
  
## <a name="next-steps"></a>次の手順  
 このチュートリアルが完了しました。 詳細については、ビジネス データ カタログを使用して参照してください「ビジネス データ カタログ」 [http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: IIS でエコー アダプターをホストします。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)