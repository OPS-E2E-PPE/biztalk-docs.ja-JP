---
title: 手順 3:アプリケーション定義ファイルの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 843fafdb-571e-4da4-ad04-7dc7f23e03ac
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 455a4423a1fe420ec9a46fe8cb8236086e3f4309
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363247"
---
# <a name="step-3-create-an-application-definition-file"></a>手順 3:アプリケーション定義ファイルを作成します。
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 15 分  
  
 Microsoft Office SharePoint Server のビジネス データ カタログ機能は、公開し、基幹業務 (LOB) アプリケーションからのデータがポータルに組み込まれています。 ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用するアプリケーション定義ファイルをビルドする必要があります。  
  
 このステップでは、ビジネス データ カタログ アプリケーション定義ファイルを作成するのに Microsoft Office SharePoint Server 2007 SDK やで利用できるビジネス データ カタログ定義エディター ツールを使用します。 この定義ファイルでは、エコー アダプターの EchoGreetings メソッドについて説明し、アダプターと通信するように SharePoint を有効にする後の手順で使用されます。  
  
 作成している Microsoft Office SharePoint Server アプリケーションの目的は、エコー アダプターの EchoGreetings メソッドの呼び出しを SharePoint Web パーツを使用して応答を返すことができるようにです。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 2。Web プロジェクトを配置](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)します。 アクセスをビジネス データ カタログ定義エディター、Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされている必要があります。 SDK をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)します。  
  
## <a name="creating-an-application-definition-file"></a>アプリケーション定義ファイルを作成します。  
 このトピックでは、IIS でホストされる WCF アダプターを使用した SharePoint ビジネス データ カタログを接続するためのアプリケーション定義ファイルを作成する手順を提供します。  
  
#### <a name="to-connect-to-the-wcf-adapter-service-and-create-entities"></a>WCF アダプターのサービスに接続し、エンティティを作成するには  
  
1.  **スタート メニュー**、 をポイント**すべてのプログラム**、 をクリックし、 **Microsoft ビジネス データ カタログ定義エディター**します。  
  
2.  ツールバーの**LOB システムの追加**します。  
  
3.  LOB システムの追加 ウィンドウで、次のようにクリックします。 **web サービスへの接続**します。  
  
4.  **URL**ボックスに、WCF サービスの URL を入力します。 URL は、次の形式である必要があります。 `https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`  
  
5.  **[接続]** をクリックします。  
  
6.  使用可能な操作を表示するには、クリックして、 **Web メソッドの追加**タブ。EchoGreetings メソッドを表示する必要があります。 メソッドは、デザイン画面にドラッグします。  
  
7.  **[OK]** をクリックします。  
  
8.  **LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。 この例では、次のように入力します。 **EchoWSLOB**、 をクリックし、 **OK**します。  
  
9. 展開、 **EchoWSLob**ノードの順に展開し、**エンティティ**ノード。 選択**Entity0**プロパティ ウィンドウの入力**EchoGreetings**の値として、**名前**プロパティ。  
  
     ![Entity Name](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")  
  
## <a name="specify-user-name-and-password-headers-for-the-method"></a>メソッドのユーザー名とパスワードのヘッダーを指定します。  
 WCF アダプターを呼び出すときに、LOB システムに渡されるユーザーの資格情報を提供する必要があります。 [手順 1。Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)MyUserHeader と MyPassHeader フィールドにユーザー名とパスワード情報を提供することを要求するようにエコー アダプターを構成します。 このアプリケーションの定義ファイルの同じフィールド名を使用する必要がありますようになりました。  
  
#### <a name="to-specify-user-name-and-password-headers"></a>ユーザー名とパスワードのヘッダーを指定するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、 **EchoGreetings**ノードの順に展開し、**メソッド**ノード。  
  
2.  をクリックして、 **EchoGreetings**ノードのプロパティ ウィンドウで、省略記号ボタンをクリックして、 **(...)** ボタン、**プロパティ**フィールド。  
  
3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、し、**名前**型、プロパティ ペインのフィールド**HttpHeaderUserName**します。  
  
     ![Username ヘッダー フィールドの指定](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")  
  
4.  **PropertyValue**フィールドに「 **MyUserHeader**します。  
  
5.  クリックして**追加**、プロパティ ウィンドウの入力**HttpHeaderPassword**名前 フィールドに入力**MyPassHeader**の**PropertyValue**フィールド。  
  
6.  **[OK]** をクリックします。  
  
## <a name="set-up-single-sign-on-for-connecting-to-the-echo-adapter"></a>エコー アダプターに接続するためのシングル サインオンの設定します。  
 SharePoint からシングル サインオン情報を使用して、MyUserHeader と MyPassHeader 認証の値に設定します。 シングル サインオンには、このアプリケーションの定義ファイルをリンクするには、SecondarySsoApplicationId を提供する必要があります。  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a>SecondarySsoApplicationId のプロパティを設定するには  
  
1. メタデータ オブジェクト ウィンドウで、展開、 **EchoWSLOB**ノードの順に展開し、**インスタンス**ノード。  
  
2. クリックして**EchoWSLOB_Instance**、プロパティ ペインで、省略記号ボタンをクリックします<strong>([...])。</strong>ボタン、**プロパティ**フィールド。  
  
3. PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **SecondarySsoApplicationId**で、**名前**フィールド。  
  
4. **PropertyValue**フィールドに「 **EchoSSO**します。  
  
    ![Secondaryssoapplicationid の](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")  
  
5. **[OK]** をクリックします。  
  
## <a name="create-input-filters-and-default-values"></a>入力フィルターと既定値を作成します。  
 アプリケーション定義ファイルは、Web サービスに渡すことがユーザー入力をそのまま使用できる必要があります。 これを実現するには、次の一連のタスクを実行する必要があります。  
  
#### <a name="to-create-a-filter-and-map-it-to-the-greeting-parameter"></a>フィルターを作成して、あいさつ文パラメーターにマップするには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、 **EchoWSLOB**ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **EchoGreetings**メソッドを右クリックして**フィルター**、順にクリックします**フィルターの追加**します。  
  
3.  プロパティ ペインで次のように入力します。 **Greeting**で、**名前**フィールド。  
  
     ![フィルター名の設定](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")  
  
4.  メタデータ オブジェクト ウィンドウで、展開、 **EchoWSLOB**ノードの順に展開し、**メソッド**ノード  
  
5.  展開、 **EchoGreetings**メソッドを順に展開し、**パラメーター**ノード。  
  
6.  展開、 **greeting**ノード、2 つ目の順に展開および**greeting**ノード。  
  
7.  をクリックして、 **greetingText**ノードのプロパティ ウィンドウで次のように選択します。 **Greeting**から、 **FilterDescriptor**一覧。  
  
#### <a name="to-create-a-finder-method-instance-for-the-echogreetings-method"></a>EchoGreetings メソッドの Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、 **EchoWSLOB**ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **EchoGreetings**メソッドを右クリックして**インスタンス**、順にクリックします**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。  
  
3.  メソッド インスタンスの作成] ウィンドウで、次のようにクリックします**Finder**の**メソッド インスタンスの型**、し、[**返す**の**戻り値の TypeDescriptor**.  
  
     ![メソッド インスタンスの作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")  
  
4.  **[OK]** をクリックします。  
  
5.  プロパティ ペインで次のように入力します。 **EchoGreetings_Instance**で、**名前**フィールド。  
  
#### <a name="to-set-default-parameters"></a>既定のパラメーターを設定するには  
  
1.  メタデータ オブジェクト ウィンドウで、展開、 **EchoWSLOB**ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **EchoGreetings**メソッドを順に展開し、**インスタンス**ノード。  
  
3.  選択、 **EchoGreetings_Instance**メソッド、インスタンスし、プロパティ ウィンドウで省略記号ボタン (…) をクリックします。、 **DefaultValues**フィールド。  
  
4.  編集ウィンドウで、展開、 **greeting**ノード、2 つ目の順に展開し、 **greeting**ノード。 展開、**名前**ノード、ツリー構造が完全に表示されるまでです。  
  
5.  編集ウィンドウでは、次の手順フィールドの値を設定します。  
  
    |これを設定します。|これを|  
    |--------------|-------------|  
    |**id**|GUID 値では、たとえば 27829ed4 583a-40-c fb8cdd9dc98d ad87 4。|  
    |**sentDateTime**|現在の日付と時刻、に対する 05/15/08 のたとえば午前 9時 12分|  
    |**firstName**|First|  
    |**middleName**|中間|  
    |**lastName**|Last|  
  
     ![既定のパラメーター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")  
  
6.  **[閉じる]** をクリックします。  
  
### <a name="to-export-the-application-definition-file"></a>アプリケーション定義ファイルをエクスポートするには  
  
1.  メタデータ オブジェクトのウィンドウで右クリックし、 **EchoWSLOB**ノード、およびクリック**エクスポート**します。  
  
2.  EchoWS.xml として保存します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 ビジネス データ カタログ定義エディター ツールを使用した IIS でホストされているアダプターとの接続を有効にするのに Microsoft Office SharePoint Server 2007 にインポートできるアプリケーション定義ファイルを作成します。  
  
## <a name="next-steps"></a>次の手順  
 この手順で作成したアプリケーション定義ファイルに基づく SharePoint アプリケーションが作成する必要があります。 参照してください[手順 4。アダプターにアクセスする Sharepoint アプリケーションを作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md)手順についてはします。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: IIS でエコー アダプターをホストする](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)