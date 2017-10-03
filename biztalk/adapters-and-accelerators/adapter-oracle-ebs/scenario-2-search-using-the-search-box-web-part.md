---
title: "シナリオ 2: 検索ボックス web パーツを使用して検索を |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a233772f-7577-4ac5-b55a-cb1ba2f464c7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03e536df00499e8965632a3952eb3ae50e3f83df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-2--search-using-the-search-box-web-part"></a>検索ボックス web パーツを使用して検索をシナリオ 2。
Microsoft Office SharePoint server の全文検索を実行できるを使用して検索アプリケーションを構成する検索の設定を構成する Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブル。 後から検索を行うことができますに検索ボックス Web パーツを追加します。  
  
 
  
##  <a name="Define"></a>コンテンツのソースを定義します。  
 このセクションでは、Microsoft Office SharePoint Server が、データをクロールする場所からのコンテンツ ソースの定義について説明します。 メソッドのインスタンスに作成される Id の列挙子へのコンテンツのマッピングが含まれます[手順 2: Oracle E-business Suite 成果物のためのアプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。  
  
#### <a name="to-define-a-content-source"></a>コンテンツ ソースを定義するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、名前の共有サービス プロバイダー (SSP) の検索アプリケーションを構成する場合をクリックします。  
  
3.  [ホーム] ページで、**検索**セクションで、をクリックして**検索設定**です。  
  
4.  検索設定の構成 ページの下の左ペインで、**クロール**をクリックして**既定のコンテンツへのアクセス アカウント**コンテンツをクロールするときに、既定のアカウントとして使用するアカウントを指定します。  
  
5.  [既定のコンテンツのアクセス アカウント] ページで、ユーザー名とパスワードの資格情報を指定し、クリックして**OK**です。 検索の管理 ページに戻ります。  
  
6.  下の左ペインで**クロール**をクリックして**コンテンツ ソース**です。  
  
7.  コンテンツ ソースの管理 ページで、**新しいコンテンツ ソース**です。  
  
8.  コンテンツ ソースの管理 ページで、**新しいコンテンツ ソース**です。  
  
9. [コンテンツ ソースの追加] ページで。  
  
    1.  型`MS_SAMPLE_EMPLOYEE`で、**名前**ボックス。  
  
    2.  **コンテンツ ソースの種類**領域で、をクリックして**ビジネス データ**です。  
  
    3.  **アプリケーション**領域で、をクリックして**クロールには、アプリケーションが選択されている**、し、、 **MS_SAMPLE_EMPLOYEE_Instance**チェック ボックスをオンします。  
  
    4.  **フル クロールの開始**領域で、**このコンテンツ ソースのフル クロールを開始**チェック ボックスをクリックして**OK**です。  
  
         ![コンテンツ ソースの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/27-add-content-source.gif "27 _ add_content_source")  
  
10. 追加された新しいコンテンツ ソースのコンテンツ ソースの管理ページに戻るされます。 Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のデータをコンテンツ ソースがクロールされます。 クロールが完了するまで待機します。  
  
11. 下の左ペインで**クロール**をクリックして**クロール ログ**、クロールが成功したことを確認するログ ファイルを確認してください。  
  
##  <a name="Scope"></a>クロールされたコンテンツのスコープを定義します。  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、名前の共有サービス プロバイダー (SSP) の検索アプリケーションを構成する場合をクリックします。  
  
3.  [ホーム] ページで、**検索**セクションで、をクリックして**検索設定**です。  
  
4.  検索設定の構成 ページの下の左ペインで、**クエリを実行し、結果**をクリックして**スコープ**データのクロールのスコープを定義します。  
  
5.  スコープの表示 ページで、をクリックして**新しいスコープ**です。  
  
6.  [スコープの作成] ページで、次のように入力します。`MS_SAMPLE_EMPLOYEE_Search`で、**タイトル**ボックスと [] をクリック**OK**です。  
  
     ![スコープを作成する](../../adapters-and-accelerators/adapter-oracle-ebs/media/28-create-scope.gif "28 _ create_scope")  
  
7.  追加された新しいスコープを持つ範囲の表示 ページに戻るされます。 **更新ステータス**、新しく追加されたスコープの列をクリックして、**規則を追加**リンクします。  
  
8.  スコープ規則の追加のページ。  
  
    1.  **スコープ規則の種類**領域で、をクリックして**コンテンツ ソース**です。  
  
    2.  **コンテンツ ソース**一覧で、をクリックして**MS_SAMPLE_EMPLOYEE**、順にクリック**OK**です。  
  
         ![スコープ規則の追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/29-add-scope-rule.gif "29 _ add_scope_rule")  
  
9. スコープに追加された規則とスコープの表示ページに戻るされます。 左側のウィンドウでをクリックして**検索管理**です。  
  
10. [検索の管理] ページで、検索、**更新プログラムを必要とするスコープ**行ををクリックして、**更新プログラムを今すぐ開始**リンクします。  
  
 **スコープ更新ステータス**行範囲の更新の状態が表示されます。 更新が完了するまで待機します。 更新が完了したら、スコープが使用できるようにします。  
  
##  <a name="AddScope"></a>検索ドロップダウン リストに、スコープを追加します。  
 検索範囲を作成した後に使用できるようにする、Microsoft Office SharePoint Server で、検索ドロップダウン リストに、スコープを追加する必要があります。  
  
#### <a name="to-add-the-scope-to-the-search-dropdown"></a>検索ドロップダウン リストに、スコープを追加するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、名前の共有サービス プロバイダー (SSP) の検索アプリケーションを構成する場合をクリックします。  
  
3.  共有サービスの管理 ページの右上隅で、をクリックして**サイトの操作**、クリックして**サイト設定**です。  
  
4.  [サイト設定] ページで、**サイト コレクションの管理**セクションで、をクリックして**検索範囲**です。  
  
5.  スコープの表示 ページで、をクリックして、**検索ドロップダウン**リンクします。  
  
     ![表示スコープ](../../adapters-and-accelerators/adapter-oracle-ebs/media/30-view-scope.gif "30_View_Scope")  
  
6.  [スコープ表示グループの編集] ページで。  
  
    1.  **スコープ**領域で、選択、 **MS_SAMPLE_EMPLOYEE_Search**チェック ボックスをオンします。  
  
    2.  **既定のスコープ**領域で、をクリックして**MS_SAMPLE_EMPLOYEE_Search**で、**既定のスコープ**ボックスの一覧し、をクリックして**[ok]**です。  
  
         ![スコープ表示グループの編集ページ](../../adapters-and-accelerators/adapter-oracle-ebs/media/31-edit-scope-display-group.gif "31 _ edit_scope_display_group")  
  
7.  検索ドロップダウン表示グループに追加された MS_SAMPLE_EMPLOYEE_Search スコープを持つ範囲の表示 ページに戻るされます。  
  
##  <a name="SearchWebPart"></a>検索ボックス Web パーツを追加します。  
 Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブルでフルテキスト検索を実行するユーザーを有効にするには、ようになりました、Web パーツ ページを作成し、検索ボックス Web パーツを追加する必要があります。  
  
#### <a name="to-add-the-search-box-web-part"></a>検索ボックス Web パーツを追加するには  
  
1.  呼ばれる Web パーツ ページを作成する**MS_SAMPLE_EMPLOYEE_Search**です。 Web パーツ ページを作成するための手順を確認する「[シナリオ 1: ビジネス データ一覧 web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)で[シナリオ 1: ビジネス データ一覧 web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)です。  
  
2.  MS_SAMPLE_EMPLOYEE_Search ページで、をクリックして**Web パーツの追加**です。  
  
3.  **Web パーツの追加** ダイアログ ボックスで、**検索** セクションで、選択、**検索ボックス**チェック ボックスをクリックして**追加**です。  
  
     ![検索ボックス Web パーツの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/32-search-web-part.gif "32 _ search_web_part")  
  
4.  検索ボックス Web パーツが MS_SAMPLE_EMPLOYEE_Search ページに追加されます。  
  
     ![検索ボックス Web パーツ](../../adapters-and-accelerators/adapter-oracle-ebs/media/33-search-web-part-final.gif "33 _ search_web_part_final")  
  
## <a name="see-also"></a>参照  
 [手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)  
 [シナリオ 1: ビジネス データ一覧 web パーツを使用してデータを表示します。](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)