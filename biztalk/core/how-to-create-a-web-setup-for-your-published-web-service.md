---
title: 公開する Web サービスの Web セットアップを作成する方法 |Microsoft Docs
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
ms.openlocfilehash: d894cba37b85c4f18fe2a05af33eb2f4e6e1981e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984387"
---
# <a name="how-to-create-a-web-setup-for-your-published-web-service"></a>公開する Web サービスの Web セットアップを作成する方法
インストール パッケージを作成すると、実稼働環境での Web サービスの設定が容易になります。 この結果、.MSI ファイルが作成されます。  
  
### <a name="to-create-an-installation-package-to-produce-an-msi-file-using-visual-studio"></a>Visual Studio を使用して .MSI ファイルを作成するためにインストール パッケージを作成するには  
  
1. 公開する ASP.NET Web サービス プロジェクトを開きます。  
  
2. ソリューション エクスプ ローラーでソリューション ノードを右クリックして**追加**、 をクリックし、**新しいプロジェクト**します。  
  
3. **新しいプロジェクトの追加**] ダイアログ ボックスで、**プロジェクトの種類**領域で、展開**その他のプロジェクトの種類**、展開**セットアップ/配置プロジェクト**、し、[ **Visual Studio インストーラー**します。 **テンプレート**領域で、 **Web セットアップ プロジェクト**します。  
  
4. **名前**テキスト ボックス、Web セットアップ プロジェクトの名前を入力します。 ASP.NET Web サービス プロジェクトと同じ名前を使用してとをサフィックスとして"_Setup"を追加および をクリックし、 **OK**します。  
  
5. ソリューション エクスプ ローラーで新しく作成された Web セットアップ プロジェクト ノードを右クリックし をポイント**ビュー**、 をクリックし、**ファイル システム**します。  
  
6. **ファイル システム**ウィンドウを右クリックし、 **Web アプリケーション フォルダー**ノードとポイント対**追加**、 をクリックし、**プロジェクト出力**します。  
  
7. **プロジェクト出力グループの追加**ダイアログ ボックスで、**プライマリ出力**と**コンテンツ ファイル**クリックしてから、ASP.NET Web サービス プロジェクトの **[ok]**.  
  
8. ソリューション エクスプ ローラーで、**依存関係の検出**Web セットアップ プロジェクトの下のノード。  
  
9. すべての依存関係を選択します。 **プロパティ**ウィンドウで、設定、**除外**プロパティを**True**します。  
  
10. Web セットアップ プロジェクトをビルドします。  
  
    > [!NOTE]
    >  Web セットアップ プロジェクトの作成に関する詳細については、「どのようにプロジェクトを作成または追加、Web セットアップ」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[ http://go.microsoft.com/fwlink/?LinkId=62268](http://go.microsoft.com/fwlink/?LinkId=62268)します。  
  
## <a name="see-also"></a>参照  
 [Visual Studio がインストールされていないコンピューターへの公開済み Web サービスの展開](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)