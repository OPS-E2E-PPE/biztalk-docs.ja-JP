---
title: SelectiveBindingImport (アプリケーションの展開サンプル) |Microsoft Docs
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
ms.openlocfilehash: 2b289e2c37797d10e8676f2d8d948090c9eb59fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005107"
---
# <a name="selectivebindingimport-application-deployment-sample"></a>SelectiveBindingImport (アプリケーションの展開サンプル)
このトピックでは、SelectiveBindingImport サンプルの使用方法について説明します。 このサンプル スクリプトを使用すると、1 つのアプリケーションをさまざまな展開先環境にインポートするときに、異なるバインドをそのアプリケーションに適用できます。 この方法は、ネットワーク共有に格納されているバインド ファイルからバインドをインポートするときに使用できます。  
  
> [!NOTE]
>  アプリケーションのインポート中にネットワーク共有からバインド ファイルを自動的にインポートする必要がない場合は、異なる展開先環境が指定されている各種のバインド ファイルをアプリケーションに追加できます。 アプリケーションをインポートするときは、環境を指定でき、その環境のバインドが自動的に適用されます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。  
  
 BizTalk アプリケーションは、通常は開発環境からテスト環境、ステージング環境、実稼働環境へと順番に移動されます。 通常は、各環境で異なるバインドが使用されます。 このサンプルを使用すると、各種の環境のバインドを次のように適用できます。  
  
1.  使用するバインド ファイルすべてをネットワーク共有に配置します。  
  
2.  アプリケーションのインポート中に特定の展開先環境用の正しいバインド ファイルをこの場所からインポートするアプリケーションに、処理後のスクリプトを追加します。 スクリプトは、ローカル コンピューターに設定された %ENVIRONMENT% という環境変数を読み取って、環境を検出します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、BizTalk アプリケーションの .msi ファイルに含まれている処理後のスクリプトを使用して、ネットワーク共有からバインド ファイルを選択的にインポートする方法を示しています。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 次のサンプル フォルダーとファイルを検索する*\<サンプル パス\>* \Application Deployment\SelectiveBindingImport:  
  
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
  
1. 実行**から Build.Bat、 *\<サンプル パス\>* \Application Deployment\CreateApp**ディレクトリ。 これで、次のファイルを作成、 *\<サンプル パス\>* \Application Deployment\CreateApp\Dlls フォルダー: Schemas.dll、Maps.dll、および Orchestrations.dll します。  
  
2. **アプリケーションを作成します。** BizTalk Server 管理コンソールで必要」の説明に従って、アプリケーションを作成[アプリケーションを作成する方法](../core/how-to-create-an-application.md)します。  
  
3. **.Dll ファイルが最初の手順で作成したアプリケーションを追加します。** 手順については、次を参照してください。[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。  
  
4. **次のように、環境変数を作成します。**  
  
   1.  [スタート] メニューを右クリックして**マイ コンピューター**クリック**プロパティ**します。  
  
   2.  **詳細**] タブで [**環境変数**。  
  
   3.  **ユーザー変数**セクションで、**新規**します。  
  
   4.  **変数名**、型**環境**します。  
  
   5.  **変数値**、環境の次の値の型:**開発**、**運用**、**ステージング**、または**テスト**します。 これらの値では、大文字と小文字が区別されます。  
  
5. クリックして**OK** 3 回です。  
  
6. **バインド ファイルをファイル システム上の場所にコピーします。** Develop、Test、Staging、および Production フォルダーの .xml バインド ファイルをファイル システム内の場所にコピーします。  
  
7. **処理後のスクリプトを編集します。** SelectiveBindings.bat を次のように編集します。  
  
   1.  **バインド ファイルの場所を指定します。** BINDINGS_LOC を含んでいる行で、REM を削除し、バインド ファイルのコピー先のパスを指定します。  
  
        例:  
  
        BINDINGS_LOC=C:\MyBindings  
  
   2.  **アプリケーション名を指定します。** APPLICATION_NAME を含んでいる行で、REM を削除し、バインドのインポート先のアプリケーション名を指定します。  
  
        例:  
  
        APPLICATION_Name=SelectiveBindingImport  
  
8. **処理後のスクリプトとしてアプリケーションにスクリプトを追加します。** 手順については、次を参照してください。[より前に追加する方法または処理後のスクリプトをアプリケーションに](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)します。  
  
9. **アプリケーションをエクスポートします。** 手順については、次を参照してください。 [BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。  
  
10. **アプリケーションを削除します。** 手順については、次を参照してください。 [BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)します。  
  
11. **アプリケーションをインポートします。** 手順については、次を参照してください。 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。 インポート先の環境を指定する必要はありません。  
  
12. **正しいバインド ファイルが適用されたことを確認します。** 確認するには、受信場所の説明フィールドを次のようにチェックします。  
  
    1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
    2. コンソール ツリーで、BizTalk グループ、BizTalk アプリケーション、および受信場所のフォルダーを展開します。  
  
    3. 右ペインで、受信場所の説明を表示します。  
  
13. **アプリケーションをインストールします。** 手順については、次を参照してください。 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開 (BizTalk Server Samples フォルダー)](../core/application-deployment-biztalk-server-samples-folder.md)   
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)