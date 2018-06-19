---
title: SharePoint での Oracle データベース アダプターの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 254204e5-3b5d-4e70-97ab-817660d1206a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a5866344e666c9e9cb49af6c6d99211774a2758
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
ms.locfileid: "23450313"
---
# <a name="use-the-oracle-database-adapter-with-sharepoint"></a>SharePoint での Oracle データベース アダプターを使用します。
WCF アダプター サービス開発ウィザード[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]Oracle データベースと、Microsoft BizTalk Adapter for Oracle E-business Suite は、Microsoft SharePoint の外部のデータ ソースと直接使用される Microsoft BizTalk Adapter を有効にします。 この機能をサポートする追加サービス開発ウィザードが起動し、 **WCF アダプタ サービス**、新しい Visual c# の Web サイトを作成するためのテンプレート[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]です。 テンプレートが付属して、[!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)]です。 また、Microsoft Windows Communication Foundation (WCF) の基幹業務 (LOB) アダプター SDK をインストールする必要があります。  
  
## <a name="sharepoint-operation-support"></a>SharePoint の操作のサポート  
 アダプター サービス開発ウィザードでは、Microsoft SharePoint と互換性がある Oracle アダプターの特別なサービス コントラクトを生成します。 ウィザードを Microsoft SharePoint と、アダプターを統合するため、次の操作を含むサービス コントラクトが生成されます。  
  
-   **作成します。** CreateItem_ 操作でサポートされています。  
  
-   **お読みください:** ReadItem_ 操作でサポートされています。  
  
-   **更新プログラム:** UpdateItem_ 操作でサポートされています。  
  
-   **削除:** DeleteItem_ 操作でサポートされています。  
  
-   **クエリ:** ReadList 操作でサポートされています。  
  
-   **関連付け:** Associate_ 操作でサポートされています。  
  
 使用して、Microsoft BizTalk Adapter 用 Oracle データベースの例として次のサービス コントラクトが生成されました。 アダプターが、EMP テーブルへのアクセスを提供するよう構成します。  
  
```  
    [System.ServiceModel.ServiceContractAttribute()]  
    public interface ISCOTT_EMP {  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] ReadList(System.Nullable<int> Limit);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void CreateItem(SCOTT_EMP_Record Input);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] ReadItem_EMPNO(System.Nullable<decimal> EMPNO);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void UpdateItem_EMPNO(SCOTT_EMP_Record Input);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void DeleteItem_EMPNO(System.Nullable<decimal> EMPNO);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] Associate_DEPTNO(System.Nullable<decimal> DEPTNO);  
}  
```  
  
## <a name="create-a-new-web-site-to-host-the-oracle-database-in-iis"></a>IIS での Oracle データベースをホストする新しい Web サイトの作成します。  
 次の手順では、Oracle データベースをホストする Microsoft BizTalk Adapter 新しい WCF web サービスを作成する WCF アダプター サービス開発ウィザードを使用する例を提供します。 サービス コントラクトは、Sharepoint とは直接互換性操作が含まれます。 したがって、外部データ ソースとして it を直接使用できます。 Oracle データベースを使用してでの認証に、アダプターが構成されている、 **SCOTT**アカウント。 場合、 **SCOTT**アカウントがロックされている、SYSDBA として SQL Plus にログインして、アカウントのロックを解除することができます。  
  
```  
<Oracle Installation Bin Directory>\Sqlplus.exe SYS AS SYSDBA  
```  
  
 次のコマンドを実行します。  
  
```  
SQL> ALTER USER scott ACCOUNT UNLOCK;  
```  
  
#### <a name="create-the-new-web-site-project"></a>新しい Web サイト プロジェクトを作成します。  
  
1.  Visual Studio を開きます。   
  
2.  Visual Studio での**ファイル**メニューの **新規**をクリックし、**プロジェクト**です。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、展開**他の言語** をクリック**Visual c#** です。 検索、 **WCF アダプター サービス**テンプレートの一覧表示し、をクリックして選択します。  
  
    > [!NOTE]
    >  **WCF アダプタ サービス**テンプレートが利用できない場合、[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]がインストールされていません。 X64 システムでは、インストールの x86 と x64 の両方のバージョン、[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]です。  
  
4.  指定**ScottEMP** をクリックし、名前の**OK**です。 **WCF アダプター サービス開発ウィザード**を開始します。  
  
5.  **概要** ページで、をクリックして**次**です。  
  
6.  **選択操作** ページで指定、 **oracleDBBinding**バインドします。  
  
7.  クリックして、**構成**ボタンをクリックします。 **アダプターの構成**ダイアログが表示されます。  
  
8.  **セキュリティ** タブで、 **Username**で、**クライアント資格情報の種類**ボックスの一覧。  
  
9. 入力**SCOTT**ユーザーの名前を指定し、SCOTT アカウントの正しいパスワードを入力します。 SCOTT アカウントの既定のパスワードは**tiger**です。  
  
10. クリックして、 **URI プロパティ** タブに Oracle サーバーの IP アドレスまたはホスト名を入力、 **ServerAddress**ボックス。  
  
11. 正しい Oracle データベース サービスで、インスタンス名を入力、 **ServiceName**ボックス。 インスタンス名の詳細については、Oracle Enterprise Manager からコピーできます。  
  
12. キーを押して、 **OK**のボタンでは、**アダプターの構成**ダイアログ  
  
13. **選択操作**ページ、ウィザードのをクリックして、**接続**ボタンをクリックし、しばらくの Oracle データベースを構築するカテゴリ。  
  
14. カテゴリを追加した後、**カテゴリを選択**一覧で、下方向にスクロール**SCOTT**それを展開します。 展開し、**テーブル** をクリックし、 **EMP**テーブル エントリ。  
  
15. **利用可能なカテゴリと操作**一覧をリスト内のすべての操作を選択し、をクリックして、**追加**ボタンをクリックします。 すべての操作に追加されます、**カテゴリと操作を追加** ボックスの一覧です。  
  
16. **選択操作** ページで、をクリックして、**次**ボタンをクリックします。  
  
17. **サービスの構成およびエンドポイント動作** ページで、設定、 **UseServiceCertificate**サービスの動作を**false**この例です。 をクリックして、**次**ボタンをクリックします。  
  
18. **を構成するサービス エンドポイントのバインドとアドレス** ページで、をクリックして、**適用**ボタンをクリックします。 をクリックして、**次**ボタンをクリックします。  
  
19. **概要** ページで、をクリックして、**完了**ボタンをクリックします。  
  
20. クリックして、**ビルド**メニュー オプションをクリック**ソリューションのビルド**です。 プロジェクトのビルドがエラーなしで成功したことを確認します。  
  
## <a name="publish-the-new-service-to-iis"></a>新しいサービスを IIS に発行します。  
 この例では、ローカル IIS web サーバーに、アダプターのホスト サービスを発行します。  
  
1.  Visual Studio のソリューション エクスプ ローラーで右クリックし、 **ScottEmp**プロジェクトし、クリックして**プロパティ**です。 プロジェクト デザイナーのタブが表示されます。  
  
2.  クリックして、 **Web**  タブのをクリックして、**を使用してローカル IIS Web サーバー**オプション。  
  
3.  クリックして、**仮想ディレクトリの作成**ボタンをクリックします。  
  
4.  ブラウザーを開き、web サービス アドレスに**http://localhost/ScottEmp/ISCOTT_EMP.svc**です。 「サービスを作成しました」というメッセージを受信する必要があります、アダプタを示すが IIS でホストされています。  
  
## <a name="add-the-external-data-source-to-a-sharepoint-site-using-sharepoint-designer"></a>SharePoint Designer を使用して SharePoint サイトに外部データ ソースを追加します。  
 このセクションでは、外部データ ソースとして SharePoint Designer を使用して新しい Web サイトに、WCF サービスを追加する方法について説明します。  
  
  
1.  SharePoint デザイナーを開き、新しい Web サイトを作成します。  
  
2.  SharePoint Designer の展開**ナビゲーション** をクリック**外部コンテンツ タイプ**で、**サイト オブジェクト** ボックスの一覧です。  
  
3.  クリックして、**外部コンテンツ タイプ**新しい外部コンテンツ タイプを作成するメニュー ボタンをクリックします。  
  
4.  横にあるテキストをクリックして**名前**新しい外部コンテンツ タイプの名前を編集します。 入力**OracleEMP**名。  
  
5.  横にあるテキスト リンクをクリックして**外部システム**見なします**ここをクリックして、外部データ ソースと操作を検出する。** です。 OracleEMP 外部コンテンツ タイプの操作のデザイナーが開きます。  
  
6.  クリックして、**接続の追加**[探索] 画面でボタンをクリックします。  
  
7.  外部データ ソースの種類の選択 ダイアログ ボックスで選択**WCF サービス** をクリックし、 **ok**ボタンをクリックします。  
  
8.  WCF の接続 ダイアログ ボックスでの**サービス メタデータの URL**ボックスに「 **https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**  
  
9. **サービス エンドポイントの URL**ボックスに「 **https://localhost/ScottEmp/ISCOTT_EMP.svc**  
  
10. をクリックして、 **OK**の WCF 接続ダイアログを閉じるボタンをクリックします。  
  
11. データ ソースの情報を設定した後に展開し、 **https://localhost/ScottEmp/ISCOTT_EMP.svc**データ ソースし、展開**Web メソッド**です。  
  
12. 右クリックして、 **ReadList**をクリックして、Web メソッドを**新しい読み取りリスト操作**です。 リストの読み取りの [構成] ダイアログ ボックスを起動します。  
  
13. リストの読み取り ダイアログ ボックスをクリックして**戻り値のパラメーター**  をクリック**EMPNO**データのソース要素にします。 クリックして、**識別子にマップ**です。  
  
14. をクリックして**完了**リストの読み取り ダイアログ ボックス。  
  
15. 」と入力して、新しい外部データ ソースを保存**Ctrl + s**です。  
  
#### <a name="test-the-external-data-source-connection"></a>外部データ ソース接続をテストします。  
  
1.  新しい web サイト をクリックして、**リストの作成とフォーム**ボタンをクリックします。 リストの作成および OracleEMP ダイアログ フォームが表示されます。  
  
2.  入力**OracleEMP_List**のリストの名前とクリック、 **[ok]** ボタンをクリックします。  
  
3.  一覧を作成すると、クリックして、**の概要 ビュー**ボタン、メニューをクリックします。  
  
4.  をクリックして**OracleEMP_List**外部リストの下。  
  
5.  クリックして、**ブラウザーでプレビュー** アダプターの ReadList 操作をテストするメニュー ボタンをクリックします。  
  
## <a name="troubleshoot"></a>[トラブルシューティング]
  
-   64 ビット コンピューターでは 32 ビットの Oracle クライアント コンポーネントもインストールされていることを確認する必要があります。 Visual Studio とウィザードの開発時に 32 ビット コンポーネントへのアクセスを必要とする 32 ビット プロセスとして実行するためです。