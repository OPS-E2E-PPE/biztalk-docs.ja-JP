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
# <a name="installing-the-designer-extensibility-sample"></a><span data-ttu-id="58b84-102">デザイナーの機能拡張のサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="58b84-102">Installing the Designer Extensibility Sample</span></span>
<span data-ttu-id="58b84-103">このセクションでは、デザイナーの機能拡張のサンプルをインストールするためのプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="58b84-103">This section describes the process for installing the Designer Extensibility sample.</span></span> <span data-ttu-id="58b84-104">サンプルをインストールする必要があります[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)と[をインストールして、動的の解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)をインストールして、このサンプルを使用する前にします。</span><span class="sxs-lookup"><span data-stu-id="58b84-104">You must install the samples in [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) and [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) before you install and use this sample.</span></span>  
  
 <span data-ttu-id="58b84-105">**デザイナーの機能拡張のサンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="58b84-105">**To install the Designer Extensibility sample**</span></span>  
  
1.  <span data-ttu-id="58b84-106">Windows エクスプ ローラーで、インストールされている、フォルダー \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample を開き、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルを開き、という名前の Microsoft Visual Studio ソリューション ファイルExtenders.Itinerary.OrchestrationSample.sln です。</span><span class="sxs-lookup"><span data-stu-id="58b84-106">In Windows Explorer, open the folder \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Microsoft Visual Studio solution file named Extenders.Itinerary.OrchestrationSample.sln.</span></span>  
  
2.  <span data-ttu-id="58b84-107">[!INCLUDE[vs2010](../includes/vs2010-md.md)]、 をクリックして**ソリューションのビルド**上、**ビルド**メニュー。</span><span class="sxs-lookup"><span data-stu-id="58b84-107">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], click **Build Solution** on the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="58b84-108">Visual Studio を閉じます。</span><span class="sxs-lookup"><span data-stu-id="58b84-108">Close Visual Studio.</span></span>  
  
4.  <span data-ttu-id="58b84-109">Windows エクスプ ローラーで、インストールされている、フォルダー \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample を開き、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルを開き、という名前の Visual Studio ソリューション ファイルExtenders.Resolvers.ResolverSample.sln です。</span><span class="sxs-lookup"><span data-stu-id="58b84-109">In Windows Explorer, open the folder \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Visual Studio solution file named Extenders.Resolvers.ResolverSample.sln.</span></span>  
  
5.  <span data-ttu-id="58b84-110">[!INCLUDE[vs2010](../includes/vs2010-md.md)]、 をクリックして**ソリューションのビルド**上、**ビルド**メニュー。</span><span class="sxs-lookup"><span data-stu-id="58b84-110">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], click **Build Solution** on the **Build** menu.</span></span>  
  
6.  <span data-ttu-id="58b84-111">Visual Studio を閉じます。</span><span class="sxs-lookup"><span data-stu-id="58b84-111">Close Visual Studio.</span></span>  
  
7.  <span data-ttu-id="58b84-112">Windows エクスプ ローラーでは、行程デザイナーのインストール パスにある \Lib フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="58b84-112">In Windows Explorer, open the \Lib folder under the Itinerary Designer install path.</span></span>  
  
8.  <span data-ttu-id="58b84-113">上記の手順で作成した Visual Studio ソリューションの \bin\Debug フォルダーから Extenders.Resolvers.ResolverSample.dll および Extenders.Itinerary.OrchestrationSample.dll ファイルを \Lib ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="58b84-113">From the \bin\Debug folders of the Visual Studio solutions built in the preceding steps, copy the files Extenders.Resolvers.ResolverSample.dll and Extenders.Itinerary.OrchestrationSample.dll to the \Lib directory.</span></span>