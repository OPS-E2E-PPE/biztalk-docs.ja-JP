---
title: 展開して、アプリケーションのエクスポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4106a0a7-878d-4052-8eca-02d546233048
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70f3638d3679fd133289a36df74efec1fd020e7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305828"
---
# <a name="deploying-and-exporting-an-application"></a>展開して、アプリケーションのエクスポート
このセクションには、BizTalk アプリケーションの展開に必要な手順を実行する方法に関する詳細情報が含まれています。 このセクションのトピックでは、次のチェックリストをサポートします。  
  
- [チェックリスト:アプリケーションを展開する](../technical-guides/checklist-deploying-an-application.md)、開発環境でアプリケーションを配置、.msi ファイルにエクスポートし、.msi ファイルから運用環境にインポートする方法を示します。  
  
- [チェックリスト:別のアプリケーションへのバインドのエクスポート](../technical-guides/checklist-exporting-bindings-from-one-application-to-another.md)、開発または実稼働環境でいずれかの別のアプリケーションにアプリケーションからバインドをエクスポートする方法を示しています。  
  
  展開し、BizTalk アプリケーションの管理は、次のツールを使用できます。  
  
|                             ツール                             |                                                                                                                                                                                                                                                                                                                                                                                                                                 新しく使用する機能                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|            BizTalk Server 管理コンソール             | このグラフィカル ユーザー インターフェイスからは、すべての BizTalk アプリケーションの場合、次の展開と管理の操作を実行できます。<br /><br /> -インポート、インストール、およびエクスポート ウィザードを開始します。<br />-追加、アプリケーションの成果物を削除して、アプリケーションには、その他の変更を加える<br />-BizTalk アプリケーションの .msi ファイルを BizTalk Server を生成します。<br />-から .msi ファイルまたはアプリケーションを .msi ファイルから別の BizTalk グループにインポートするコンピュータにアプリケーションのインストール<br />-アプリケーションのバインドのバインド ファイルからインポート<br /><br /> 管理コンソールの詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](http://go.microsoft.com/fwlink/?LinkID=154689)(<http://go.microsoft.com/fwlink/?LinkID=154689>)。 |
|                  BTSTask コマンド ライン ツール                   |                                                                                                                                                                                                                                                                                                  コマンドラインから多くのアプリケーション管理タスクを実行することができます。 コマンド ライン ツールの詳細については、次を参照してください。 [BTSTask コマンド ライン リファレンス](http://go.microsoft.com/fwlink/?LinkId=155003)(<http://go.microsoft.com/fwlink/?LinkId=155003>)。                                                                                                                                                                                                                                                                                                   |
|              スクリプトとプログラミング Api              |                                                                                                                                                                                                                                                           作成し、多くのアプリケーション管理タスクを自動化するスクリプトを実行する Microsoft Windows Management Instrumentation (WMI) や BizTalk エクスプ ローラー オブジェクト モデルを使用することができます。 スクリプトの詳細については、次を参照してください。 [WMI クラスの参照](http://go.microsoft.com/fwlink/?LinkId=155004)(<http://go.microsoft.com/fwlink/?LinkId=155004>)。                                                                                                                                                                                                                                                           |
| [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)] |                                                                                                                                                                                                Visual Studio で BizTalk アセンブリを作成、デプロイ コマンドを使用して、BizTalk アプリケーションに自動的に展開、および BizTalk エクスプ ローラーを使用して、Visual Studio 内からアプリケーションのアイテムを構成することができます。 Visual Studio 内での操作の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/?LinkID=154719)(<http://go.microsoft.com/fwlink/?LinkID=154719>)。                                                                                                                                                                                                |
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アプリケーションの削除](../technical-guides/creating-an-application.md)  
  
-   [アセンブリの展開](../technical-guides/deploying-an-assembly.md)  
  
-   [アイテムのアプリケーションへの追加](../technical-guides/adding-artifacts-to-an-application.md)  
  
-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)  
  
-   [バインド ファイルにバインドをエクスポートする方法](../technical-guides/how-to-export-bindings-to-a-binding-file.md)  
  
-   [バインド ファイルを Application1 を追加する方法](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)  
  
-   [.msi ファイルのアプリケーションをインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)  
  
-   [アプリケーションをインストールする方法](../technical-guides/how-to-install-an-application.md)  
  
-   [バインド ファイルからバインドをインポートする方法](../technical-guides/how-to-import-bindings-from-a-binding-file.md)  
  
-   [アプリケーションのテスト](../technical-guides/testing-an-application.md)  
  
-   [アプリケーションに参照を追加する方法](../technical-guides/how-to-add-a-reference-to-an-application.md)