---
title: "開発活動の前提条件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54c91405-f9a4-4676-b5c5-fe90b3b51b45
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbc79fd31e78581d98ecad34579958ff90f3b1e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="prerequisites-for-the-development-activities"></a>開発活動の前提条件
このセクションの一部として含まれている開発作業の手順を実行するように環境を準備する方法について説明、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。 開発作業の手順のいずれかの操作を行う前に、次のセットアップを完了します。  
  
## <a name="set-up-your-computer-to-perform-the-procedures-in-the-biztalk-esb-toolkit-development-activities"></a>BizTalk ESB Toolkit の開発作業の手順を実行するコンピューターを設定します。  
  
1.  インストールし、旅程サンプル アプリケーション、動的な解決サンプル アプリケーション、および複数の Web サービス サンプル アプリケーションを展開します。 インストールして、これらのアプリケーションの展開に関する詳細については、次を参照してください。 [BizTalk ESB Toolkit のサンプル アプリケーション](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)です。  
  
2.  UDDI 発行元のユーティリティを実行します。  
  
3.  開発用コンピューター上の Windows エクスプ ローラーで、次のパスを作成します。  
  
    -   C:\HowTos  
  
    -   C:\HowTos\Itineraries  
  
    -   C:\HowTos\DropFolder  
  
    -   C:\HowTos\Out  
  
4.  BizTalk Server サービス アカウントがあることを確認**フルコントロール**C:\HowTos ディレクトリ構造へのアクセス許可。  
  
5.  Microsoft BizTalk Server サービス アカウントがあることを確認**書き込み**C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out へのアクセス許可。  
  
6.  次のテスト メッセージを C:\HowTos フォルダーにコピーします。  
  
    -   C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.xml  
  
7.  C:\HowTos フォルダーでは、次の場所で見つかった、行程テスト用クライアント アプリケーションへのショートカットを作成します。  
  
    -   C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB です。Itinerary.Test\bin\Debug\ESB です。Itinerary.Test.exe  
  
## <a name="create-the-visual-studio-solution"></a>Visual Studio ソリューションを作成します。  
  
1.  Visual Studio で、[ファイル] メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
2.  **新しいプロジェクト**ダイアログ ボックスで、プロジェクトの種類 ペインで、をクリックして**Visual c#**、クリックして**クラス ライブラリ**テンプレート ペインでします。  
  
3.  **名前**ボックスに、入力**ItineraryLibrary**です。  
  
4.  **場所**ボックスに、入力**C:\HowTos**です。  
  
5.  選択、**ソリューションのディレクトリを作成**チェック ボックスをオンします。  
  
6.  **ソリューション名**ボックスに、入力**パターン**、クリックして**[ok]**ソリューションを作成します。  
  
7.  削除、 **Class1.cs**ファイルから、 **ItineraryLibrary**プロジェクト。