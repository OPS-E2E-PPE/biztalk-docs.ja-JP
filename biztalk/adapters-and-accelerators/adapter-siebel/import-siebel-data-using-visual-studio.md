---
title: Siebel を Visual Studio を使用してデータをインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33701361-eca2-4795-a5e0-78162a98e9ba
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4479fbbfd704cea30b8981866d3b7a354ca7269f
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
ms.locfileid: "23450507"
---
# <a name="import-siebel-data-using-visual-studio"></a>Siebel を Visual Studio を使用してデータをインポートします。
このセクションでは、Microsoft の使用方法に関する情報を提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Siebel システムから SQL Server データベースにデータをインポートします。 また、作成し、このデータをインポートする SSIS パッケージを実行する方法の手順についても提供します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックに記載されている手順を実行する前に確認します。  
  
-   [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]がコンピューターにインストールされています。  
  
-   Microsoft Visual Studio は、コンピューターにインストールされています。  
  
## <a name="import-in-visual-studio"></a>Visual Studio でのインポート  
 
1.  開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Integration Service プロジェクトを作成します。  
  
2.  **プロジェクト**メニューの  **SSIS インポートおよびエクスポート ウィザード**です。 これは、SQL Server インポートおよびエクスポート ウィザードを起動します。  
  
3.  [ようこそ] 画面で、情報を参照し、をクリックして**次**です。  
  
4.  **データ ソースを選択** ダイアログ ボックスから、**データ ソース**ドロップ ダウン リスト **.NET Framework Data Provider 用 Siebel eBusiness Applications**です。 さまざまな接続のプロパティの値を指定、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]接続文字列。 接続文字列プロパティの詳細については、次を参照してください。 [Siebel 接続文字列のデータ プロバイダーのプロパティ](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)です。  
  
     **[次へ]** をクリックします。  
  
5.  **先選択** ダイアログ ボックス。  
  
    1.  **先**ドロップダウン リストで、 **SQL Native Client**です。  
  
    2.  **サーバー名**ドロップダウン リストで、SQL Server 名を選択します。  
  
    3.  認証モードを選択します。  
  
    4.  **データベース**ドロップダウン リストで、Siebel テーブルをインポートするデータベースを選択します。  
  
    5.  **[次へ]** をクリックします。  
  
6.  **テーブルのコピーを指定またはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプション。  
  
7.  **ソース クエリを指定する** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。 クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)です。  
  
8.  クエリを検証するには、をクリックして、**解析**ボタンをクリックし**OK**をクリックしてポップアップ ダイアログ ボックスで、 **[次へ]** です。  
  
9. **[ソース テーブルおよびビュー** ] ダイアログ ボックスで、ソース テーブルと対象テーブルに対してチェック ボックスをオンにします。 ソースは、Siebel からデータを取得するように指定したクエリを示します。 変換先は、SQL Server データベースに作成されるテーブルになります。  
  
10. ウィザードでは、テーブルのフィールド、ソースと移行先の既定のマッピングを作成します。 ただし、要件に従って、マッピングを変更することができます。 フィールド マッピングを変更する をクリックして**マッピングの編集**です。  
  
11. **列マッピング**ダイアログ ボックスで、することができます。  
  
    -   変換先テーブル内の列の名前を変更します。  
  
    -   変換先テーブル内の特定の列を無視します。  
  
    -   コピー先のテーブル内のフィールドのデータ型を変更します。  
  
    -   Nullable、サイズ、有効桁数、小数点以下桁数などその他のフィールドの属性を変更します。  
  
    -   **[OK]** をクリックします。  
  
     ![Siebel テーブルと SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")  
  
12. **ソース テーブルおよびビュー**ダイアログ ボックスで、をクリックして**次へ**です。  
  
13. **ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**です。  
  
14. **操作の実行**Siebel から SQL Server データベース テーブルに情報をインポートするタスクを実行してダイアログ ボックスで、ウィザードを起動します。 各タスクの状態は、ウィザードに表示されます。  
  
15. すべてのタスクが正常に実行される、クリックして**閉じる**です。 タスクが失敗した場合、対応するエラー メッセージを参照してください、問題を修正、ウィザードを再実行します。  
  
16. ウィザードでは、統合サービス プロジェクトに、SSIS パッケージを追加します。 統合サービス プロジェクトを保存します。  
  
## <a name="run-the-ssis-package"></a>SSIS パッケージを実行します。  
 統合サービス プロジェクト内で、パッケージが作成されると、Siebel システムから SQL Server データベースにデータをインポートすることを実行できます。 パッケージを実行して Siebel データをインポートするのには、次の手順を実行します。  
  
1.  ソリューション エクスプ ローラーで SSIS パッケージに移動します。  
  
2.  パッケージ名を右クリックし、**パッケージ実行**です。  
  
[Integration Services (SSIS) パッケージの実行](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages)詳細な情報を提供します。 
  
## <a name="verify-the-results"></a>結果を確認します。  
 パッケージを実行すると、SQL Server にログオンし、Siebel データのインポート先となるデータベースに移動することによって結果を確認する必要があります。 パッケージを実行する必要がありますテーブルを作成したコピー先データベースにします。 このテーブルは、Siebel テーブルからの値に設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [Siebel と SSIS のデータ プロバイダーを使用します。](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)