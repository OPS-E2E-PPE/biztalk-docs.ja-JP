---
title: Visual Studio を使用して SAP データのインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- importing SAP data, using Visual Studio
- Visual Studio, importing SAP data
ms.assetid: 70cce089-232d-4ab9-81bd-6b0d6f0097d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1295f763815872bacedf2262f7c022d6813bd75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217754"
---
# <a name="import-sap-data-using-visual-studio"></a>Visual Studio を使用して SAP データのインポート
このセクションでは、Microsoft を使用する方法の情報を提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]SAP システムから SQL Server データベースにデータをインポートします。 このセクションでは、データをインポートする実行可能な SSIS パッケージを作成する方法の命令を提供します。 このセクションでは、SSIS パッケージを実行する方法についても情報を提供します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックに記載されている手順を実行する前に確認します。  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]コンピューターにインストールされます。  
  
-   [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]コンピューターにインストールされます。  
  
### <a name="to-import-data-using-visual-studio"></a>Visual Studio を使用してデータをインポートするには  
  
1.  開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Integration Service プロジェクトを作成します。  
  
2.  **プロジェクト**メニューの  **SSIS インポートおよびエクスポート ウィザード**です。 起動、 **SQL Server インポートおよびエクスポート ウィザード**です。  
  
3.  クリックして [ようこそ] 画面の情報を読み取る**次**です。  
  
4.  **データ ソースを選択** ダイアログ ボックスから、**データ ソース**ドロップ ダウン リスト **.NET Framework Data Provider 用 mySAP Business Suite**です。 ダイアログ ボックスは、SAP システムへの接続に別の接続パラメーターを一覧表示します。 使用して SAP システムへの接続に一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。  
  
    -   接続の接続パラメーターを入力します。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1*種類の接続をします。 たとえば、接続の種類、システム数と、アプリケーション サーバーのホストの名前を指定する必要があります。  
  
    -   ユーザー名やパスワードなど、SAP システムへの接続にログイン情報。  
  
     使用して SAP システムへの接続への接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。  
  
     **データ ソースを選択** ダイアログ ボックスで指定します。  
  
    -   任意の 1 つの接続の接続パラメーターを入力します。  
  
    -   SAP システムへの接続にログイン情報。  
  
    -   SAP GUI のデバッグを有効にするかどうか。  
  
    -   RFC SDK トレースを使用するかどうか。  
  
     **[次へ]** をクリックします。  
  
5.  **先選択** ダイアログ ボックス。  
  
    1.  **先**ドロップダウン リストで、 **SQL Native Client**です。  
  
    2.  **サーバー名**ドロップダウン リストで、SQL server 名を選択します。  
  
    3.  認証モードを選択します。  
  
    4.  **データベース**ドロップダウン リストで、SAP テーブルをインポートするデータベースを選択します。  
  
    5.  **[次へ]** をクリックします。  
  
6.  **テーブルのコピーを指定またはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプションし、をクリックして**次**です。  
  
7.  **ソース クエリを指定する** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。 クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)です。  
  
     をクリックして、**解析**クエリを検証し、をクリックするボタン **[ok]** ポップアップ ダイアログ ボックスにします。 **[次へ]** をクリックします。  
  
8.  **[ソース テーブルおよびビュー** ] ダイアログ ボックスで、ソース テーブルと対象テーブルに対してチェック ボックスをオンにします。 ソースは、SAP からデータを取得するように指定したクエリを示します。 変換先は、SQL Server データベースに作成されるテーブルです。  
  
9. ウィザードでは、テーブルのフィールド、ソースと移行先の既定のマッピングを作成します。 ただし、要件に従って、マッピングを変更することができます。 フィールド マッピングを変更する をクリックして**マッピングの編集**です。  
  
     ![SAP テーブルと SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")  
  
10. **列マッピング**ダイアログ ボックスで、することができます。  
  
    -   変換先テーブル内の列の名前を変更します。  
  
    -   変換先テーブル内の特定の列を無視します。  
  
    -   コピー先のテーブル内のフィールドのデータ型を変更します。  
  
    -   Nullable、サイズ、有効桁数、小数点以下桁数などその他のフィールドの属性を変更します。  
  
    -   **[OK]** をクリックします。  
  
11. **ソース テーブルおよびビュー**ダイアログ ボックスで、をクリックして**次へ**です。  
  
12. **ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**です。  
  
13. **を実行する操作**SAP から情報を SQL Server データベース テーブルにインポートするタスクを実行してダイアログ ボックスで、ウィザードを起動します。 各タスクの状態は、ウィザードに表示されます。  
  
14. すべてのタスクが正常に実行される、クリックして**閉じる**です。 タスクが失敗した場合、対応するエラー メッセージを参照してください、問題を修正、ウィザードを再実行します。  
  
15. ウィザードでは、統合サービス プロジェクトに、SSIS パッケージを追加します。 統合サービス プロジェクトを保存します。  
  
## <a name="running-the-ssis-package"></a>SSIS パッケージを実行します。  
 統合サービス プロジェクト内で、パッケージが作成されると、SAP システムから SQL Server データベースにデータをインポートすることを実行できます。 パッケージを実行して SAP データをインポートするのには、次の手順を実行します。  
  
#### <a name="to-run-the-package-from-visual-studio"></a>Visual Studio からパッケージを実行するには  
  
1.  ソリューション エクスプ ローラーで SSIS パッケージに移動します。  
  
2.  パッケージ名を右クリックし **パッケージ実行**です。  
  
 パッケージの実行の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)です。 SSIS パッケージに関連するその他の情報を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)です。  
  
## <a name="verifying-the-results"></a>結果の確認  
 パッケージを実行すると、SQL Server にログオンし、SAP データのインポート先となるデータベースに移動することによって結果を確認する必要があります。 パッケージの実行がコピー先データベースにテーブルを作成し、SAP テーブルから値を挿入します。  
  
## <a name="see-also"></a>参照  
 [SAP と SSIS のデータ プロバイダーを使用します。](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)