---
title: '手順 4: アダプターにアクセスする Sharepoint アプリケーションの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d8c398-370a-4c62-961d-0eab6066ad5a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15da47a4171d6bdf4f3b53e2208851bd15ecb0d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986643"
---
# <a name="step-4-create-a-sharepoint-application-to-access-the-adapter"></a>手順 4: アダプターにアクセスする Sharepoint アプリケーションを作成します。
![手順 4 の 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **所要時間:** 15 分  
  
 この手順では、ビジネス データ カタログ定義エディター ツールを使用して作成したアプリケーション定義ファイルを取得し、Microsoft Office SharePoint Server にインポートします。  
  
## <a name="prerequisites"></a>前提条件  
  
-   作成済みアプリケーションのファイル」の説明に従って[手順 3: アプリケーション定義ファイルを作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)です。  
  
-   Microsoft シングル サインオン サービスを実行する必要があります。  
  
## <a name="how-to-create-a-sharepoint-application"></a>SharePoint アプリケーションを作成する方法  
 SharePoint アプリケーションを作成するには、次の手順が含まれます。  
  
- SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。  
  
- 共有サービス プロバイダーを作成し、アプリケーション定義ファイルをインポートします。  
  
- Web パーツ ページを作成し、Web パーツを追加します。  
  
  このトピックでは、次の手順を実行する方法を示します。  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>SharePoint での SSO アプリケーションの作成  
 SharePoint アプリケーションからユーザーの資格情報をエコー アダプターに渡すには、ユーザー アカウントまたはグループにマップする SSO アプリケーションを設定する必要があります。  
  
#### <a name="manage-server-settings-for-single-sign-on"></a>シングル サインオン用のサーバー設定を管理します。  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 **開始**メニューで、**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリックし、 **SharePoint 3.0 サーバーの全体管理**.  
  
2.  上部のナビゲーション バーでクリックして**操作**します。  
  
3.  操作 ページで、**セキュリティの構成**セクションで、**でシングル サインオンの設定を管理**。  
  
4.  シングル サインオン] ページで、次の管理設定で、**サーバー設定**セクションで、[**サーバー設定の管理**します。  
  
5.  このページの情報が、シングル サインオンのインストールの正しいことを確認します。 これらの操作の詳細についてを参照してください「シングル サインオン (Office SharePoint Server) の構成」 [ http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)します。  
  
#### <a name="manage-settings-for-enterprise-application-definitions"></a>エンタープライズ アプリケーション定義の設定を管理します。  
  
1.  SharePoint サーバーの全体管理で、上部のナビゲーション バーでクリックして**操作**します。  
  
2.  操作 ページで、**セキュリティの構成**セクションで、**でシングル サインオンの設定の管理**。  
  
3.  シングル サインオン] ページで、次の管理設定で、**エンタープライズ アプリケーション定義の設定**セクションで、[**企業アプリケーション定義の設定の管理**します。  
  
4.  エンタープライズ アプリケーション定義の管理 ページで、次のようにクリックします。**新しい項目の**します。  
  
5.  作成エンタープライズ アプリケーション定義 ページで、設定、**表示名**フィールドを**EchoSSO**、し、設定、**アプリケーション名**フィールドを**EchoSSO**します。 この値がで指定した SecondarySsoApplicationId と一致する必要があります[手順 3: アプリケーション定義ファイルを作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)です。  
  
6.  **連絡先の電子メール アドレス**フィールドを電子メール アドレスを入力し、をクリックし、 **OK**します。  
  
#### <a name="manage-account-information-for-enterprise-application-definitions"></a>エンタープライズ アプリケーション定義のアカウント情報を管理します。  
  
1.  SharePoint サーバーの全体管理で、上部のナビゲーション バーでクリックして**操作**します。  
  
2.  操作 ページで、**セキュリティ構成セクション**、 をクリックして**でシングル サインオンの設定を管理**します。  
  
3.  シングル サインオン] ページで、次の管理設定で、**エンタープライズ アプリケーション定義の設定**セクションで、[**管理アカウントについて、エンタープライズ アプリケーション定義**します。  
  
4.  エンタープライズ アプリケーション定義の管理アカウントは、次のように選択します。 **EchoSSO**から、**エンタープライズ アプリケーション定義**一覧。  
  
5.  **グループ アカウント名**フィールドに、このアプリケーションの定義をセキュリティで保護するために使用する Windows グループを入力します。 たとえば、 **DOMAIN\Domain ユーザー**します。  
  
6.  **[設定]** をクリックします。  
  
7.  EchoSSO アカウント情報の提供 ページで、 **Username**フィールドに「 **testuser**、し、**パスワード**フィールドに「 **testpassword**.  
  
8.  をクリックして**OK**、順にクリックします**完了**します。  
  
## <a name="creating-a-shared-services-provider-and-importing-the-application-definition-file"></a>共有サービス プロバイダーを作成し、アプリケーション定義ファイルをインポートします。  
 共有サービス プロバイダー (SSP) は、共有サービスとその関連リソースの論理グループです。 SSP は、SharePoint サーバーの全体管理コンソールを使用して作成できます。 この例は、任意 SSP. で動作します。 SSP の作成の詳細については、"」の章の概要: を作成および構成共有サービスのプロバイダー"で[ http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)を参照してください。  
  
### <a name="to-import-the-application-definition-file"></a>アプリケーション定義ファイルをインポートするには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 **開始**メニューで、**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリックし、 **SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーションの定義をインポートする SSP の名前をクリックします。  
  
3.  **ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**します。  
  
4.  アプリケーション定義のインポート ページで、次のようにクリックします。**参照**、し EchoWS.xml ファイルを選択します。  
  
5.  クリックして**インポート**、順にクリックします**OK**します。  
  
## <a name="creating-web-parts"></a>Web パーツの作成  
 ビジネス データ カタログ定義エディターで作成メソッドのインスタンスを使用する SharePoint サイトで Web パーツを作成する必要があります。 Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含めることができ、データベース情報を再利用可能なコンポーネントです。  
  
#### <a name="to-create-a-web-part-page"></a>Web パーツ ページを作成するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 **開始**メニューで、**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリックし、 **SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーション定義ファイルをインポートした SSP の名前をクリックします。  
  
3.  共有サービス管理 ページで、右上隅にある**サイトの操作**、 をクリックし、**作成**です。  
  
     ![サイトの操作を作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")  
  
4.  **作成**ページで、 **Web ページ**セクションで、 **Web パーツ ページ**します。  
  
5.  新しい Web パーツ] ページで、**名前**フィールドに「 **EchoPart**、し、[**ページ全体を垂直**から、 **レイアウトテンプレートを選択した**一覧。  
  
6.  **[作成]** をクリックします。  
  
#### <a name="to-add-a-business-data-web-part"></a>ビジネス データ Web パーツを追加するには  
  
1.  **[Web パーツの追加]** をクリックします。  
  
2.  **Web パーツの追加**ダイアログ ボックスで、**ビジネス データ一覧**、 をクリックし、**追加**します。  
  
     ![ビジネス データ一覧](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")  
  
3.  クリックして**ツール ウィンドウを開く**します。  
  
4.  ビジネス データ一覧のツール ウィンドウが右側のウィンドウで開きます。 **ビジネス データ一覧**セクションの**型**フィールドに、をクリックして、**参照**ボタン。  
  
     ![種類を選択して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")  
  
5.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **EchoWSLob_Instance**アプリケーション、およびクリック**OK**します。  
  
6.  ビジネス データ一覧のツール ウィンドウで、をクリックして**OK**します。  
  
7.  EchoGreetings メソッドに渡される応答メッセージの値を入力することを許可するフィールドが表示されます。 応答メッセージのフィールドにデータを入力し、クリックして**データの取得**します。 これにより、IIS でホストされているエコー アダプターの EchoGreetings メソッドを呼び出し、応答を返します。  
  
     ![EchoGreetings 一覧](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")  
  
    > [!NOTE]
    >  [名前] 列にユーザーの情報が含まれていませんが、BDC をのみが表示されます。名前。 これは、BDC 単純なレコード構造体、のみを要求し、[名前] フィールドで表される複雑な構造は表示されないために発生します。  
  
8.  クリックして**編集モードの終了**ページの上部隅から。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 アプリケーション定義をインポートし、この定義を使用してエコー アダプターの EchoGreetings 操作を呼び出す Web パーツを作成するのには、SharePoint 3.0 サーバーの全体管理を使用しました。  
  
## <a name="next-steps"></a>次の手順  
 このチュートリアルが完了しました。 詳細については、ビジネス データ カタログを使用して参照してください「ビジネス データ カタログ」 [ http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: IIS でエコー アダプターをホストする](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)