---
title: "例外処理サービスのサンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d69e720c-89e4-42c2-b4d0-31f0b865ab7f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dd7c87e84cf7e6e107fc110c611369d0407e003
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="running-the-exception-handling-service-sample"></a><span data-ttu-id="3763a-102">例外処理サービスのサンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3763a-102">Running the Exception Handling Service Sample</span></span>
<span data-ttu-id="3763a-103">例外処理サービスのサンプルでは、外部アプリケーションから、例外処理の ESB フレームワークにはエラーを送信するために、例外処理の Web サービスを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3763a-103">The Exception Handling Service sample demonstrates how to consume the Exception Handling Web Service in order to submit a fault into the ESB Exception Handling Framework from an external application.</span></span> <span data-ttu-id="3763a-104">このサンプルを実行するため、次の手順が必要です[例外管理のサンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="3763a-104">The following procedure for running this sample requires [Installing the Exception Management Samples](../esb-toolkit/installing-the-exception-management-samples.md).</span></span>  
  
 <span data-ttu-id="3763a-105">**例外処理サービス サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="3763a-105">**To run the Exception Handling Service sample**</span></span>  
  
1.  <span data-ttu-id="3763a-106">Windows エクスプ ローラーで、インストールされている、フォルダー \Source\Samples\ExceptionHandlingService を開き、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルを開き、ExceptionHandlingService.sln をという名前の Visual Studio ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="3763a-106">In Windows Explorer, open the folder \Source\Samples\ExceptionHandlingService, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Visual Studio solution file named ExceptionHandlingService.sln.</span></span>  
  
2.  <span data-ttu-id="3763a-107">Visual Studio で、[**デバッグの開始]**ツールバー。</span><span class="sxs-lookup"><span data-stu-id="3763a-107">In Visual Studio, click **Start Debugging** on the Toolbar.</span></span>  
  
3.  <span data-ttu-id="3763a-108">フォームを読み込みますが、をクリックして、**生成例外**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3763a-108">On the form that loads, click the **Generate Exception** button.</span></span>  
  
4.  <span data-ttu-id="3763a-109">Windows エクスプ ローラーで、フォルダー \Samples\Exception Handling\Test\Filedrop\All_Exceptions を開き、最新の Exceptions_ {GUID} .xml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3763a-109">In Windows Explorer, open the folder \Samples\Exception Handling\Test\Filedrop\All_Exceptions, and then open the most recent Exceptions_{GUID}.xml file.</span></span>  
  
5.  <span data-ttu-id="3763a-110">生成された例外の内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="3763a-110">Examine the contents of the generated exception.</span></span>  
  
 <span data-ttu-id="3763a-111">例外処理サービスのサンプルが、例外管理サービスを使用する方法に関する詳細については、次を参照してください。 [「例外の処理サービス サンプルの動作](../esb-toolkit/how-the-exception-handling-service-sample-works.md)です。</span><span class="sxs-lookup"><span data-stu-id="3763a-111">For more information about how the Exception Handling Service sample uses the Exception Management service, see [How the Exception Handling Service Sample Works](../esb-toolkit/how-the-exception-handling-service-sample-works.md).</span></span>