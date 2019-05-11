---
title: Visual Studio を使用して Siebel データのインポート |Microsoft Docs
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
ms.openlocfilehash: 3397bfcb75dd68945b87c47ad0af237e677c3a92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371498"
---
# <a name="import-siebel-data-using-visual-studio"></a>Visual Studio を使用して Siebel データをインポートします。
このセクションでは、Microsoft を使用する方法についての情報を提供します。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Siebel システムから SQL Server データベースにデータをインポートします。 また、作成し、このデータをインポートする SSIS パッケージを実行する方法の手順を提供します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックで説明する手順を実行する前に確認します。  
  
- [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]コンピューターにインストールされます。  
  
- Microsoft Visual Studio は、コンピューターにインストールされます。  
  
## <a name="import-in-visual-studio"></a>Visual Studio でのインポート  
 
1. 開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との統合サービス プロジェクトを作成します。  
  
2. **プロジェクト**メニューの  **SSIS インポートおよびエクスポート ウィザード**します。 これは、SQL Server インポートおよびエクスポート ウィザードを起動します。  
  
3. クリックして、ようこそ画面の情報を読み取る**次**します。  
  
4. **データ ソースの選択** ダイアログ ボックスから、**データ ソース**ドロップダウン リスト**Siebel eBusiness Applications の .NET Framework Data Provider**します。 さまざまな接続のプロパティの値を指定、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]接続文字列。 接続文字列プロパティの詳細については、次を参照してください。 [Siebel 接続文字列のデータ プロバイダー プロパティ](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)します。  
  
    **[次へ]** をクリックします。  
  
5. **変換先の選択** ダイアログ ボックス。  
  
   1.  **先**ドロップダウン リストで、 **SQL Native Client**します。  
  
   2.  **サーバー名**ドロップダウン リストで、SQL Server 名を選択します。  
  
   3.  認証モードを選択します。  
  
   4.  **データベース**ドロップダウン リストで、Siebel テーブルをインポートするデータベースを選択します。  
  
   5.  **[次へ]** をクリックします。  
  
6. **指定のテーブルのコピーまたはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプション。  
  
7. **ソース クエリの指定** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。 クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)します。  
  
8. クエリを検証するには、次のようにクリックします。、**解析**ボタンをクリック**OK**でクリックしてポップアップ ダイアログ ボックスで、 **[次へ]**。  
  
9. **選択元のテーブルおよびビュー**  ダイアログ ボックスで、ソースと変換先のテーブルに対してチェック ボックスをオンにします。 ソースは、Siebel からデータを取得する指定したクエリです。 変換先は、SQL Server データベースに作成されるテーブルになります。  
  
10. ウィザードは、ソースと宛先の間の既定のマッピング テーブルのフィールドを作成します。 ただし、要件に従って、マッピングを変更することができます。 フィールド マッピングを変更するには、クリックして**マッピングの編集**します。  
  
11. **列マッピング** ダイアログ ボックスができます。  
  
    - 変換先テーブル内の列の名前を変更します。  
  
    - 変換先テーブルで特定の列を無視します。  
  
    - 変換先テーブル内のフィールドのデータ型を変更します。  
  
    - Null 許容型のサイズ、有効桁数、およびスケールなどの他のフィールドの属性を変更します。  
  
    - **[OK]** をクリックします。  
  
      ![Siebel および SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")  
  
12. **選択元のテーブルおよびビュー**ダイアログ ボックスで、をクリックして**次**。  
  
13. **ウィザードを完了**] ダイアログ ボックスで、ウィザードを実行し、[アクションの概要を確認**完了**します。  
  
14. **操作の実行**Siebel から SQL Server データベースのテーブルに情報をインポートするタスクの実行 ダイアログ ボックスで、ウィザードが起動します。 ウィザードでは、各タスクの状態が表示されます。  
  
15. すべてのタスクが正常に実行される、クリックして**閉じる**します。 タスクが失敗した場合、対応するエラー メッセージが表示、問題を解決し、ウィザードを再実行します。  
  
16. ウィザードでは、統合サービス プロジェクトに、SSIS パッケージを追加します。 統合サービス プロジェクトを保存します。  
  
## <a name="run-the-ssis-package"></a>SSIS パッケージを実行します。  
 統合サービス プロジェクトでは、パッケージが作成されたら、Siebel システムから SQL Server データベースにデータをインポートすることを実行できます。 パッケージを実行して Siebel データをインポートするのには、次の手順を実行します。  
  
1.  ソリューション エクスプ ローラーで SSIS パッケージに移動します。  
  
2.  パッケージ名を右クリックし、**パッケージ実行**します。  
  
[Integration Services (SSIS) パッケージを実行する](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages)詳細情報を提供します。 
  
## <a name="verify-the-results"></a>結果を確認します。  
 パッケージを実行した後は、SQL Server にログオンしている、Siebel データをインポートするデータベースに移動して結果を確認する必要があります。 パッケージを実行する必要がありますのテーブルを作成、転送先データベース。 このテーブル Siebel テーブルから値を持つデータを設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [Data Provider for Siebel を SSIS と一緒に使用する](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)