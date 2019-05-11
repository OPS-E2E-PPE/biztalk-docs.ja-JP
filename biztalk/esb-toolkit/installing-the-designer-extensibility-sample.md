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
ms.openlocfilehash: ad1a88c7f497d236a8e11456cfbc48de45494e1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295126"
---
# <a name="installing-the-designer-extensibility-sample"></a><span data-ttu-id="9c122-102">デザイナー機能拡張サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9c122-102">Installing the Designer Extensibility Sample</span></span>
<span data-ttu-id="9c122-103">このセクションでは、デザイナーの機能拡張サンプルをインストールするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9c122-103">This section describes the process for installing the Designer Extensibility sample.</span></span> <span data-ttu-id="9c122-104">サンプルをインストールする必要があります[をインストールして、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)と[をインストールして、動的解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)インストールしてこのサンプルを使用する前にします。</span><span class="sxs-lookup"><span data-stu-id="9c122-104">You must install the samples in [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) and [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) before you install and use this sample.</span></span>  

 <span data-ttu-id="9c122-105">**デザイナーの機能拡張サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="9c122-105">**To install the Designer Extensibility sample**</span></span>  

1. <span data-ttu-id="9c122-106">Windows エクスプ ローラーで開くフォルダーの \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample、インストールされている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルの場合と、という名前の Microsoft Visual Studio ソリューション ファイルを開きますExtenders.Itinerary.OrchestrationSample.sln します。</span><span class="sxs-lookup"><span data-stu-id="9c122-106">In Windows Explorer, open the folder \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Microsoft Visual Studio solution file named Extenders.Itinerary.OrchestrationSample.sln.</span></span>  

2. <span data-ttu-id="9c122-107">Visual Studio で、次のようにクリックします。**ソリューションのビルド**上、**ビルド**メニュー。</span><span class="sxs-lookup"><span data-stu-id="9c122-107">In Visual Studio, click **Build Solution** on the **Build** menu.</span></span>  

3. <span data-ttu-id="9c122-108">Visual Studio を閉じます。</span><span class="sxs-lookup"><span data-stu-id="9c122-108">Close Visual Studio.</span></span>  

4. <span data-ttu-id="9c122-109">Windows エクスプ ローラーで開くフォルダーの \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample、インストールされている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルの場合と、という名前の Visual Studio ソリューション ファイルを開きますExtenders.Resolvers.ResolverSample.sln します。</span><span class="sxs-lookup"><span data-stu-id="9c122-109">In Windows Explorer, open the folder \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Visual Studio solution file named Extenders.Resolvers.ResolverSample.sln.</span></span>  

5. <span data-ttu-id="9c122-110">Visual Studio で、次のようにクリックします。**ソリューションのビルド**上、**ビルド**メニュー。</span><span class="sxs-lookup"><span data-stu-id="9c122-110">In Visual Studio, click **Build Solution** on the **Build** menu.</span></span>  

6. <span data-ttu-id="9c122-111">Visual Studio を閉じます。</span><span class="sxs-lookup"><span data-stu-id="9c122-111">Close Visual Studio.</span></span>  

7. <span data-ttu-id="9c122-112">Windows エクスプ ローラーでは、旅行プラン デザイナーのインストール パスの下 \Lib フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="9c122-112">In Windows Explorer, open the \Lib folder under the Itinerary Designer install path.</span></span>  

8. <span data-ttu-id="9c122-113">上記の手順で構築された Visual Studio ソリューションの \bin\Debug フォルダーからには、\Lib のディレクトリに Extenders.Resolvers.ResolverSample.dll および Extenders.Itinerary.OrchestrationSample.dll ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9c122-113">From the \bin\Debug folders of the Visual Studio solutions built in the preceding steps, copy the files Extenders.Resolvers.ResolverSample.dll and Extenders.Itinerary.OrchestrationSample.dll to the \Lib directory.</span></span>
