---
title: テンプレート (アプリケーションの展開サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, examples
- scripts, deploying
- deploying, scripts
- examples, deploying
ms.assetid: 7e77ff8e-b2bc-4d38-b5fd-329d6d54221f
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 315a685f0e289d60e3db9dfbe77bae5a7e2b19f0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975016"
---
# <a name="template-application-deployment-sample"></a>Template (アプリケーションの展開サンプル)
このトピックでは、Template サンプルを使用してアプリケーションを展開する方法について説明します。  
  
 2 種類の展開スクリプト (処理前のスクリプトと処理後のスクリプト) を作成して使用し、BizTalk アプリケーションの展開をカスタマイズできます。 処理前のスクリプトは、アプリケーションのインストールおよびインポートの開始前およびアンインストールの完了後に呼び出されます。 処理後のスクリプトは、アプリケーションのインストールおよびインポートの完了後およびアンインストールの開始前に呼び出されます。  
  
 処理前と処理後のスクリプトは、これらの個々の操作で呼び出されるように記述できます。 別の方法として、いずれかの操作の後にだけ実行するようスクリプトを構成することもできます。 スクリプトの作成の詳細については、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)です。  
  
 このトピックでは、1 つの操作の前または後にのみ呼び出されるようスクリプトを記述して展開する方法について説明します。 3 つの環境変数の値をチェックして、自身が呼び出されるコンテキストの操作を判断するスクリプトを記述します。 そのコンテキストに基づいて、スクリプトは実行を継続または停止します。  
  
 このトピックでは、以下の手順を実行する方法について説明します。  
  
1.  スクリプト操作のログ ファイルを生成できるようログ ファイルの場所を設定します。  
  
    > [!NOTE]
    >  ベスト プラクティスとして、スクリプトの操作の検証および問題のトラブルシューティングを行うことができるようにログ ファイルを常に生成することをお勧めします。  
  
2.  新しい BizTalk アプリケーションを作成し、サンプル スクリプトを追加します。  
  
3.  アプリケーションのアイテムを含む .msi ファイルをエクスポートします。  
  
4.  .msi ファイルを同じグループにインポートして .msi ファイルからアプリケーションをインストールできるように、BizTalk グループからアプリケーションを削除します。  
  
5.  アプリケーションをインポートし、ログ ファイルをチェックしてインポート操作が記録されていることを確認します。  
  
6.  アプリケーションをインストールし、ログ ファイルをチェックしてインストール ログがログ ファイルに追加されていることを確認します。  
  
7.  ログ ファイルを表示して、スクリプトによって実行された操作および操作がいつ実行されたかを確認します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルには、インポート、インストール、およびアンインストールの環境変数の値を含む 2 つの .bat ファイルが付属しています。 SamplePreProcessing.bat には、処理前のスクリプトの変数が含まれています。 SamplePostProcessing.bat には、処理後のスクリプトの変数が含まれています。 これらのファイルは、スクリプトからのメッセージをログ記録する方法も示します。 これらのファイル内の関連するセクションをスクリプトにコピーできます。  
  
> [!IMPORTANT]
>  スクリプト ファイル内のコメントには間違っているものがあります。次に例を示します。  
>   
>  SamplePreProcessing.bat の "既存のアプリケーションのアンインストール前に呼び出されるスクリプトの部分 (Pre uninstall part of the script called for an existing application)" というコメントは、"既存のアプリケーションのアンインストール後に呼び出されるスクリプトの部分 (Post uninstall part of the script called for an existing application)" の誤りです。  
>   
>  SamplePostProcessing.bat の "既存のアプリケーションのアンインストール後に呼び出されるスクリプトの部分 (Post uninstall part of the script called for an existing application)" というコメントは、"既存のアプリケーションのアンインストール前に呼び出されるスクリプトの部分 (Pre uninstall part of the script called for an existing application)" の誤りです。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール フォルダーに格納されています  
  
 *\<パスのサンプル\>* \Application Deployment\Template  
  
 前に説明したように、サンプルには以下の 2 つのファイルが含まれています。  
  
-   SamplePreProcessing.bat  
  
-   SamplePostProcessing.bat  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルを実行するには、次の手順を実行します。  
  
### <a name="to-set-the-logging-location"></a>ログ ファイルの場所を設定するには  
  
-   両方のスクリプト サンプルを開き、LogFile 変数を変更して、ログ ファイルを書き込む場所を指定します。 ファイル名を含む完全なパスを指定する必要があります。 スペースが含まれている場合は、二重引用符 (") でのパスを囲む必要があります。  
  
     例:  
  
     ログ ファイルの設定 ="*\<サンプル パス\>* \ApplicationDeployment\Templates\SampleLogOut.txt"  
  
### <a name="to-create-a-new-application"></a>新しいアプリケーションの作成  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、[BizTalk グループ] の順に展開します。  
  
3.  右クリック**アプリケーション** をクリックし、**新規**です。  
  
4.  **アプリケーション名**、型`SamplesTemplate`、順にクリック**OK**です。  
  
### <a name="to-add-the-scripts-to-the-application"></a>アプリケーションへのスクリプトの追加  
  
1.  作成した SamplesTemplate アプリケーションのフォルダーを展開し、右クリック**リソース**左側のウィンドウでします。  
  
2.  指す**追加** をクリック**処理前のスクリプト**です。  
  
3.  をクリックして**追加**し、SamplePreProcessing.bat を参照します。  
  
4.  ファイルを選択し、をクリックして**開く**です。  
  
5.  **ファイルの種類**、 をクリックして**System.BizTalk:PreprocessingScript**、順にクリック**OK**です。  
  
     SamplePreProcessing.bat が追加されて、アプリケーションのリソース フォルダーに表示されます。  
  
6.  リソースをもう一度右クリックし、**追加**、クリックして**処理後のスクリプト**です。  
  
7.  をクリックして**追加**し、SamplePostProcessing.bat を参照します。  
  
8.  ファイルを選択し、をクリックして**開く**です。  
  
9. **ファイルの種類**、 をクリックして**System.BizTalk:PostprocessingScript**、順にクリック**OK**です。  
  
     SamplePostProcessing.bat が追加されて、アプリケーションのリソース フォルダーに表示されます。  
  
### <a name="to-export-an-msi-file"></a>.msi ファイルのエクスポート  
  
1.  BizTalk Server 管理コンソールで、SamplesTemplate アプリケーションを右クリックし、**エクスポート**、クリックして**MSI ファイル**です。  
  
2.  エクスポート ウィザードのページへようこそ、をクリックして**次**です。  
  
3.  リソースの選択 ページで、をクリックして**次**です。  
  
4.  IIS ホストの指定 ページで、をクリックして**次**です。  
  
5.  依存関係 ページで、をクリックして**次**です。  
  
6.  [宛先] ページで**送信先アプリケーション名**アプリケーション名を入力します。  
  
7.  **を生成する MSI ファイル**MSI ファイルの完全なパスを入力して、をクリックして**エクスポート**です。 例: C:\MSI\SamplesTemplate.msi  
  
8.  [概要] ページで、をクリックして**完了**です。  
  
### <a name="delete-the-application"></a>アプリケーションの削除  
  
-   BizTalk Server 管理コンソールで、SamplesTemplate アプリケーションを右クリックし、をクリックして**削除**です。  
  
### <a name="to-import-the-msi-file"></a>.msi ファイルのインポート  
  
1.  BizTalk Server 管理コンソールを右クリックして**アプリケーション**、 をポイント**インポート**、クリックして**MSI ファイル**です。  
  
2.  インポート ウィザードのページへようこそ で**インポートする MSI ファイル**、事前にエクスポートしてをクリックした .msi ファイルのパスを入力**次**です。 かどうか必要に応じてを参照できます、MSI ファイル をクリックして、 **(...)** ボタンをクリックします。  
  
3.  [アプリケーションの設定] ページで、**アプリケーション名**ドロップダウン一覧で、アプリケーションの名前を選択します。  
  
4.  **への参照を追加できるアプリケーション**存在する場合、参照を追加するアプリケーションを選択して、をクリックして**次**です。  
  
5.  アプリケーションのターゲット環境の設定 ページで、**次**です。  
  
    > [!NOTE]
    >  このサンプルではターゲット環境を指定する必要はありません。 この機能の基礎知識については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。 バインド ファイルを追加する方法の詳細については、次を参照してください。[アプリケーションにバインド ファイルを追加する方法](../core/how-to-add-a-binding-file-to-an-application2.md)です。  
  
6.  インポートの概要 ページで、概要情報が正しいことを確認し、をクリックして**インポート**です。  
  
7.  [結果] ページで、をクリックして**完了**です。  
  
8.  スクリプトの実行時に作成されたログ ファイルを開き、インポート操作が記録されていることを確認します。  
  
### <a name="to-install-the-application"></a>アプリケーションをインストールするには  
  
1.  .msi ファイルをダブルクリックし、インストール ウィザードを実行します。  
  
2.  ログ ファイルを開き、ログ情報にインストール操作が追加されていることを確認します。  
  
### <a name="to-verify-that-the-scripts-functioned-correctly"></a>スクリプトが正常に機能したことの確認  
  
-   ログ ファイルを開き、指定した操作でスクリプトが実行されたことを確認します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開 (BizTalk Server Samples フォルダ)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)