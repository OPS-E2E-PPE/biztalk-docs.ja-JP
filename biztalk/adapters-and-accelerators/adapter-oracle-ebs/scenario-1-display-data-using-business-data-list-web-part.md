---
title: "シナリオ 1: ビジネス データ一覧 web パーツを使用してデータの表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3831814-8b70-4352-b22f-cebd08750ef5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1add974ca3ad0b80b7838b120920f4de47f1650
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-1-display-data-using-business-data-list-web-part"></a>シナリオ 1: ビジネス データ一覧 web パーツを使用してデータを表示します。
使用して、**ビジネス データ一覧**用の Web パーツ、 **Finder**メソッド インスタンス。 この Web パーツでは、Oracle E-business Suite から従業員の一覧を取得する検索文字列を指定することができます。 このチュートリアルでは、これには、ディスプレイの従業員の Web パーツを呼び出されます。 このセクションでは、この Web パーツを作成する手順を説明します。 Web パーツの作成の詳細についてを参照してください「ビジネス データ リストのカスタマイズ、Web パーツ、およびサイト」で[http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)です。  
  
 Web パーツを追加する前に、Web パーツ ページを作成する必要があります。  
  
## <a name="creating-a-web-part-page"></a>Web パーツ ページを作成します。  
 このセクションでは、Web パーツ ページを作成する手順を説明します。  
  
###  <a name="WebPart"></a>Web パーツ ページを作成するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリック**SharePoint 3.0 サーバーの全体管理**です。  
  
2.  左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。  
  
3.  共有サービスの管理 ページの右上隅で、をクリックして**サイトの操作**、クリックして**作成**です。  
  
     ![Web パーツを作成するにはメニュー](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  作成 ページで、 **Web ページ**セクションで、 **Web パーツ ページ**です。  
  
5.  新しい Web パーツ ページには、次の操作を行います。  
  
    1.  **名前**フィールドに、ページの名前を入力します。 このチュートリアルでは、名前を入力しますとして**MS_SAMPLE_EMPLOYEE**です。  
  
    2.  選択、**ファイルが既に存在する場合に上書き**チェック ボックスを作成する新しいページと同じ名前の古いページを上書きする場合。  
  
    3.  **レイアウト** セクションから、**レイアウト テンプレートを選択して**ボックスで、Web パーツ ページのレイアウトを選択します。 このチュートリアルでは、次のように選択します。**ページ全体を垂直方向**です。  
  
    4.  **保存場所**セクションで、**ドキュメント ライブラリ**一覧で、クリックして**フォーム テンプレート**です。  
  
    5.  **[作成]**をクリックします。 次の図は、作成した後、Web パーツ ページを示します。  
  
         ![新しい WebPart ページ](../../adapters-and-accelerators/adapter-oracle-ebs/media/23-web-part.gif "23 _ web_part")  
  
    6.  このページに Web パーツを追加する必要があります。  
  
## <a name="adding-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加します。  
 ビジネス データ一覧 Web パーツを Web パーツ ページに追加する必要があります。 この Web パーツを使用して、検索式に一致する Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブルから従業員レコードの一覧が取得されます。 この Web パーツに対応する、 **Finder**メソッド インスタンス (*Finder_Instance*) で、ビジネス データ カタログ定義エディターを作成しました。  
  
#### <a name="to-add-a-business-data-list-web-part"></a>ビジネス データ一覧 Web パーツを追加するには  
  
1.  MS_SAMPLE_EMPLOYEE ページで、をクリックして**Web パーツの追加**です。  
  
2.  **Web パーツの追加** ダイアログ ボックスで、**ビジネス データ** セクションで、選択、**ビジネス データ一覧**チェック ボックスをクリックして**追加**です。  
  
     ![ビジネス データ Web パーツを作成するオプションを](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  新しく追加されたビジネス データ一覧 Web パーツ、クリックして、**ツール ウィンドウを開いて**リンクします。  
  
     ![Web パーツのツール ウィンドウを開いて](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  ビジネス データ一覧のツール ウィンドウは、右側のウィンドウで開きます。 **ビジネス データ一覧** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。  
  
     ![ビジネス データ一覧のツール ウィンドウ](../../adapters-and-accelerators/adapter-oracle-ebs/media/24-bdc-browse.gif "24 _ bdc_browse")  
  
5.  **ビジネス データの種類の選択**ダイアログ ボックスで、 **MS_SAMPLE_EMPLOYEE_Instance**クリックしてアプリケーションでは、 **OK**です。  
  
     ![アプリケーション インスタンスの選択](../../adapters-and-accelerators/adapter-oracle-ebs/media/25-bdc-picker.gif "25 _ bdc_picker")  
  
6.  展開、**外観**ノード、および、**タイトル**ボックスで、Web パーツのタイトルを入力します。 この Web パーツの次のように入力します。**従業員一覧**です。  
  
7.  ビジネス データ一覧のツール ウィンドウで、をクリックして**適用**、クリックして**OK**です。 ビジネス データ一覧 Web パーツは、次のようになります。  
  
     ![ビジネス データ一覧 Web パーツ](../../adapters-and-accelerators/adapter-oracle-ebs/media/26-bdc-webpart.gif "26 _ bdc_webpart")  
  
8.  Web パーツには、MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する選択操作を実行することによって返されるフィールドが一覧表示します。  
  
## <a name="see-also"></a>参照  
 [手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)   
 [検索ボックス Web パーツを使用して検索をシナリオ 2。](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)