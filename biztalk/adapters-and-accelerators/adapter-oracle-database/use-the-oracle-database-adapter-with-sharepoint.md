---
title: SharePoint での Oracle データベース アダプターの使用 |Microsoft Docs
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
ms.openlocfilehash: 7ca498313f74ac863cfb8d3c3846cb590cddebe8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528981"
---
# <a name="use-the-oracle-database-adapter-with-sharepoint"></a>SharePoint での Oracle データベース アダプターを使用します。
WCF アダプター サービス開発ウィザード[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]で Microsoft SharePoint の外部データ ソースとして直接使用するには、Oracle データベース、Microsoft BizTalk Adapter for Oracle E-business Suite の Microsoft BizTalk Adapter を有効にします。 この機能をサポートする追加サービス開発ウィザードを起動、 **WCF アダプタ サービス**、新しい Visual c# での Websites を作成するためのテンプレート[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]します。 テンプレートが付属、[!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)]します。 Microsoft Windows Communication Foundation (WCF) の基幹業務 (LOB) アダプター SDK をインストールすることも必要があります。  
  
## <a name="sharepoint-operation-support"></a>SharePoint の操作のサポート  
 アダプター サービス開発ウィザードは、Microsoft SharePoint と互換性がある Oracle アダプターの特別なサービス コントラクトを生成します。 ウィザードを Microsoft SharePoint アダプターを統合するために、次の操作を含むサービス コントラクトが生成されます。  
  
- **作成します。** CreateItem_ 操作によってサポートされています。  
  
- **読み取り:** ReadItem_ 操作によってサポートされています。  
  
- **更新プログラム:** UpdateItem_ 操作によってサポートされています。  
  
- **削除します。** DeleteItem_ 操作によってサポートされています。  
  
- **クエリ:** ReadList 操作によってサポートされています。  
  
- **関連付けます。** Associate_ 操作によってサポートされています。  
  
  例として、Microsoft BizTalk adapter for Oracle Database を使用に次のサービス コントラクトが生成されました。 EMP テーブルへのアクセスを提供するアダプターが構成されています。  
  
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
  
## <a name="create-a-new-web-site-to-host-the-oracle-database-in-iis"></a>IIS での Oracle データベースをホストする新しい Web サイトを作成します。  
 次の手順では、Microsoft BizTalk Adapter for Oracle Database をホストしている新しい WCF web サービスを作成する WCF アダプター サービス開発ウィザードを使用する例を提供します。 サービス コントラクトは、Sharepoint と直接的な互換性の操作が含まれます。 したがって、外部データ ソースとしてその it を直接使用できます。 アダプターが使用して Oracle データベースでの認証に構成されている、 **SCOTT**アカウント。 場合、 **SCOTT**アカウントがロックされている、SYSDBA として SQL Plus にログインして、アカウントのロックを解除することができます。  
  
```  
<Oracle Installation Bin Directory>\Sqlplus.exe SYS AS SYSDBA  
```  
  
 次のコマンドを実行します。  
  
```  
SQL> ALTER USER scott ACCOUNT UNLOCK;  
```  
  
#### <a name="create-the-new-web-site-project"></a>新しい Web サイト プロジェクトを作成します。  
  
1. Visual Studio を開きます。   
  
2. Visual Studio での**ファイル**メニューの **新規**順にクリックします**プロジェクト**します。  
  
3. **新しいプロジェクト** ダイアログ ボックスで、展開**他の言語**クリック**Visual c#**。 検索、 **WCF アダプタ サービス**テンプレートの一覧表示し、をクリックして選択します。  
  
   > [!NOTE]
   >  **WCF アダプタ サービス**テンプレートが利用できない場合、[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]がインストールされていません。 X64 システムでは、インストールの x86 と x64 の両方のバージョン、[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]します。  
  
4. 指定**ScottEMP**名、およびクリック**OK**します。 **WCF アダプター サービス開発ウィザード**を開始します。  
  
5. **概要**] ページで [**次**。  
  
6. **選択操作**ページで、指定、 **oracleDBBinding**バインドします。  
  
7. をクリックして、**構成**ボタンをクリックします。 **アダプターの構成**ダイアログが表示されます。  
  
8. **セキュリティ**] タブで [ **Username**で、**クライアント資格情報の種類**ボックスの一覧。  
  
9. 入力**SCOTT**ユーザーの名前を指定し、SCOTT アカウントの正しいパスワードを入力します。 SCOTT のアカウントの既定のパスワードは**tiger**します。  
  
10. をクリックして、 **URI プロパティ** タブで Oracle サーバーの IP アドレスまたはホスト名を入力、 **ServerAddress**ボックス。  
  
11. 正しい Oracle データベース サービス インスタンス名を入力、 **ServiceName**ボックス。 Oracle Enterprise Manager からインスタンス名の情報をコピーできます。  
  
12. キーを押して、 **OK**のボタンでは、**アダプターの構成**ダイアログ  
  
13. **選択操作**ページ、ウィザードのをクリックして、 **Connect**ボタンをクリックし、Oracle データベース用にビルドするカテゴリをしばらく待ってから。  
  
14. カテゴリが追加されると、**カテゴリを選択**一覧で、下へスクロールして**SCOTT**を展開します。 順に展開**テーブル** をクリックし、 **EMP**テーブル エントリ。  
  
15. **利用可能なカテゴリと操作**リストでの一覧で、すべての操作を選択してをクリックして、**追加**ボタンをクリックします。 すべての操作に追加されます、**カテゴリと操作を追加**一覧。  
  
16. **選択操作** ページで、をクリックして、**次**ボタン。  
  
17. **サービスの構成およびエンドポイントの動作** ページで、設定、 **UseServiceCertificate**サービスの動作を**false**この例です。 をクリックし、**次**ボタンをクリックします。  
  
18. **を構成するサービス エンドポイントのバインドとアドレス** ページで、をクリックして、**適用**ボタンをクリックします。 をクリックし、**次**ボタンをクリックします。  
  
19. **概要** ページで、をクリックして、**完了**ボタンをクリックします。  
  
20. をクリックして、**ビルド**メニュー オプションをクリック**ソリューションのビルド**します。 プロジェクトのビルドがエラーなしで成功したことを確認します。  
  
## <a name="publish-the-new-service-to-iis"></a>新しいサービスを IIS に発行します。  
 この例では、ローカル IIS web サーバーにアダプターのホスト サービスを発行するは。  
  
1.  Visual Studio のソリューション エクスプ ローラーで右クリックし、 **ScottEmp**プロジェクトし、クリックして**プロパティ**。 プロジェクト デザイナーのタブが表示されます。  
  
2.  をクリックして、 **Web**  タブの  をクリックし、**使用ローカル IIS Web サーバー**オプション。  
  
3.  をクリックして、**仮想ディレクトリの作成**ボタンをクリックします。  
  
4.  サービス アドレスに web ブラウザーを開いて **http://localhost/ScottEmp/ISCOTT_EMP.svc**します。 「サービスを作成した」というメッセージを受信する必要があります、アダプタを示す、IIS でホストされます。  
  
## <a name="add-the-external-data-source-to-a-sharepoint-site-using-sharepoint-designer"></a>SharePoint Designer を使用して SharePoint サイトに外部データ ソースを追加します。  
 このセクションでは、外部データ ソースとして SharePoint Designer を使用して新しい Web サイトに、WCF サービスを追加する方法について説明します。  
  
  
1.  SharePoint デザイナーを開き、新しい Web サイトを作成します。  
  
2.  SharePoint Designer で **[ナビゲーション]** をクリック**外部コンテンツ タイプ**で、**サイト オブジェクト**一覧。  
  
3.  をクリックして、**外部コンテンツ タイプ**新しい外部コンテンツ タイプを作成するメニュー ボタンをクリックします。  
  
4.  横にあるテキストをクリックします。**名前**、新しい外部コンテンツ タイプの名前を編集します。 入力**OracleEMP**名。  
  
5.  横にあるテキスト リンクをクリックして**外部システム**見なします**ここをクリックすると、外部データ ソースと操作を検出します。** します。 OracleEMP 外部コンテンツ タイプの操作のデザイナーが開きます。  
  
6.  をクリックして、**接続の追加**探索画面にボタンをクリックします。  
  
7.  外部データ ソースの種類の選択 ダイアログ ボックスで、次のように選択します。 **WCF サービス** をクリックし、 **OK**ボタン。  
  
8.  WCF の接続 ダイアログで、**サービス メタデータの URL**ボックスに入力します **https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**  
  
9. **サービス エンドポイントの URL**ボックスに入力します **https://localhost/ScottEmp/ISCOTT_EMP.svc**  
  
10. をクリックして、 **OK**ボタンの WCF 接続ダイアログ ボックスを閉じます。  
  
11. データ ソース情報を設定すると、展開、 **https://localhost/ScottEmp/ISCOTT_EMP.svc**データ ソースを展開**Web メソッド**します。  
  
12. 右クリックして、 **ReadList**をクリックして、Web メソッドを**新しい読み取りリスト操作**します。 リストの読み取りの構成 ダイアログが起動します。  
  
13. リストの読み取り ダイアログで次のようにクリックします。**パラメーターを返す** をクリック**EMPNO**でデータ ソースの要素。 をクリックして、**識別子にマップ**します。  
  
14. クリックして**完了**リストの読み取り ダイアログ ボックス。  
  
15. 」と入力して、新しい外部データ ソースを保存**Ctrl + s**します。  
  
#### <a name="test-the-external-data-source-connection"></a>外部データ ソースの接続をテストします。  
  
1.  新しい web サイトをクリックして、**リストの作成とフォーム**ボタンをクリックします。 リストの作成とフォーム OracleEMP ダイアログが表示されます。  
  
2.  入力**OracleEMP_List**リスト名と をクリックして、 **OK**ボタン。  
  
3.  リストを作成すると、クリックして、**概要ビュー**メニュー ボタン。  
  
4.  クリックして**OracleEMP_List**外部リストの下。  
  
5.  をクリックして、**ブラウザーでプレビュー**アダプターの ReadList 操作をテストするメニュー ボタンをクリックします。  
  
## <a name="troubleshoot"></a>[トラブルシューティング]
  
-   64 ビット コンピューターでは 32 ビット Oracle クライアント コンポーネントもインストールされていることを確認する必要があります。 これは、ため、開発中に、32 ビット コンポーネントへのアクセスを必要とする 32 ビット プロセスとして実行される Visual Studio とのウィザードです。