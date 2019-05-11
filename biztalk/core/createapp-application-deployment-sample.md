---
title: CreateApp (アプリケーションの展開サンプル) |Microsoft Docs
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
ms.openlocfilehash: ce2b895b11a8a2ad0fc6b863d3cd67a20c5c1007
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354178"
---
# <a name="createapp-application-deployment-sample"></a>CreateApp (アプリケーションの展開サンプル)
このトピックでは、CreateApp サンプルは、BTSTask コマンド ライン ツールを使用して、展開および BizTalk アプリケーションを展開解除する方法を使用する方法について説明します。 このサンプルに含まれるものなどのスクリプトを使用して、デプロイし、BizTalk アプリケーションの展開を解除し、夜間ビルド プロセスを自動化する可能性があります。  
  
> [!IMPORTANT]
>  いつでも、サイレント モードで実行する配置スクリプトを記述する必要があります。 そうでない場合は、ユーザー入力を必要とするダイアログ ボックスが表示されます。 ダイアログ ボックスを手動で閉じると、インポート プロセスがハングアップする可能性があるまで、展開プロセスを停止します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルには、アプリケーション展開タスクを自動化するスクリプトが含まれます。 これらのタスクを実行するには、BizTalk プロジェクトとファイルを生成するスクリプトを実行します。 2 つの BizTalk アプリケーションの .msi ファイル – すべてのアプリケーションで 1 つだけのアセンブリを含む、アプリケーションと別のアイテムを含む .msi ファイルを生成するスクリプトを実行します。 次に、BizTalk グループにアプリケーションをインポートして、ローカル コンピューター上にアプリケーションをインストールする .msi ファイルを使用するスクリプトを実行します。 インストール中には、処理前のスクリプトをアプリケーションに含まれるはアプリケーションによって使用されるフォルダーを作成し、ファイルにその操作を記録します。 最後に、削除し、アプリケーションをアンインストールするスクリプトを実行します。 アンインストール中は、アプリケーションに含まれる処理前のスクリプトは、ファイルとフォルダーのインストール時に作成されたを削除し、ファイルにその操作を記録します。  
  
 次に、このサンプルに含まれているスクリプトを示します。  
  
-   **Build.bat します。** キー ファイルが生成され、Visual Studio でプロジェクトをビルド、.dll ファイルに署名します。  
  
-   **CreateFullAndPartialMSI.bat.** 順序で、次の操作を受け取ります。  
  
    1.  BTSTask を使用して[AddApp コマンド](../core/addapp-command.md)アプリケーションを作成します。  
  
    2.  BTSTask を使用して[AddResource コマンド](../core/addresource-command.md)Build.bat によって生成されたや他のリソースをアプリケーション 3 つの BizTalk アセンブリに追加します。  
  
    3.  BTSTask を使用して[ExportApp コマンド](../core/exportapp-command.md)CreateApplicationSample.msi という名前のアプリケーションのアイテムを .msi ファイルにエクスポートします。  
  
    4.  BTSTask を使用して[ListApp コマンド](../core/listapp-command.md)をアプリケーションに含まれるアイテムの一覧が表示、AppManifest.xml という名前のアプリケーション マニフェストを生成します。  
  
    5.  BTSTask を使用して[ExportApp コマンド](../core/exportapp-command.md)CreateApplicationSamplePartial.msi という名前の .msi ファイルに、オーケストレーション アセンブリのみをエクスポートします。 この機能を使用するには、ResourceSpec パラメーターに ResourceSpecPartial.xml を提供します。 ResouceSpecPartial.xml が含まれているが、このサンプルで指定されている ResourceSpecComplete.xml の編集済みバージョンです。 このファイルは、オーケストレーション アセンブリのみへの参照を含むように編集されました。 このパラメーターで指定した場合、BTSTask は ResourceSpecPartial.xml ファイル – ここでは、オーケストレーション アセンブリで表示されているアイテムのみをエクスポートします。  
  
    6.  グループの BizTalk 管理データベースからアプリケーションを削除します。  
  
-   **CreateNewAppFromMSI.bat します。** CreateFullAndPartialMSI.bat によって生成された CreateApplicationSample.msi を使用して、BizTalk グループにアプリケーションをインポートするほか、ローカル コンピューターに CreateApplicationSample という名前のアプリケーションをインストールします。 インストール中に PreProcScript.bat が後の説明に従って、自動的に実行されます。  
  
-   **RemoveApp.bat.** 順序で、次の操作を受け取ります。  
  
    1.  BTSTask を使用して[RemoveApp コマンド](../core/removeapp-command.md)グループの BizTalk 管理データベースから CreateApplicationSample アプリケーションを削除します。  
  
    2.  BTSTask を使用して[UninstallApp コマンド](../core/uninstallapp-command.md)CreateApplicationSample アプリケーションをローカル コンピューターからアンインストールします。 インストール中に PreProcScript.bat はよう自動的に実行されます。  
  
-   **PreProcScript.bat します。** 次の操作を実行します。  
  
    -   たびに、実行、ユーザーが提供されているアセンブリの公開キー トークンを設定します。  
  
    -   アプリケーションのインストール中は、メッセージを格納する、CreateApplicationSample アプリケーションによって使用される次のフォルダーを作成します。  
  
         C:\CreateApplicationSample\Out  
  
         C:\CreateApplicationSample\In  
  
    -   アプリケーションのアンインストール中には、ファイルおよびインストール中に作成されたフォルダーを削除します。 インストール時に GAC にインストールされているすべてのアセンブリをグローバル アセンブリ キャッシュ (GAC) からアンインストールし、そのアクションをファイルにログインします。 GAC からアセンブリをアンインストールするにはユーザーによって提供される公開キー トークンを指します。  
  
    -   インストールおよびアンインストール中には、次の場所にログ ファイルを作成します。  
  
         C:\ScriptLog.txt  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 次のフォルダーにサンプル ファイルを検索できる*\<サンプル パス\>* \Application Deployment\\:  
  
-   CreateApp (フォルダ)  
  
    -   Build.bat  
  
    -   CreateFullAndPartialMSI.bat  
  
    -   CreateNewAppFromMSI.bat  
  
    -   RemoveApp.bat  
  
-   CreateApp\Bindings (Folder)  
  
    -   CreateApplicationSampleBindings.xml  
  
-   Createapp \dlls (フォルダ)  
  
    -   空  
  
-   Createapp \resourcespecs (フォルダ)  
  
    -   ResourceSpecPartial.xml  
  
    -   ResourceSpecComplete.xml  
  
-   CreateApp\Scripts (Folder)  
  
    -   PreProcScript.bat  
  
-   Createapp \helloapplicationdeployment (フォルダ)  
  
    -   HelloApplicationDeployment.suo  
  
    -   HelloApplicationDeployment.sln  
  
-   CreateApp\HelloApplicationDeployment\Maps (Folder)  
  
    -   POToInvoice.btm  
  
    -   Maps.btproj  
  
-   CreateApp\HelloApplicationDeployment\Orchestrations (Folder)  
  
    -   Orchestrations.btproj  
  
    -   HelloOrchestration.odx  
  
-   Createapp \helloapplicationdeployment\schemas (フォルダ)  
  
    -   Schemas.btproj  
  
    -   POSchema.xsd  
  
    -   InvoiceSchema.xsd  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルを使用するのにには、次の手順を使用します。  
  
### <a name="to-use-the-sample"></a>サンプルを使用するには  
  
1.  Build.bat を実行します。 これは、コマンドで、キー ファイルを生成、HelloApplicationDeployment フォルダーの下のプロジェクトのビルド、結果の .dll ファイルに署名、および、Dlls フォルダに行われますファイルを配置します。  
  
2.  Createapp \scripts フォルダにある PreProcScript.bat ファイルを開きます。 次のコード行で REM を削除し、アセンブリの公開キー トークンを提供します。  
  
     **REM 設定 PublicKeyToken =**  
  
     例:  
  
     **set PublicKeyToken=1234a5b6c1234567**  
  
3.  CreateFullAndPartialMSI.bat を実行します。 これにより、CreateApplicationSample.msi と CreateApplicationSamplePartial.msi 2 つのアプリケーション .msi ファイルが作成されます。  
  
4.  CreateNewAppFromMSI.bat を実行します。 これにより、CreateApplicationSample アプリケーションを BizTalk グループにインポートし、ローカル コンピューターにインストールします。  
  
5.  スクリプトがインストール アクションを記録することを確認する c:\scriptlog.txt にある、スクリプト ログ ファイルを確認します。  
  
6.  BizTalk Server 管理コンソールと追加と削除 の両方に、CreateApplicationSample アプリケーションが表示されることを確認します。  
  
7.  RemoveApp.bat を実行します。 これは、CreateApplicationSample が BizTalk 管理データベースから削除し、ローカル コンピューターからアンインストールされます。  
  
8.  スクリプトがアンインストール アクションを記録することを確認する c:\scriptlog.txt にある、スクリプト ログ ファイルを確認します。 インストール時に以前では、ログに記録するインストール アクションの後に出現する必要があります。  
  
9. BizTalk Server 管理コンソールまたは追加と削除 で、CreateApplicationSample アプリケーションが表示されないことを確認します。  
  
10. インストール中に作成されたフォルダーが削除されたことを確認します。  
  
11. アセンブリが GAC からアンインストールされていることを確認します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開 (BizTalk Server Samples フォルダー)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)