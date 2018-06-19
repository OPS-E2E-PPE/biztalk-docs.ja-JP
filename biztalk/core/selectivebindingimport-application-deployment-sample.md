---
title: SelectiveBindingImport (アプリケーションの展開サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding files, importing
- examples, applications
- binding files, examples
- examples, importing
- applications, binding files
- applications, examples
- applications, importing
- deploying, scripts
- examples, binding files
ms.assetid: 963bfc80-8cc4-4d90-96b4-e85ae04405cf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88e6a2aa02decf1e4ed9c4a9838077be0c3b97b2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974832"
---
# <a name="selectivebindingimport-application-deployment-sample"></a>SelectiveBindingImport (アプリケーションの展開サンプル)
このトピックでは、SelectiveBindingImport サンプルの使用方法について説明します。 このサンプル スクリプトを使用すると、1 つのアプリケーションをさまざまな展開先環境にインポートするときに、異なるバインドをそのアプリケーションに適用できます。 この方法は、ネットワーク共有に格納されているバインド ファイルからバインドをインポートするときに使用できます。  
  
> [!NOTE]
>  アプリケーションのインポート中にネットワーク共有からバインド ファイルを自動的にインポートする必要がない場合は、異なる展開先環境が指定されている各種のバインド ファイルをアプリケーションに追加できます。 アプリケーションをインポートするときは、環境を指定でき、その環境のバインドが自動的に適用されます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)です。  
  
 BizTalk アプリケーションは、通常は開発環境からテスト環境、ステージング環境、実稼働環境へと順番に移動されます。 通常は、各環境で異なるバインドが使用されます。 このサンプルを使用すると、各種の環境のバインドを次のように適用できます。  
  
1.  使用するバインド ファイルすべてをネットワーク共有に配置します。  
  
2.  アプリケーションのインポート中に特定の展開先環境用の正しいバインド ファイルをこの場所からインポートするアプリケーションに、処理後のスクリプトを追加します。 スクリプトは、ローカル コンピューターに設定された %ENVIRONMENT% という環境変数を読み取って、環境を検出します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、BizTalk アプリケーションの .msi ファイルに含まれている処理後のスクリプトを使用して、ネットワーク共有からバインド ファイルを選択的にインポートする方法を示しています。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 次のサンプル フォルダーとファイルを検索できます*\<サンプル パス\>* \Application Deployment\SelectiveBindingImport:  
  
-   Develop (フォルダー)  
  
    -   Dev.xml  
  
-   Production (フォルダー)  
  
    -   Production.xml  
  
-   Staging (フォルダー)  
  
    -   Staging.xml  
  
-   Test (フォルダー)  
  
    -   Test.xml  
  
-   SelectiveBindings.bat  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 次の手順に従って、このサンプルを実行します。  
  
### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  実行**から Build.Bat、 *\<サンプル パス\>* \Application Deployment\CreateApp**ディレクトリ。 これには、次のファイルが作成、 *\<サンプル パス\>* \Application Deployment\CreateApp\Dlls フォルダー: Schemas.dll、Maps.dll、および Orchestrations.dll です。  
  
2.  **アプリケーションを作成します。** BizTalk Server 管理コンソールには、アプリケーションを」の説明に従って作成[アプリケーションを作成する方法](../core/how-to-create-an-application.md)です。  
  
3.  **最初の手順で作成した .dll ファイル、アプリケーションに追加します。** 手順については、次を参照してください。 [BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。  
  
4.  **次のように、環境変数を作成します。**  
  
    1.  スタート メニューを右クリックして**マイ コンピューター**  をクリック**プロパティ**です。  
  
    2.  **詳細** タブで、をクリックして**環境変数**です。  
  
    3.  **ユーザー変数**セクションで、**新規**です。  
  
    4.  **変数名**、型**環境**です。  
  
    5.  **変数値**、環境内の次の値の型:**開発**、**運用**、**ステージング**、または**テスト**です。 これらの値では、大文字と小文字が区別されます。  
  
5.  をクリックして**OK** 3 回です。  
  
6.  **バインド ファイルをファイル システム上の場所にコピーします。** Develop、Test、Staging、および Production フォルダーの .xml バインド ファイルをファイル システム内の場所にコピーします。  
  
7.  **処理後のスクリプトを編集します。** SelectiveBindings.bat を次のように編集します。  
  
    1.  **バインド ファイルの場所を指定します。** BINDINGS_LOC を含んでいる行で、REM を削除し、バインド ファイルのコピー先のパスを指定します。  
  
         例:  
  
         BINDINGS_LOC=C:\MyBindings  
  
    2.  **アプリケーション名を指定します。** APPLICATION_NAME を含んでいる行で、REM を削除し、バインドのインポート先のアプリケーション名を指定します。  
  
         例:  
  
         APPLICATION_Name=SelectiveBindingImport  
  
8.  **処理後のスクリプトとしてアプリケーションにスクリプトを追加します。** 手順については、次を参照してください。[前に追加する方法または処理後のスクリプトをアプリケーションに](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)です。  
  
9. **アプリケーションをエクスポートします。** 手順については、次を参照してください。[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。  
  
10. **アプリケーションを削除します。** 手順については、次を参照してください。 [BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)です。  
  
11. **アプリケーションをインポートします。** 手順については、次を参照してください。[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。 インポート先の環境を指定する必要はありません。  
  
12. **正しいバインド ファイルが適用されていることを確認します。** 確認するには、受信場所の説明フィールドを次のようにチェックします。  
  
    1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
    2.  コンソール ツリーで、BizTalk グループ、BizTalk アプリケーション、および受信場所のフォルダーを展開します。  
  
    3.  右ペインで、受信場所の説明を表示します。  
  
13. **アプリケーションをインストールします。** 手順については、次を参照してください。[を BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)です。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開 (BizTalk Server Samples フォルダ)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)