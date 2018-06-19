---
title: CreateApp (アプリケーションの展開サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, examples
- deploying, .msi file
- deploying, exporting
- .msi files, deploying
- examples, deploying
ms.assetid: 825627ee-21d0-4505-9df4-1dadc51335b6
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 842683d2eec04d77bad2b7726af0d687fae12884
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969712"
---
# <a name="createapp-application-deployment-sample"></a>CreateApp (アプリケーションの展開サンプル)
このトピックでは、CreateApp サンプルの使用方法について説明し、BTSTask コマンド ライン ツールを使用して BizTalk アプリケーションを展開および展開解除する方法を示します。 このサンプルに含まれるスクリプトを使用して夜間のビルド プロセスを自動化し、BizTalk アプリケーションを展開および展開解除できます。  
  
> [!IMPORTANT]
>  サイレント モードで実行する展開スクリプトを必ず記述します。 記述しないと、ユーザー入力を必要とするダイアログ ボックスが表示されます。 ダイアログ ボックスが手動で閉じられるまで展開プロセスが停止され、インポート プロセスが中断されます。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルには、アプリケーション展開タスクを自動化するスクリプトが含まれています。 これらのタスクを実行するには、BizTalk プロジェクトおよびファイルを生成するスクリプトを実行します。 次に、2 つの BizTalk アプリケーションの .msi ファイルを生成するスクリプトを実行します。これらのファイルは、アプリケーションのすべてのアイテムを含んでいるファイルと、アプリケーションの 1 つのアセンブリのみを含んでいるファイルです。 その後、.msi ファイルを使用してアプリケーションを BizTalk グループにインポートするスクリプトを実行し、アプリケーションをローカル コンピュータにインストールします。 インストール中には、処理前のスクリプトをアプリケーションに含まれてはアプリケーションによって使用されるフォルダーを作成し、ファイルにその操作を記録します。 最後に、アプリケーションを削除およびアンインストールするスクリプトを実行します。 アンインストール中は、アプリケーションに含まれている処理前のスクリプトは、ファイルとフォルダーのインストール時に作成されたを削除し、ファイルにその操作を記録します。  
  
 このサンプルに含まれるスクリプトは次のとおりです。  
  
-   **Build.bat です。** キー ファイルを生成し、Visual Studio 内にプロジェクトをビルドし、.dll ファイルに署名します。  
  
-   **CreateFullAndPartialMSI.bat です。** 以下の処理を順番に実行します。  
  
    1.  BTSTask を使用して[AddApp コマンド](../core/addapp-command.md)アプリケーションを作成します。  
  
    2.  BTSTask を使用して[AddResource コマンド](../core/addresource-command.md)Build.bat によって生成されたも他のリソースをアプリケーション 3 つの BizTalk アセンブリを追加します。  
  
    3.  BTSTask を使用して[ExportApp コマンド](../core/exportapp-command.md)アプリケーションのアイテムを .msi ファイルにエクスポートする CreateApplicationSample.msi という名前です。  
  
    4.  BTSTask を使用して[ListApp コマンド](../core/listapp-command.md)をすべてのアプリケーションに含まれているアイテムの一覧を表示する、AppManifest.xml という名前のアプリケーション マニフェストを生成します。  
  
    5.  BTSTask を使用して[ExportApp コマンド](../core/exportapp-command.md)CreateApplicationSamplePartial.msi という名前の .msi ファイルに、オーケストレーション アセンブリのみをエクスポートします。 これは、ResourceSpec パラメーターに ResourceSpecPartial.xml を指定することによって行われます。 ResouceSpecPartial.xml は、このサンプルに含まれている ResourceSpecComplete.xml の編集されたバージョンです。 このファイルは、オーケストレーション アセンブリのみの参照が含まれるように編集されています。 このパラメーターがある場合、BTSTask は ResourceSpecPartial.xml ファイル (この場合はオーケストレーション アセンブリ) にリストされているアイテムのみをエクスポートします。  
  
    6.  グループの BizTalk 管理データベースからアプリケーションを削除します。  
  
-   **CreateNewAppFromMSI.bat です。** CreateFullAndPartialMSI.bat によって生成された CreateApplicationSample.msi を使用して、ローカル コンピュータに CreateApplicationSample という名前のアプリケーションをインストールすると共に、BizTalk グループにアプリケーションをインポートします。 インストール中に、PreProcScript.bat は後の説明に従って、自動的に実行されます。  
  
-   **RemoveApp.bat です。** 以下の処理を順番に実行します。  
  
    1.  BTSTask を使用して[RemoveApp コマンド](../core/removeapp-command.md)グループの BizTalk 管理データベースから CreateApplicationSample アプリケーションを削除します。  
  
    2.  BTSTask を使用して[UninstallApp コマンド](../core/uninstallapp-command.md)をローカル コンピューターから、CreateApplicationSample アプリケーションをアンインストールします。 インストール中は、後で説明するように PreProcScript.bat が自動的に実行されます。  
  
-   **PreProcScript.bat です。** 次の処理を実行します。  
  
    -   実行のたびに、ユーザーに提供されたアセンブリの公開キー トークンを設定します。  
  
    -   アプリケーションのインストール中、CreateApplicationSample アプリケーションがメッセージを格納するために使用する次のフォルダを作成します。  
  
         C:\CreateApplicationSample\Out  
  
         C:\CreateApplicationSample\In  
  
    -   アプリケーションのアンインストール中、インストール中に作成されたファイルおよびフォルダを削除します。 インストール中にグローバル アセンブリ キャッシュ (GAC) にインストールされたアセンブリをアンインストールし、ファイルにアクションのログを記録します。 GAC からアセンブリをアンインストールするために、ユーザーが提供した公開キー トークンを参照します。  
  
    -   インストールおよびアンインストール中、次の場所にログ ファイルを作成します。  
  
         C:\ScriptLog.txt  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 次のフォルダーにサンプル ファイルを検索できる*\<サンプル パス\>* \Application 展開\\:  
  
-   CreateApp (フォルダ)  
  
    -   Build.bat  
  
    -   CreateFullAndPartialMSI.bat  
  
    -   CreateNewAppFromMSI.bat  
  
    -   RemoveApp.bat  
  
-   CreateApp\Bindings (フォルダ)  
  
    -   CreateApplicationSampleBindings.xml  
  
-   CreateApp\Dlls (フォルダ)  
  
    -   空  
  
-   CreateApp\ResourceSpecs (フォルダ)  
  
    -   ResourceSpecPartial.xml  
  
    -   ResourceSpecComplete.xml  
  
-   CreateApp\Scripts (フォルダ)  
  
    -   PreProcScript.bat  
  
-   CreateApp\HelloApplicationDeployment (フォルダ)  
  
    -   HelloApplicationDeployment.suo  
  
    -   HelloApplicationDeployment.sln  
  
-   CreateApp\HelloApplicationDeployment\Maps (フォルダ)  
  
    -   POToInvoice.btm  
  
    -   Maps.btproj  
  
-   CreateApp\HelloApplicationDeployment\Orchestrations (フォルダ)  
  
    -   Orchestrations.btproj  
  
    -   HelloOrchestration.odx  
  
-   CreateApp\HelloApplicationDeployment\Schemas (フォルダ)  
  
    -   Schemas.btproj  
  
    -   POSchema.xsd  
  
    -   InvoiceSchema.xsd  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 次の手順に従って、このサンプルを使用します。  
  
### <a name="to-use-the-sample"></a>サンプルを使用するには  
  
1.  Build.bat を実行します。 これにより、キー ファイルの生成、HelloApplicationDeployment フォルダでのプロジェクトのビルド、結果の .dll ファイルの署名、Dlls フォルダへの .dll ファイルの配置が行われます。  
  
2.  CreateApp\Scripts フォルダにある PreProcScript.bat ファイルを開きます。 次のコードで、REM を削除し、アセンブリの公開キー トークンを入力します。  
  
     **REM 設定 PublicKeyToken =**  
  
     例:  
  
     **設定 PublicKeyToken 1234a5b6c1234567 を =**  
  
3.  CreateFullAndPartialMSI.bat を実行します。 これにより、CreateApplicationSample.msi と CreateApplicationSamplePartial.msi の 2 つのアプリケーション .msi ファイルが作成されます。  
  
4.  CreateNewAppFromMSI.bat を実行します。 これにより、CreateApplicationSample アプリケーションが BizTalk グループにインポートされ、ローカル コンピュータにインストールされます。  
  
5.  C:\ScriptLog.txt にあるスクリプト ログ ファイルをチェックし、スクリプトによってインストール アクションのログが記録されたかどうかを確認します。  
  
6.  CreateApplicationSample アプリケーションが BizTalk Server 管理コンソールおよび [アプリケーションの追加と削除] に表示されているかどうかを確認します。  
  
7.  RemoveApp.bat を実行します。 これにより、CreateApplicationSample が BizTalk 管理データベースから削除され、ローカル コンピュータからアンインストールされます。  
  
8.  C:\ScriptLog.txt にあるスクリプト ログ ファイルをチェックし、スクリプトによってアンインストール アクションのログが記録されたかどうかを確認します。 このログは、インストール中に記録されたインストール アクションの後に表示されます。  
  
9. CreateApplicationSample アプリケーションが BizTalk Server 管理コンソールおよび [アプリケーションの追加と削除] に表示されていないことを確認します。  
  
10. インストール中に作成されたフォルダが削除されているかどうかを確認します。  
  
11. アセンブリが GAC からアンインストールされているかどうかを確認します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開 (BizTalk Server Samples フォルダ)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)