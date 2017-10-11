---
title: "デザイナーの機能拡張のサンプルのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eba13a4a-1b87-4268-af91-29af3a5bc5ef
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ae913ddbcdd0b87b6ebfc1a4f38790ecdb67bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-designer-extensibility-sample"></a>デザイナーの機能拡張のサンプルをインストールします。
このセクションでは、デザイナーの機能拡張のサンプルをインストールするためのプロセスについて説明します。 サンプルをインストールする必要があります[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)と[をインストールして、動的の解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)をインストールして、このサンプルを使用する前にします。  
  
 **デザイナーの機能拡張のサンプルをインストールするには**  
  
1.  Windows エクスプ ローラーで、インストールされている、フォルダー \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample を開き、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルを開き、という名前の Microsoft Visual Studio ソリューション ファイルExtenders.Itinerary.OrchestrationSample.sln です。  
  
2.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]、 をクリックして**ソリューションのビルド**上、**ビルド**メニュー。  
  
3.  Visual Studio を閉じます。  
  
4.  Windows エクスプ ローラーで、インストールされている、フォルダー \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample を開き、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルを開き、という名前の Visual Studio ソリューション ファイルExtenders.Resolvers.ResolverSample.sln です。  
  
5.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]、 をクリックして**ソリューションのビルド**上、**ビルド**メニュー。  
  
6.  Visual Studio を閉じます。  
  
7.  Windows エクスプ ローラーでは、行程デザイナーのインストール パスにある \Lib フォルダーを開きます。  
  
8.  上記の手順で作成した Visual Studio ソリューションの \bin\Debug フォルダーから Extenders.Resolvers.ResolverSample.dll および Extenders.Itinerary.OrchestrationSample.dll ファイルを \Lib ディレクトリにコピーします。