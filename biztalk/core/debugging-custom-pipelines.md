---
title: "カスタム パイプラインのデバッグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27e5445a-6415-4c52-a450-b74a71fc4aa2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a0f701518714aaf28d0ae07867c8c490c140fa0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="debugging-custom-pipelines"></a>カスタム パイプラインのデバッグ
カスタム パイプラインでメッセージ処理が失敗するときは、ソース レベルのデバッグを使用して、問題の特定と修正を行うことができます。 ソース レベルのデバッグは、BTSNTSVC.exe (カスタム パイプラインを配置している場合) または Pipeline.exe (スタンドアロン パイプライン ツールを使用している場合) にアタッチすることにより、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] デバッガーを使用して行います。  
  
## <a name="procedures"></a>手順  
 次の手順に従って、カスタム パイプラインをデバッグします。  
  
### <a name="how-to-debug-a-deployed-pipeline"></a>配置済みのパイプラインをデバッグする方法  
 [グループ ハブ] ページからのクエリの追跡およびイベント ビューアーでは、配置済みのコンポーネントでのメッセージ処理の失敗に関する役立つ情報が提供されます。 この情報を使用すると、問題の原因を絞り込むことができます。 カスタム パイプラインが関係している場合には、ソース レベルのデバッグを使用して、問題のあるコードを特定できます。  
  
##### <a name="to-debug-a-deployed-custom-pipeline-using-visual-studio"></a>Visual Studio を使用して配置済みのカスタム パイプラインをデバッグするには  
  
1.  カスタム パイプライン プロジェクトのソリューションを [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に読み込みます。  
  
2.  ソリューションの出力パスを変更する*\<インストール フォルダー >*\Pipeline Components です。 ソリューション エクスプ ローラーでプロジェクトを右クリックし、ビルド タブをクリックしをクリックして出力パスを変更、**参照** ボタンを選択して、 *\<インストール フォルダー >*\パイプライン コンポーネント ディレクトリです。  
  
3.  内から[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]をクリックして、ソリューションをデプロイ**ビルド**& #124 です。**展開**です。  
  
4.  パイプラインを実行するホスト インスタンスを再起動します。 BizTalk Server 管理コンソールを使用してパイプラインを実行するホスト インスタンスに移動し、ホスト インスタンスを右クリックし、をクリックして**再起動**です。  
  
5.  アタッチ、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]デバッガーを BTSNTSVC.exe にします。 クリックしてこれ行う**デバッグ**& #124 です。**プロセスにアタッチする**を すべてのセッションのプロセス表示をクリックし、BTSNTSVC.exe をダブルクリックします。  
  
6.  ブレークポイントを設定します。  
  
7.  適切な位置にメッセージをドロップして、カスタム パイプライン コンポーネントを開始します。 設定したブレークポイントで処理が停止します。  
  
> [!NOTE]
>  コードが例外をスローすると、BizTalk Server がそれをキャッチし、最終的にメッセージを保留します。 この動作を回避するには、初回例外でブレークする必要があります。  
  
### <a name="how-to-debug-using-pipelineexe"></a>Pipeline.exe を使用してデバッグする方法  
 Pipeline.exe を使用してカスタム パイプラインをテストすることもできます。 これにより、実稼働に近い条件下で実行されていないを犠牲にして、パイプラインをデプロイする必要がないという利点があります。  
  
> [!NOTE]
>  カスタム パイプラインがフラット ファイル アセンブラー/逆アセンブラーを使用している場合は、Pipeline.exe は正常に機能しません。 これは、Pipeline.exe が BizTalk データベースにアクセスしないためです。 1 つのソリューションは、アセンブラーを削除する/逆アセンブラー コンポーネント FFDasm.exe および FFAsm.exe でそれらを個別にテストします。 参照してください[パイプライン ツール](../core/pipeline-tools.md)詳細についてはします。  
  
##### <a name="to-debug-a-custom-pipeline-using-pipelineexe-and-visual-studio"></a>Pipeline.exe と Visual Studio を使用してカスタム パイプラインをデバッグするには  
  
1.  カスタム パイプライン プロジェクトのソリューションを [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に読み込みます。  
  
2.  ソリューションの出力パスを変更する*\<インストール フォルダー >*\Pipeline Components です。 ソリューション エクスプ ローラーでプロジェクトを右クリックし、ビルド タブをクリックしをクリックして出力パスを変更、**参照** ボタンを選択して、 *\<インストール フォルダー >*\パイプライン コンポーネント ディレクトリです。  
  
3.  ソリューションの開始アクションを変更します。 ソリューション エクスプ ローラーでプロジェクトを右クリックし、デバッグ タブをクリックして、外部プログラムの開始 をクリックし をクリック**しています.** 移動して*\<インストール フォルダー >*\SDK\Utilities\PipelineTools Pipeline.exe を選択します。 [開始オプション]、コンポーネントの適切なコマンドライン引数を入力します。 Pipeline.exe の詳細については、次を参照してください。[パイプライン ツール](../core/pipeline-tools.md)です。 一般的な構成では、パイプラインとサンプル ファイルを指定します。  
  
    ```  
    <Path>\YourPipeline.btp -d <Path>\YourTestFile.txt -c  
    ```  
  
4.  ブレークポイントを設定します。  
  
5.  F5 キーを押してデバッグを開始します。  
  
## <a name="see-also"></a>参照  
 [パイプライン ツール](../core/pipeline-tools.md)