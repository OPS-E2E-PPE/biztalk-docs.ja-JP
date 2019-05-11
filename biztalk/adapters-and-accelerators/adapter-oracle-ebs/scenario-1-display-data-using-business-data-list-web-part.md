---
title: シナリオ 1:ビジネス データ一覧 web パーツを使用してデータの表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3831814-8b70-4352-b22f-cebd08750ef5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2a88c99c6b0386a621a9ecdf44d901312736254
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374646"
---
# <a name="scenario-1-display-data-using-business-data-list-web-part"></a>シナリオ 1:ビジネス データ一覧 web パーツを使用してデータを表示します。
使用して、**ビジネス データ一覧**用の Web パーツ、 **Finder**メソッド インスタンス。 この Web パーツでは、Oracle E-business Suite から従業員の一覧を取得する検索文字列を指定することができます。 このチュートリアルでは、この表示の従業員の Web パーツは呼び出されます。 ここでは、この Web パーツを作成する手順について説明します。 Web パーツの作成の詳細についてを参照してください「ビジネス データ リストのカスタマイズ、Web パーツ、およびサイト」 [ http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)します。  
  
 Web パーツを追加する前に、Web パーツ ページを作成する必要があります。  
  
## <a name="creating-a-web-part-page"></a>Web パーツ ページの作成  
 ここでは、Web パーツ ページを作成する手順について説明します。  
  
###  <a name="WebPart"></a> Web パーツ ページを作成するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリック**SharePoint 3.0 サーバーの全体管理**します。  
  
2.  左側のナビゲーション ウィンドウで、アプリケーションの定義をインポートする SSP の名前をクリックします。  
  
3.  共有サービス管理 ページで、右上隅にある**サイトの操作**、 をクリックし、**作成**です。  
  
     ![Web パーツを作成するにはメニュー](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  作成 ページで、 **Web ページ**セクションで、 **Web パーツ ページ**します。  
  
5.  新しい Web パーツ ページで、次の操作を行います。  
  
    1.  **名前**フィールドに、ページの名前を入力します。 このチュートリアルでは、入力として名前**MS_SAMPLE_EMPLOYEE**します。  
  
    2.  選択、**ファイルが既に存在する場合に上書き**チェック ボックスで、古いページを作成する新しいページと同じ名前で上書きする場合。  
  
    3.  **レイアウト**セクションから、**レイアウト テンプレートの選択**ボックスに、Web パーツ ページのレイアウトを選択します。 このチュートリアルでは、次のように選択します。**ページ全体を垂直**します。  
  
    4.  **保存場所**セクションで、**ドキュメント ライブラリ**一覧で、**フォーム テンプレート**します。  
  
    5.  **[作成]** をクリックします。 次の図は、作成後に、Web パーツ ページを示します。  
  
         ![新しい web パーツ ページ](../../adapters-and-accelerators/adapter-oracle-ebs/media/23-web-part.gif "23 _ web_part")  
  
    6.  このページを Web パーツを追加する必要があります。  
  
## <a name="adding-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加します。  
 Web パーツ ページに、ビジネス データ一覧 Web パーツを追加する必要がありますようになりました。 この Web パーツを使用して、検索式に一致する Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブルから従業員レコードの一覧が取得されます。 この Web パーツに対応する、 **Finder**メソッド インスタンス (*Finder_Instance*) でビジネス データ カタログ定義エディターを作成します。  
  
#### <a name="to-add-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加するには  
  
1.  MS_SAMPLE_EMPLOYEE ページで、次のようにクリックします。 **Web パーツの追加**します。  
  
2.  **Web パーツの追加** ダイアログ ボックスで、**ビジネス データ**セクションで、**ビジネス データ一覧**チェック ボックスをオンにして**追加**します。  
  
     ![ビジネス データ Web パーツを作成するオプション](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  新しく追加されたビジネス データ一覧 Web パーツ、クリックして、**ツール ウィンドウを開く**リンク。  
  
     ![Web パーツのツール ウィンドウを開く](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  ビジネス データ一覧のツール ウィンドウが右側のウィンドウで開きます。 **ビジネス データ一覧**セクションの**型**フィールドに、をクリックして、**参照**ボタン。  
  
     ![ビジネス データ一覧のツール ウィンドウ](../../adapters-and-accelerators/adapter-oracle-ebs/media/24-bdc-browse.gif "24 _ bdc_browse")  
  
5.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **MS_SAMPLE_EMPLOYEE_Instance**アプリケーション、およびクリック**OK**します。  
  
     ![アプリケーション インスタンスの選択](../../adapters-and-accelerators/adapter-oracle-ebs/media/25-bdc-picker.gif "25 _ bdc_picker")  
  
6.  展開、**外観**ノード、および、**タイトル**ボックスに、Web パーツのタイトルを入力します。 この Web パーツでは、入力**従業員リスト**します。  
  
7.  ビジネス データ一覧のツール ウィンドウで、次のようにクリックします。**適用**、 をクリックし、 **OK**します。 ビジネス データ一覧 Web パーツは、次のようになります。  
  
     ![ビジネス データ一覧 Web パーツ](../../adapters-and-accelerators/adapter-oracle-ebs/media/26-bdc-webpart.gif "26 _ bdc_webpart")  
  
8.  Web パーツには、MS_SAMPLE_EMPLOYEE インターフェイス テーブルの選択操作を実行することによって返されるフィールドが一覧表示します。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)   
 [シナリオ 2: 検索ボックス Web パーツを使用して検索します。](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)