---
title: 公開された Web サービスの Web 設定を作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
- Web services, .msi file
- .msi files, Web services
ms.assetid: 77c86242-1d27-4d99-ae00-fe2614bc13ef
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87c5ec4fe61c8649fe951460917cfde8788f2e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249682"
---
# <a name="how-to-create-a-web-setup-for-your-published-web-service"></a>公開する Web サービスの Web セットアップを作成する方法
インストール パッケージを作成すると、実稼働環境での Web サービスの設定が容易になります。 この結果、.MSI ファイルが作成されます。  
  
### <a name="to-create-an-installation-package-to-produce-an-msi-file-using-visual-studio"></a>Visual Studio を使用して .MSI ファイルを作成するためにインストール パッケージを作成するには  
  
1.  公開する ASP.NET Web サービス プロジェクトを開きます。  
  
2.  ソリューション エクスプ ローラーでソリューション ノードを右クリックし、をクリックして**追加**、クリックして**新しいプロジェクト**です。  
  
3.  **新しいプロジェクトの追加**] ダイアログ ボックスで、**プロジェクトの種類**領域で、展開**その他のプロジェクトの種類**、展開**セットアップ/配置プロジェクト**、し、[ **Visual Studio インストーラー**です。 **テンプレート**領域で、 **Web セットアップ プロジェクト**です。  
  
4.  **名前**テキスト ボックス、Web セットアップ プロジェクトの名前を入力します。 ASP.NET Web サービス プロジェクトと同じ名前を使用してとをサフィックスとして"_Setup"を追加してをクリックして**OK**です。  
  
5.  ソリューション エクスプ ローラーで、新しく作成された Web セットアップ プロジェクト ノードを右クリックし、順にポイント**ビュー**、クリックして**ファイル システム**です。  
  
6.  **ファイル システム**ウィンドウを右クリックし、 **Web アプリケーション フォルダー**ノードをポイントして**追加**をクリックし、**プロジェクト出力**です。  
  
7.  **プロジェクト出力グループの追加**ダイアログ ボックスで、**プライマリ出力**と**コンテンツ ファイル**プロジェクトから ASP.NET Web サービスと、をクリックして**OK**.  
  
8.  ソリューション エクスプ ローラーで、展開、**依存関係の検出**Web セットアップ プロジェクトの下にあるノード。  
  
9. すべての依存関係を選択します。 **プロパティ**ウィンドウで、設定、**除外**プロパティを**True**です。  
  
10. Web セットアップ プロジェクトをビルドします。  
  
    > [!NOTE]
    >  Web セットアップ プロジェクトの作成の詳細についてを参照してください「方法を作成または追加 Web セットアップ プロジェクト」、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=62268](http://go.microsoft.com/fwlink/?LinkId=62268)です。  
  
## <a name="see-also"></a>参照  
 [非 Visual Studio コンピューターに公開された Web サービスを展開します。](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)