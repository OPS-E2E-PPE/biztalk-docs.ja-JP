---
title: "展開して、アプリケーションのエクスポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4106a0a7-878d-4052-8eca-02d546233048
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b33762f50f32dda58f1453fde7be37bc959af6aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-and-exporting-an-application"></a>展開して、アプリケーションをエクスポートします。
このセクションには、BizTalk アプリケーションの展開に必要な手順を実行する方法に関する詳細情報が含まれています。 このセクションのトピックでは、次のチェックリストをサポートします。  
  
-   [チェックリスト: アプリケーションを展開する](../technical-guides/checklist-deploying-an-application.md)、開発環境でアプリケーションを展開、.msi ファイルにエクスポートし、.msi ファイルから実稼働環境にインポートする方法が示されます。  
  
-   [チェックリスト: から別のアプリケーションへのバインドのエクスポート](../technical-guides/checklist-exporting-bindings-from-one-application-to-another.md)、いずれかで他のアプリケーションにアプリケーションからバインドをエクスポートする方法、開発環境または運用環境が示されます。  
  
 次のツールを使用して、展開および BizTalk アプリケーションを管理することができます。  
  
|ツール|新しく使用する機能|  
|----------|---------|  
|BizTalk Server 管理コンソール|このグラフィカル ユーザー インターフェイスからすべての BizTalk アプリケーションの場合、次の展開と管理の操作を行うことができます。<br /><br /> -インポート、インストール、およびエクスポート ウィザードを開始します。<br />-追加、アプリケーションのアイテムを削除して、アプリケーションにその他の変更を加える<br />生成する BizTalk アプリケーションの .msi ファイルを BizTalk Server<br />.Msi ファイルからコンピューターにアプリケーションのインストールや、アプリケーションを .msi ファイルから別の BizTalk グループにインポートします。<br />-バインド ファイルからアプリケーションのバインドをインポートします。<br /><br /> 管理コンソールの詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](http://go.microsoft.com/fwlink/?LinkID=154689)(http://go.microsoft.com/fwlink/?LinkID=154689)。|  
|BTSTask コマンド ライン ツール|コマンドラインから多くのアプリケーション管理タスクを実行することができます。 コマンド ライン ツールの詳細については、次を参照してください。 [BTSTask コマンド ライン リファレンス](http://go.microsoft.com/fwlink/?LinkId=155003)(http://go.microsoft.com/fwlink/?LinkId=155003)。|  
|スクリプト API とプログラミング API|Microsoft Windows Management Instrumentation (WMI) や BizTalk エクスプローラー オブジェクト モデルを使用して、多くのアプリケーション管理タスクを自動化するスクリプトを作成および実行することができます。 スクリプト作成の詳細については、次を参照してください。 [WMI クラス参照](http://go.microsoft.com/fwlink/?LinkId=155004)(http://go.microsoft.com/fwlink/?LinkId=155004)。|  
|[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]|Visual Studio で BizTalk アセンブリを作成、BizTalk アプリケーションに自動的に展開する展開コマンドを使用して、および BizTalk エクスプ ローラーを使用して、Visual Studio 内からアプリケーションのアイテムを構成することができます。 Visual Studio 内での作業の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アプリケーションを作成します。](../technical-guides/creating-an-application.md)  
  
-   [アセンブリを展開します。](../technical-guides/deploying-an-assembly.md)  
  
-   [成果物をアプリケーションに追加します。](../technical-guides/adding-artifacts-to-an-application.md)  
  
-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)  
  
-   [バインドをバインド ファイルにエクスポートする方法](../technical-guides/how-to-export-bindings-to-a-binding-file.md)  
  
-   [バインド ファイルをアプリケーション 1 に追加する方法](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)  
  
-   [アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)  
  
-   [アプリケーションをインストールする方法](../technical-guides/how-to-install-an-application.md)  
  
-   [バインド ファイルからバインドをインポートする方法](../technical-guides/how-to-import-bindings-from-a-binding-file.md)  
  
-   [アプリケーションのテスト](../technical-guides/testing-an-application.md)  
  
-   [アプリケーションへの参照を追加する方法](../technical-guides/how-to-add-a-reference-to-an-application.md)