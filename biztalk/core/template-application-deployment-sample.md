---
title: テンプレート (アプリケーションの展開サンプル) |Microsoft Docs
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
ms.openlocfilehash: 7d096dac4d1c51101ddadff9eb6c49c04202d375
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000059"
---
# <a name="template-application-deployment-sample"></a>Template (アプリケーションの展開サンプル)
このトピックでは、Template サンプルを使用してアプリケーションを展開する方法について説明します。  
  
 2 種類の展開スクリプト (処理前のスクリプトと処理後のスクリプト) を作成して使用し、BizTalk アプリケーションの展開をカスタマイズできます。 処理前のスクリプトは、アプリケーションのインストールおよびインポートの開始前およびアンインストールの完了後に呼び出されます。 処理後のスクリプトは、アプリケーションのインストールおよびインポートの完了後およびアンインストールの開始前に呼び出されます。  
  
 処理前と処理後のスクリプトは、これらの個々の操作で呼び出されるように記述できます。 別の方法として、いずれかの操作の後にだけ実行するようスクリプトを構成することもできます。 スクリプトの作成の詳細については、[アプリケーション展開のカスタマイズを前処理および後処理のスクリプトを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)を参照してください。  
  
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
  
-   両方のスクリプト サンプルを開き、LogFile 変数を変更して、ログ ファイルを書き込む場所を指定します。 ファイル名を含む完全なパスを指定する必要があります。 スペースが含まれている場合、パスを二重引用符 (") で囲む必要があります。  
  
     例:  
  
     設定のログ ファイル ="*\<サンプル パス\>* \ApplicationDeployment\Templates\SampleLogOut.txt"  
  
### <a name="to-create-a-new-application"></a>新しいアプリケーションの作成  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、[BizTalk グループ] の順に展開します。  
  
3. 右クリックして**アプリケーション** をクリックし、**新規**します。  
  
4. **アプリケーション名**、型`SamplesTemplate`、 をクリックし、 **OK**。  
  
### <a name="to-add-the-scripts-to-the-application"></a>アプリケーションへのスクリプトの追加  
  
1.  先ほど作成した SamplesTemplate アプリケーションのフォルダーを展開し、右クリックして**リソース**左側のウィンドウでします。  
  
2.  をポイント**追加**クリック**処理前のスクリプト**します。  
  
3.  クリックして**追加**SamplePreProcessing.bat を参照します。  
  
4.  ファイルを選択し、をクリックして**オープン**します。  
  
5.  **ファイルの種類**、 をクリックして**System.BizTalk:PreprocessingScript**、 をクリックし、 **OK**。  
  
     SamplePreProcessing.bat が追加されて、アプリケーションのリソース フォルダーに表示されます。  
  
6.  リソースをもう一度右クリックし、[**追加**、] をクリックし、**処理後のスクリプト**します。  
  
7.  クリックして**追加**SamplePostProcessing.bat を参照します。  
  
8.  ファイルを選択し、をクリックして**オープン**します。  
  
9. **ファイルの種類**、 をクリックして**System.BizTalk:PostprocessingScript**、 をクリックし、 **OK**。  
  
     SamplePostProcessing.bat が追加されて、アプリケーションのリソース フォルダーに表示されます。  
  
### <a name="to-export-an-msi-file"></a>.msi ファイルのエクスポート  
  
1.  BizTalk Server 管理コンソールで、SamplesTemplate アプリケーションを右クリックして**エクスポート**、 をクリックし、 **MSI ファイル**します。  
  
2.  エクスポート ウィザードのページへようこそ、をクリックして**次**します。  
  
3.  リソースの選択 ページで、次のようにクリックします。**次**します。  
  
4.  IIS ホストの指定 ページで、次のようにクリックします。**次**します。  
  
5.  依存関係 ページで、次のようにクリックします。**次**します。  
  
6.  変換先 ページで**送信先アプリケーション名**アプリケーション名を入力します。  
  
7.  **を生成する MSI ファイル**、MSI ファイルの完全なパスを入力し、クリックして**エクスポート**します。 例: C:\MSI\SamplesTemplate.msi  
  
8.  [概要] ページで、次のようにクリックします。**完了**します。  
  
### <a name="delete-the-application"></a>アプリケーションの削除  
  
-   BizTalk Server 管理コンソールで、SamplesTemplate アプリケーションを右クリックし、**削除**します。  
  
### <a name="to-import-the-msi-file"></a>.msi ファイルのインポート  
  
1.  右クリックし、BizTalk Server 管理コンソールで**アプリケーション**、 をポイント**インポート**、 をクリックし、 **MSI ファイル**。  
  
2.  インポート ウィザードのページへようこそ で**インポートする MSI ファイル**、以前エクスポートされたをクリックした .msi ファイルのパスを入力**次**します。 かどうか必要に応じてを参照できます、MSI ファイルをクリックして、 **(...)** ボタンをクリックします。  
  
3.  アプリケーションの設定 ページで、**アプリケーション名**ドロップダウン リストで、アプリケーション名を選択します。  
  
4.  **への参照を追加できるアプリケーション**存在する場合、参照を追加するアプリケーションを選択し、クリックして**次**します。  
  
5.  アプリケーションのターゲット環境の設定 ページで、次のようにクリックします。**次**します。  
  
    > [!NOTE]
    >  このサンプルではターゲット環境を指定する必要はありません。 この機能の背景については、[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)を参照してください。 バインド ファイルを追加する手順については、[アプリケーションにバインド ファイルを追加する方法](../core/how-to-add-a-binding-file-to-an-application2.md)を参照してください。  
  
6.  インポートの概要 ページで、概要情報が正しいことを確認し、**インポート**します。  
  
7.  [結果] ページで、次のようにクリックします。**完了**します。  
  
8.  スクリプトの実行時に作成されたログ ファイルを開き、インポート操作が記録されていることを確認します。  
  
### <a name="to-install-the-application"></a>アプリケーションをインストールするには  
  
1.  .msi ファイルをダブルクリックし、インストール ウィザードを実行します。  
  
2.  ログ ファイルを開き、ログ情報にインストール操作が追加されていることを確認します。  
  
### <a name="to-verify-that-the-scripts-functioned-correctly"></a>スクリプトが正常に機能したことの確認  
  
-   ログ ファイルを開き、指定した操作でスクリプトが実行されたことを確認します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開 (BizTalk Server Samples フォルダー)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)