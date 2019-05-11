---
title: 例外処理サービス サンプルを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d69e720c-89e4-42c2-b4d0-31f0b865ab7f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17a1460b1248aa64ba043e8e6c01a66dc6215490
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242849"
---
# <a name="running-the-exception-handling-service-sample"></a><span data-ttu-id="d2ecc-102">例外処理サービス サンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="d2ecc-102">Running the Exception Handling Service Sample</span></span>
<span data-ttu-id="d2ecc-103">例外処理サービス サンプルでは、外部アプリケーションから、例外処理の ESB フレームワークにエラーを送信するには、例外処理の Web サービスを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d2ecc-103">The Exception Handling Service sample demonstrates how to consume the Exception Handling Web Service in order to submit a fault into the ESB Exception Handling Framework from an external application.</span></span> <span data-ttu-id="d2ecc-104">このサンプルを実行するには、次の手順が必要です[例外管理サンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2ecc-104">The following procedure for running this sample requires [Installing the Exception Management Samples](../esb-toolkit/installing-the-exception-management-samples.md).</span></span>  
  
 <span data-ttu-id="d2ecc-105">**例外処理サービス サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="d2ecc-105">**To run the Exception Handling Service sample**</span></span>  
  
1. <span data-ttu-id="d2ecc-106">Windows エクスプ ローラーで開くフォルダーの \Source\Samples\ExceptionHandlingService、インストールされている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルの場合と、ExceptionHandlingService.sln という名前の Visual Studio ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d2ecc-106">In Windows Explorer, open the folder \Source\Samples\ExceptionHandlingService, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Visual Studio solution file named ExceptionHandlingService.sln.</span></span>  
  
2. <span data-ttu-id="d2ecc-107">Visual Studio で、次のようにクリックします。**デバッグの開始**ツールバー。</span><span class="sxs-lookup"><span data-stu-id="d2ecc-107">In Visual Studio, click **Start Debugging** on the Toolbar.</span></span>  
  
3. <span data-ttu-id="d2ecc-108">フォームを読み込みますが、をクリックして、**生成例外**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2ecc-108">On the form that loads, click the **Generate Exception** button.</span></span>  
  
4. <span data-ttu-id="d2ecc-109">Windows エクスプ ローラーでフォルダー \Samples\Exception Handling\Test\Filedrop\All_Exceptions を開き、最新の Exceptions_ {GUID} .xml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d2ecc-109">In Windows Explorer, open the folder \Samples\Exception Handling\Test\Filedrop\All_Exceptions, and then open the most recent Exceptions_{GUID}.xml file.</span></span>  
  
5. <span data-ttu-id="d2ecc-110">生成された例外の内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="d2ecc-110">Examine the contents of the generated exception.</span></span>  
  
   <span data-ttu-id="d2ecc-111">例外処理サービス サンプルが、例外管理サービスを使用する方法についての詳細については、次を参照してください。 [、例外処理サービス サンプルのしくみ](../esb-toolkit/how-the-exception-handling-service-sample-works.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2ecc-111">For more information about how the Exception Handling Service sample uses the Exception Management service, see [How the Exception Handling Service Sample Works](../esb-toolkit/how-the-exception-handling-service-sample-works.md).</span></span>