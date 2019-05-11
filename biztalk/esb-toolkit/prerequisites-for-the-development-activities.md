---
title: 開発活動の前提条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c91405-f9a4-4676-b5c5-fe90b3b51b45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c81bd4acffed295de12e8b123451ae1eb77864f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301783"
---
# <a name="prerequisites-for-the-development-activities"></a>開発活動の前提条件
このセクションの一部として含まれる開発作業の手順を完了するための環境を準備する方法を説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。 開発作業の手順のいずれかの操作を行う前に、次のセットアップを完了します。  
  
## <a name="set-up-your-computer-to-perform-the-procedures-in-the-biztalk-esb-toolkit-development-activities"></a>BizTalk ESB Toolkit の開発アクティビティで手順を実行するコンピューターをセットアップします。  
  
1.  インストールし、スケジュールのサンプル アプリケーション、動的解決サンプル アプリケーション、および複数の Web サービスのサンプル アプリケーションをデプロイします。 インストールして、これらのアプリケーションの展開についての詳細については、次を参照してください。 [BizTalk ESB Toolkit のサンプル アプリケーション](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)します。  
  
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
  
7.  C:\HowTos フォルダーでは、次の場所にある、旅行プランのテスト用クライアント アプリケーションへのショートカットを作成します。  
  
    -   C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug\ESB.Itinerary.Test.exe  
  
## <a name="create-the-visual-studio-solution"></a>Visual Studio ソリューションを作成します。  
  
1.  Visual Studio で、ファイル メニューをポイント**新規**、 をクリックし、**プロジェクト**します。  
  
2.  **新しいプロジェクト** ダイアログ ボックスで、プロジェクトの種類 ペインで、をクリックして**Visual C#** 、 をクリックし、**クラス ライブラリ**テンプレート ペインでします。  
  
3.  **名前**ボックスに「 **ItineraryLibrary**します。  
  
4.  **場所**ボックスに「 **C:\HowTos**します。  
  
5.  選択、**ソリューションのディレクトリを作成**チェック ボックスをオンします。  
  
6.  **ソリューション名**ボックスに「**パターン**、順にクリックします**OK** 、ソリューションを作成しますします。  
  
7.  削除、 **Class1.cs**ファイルから、 **ItineraryLibrary**プロジェクト。