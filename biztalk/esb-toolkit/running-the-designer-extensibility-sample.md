---
title: "デザイナーの機能拡張のサンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05ac3b50-5bf2-4566-8654-472391476d1f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b26c483568e1ceb05679d7548721c1cce818fde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-designer-extensibility-sample"></a>デザイナーの機能拡張のサンプルを実行します。
デザイナーの機能拡張のサンプルでは、2 つのサンプル エクステンダーを使用して、カスタム競合回避モジュールとの itinerary サービス、デザイン時構成オプションをようにする方法を示します。  
  
 **デザイナーの機能拡張のサンプルを実行するには**  
  
1.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]を起動します。  
  
2.  Visual Studio で、指す**新規**上、**ファイル** メニューをクリックして**プロジェクト**です。  
  
3.  C# クラス ライブラリ テンプレートの種類の選択**ItineraryLibrary**で、**名前**ボックスし、をクリックして**OK**です。  
  
4.  ソリューション エクスプ ローラーでプロジェクトを右クリックして、ItineraryLibrary をポイントし、**追加**、クリックして**新しい行程**です。  
  
5.  **名前**ボックスに、入力**TestItinerary**、ENTER キーを押します。  
  
6.  ツールボックスで、On ごとの傾斜増加モデル要素の場合をクリックし、デザイン画面にドラッグします。  
  
7.  ツールボックスで、行程サービス モデル要素の場合をクリックし、デザイン画面にドラッグします。  
  
8.  ツールボックスで、別の日程サービス モデル要素をクリックし、デザイン画面にドラッグします。  
  
9. ツールボックスで、Off ごとの傾斜増加モデル要素の場合をクリックし、デザイン画面にドラッグします。  
  
10. ツールボックスで、[コネクタ ツール] をクリックし、ドラッグ間の接続、 **OnRamp1**モデル要素と**ItineraryService1**モデル要素。  
  
11. ツールボックスで、[コネクタ ツール] をクリックし、ドラッグ間の接続、 **ItineraryService1**モデル要素と**ItineraryService2**モデル要素。  
  
12. ツールボックスで、[コネクタ ツール] をクリックし、ドラッグ間の接続、 **ItineraryService2**モデル要素と**OffRamp1**モデル要素。  
  
13. クリックして、 **OnRamp1**要素をモデル化し、[プロパティ] ウィンドウにエクステンダー プロパティを設定し、**入り口 ESB サービス拡張**です。  
  
14. 設定、 **BizTalk アプリケーション**プロパティを**Microsoft.Practices.ESB**です。  
  
15. 設定、**受信ポート**プロパティを**OnRamp.Itinerary**です。  
  
16. クリックして、 **ItinearyService1**要素をモデル化し、[プロパティ] ウィンドウで次のように設定します。、 **Extender**プロパティを**サンプル オーケストレーション行程サービス拡張**です。  
  
    > [!NOTE]
    >  これは、デザイナーの機能拡張のサンプルの一部としてインストールされているカスタム拡張機能です。 プロパティをオーケストレーションに基づく itinerary サービスに渡されるプロパティ バッグに追加することができます。  
  
17. 設定、 **OtherValue**プロパティを**1**です。  
  
18. 設定、 **ServiceName**プロパティを**Microsoft.Practices.ESB.Services.Routing**です。  
  
19. 設定、 **SomeValue**プロパティを**2**です。  
  
20. 右クリックし、**リゾルバー**のコレクション**ItineraryService1**、クリックして**新しいリゾルバーを追加**です。  
  
21. をクリックして**Resolver1**、し、[プロパティ] ウィンドウで次のように設定します。、**リゾルバーの実装**プロパティを**競合回避モジュールの拡張機能のサンプル**です。  
  
22. 設定、 **SomeResolverValue**プロパティを**テスト**に version プロパティを設定および**1.0**です。  
  
23. クリックして、 **ItineraryService2**要素をモデル化し、[プロパティ] ウィンドウで次のように設定します、**行程サービス エクステンダー**プロパティを**出口行程サービス拡張**。.  
  
24. 設定、**出口**プロパティを**OffRamp1 > 送信ハンドラー**です。  
  
25. クリックして、 **OffRamp1**要素をモデル化し、[プロパティ] ウィンドウで次のように設定します。、 **Extender**プロパティを**出口 ESB サービス拡張**です。  
  
26. 設定、 **BizTalk アプリケーション**プロパティを**GlobalBank.ESB**です。  
  
27. 設定、**送信ポート**プロパティを**DynamicResolutionOneWay**です。  
  
28. デザイン サーフェイスを右クリックし、をクリックして**モデルのエクスポート**です。  
  
29. 生成された XML を確認します。  
  
    > [!NOTE]
    >  通知、 **PropertyBag**要素およびプロパティが含まれています。 競合回避モジュールの接続文字列の例およびを確認の構成方法入力プロパティを基にします。