---
title: '手順 3: アプリケーション定義ファイルの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: ce22a63e8267c36c1306974caa0faa5f9aa6be4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227010"
---
# <a name="step-3-create-an-application-definition-file"></a>手順 3: アプリケーション定義ファイルを作成します。
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 15 分  
  
 Microsoft Office SharePoint Server でビジネス データ カタログの機能は、公開し、ポータルに基幹業務 (LOB) アプリケーションからのデータが組み込まれています。 ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用できるアプリケーション定義ファイルをビルドする必要があります。  
  
 このステップでは、Microsoft Office SharePoint Server 2007 SDK で利用可能なビジネス データ カタログ定義エディター ツールを使用してのビジネス データ カタログ アプリケーション定義ファイルを作成します。 この定義ファイルでは、エコー アダプターの EchoGreetings メソッドをについて説明し、アダプターと通信するように SharePoint を有効にする後の手順で使用されます。  
  
 作成している Microsoft Office SharePoint Server アプリケーションの目的は、使用すると、エコー アダプターの EchoGreetings メソッドを呼び出すし、SharePoint Web パーツを使用して応答を返すを開始します。  
  
## <a name="prerequisites"></a>前提条件  
 作成した[手順 2: Web プロジェクトを配置](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)です。 エディターへアクセス、ビジネス データ カタログの定義、Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされている必要があります。 SDK をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)です。  
  
## <a name="creating-an-application-definition-file"></a>アプリケーション定義ファイルを作成します。  
 このトピックでは、IIS でホストされる WCF アダプター SharePoint ビジネス データ カタログへの接続用のアプリケーション定義ファイルを作成する手順を説明します。  
  
#### <a name="to-connect-to-the-wcf-adapter-service-and-create-entities"></a>WCF アダプターのサービスに接続し、エンティティを作成するには  
  
1.  **スタート メニュー**、 をポイント**すべてのプログラム**、クリックして**Microsoft ビジネス データ カタログ定義エディター**です。  
  
2.  ツールバーで、をクリックして**LOB システムの追加**です。  
  
3.  LOB システムの追加] ウィンドウで、[ **web サービスへの接続**です。  
  
4.  **URL**ボックスには、WCF サービスの URL を入力します。 URL は、次の形式である必要があります。`https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`  
  
5.  **[接続]** をクリックします。  
  
6.  使用可能な操作を表示するをクリックして、 **Web メソッドの追加**タブです。EchoGreetings メソッドが表示されます。 メソッドは、デザイン画面にドラッグします。  
  
7.  **[OK]** をクリックします。  
  
8.  **LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。 この例では、次を入力してください。 **EchoWSLOB**、クリックして**OK**です。  
  
9. 展開、 **EchoWSLob**  ノードの順に展開し、**エンティティ**ノード。 選択**Entity0**プロパティ ウィンドウの入力**EchoGreetings**の値として、**名前**プロパティです。  
  
     ![エンティティ名](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")  
  
## <a name="specify-user-name-and-password-headers-for-the-method"></a>メソッドのユーザー名とパスワードのヘッダーを指定します。  
 WCF アダプターを呼び出すときに、LOB システムに渡されるユーザーの資格情報を提供する必要があります。 [手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)、MyUserHeader および MyPassHeader フィールドにユーザー名とパスワード情報が提供されることを要求するようにエコー アダプターを構成します。 このアプリケーション定義ファイルの同じフィールド名を使用する必要があります。  
  
#### <a name="to-specify-user-name-and-password-headers"></a>ユーザー名とパスワードのヘッダーを指定するには  
  
1.  メタデータ オブジェクト ペインで、展開、 **EchoGreetings**  ノードの順に展開し、**メソッド**ノード。  
  
2.  クリックして、 **EchoGreetings**ノードのプロパティ ウィンドウで、省略記号ボタンをクリックし、 **(...)** ボタンをクリックして、**プロパティ**フィールドです。  
  
3.  PropertyView コレクション エディター ウィンドウで、**追加**、し、、**名前**型、プロパティ ペインのフィールド**HttpHeaderUserName**です。  
  
     ![Username ヘッダー フィールドの指定](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")  
  
4.  **PropertyValue**フィールドに「 **MyUserHeader**です。  
  
5.  をクリックして**追加**、およびプロパティ ペイン型**HttpHeaderPassword** [名前] フィールドを入力し、 **MyPassHeader**の**PropertyValue**フィールドです。  
  
6.  **[OK]** をクリックします。  
  
## <a name="set-up-single-sign-on-for-connecting-to-the-echo-adapter"></a>エコー アダプターに接続するためのシングル サインオンを設定します。  
 SharePoint からシングル サインオン情報を使用して、認証の値を持つ MyUserHeader および MyPassHeader を設定します。 シングル サインオンには、このアプリケーション定義ファイルをリンクするには、SecondarySsoApplicationId を指定する必要があります。  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a>SecondarySsoApplicationId のプロパティを設定するには  
  
1.  メタデータ オブジェクト ペインで、展開、 **EchoWSLOB**  ノードの順に展開し、**インスタンス**ノード。  
  
2.  をクリックして**EchoWSLOB_Instance**、プロパティ ペインで、省略記号ボタンをクリックして **([...])** ボタンをクリックして、**プロパティ**フィールドです。  
  
3.  PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **SecondarySsoApplicationId**で、**名前**フィールドです。  
  
4.  **PropertyValue**フィールドに「 **EchoSSO**です。  
  
     ![Secondaryssoapplicationid の](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")  
  
5.  **[OK]** をクリックします。  
  
## <a name="create-input-filters-and-default-values"></a>入力フィルターと既定値を作成します。  
 アプリケーション定義ファイルを Web サービスに渡すことができるユーザーの入力を受け付けることがあります。 これを実現するには、次の一連のタスクを実行する必要があります。  
  
#### <a name="to-create-a-filter-and-map-it-to-the-greeting-parameter"></a>フィルターを作成してあいさつ文パラメーターにマップするには  
  
1.  メタデータ オブジェクト ペインで、展開、 **EchoWSLOB**  ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **EchoGreetings**メソッドを右クリックして**フィルター**、クリックして**フィルターの追加**です。  
  
3.  プロパティ ウィンドウで、次のように入力します。 **Greeting**で、**名前**フィールドです。  
  
     ![フィルター名の設定](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")  
  
4.  メタデータ オブジェクト ペインで、展開、 **EchoWSLOB**  ノードの順に展開し、**メソッド**ノード  
  
5.  展開、 **EchoGreetings**メソッドの順に展開し、**パラメーター**ノード。  
  
6.  展開、 **greeting**ノード、2 番目の順に展開および**greeting**ノード。  
  
7.  をクリックして、 **greetingText**ノード、プロパティ ウィンドウで、次のように選択します。 **Greeting**から、 **FilterDescriptor**  ボックスの一覧です。  
  
#### <a name="to-create-a-finder-method-instance-for-the-echogreetings-method"></a>EchoGreetings メソッドの Finder メソッド インスタンスを作成するには  
  
1.  メタデータ オブジェクト ペインで、展開、 **EchoWSLOB**  ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **EchoGreetings**メソッドを右クリックして**インスタンス**、クリックして**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。  
  
3.  メソッド インスタンスの作成] ウィンドウで、をクリックして**Finder**の**メソッド インスタンスの型**、し、[**返す**の**戻り値の TypeDescriptor**.  
  
     ![メソッド インスタンスの作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")  
  
4.  **[OK]** をクリックします。  
  
5.  プロパティ ウィンドウで、次のように入力します。 **EchoGreetings_Instance**で、**名前**フィールドです。  
  
#### <a name="to-set-default-parameters"></a>既定のパラメーターを設定するには  
  
1.  メタデータ オブジェクト ペインで、展開、 **EchoWSLOB**  ノードの順に展開し、**メソッド**ノード。  
  
2.  展開、 **EchoGreetings**メソッドの順に展開し、**インスタンス**ノード。  
  
3.  選択、 **EchoGreetings_Instance**メソッドをインスタンス化、およびプロパティ ウィンドウで、省略記号ボタン (...) をクリックして、 **DefaultValues**フィールドです。  
  
4.  編集ウィンドウで、展開、 **greeting**ノード、2 番目の順に展開および**greeting**ノード。 展開して、**名前**ノードをツリー構造が完全に表示されるまでです。  
  
5.  編集ウィンドウでは、よう、フィールドの値を設定します。  
  
    |設定対象|次の値に設定|  
    |--------------|-------------|  
    |**id**|GUID 値では、たとえば 27829ed4 583a-40-c fb8cdd9dc98d ad87 4。|  
    |**sentDateTime**|現在の日付と時刻、に対する 05/15/08 のたとえば午前 9時 12分|  
    |**firstName**|First|  
    |**middleName**|Middle|  
    |**[氏名]**|Last|  
  
     ![既定のパラメーター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")  
  
6.  **[閉じる]** をクリックします。  
  
### <a name="to-export-the-application-definition-file"></a>アプリケーション定義ファイルをエクスポートするには  
  
1.  メタデータ オブジェクト ペインで右クリックし、 **EchoWSLOB**ノードをクリックして**エクスポート**です。  
  
2.  EchoWS.xml としてファイルを保存します。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 ビジネス データ カタログ定義エディター ツールを使用する IIS でホストされているアダプターとの接続を有効にするのに Microsoft Office SharePoint Server 2007 にインポートできるアプリケーション定義ファイルを作成します。  
  
## <a name="next-steps"></a>次の手順  
 この手順で作成したアプリケーション定義ファイルに基づく SharePoint アプリケーションを作成する必要がありますようになりました。 参照してください[手順 4: アダプターにアクセスする Sharepoint アプリケーションを作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md)手順についてはします。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: IIS でエコー アダプターをホストします。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)