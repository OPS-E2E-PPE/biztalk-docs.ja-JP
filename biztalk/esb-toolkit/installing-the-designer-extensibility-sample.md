---
title: デザイナー機能拡張サンプルをインストールする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eba13a4a-1b87-4268-af91-29af3a5bc5ef
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7068f86f3e6be2cd71741a6afe5f2438ac3800b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985715"
---
# <a name="installing-the-designer-extensibility-sample"></a>デザイナー機能拡張サンプルをインストールします。
このセクションでは、デザイナーの機能拡張サンプルをインストールするプロセスについて説明します。 サンプルをインストールする必要があります[をインストールして、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)と[をインストールして、動的解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)インストールしてこのサンプルを使用する前にします。  

 **デザイナーの機能拡張サンプルをインストールするには**  

1. Windows エクスプ ローラーで開くフォルダーの \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample、インストールされている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルの場合と、という名前の Microsoft Visual Studio ソリューション ファイルを開きますExtenders.Itinerary.OrchestrationSample.sln します。  

2. Visual Studio で、次のようにクリックします。**ソリューションのビルド**上、**ビルド**メニュー。  

3. Visual Studio を閉じます。  

4. Windows エクスプ ローラーで開くフォルダーの \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample、インストールされている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルの場合と、という名前の Visual Studio ソリューション ファイルを開きますExtenders.Resolvers.ResolverSample.sln します。  

5. Visual Studio で、次のようにクリックします。**ソリューションのビルド**上、**ビルド**メニュー。  

6. Visual Studio を閉じます。  

7. Windows エクスプ ローラーでは、旅行プラン デザイナーのインストール パスの下 \Lib フォルダーを開きます。  

8. 上記の手順で構築された Visual Studio ソリューションの \bin\Debug フォルダーからには、\Lib のディレクトリに Extenders.Resolvers.ResolverSample.dll および Extenders.Itinerary.OrchestrationSample.dll ファイルをコピーします。
