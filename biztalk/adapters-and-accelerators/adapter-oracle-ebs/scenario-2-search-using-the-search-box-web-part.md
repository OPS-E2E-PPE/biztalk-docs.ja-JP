---
title: 'シナリオ 2: 検索ボックス web パーツを使用して検索 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a233772f-7577-4ac5-b55a-cb1ba2f464c7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f8eff487547ad3c7e101c7cf002b0dca1833e71
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374638"
---
# <a name="scenario-2--search-using-the-search-box-web-part"></a>シナリオ 2: 検索ボックス web パーツを使用して検索します。
検索設定を使用してのフル テキスト検索を実行できる検索アプリケーションを構成する Microsoft Office SharePoint Server で構成が Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブル。 後で、検索を実行するからに検索ボックス Web パーツを追加します。  
  
 
  
##  <a name="Define"></a> コンテンツ ソースを定義します。  
 このセクションから Microsoft Office SharePoint Server がデータをクロールできるコンテンツ ソースの定義について説明します。 メソッドのインスタンスに作成される Id の列挙子へのコンテンツのマッピングは、[手順 2。Oracle E-business Suite の成果物のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。  
  
#### <a name="to-define-a-content-source"></a>コンテンツ ソースを定義するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで名前の共有サービス プロバイダー (SSP) の検索アプリケーションを構成する をクリックします。  
  
3.  ホーム ページで、**検索**セクションで、**検索設定**。  
  
4.  検索設定の構成 ページで、下の左ペインで**クロール**、 をクリックして**既定のコンテンツへのアクセス アカウント**コンテンツのクロール時に既定のアカウントとして使用するアカウントを指定します。  
  
5.  既定のコンテンツへのアクセス アカウント ページで、ユーザー名とパスワードの資格情報を指定し、クリックして**OK**します。 検索の管理ページに戻ります。  
  
6.  下の左ペインで**クロール**、 をクリックして**コンテンツ ソース**します。  
  
7.  コンテンツ ソースの管理 ページで、次のようにクリックします。**コンテンツ ソースの新しい**します。  
  
8.  コンテンツ ソースの管理 ページで、次のようにクリックします。**コンテンツ ソースの新しい**します。  
  
9. [コンテンツ ソースの追加] ページで。  
  
    1.  型`MS_SAMPLE_EMPLOYEE`で、**名前**ボックス。  
  
    2.  **コンテンツ ソースの種類**領域で、をクリックして**ビジネス データ**します。  
  
    3.  **アプリケーション**領域で、をクリックして**クロールには、アプリケーションが選択されている**を選び、 **MS_SAMPLE_EMPLOYEE_Instance**チェック ボックスをオンします。  
  
    4.  **フル クロールの開始**領域で、、**このコンテンツ ソースのフル クロールを開始**チェック ボックスをオンにし**OK**。  
  
         ![コンテンツ ソースの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/27-add-content-source.gif "27 _ add_content_source")  
  
10. 追加された新しいコンテンツ ソースのコンテンツ ソースの管理ページに戻ったらされます。 Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のデータをコンテンツ ソースをクロールします。 クロールが完了するまで待機します。  
  
11. 下の左ペインで**クロール**、 をクリックして**クロール ログ**、クロールが成功したことを確認するログ ファイルを確認します。  
  
##  <a name="Scope"></a> クロールされたコンテンツのスコープを定義します。  
  
1. SharePoint 3.0 サーバーの全体管理を開始します。 クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.  
  
2. 左側のナビゲーション ウィンドウで名前の共有サービス プロバイダー (SSP) の検索アプリケーションを構成する をクリックします。  
  
3. ホーム ページで、**検索**セクションで、**検索設定**。  
  
4. 検索設定の構成 ページで、下の左ペインで**クエリを実行し、結果**、 をクリックして**スコープ**データのクロールのスコープを定義します。  
  
5. スコープの表示 ページで、次のようにクリックします。**新しいスコープ**します。  
  
6. スコープの作成 ページで、次のように入力します。`MS_SAMPLE_EMPLOYEE_Search`で、**タイトル**ボックスをクリック**OK**します。  
  
    ![スコープを作成する](../../adapters-and-accelerators/adapter-oracle-ebs/media/28-create-scope.gif "28 _ create_scope")  
  
7. スコープの表示 ページを返す、新しいスコープが追加されます。 **更新ステータス**、新しく追加したスコープの列をクリックして、**ルールを追加**リンク。  
  
8. スコープ規則の追加ページの内容。  
  
   1.  **スコープ規則の種類**領域で、をクリックして**コンテンツ ソース**します。  
  
   2.  **コンテンツ ソース**一覧で、 **MS_SAMPLE_EMPLOYEE**、順にクリックします**OK**します。  
  
        ![スコープ規則の追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/29-add-scope-rule.gif "29 _ add_scope_rule")  
  
9. スコープの追加の規則に、スコープの表示ページに戻るされます。 左側のウィンドウで次のようにクリックします。 **Search Administration**します。  
  
10. 検索の管理 ページで、検索、**スコープの更新プログラムが必要**行の をクリックし、**更新プログラムを今すぐ開始**リンク。  
  
    **スコープの更新状態**行範囲の更新の状態が表示されます。 更新が完了するまで待機します。 更新が完了した後、スコープは、すぐに使用できます。  
  
##  <a name="AddScope"></a> 検索ボックスに、スコープを追加します。  
 検索スコープを作成した後は、使用できるように、スコープを Microsoft Office SharePoint Server で検索ドロップダウンに追加する必要があります。  
  
#### <a name="to-add-the-scope-to-the-search-dropdown"></a>検索ボックスに、スコープを追加するには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで名前の共有サービス プロバイダー (SSP) の検索アプリケーションを構成する をクリックします。  
  
3.  共有サービス管理 ページの右上隅で、**サイトの操作**、 をクリックし、**サイト設定**します。  
  
4.  サイトの設定] ページで、**サイト コレクションの管理**セクションで、[**検索スコープ**します。  
  
5.  スコープの表示 ページで、をクリックして、**検索ドロップダウン**リンク。  
  
     ![表示スコープ](../../adapters-and-accelerators/adapter-oracle-ebs/media/30-view-scope.gif "30_View_Scope")  
  
6.  [スコープ表示グループの編集] ページで。  
  
    1.  **スコープ**領域で、、 **MS_SAMPLE_EMPLOYEE_Search**チェック ボックスをオンします。  
  
    2.  **既定のスコープ**領域で、をクリックして**MS_SAMPLE_EMPLOYEE_Search**で、**スコープの既定の**ボックスの一覧をクリックして **[ok]** します。  
  
         ![スコープ表示グループの編集ページ](../../adapters-and-accelerators/adapter-oracle-ebs/media/31-edit-scope-display-group.gif "31 _ edit_scope_display_group")  
  
7.  検索ドロップダウン表示グループに追加された MS_SAMPLE_EMPLOYEE_Search スコープを持つ、範囲の表示 ページに戻るされます。  
  
##  <a name="SearchWebPart"></a> 検索ボックス Web パーツを追加します。  
 Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイスのテーブルに対してフルテキスト検索を実行するユーザーを有効にするには、ようになりました、Web パーツ ページを作成し、検索ボックス Web パーツを追加する必要があります。  
  
#### <a name="to-add-the-search-box-web-part"></a>検索ボックス Web パーツを追加するには  
  
1.  呼ばれる Web パーツ ページを作成する**MS_SAMPLE_EMPLOYEE_Search**します。 Web パーツ ページを作成する手順については、次を参照してください。[シナリオ 1。ビジネス データ一覧 web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)で[シナリオ 1。ビジネス データ一覧 web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)します。  
  
2.  MS_SAMPLE_EMPLOYEE_Search ページで、次のようにクリックします。 **Web パーツの追加**します。  
  
3.  **Web パーツの追加** ダイアログ ボックスで、**検索**セクションで、**検索ボックス**チェック ボックスをオンにして**追加**します。  
  
     ![検索ボックス Web パーツを追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/32-search-web-part.gif "32 _ search_web_part")  
  
4.  検索ボックス Web パーツは、MS_SAMPLE_EMPLOYEE_Search ページに追加されます。  
  
     ![検索ボックス Web パーツ](../../adapters-and-accelerators/adapter-oracle-ebs/media/33-search-web-part-final.gif "33 _ search_web_part_final")  
  
## <a name="see-also"></a>参照  
 [ステップ 3:Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)  
 [シナリオ 1: ビジネス データ リスト Web パーツを使用してデータを表示する](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)