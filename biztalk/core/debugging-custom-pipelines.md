---
title: カスタム パイプラインのデバッグ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27e5445a-6415-4c52-a450-b74a71fc4aa2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f03391660e7f06892294a84ba2be3fdabbc4703
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012019"
---
# <a name="debugging-custom-pipelines"></a>カスタム パイプラインのデバッグ
カスタム パイプラインでメッセージ処理が失敗するときは、ソース レベルのデバッグを使用して、問題の特定と修正を行うことができます。 ソース レベルのデバッグは、BTSNTSVC.exe (カスタム パイプラインを配置している場合) または Pipeline.exe (スタンドアロン パイプライン ツールを使用している場合) にアタッチすることにより、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] デバッガーを使用して行います。  
  
## <a name="procedures"></a>手順  
 次の手順に従って、カスタム パイプラインをデバッグします。  
  
### <a name="how-to-debug-a-deployed-pipeline"></a>配置済みのパイプラインをデバッグする方法  
 [グループ ハブ] ページからのクエリの追跡およびイベント ビューアーでは、配置済みのコンポーネントでのメッセージ処理の失敗に関する役立つ情報が提供されます。 この情報を使用すると、問題の原因を絞り込むことができます。 カスタム パイプラインが関係している場合には、ソース レベルのデバッグを使用して、問題のあるコードを特定できます。  
  
##### <a name="to-debug-a-deployed-custom-pipeline-using-visual-studio"></a>Visual Studio を使用して配置済みのカスタム パイプラインをデバッグするには  
  
1. カスタム パイプライン プロジェクトのソリューションを [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に読み込みます。  
  
2. ソリューションは、出力パスを変更して*\<インストール フォルダー\>* \Pipeline Components です。 ソリューション エクスプ ローラーでプロジェクトを右クリックし、ビルド タブをクリックしておよびクリックして、出力パスを変更、**参照**ボタンをクリックしを選択すると、 *\<インストール フォルダー\>* \Pipeline components ディレクトリ。  
  
3. 内から[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、 をクリックして、ソリューションを配置**ビルド** &#124; **デプロイ**します。  
  
4. パイプラインを実行するホスト インスタンスを再起動します。 パイプラインを実行するホスト インスタンスに移動し、ホスト インスタンスを右クリックし をクリックして、BizTalk Server 管理コンソールを使用して、**再起動**します。  
  
5. アタッチ、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]デバッガーを BTSNTSVC.exe にします。 これをクリックして実行できます**デバッグ** &#124; **プロセスにアタッチ**、すべてのセッションでプロセス表示をクリックし、BTSNTSVC.exe をダブルクリックします。  
  
6. ブレークポイントを設定します。  
  
7. 適切な位置にメッセージをドロップして、カスタム パイプライン コンポーネントを開始します。 設定したブレークポイントで処理が停止します。  
  
> [!NOTE]
>  コードが例外をスローすると、BizTalk Server がそれをキャッチし、最終的にメッセージを保留します。 この動作を回避するには、初回例外でブレークする必要があります。  
  
### <a name="how-to-debug-using-pipelineexe"></a>Pipeline.exe を使用してデバッグする方法  
 Pipeline.exe を使用してカスタムのパイプラインをテストすることもできます。 これにより、運用環境のような条件下で実行されていないと引き換えパイプラインをデプロイする必要がないという利点があります。  
  
> [!NOTE]
>  カスタム パイプラインがフラット ファイル アセンブラー/逆アセンブラーを使用している場合は、Pipeline.exe は正常に機能しません。 これは、Pipeline.exe が BizTalk データベースにアクセスしないためです。 1 つのソリューションは、アセンブラーを削除する/逆アセンブラー コンポーネント FFDasm.exe および FFAsm.exe を個別にテストします。 参照してください[パイプライン ツール](../core/pipeline-tools.md)詳細についてはします。  
  
##### <a name="to-debug-a-custom-pipeline-using-pipelineexe-and-visual-studio"></a>Pipeline.exe と Visual Studio を使用してカスタム パイプラインをデバッグするには  
  
1. カスタム パイプライン プロジェクトのソリューションを [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に読み込みます。  
  
2. ソリューションは、出力パスを変更して*\<インストール フォルダー\>* \Pipeline Components です。 ソリューション エクスプ ローラーでプロジェクトを右クリックし、ビルド タブをクリックしておよびクリックして、出力パスを変更、**参照**ボタンをクリックしを選択すると、 *\<インストール フォルダー\>* \Pipeline components ディレクトリ。  
  
3. ソリューションの開始アクションを変更します。 ソリューション エクスプ ローラーでプロジェクトを右クリックを [デバッグ] タブをクリックし、[外部プログラムの開始] をクリックしてをクリックして **.** 移動します*\<インストール フォルダー\>* \SDK\Utilities\PipelineTools Pipeline.exe を選択します。 [開始オプション]、コンポーネントの適切なコマンドライン引数を入力します。 Pipeline.exe の詳細については、次を参照してください。[パイプライン ツール](../core/pipeline-tools.md)します。 一般的な構成では、パイプラインとサンプル ファイルを指定します。  
  
   ```  
   <Path>\YourPipeline.btp -d <Path>\YourTestFile.txt -c  
   ```  
  
4. ブレークポイントを設定します。  
  
5. F5 キーを押してデバッグを開始します。  
  
## <a name="see-also"></a>参照  
 [パイプライン ツール](../core/pipeline-tools.md)