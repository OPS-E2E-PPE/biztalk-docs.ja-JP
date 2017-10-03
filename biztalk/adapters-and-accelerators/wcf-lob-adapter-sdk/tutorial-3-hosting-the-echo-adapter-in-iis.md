---
title: "チュートリアル 3: IIS でエコー アダプターをホストしている |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3044cdea-e9b2-4cc2-b66e-799da1dfc07e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74addb5a69e8f17319a7019167eac1415a3a88d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-3-hosting-the-echo-adapter-in-iis"></a><span data-ttu-id="c20a1-102">チュートリアル 3: IIS でエコー アダプターをホストします。</span><span class="sxs-lookup"><span data-stu-id="c20a1-102">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>
<span data-ttu-id="c20a1-103">このチュートリアルで開発されたエコー アダプターをホストするために手順を説明します[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c20a1-103">This tutorial provides step-by-step instructions for hosting the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="c20a1-104">具体的には、手順の表示を使用して、アダプターでは、インターネット インフォメーション サービス (IIS) をホストする方法、[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c20a1-104">More specifically, the steps show how you can host the adapter in Internet Information Services (IIS) by using the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span></span> <span data-ttu-id="c20a1-105">Sharepoint ビジネス データ カタログ機能を使用しても、IIS でホストされるアダプターの EchoGreetings 操作を呼び出すし、Web パーツの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c20a1-105">You will also use the Business Data Catalog feature in SharePoint to call the EchoGreetings operation of the IIS-hosted adapter, and then display the results in a Web Part.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="c20a1-106">エコー アダプター、テスト コード、およびインストール スクリプトは、BizTalk のインストール ファイルに含まれる`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`または`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`です。</span><span class="sxs-lookup"><span data-stu-id="c20a1-106">The Echo Adapter, test code, and installation script are included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="c20a1-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c20a1-107">In This Section</span></span>  
  
-   [<span data-ttu-id="c20a1-108">手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="c20a1-108">Step 1: Use the Adapter Service Development Wizard to Create the Web Project</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)  
  
-   [<span data-ttu-id="c20a1-109">手順 2: Web プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="c20a1-109">Step 2: Deploy the Web Project</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)  
  
-   [<span data-ttu-id="c20a1-110">手順 3: アプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c20a1-110">Step 3: Create an Application Definition File</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)  
  
-   [<span data-ttu-id="c20a1-111">手順 4: アダプターにアクセスする Sharepoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c20a1-111">Step 4: Create a Sharepoint Application to Access the Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="c20a1-112">参照</span><span class="sxs-lookup"><span data-stu-id="c20a1-112">See Also</span></span>  
 <span data-ttu-id="c20a1-113">[チュートリアル 1: エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c20a1-113">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span></span>  
  [<span data-ttu-id="c20a1-114">WCF LOB アダプター SDK のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="c20a1-114">WCF LOB Adapter SDK Tutorials</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)