---
title: チュートリアル 3:IIS でエコー アダプターのホスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3044cdea-e9b2-4cc2-b66e-799da1dfc07e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb0bd41dd06c895e260a0f8bdc5a4f0c1ccb0d77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363023"
---
# <a name="tutorial-3-hosting-the-echo-adapter-in-iis"></a><span data-ttu-id="4ade0-102">チュートリアル 3:IIS でエコー アダプターをホストしています。</span><span class="sxs-lookup"><span data-stu-id="4ade0-102">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>
<span data-ttu-id="4ade0-103">このチュートリアルで開発されたエコー アダプターをホストの手順について説明します[チュートリアル 1。エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ade0-103">This tutorial provides step-by-step instructions for hosting the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="4ade0-104">具体的には、手順の表示を使用して、アダプターでは、インターネット インフォメーション サービス (IIS) をホストする方法、[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4ade0-104">More specifically, the steps show how you can host the adapter in Internet Information Services (IIS) by using the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span></span> <span data-ttu-id="4ade0-105">SharePoint のビジネス データ カタログ機能を使用しても、IIS でホストされるアダプターの EchoGreetings 操作の呼び出しを Web パーツで結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="4ade0-105">You will also use the Business Data Catalog feature in SharePoint to call the EchoGreetings operation of the IIS-hosted adapter, and then display the results in a Web Part.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="4ade0-106">エコー アダプター、テスト コード、およびインストール スクリプトは、BizTalk のインストール ファイルに含まれる`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`または`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`します。</span><span class="sxs-lookup"><span data-stu-id="4ade0-106">The Echo Adapter, test code, and installation script are included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="4ade0-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4ade0-107">In This Section</span></span>  
  
-   [<span data-ttu-id="4ade0-108">ステップ 1: アダプター サービス開発ウィザードを使用して Web プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="4ade0-108">Step 1: Use the Adapter Service Development Wizard to Create the Web Project</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)  
  
-   [<span data-ttu-id="4ade0-109">手順 2:Web プロジェクトを展開する</span><span class="sxs-lookup"><span data-stu-id="4ade0-109">Step 2: Deploy the Web Project</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)  
  
-   [<span data-ttu-id="4ade0-110">ステップ 3:アプリケーション定義ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4ade0-110">Step 3: Create an Application Definition File</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)  
  
-   [<span data-ttu-id="4ade0-111">手順 4:アダプターにアクセスするための SharePoint アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="4ade0-111">Step 4: Create a Sharepoint Application to Access the Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ade0-112">参照</span><span class="sxs-lookup"><span data-stu-id="4ade0-112">See Also</span></span>  
 <span data-ttu-id="4ade0-113">[チュートリアル 1:エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4ade0-113">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span></span>  
  [<span data-ttu-id="4ade0-114">WCF LOB アダプター SDK のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="4ade0-114">WCF LOB Adapter SDK Tutorials</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)