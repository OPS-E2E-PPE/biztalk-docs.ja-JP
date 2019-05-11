---
title: BizTalk Server Integration2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 562a628d-52cb-4aae-8729-b5ba855bea5f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa771b568123a9aedaf7e6d53928a20a0c659270
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302322"
---
# <a name="biztalk-server-integration"></a><span data-ttu-id="300fd-102">BizTalk Server の統合</span><span class="sxs-lookup"><span data-stu-id="300fd-102">BizTalk Server Integration</span></span>
<span data-ttu-id="300fd-103">AmberPoint では、カスタム BizTalk パイプライン コンポーネントとして、Microsoft BizTalk Server 統合製品をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="300fd-103">AmberPoint packages its Microsoft BizTalk Server integration product as a custom BizTalk pipeline component.</span></span> <span data-ttu-id="300fd-104">図 1 に示すように、Visual Studio を使用して、既存のカスタム パイプラインにこのコンポーネントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="300fd-104">You can add this component to your existing custom pipelines using Visual Studio, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="300fd-105">![VisualStudio Pipeline](../esb-toolkit/media/ch9-visualstudiopipeline.jpg "Ch9-VisualStudioPipeline")</span><span class="sxs-lookup"><span data-stu-id="300fd-105">![VisualStudio Pipeline](../esb-toolkit/media/ch9-visualstudiopipeline.jpg "Ch9-VisualStudioPipeline")</span></span>  
  
 <span data-ttu-id="300fd-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="300fd-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="300fd-107">**送信パイプラインに AmberPoint コンポーネントをインストールします。**</span><span class="sxs-lookup"><span data-stu-id="300fd-107">**Installing the AmberPoint component into a send pipeline**</span></span>  
  
 <span data-ttu-id="300fd-108">さらに、AmberPoint 船 4 つ定義済みパイプライン既存に直接バインドできる受信場所と送信ポートが BizTalk 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="300fd-108">In addition, AmberPoint ships four predefined pipelines that you can bind directly to existing receive locations and send ports using the BizTalk Administration Console.</span></span> <span data-ttu-id="300fd-109">図 2 は、アダプター、受信パイプラインのバインドを示します。</span><span class="sxs-lookup"><span data-stu-id="300fd-109">Figure 2 shows the binding of a receive pipeline to an adapter.</span></span>  
  
 <span data-ttu-id="300fd-110">![AmberPoint のバインド](../esb-toolkit/media/ch9-bindingamberpoint.jpg "Ch9 BindingAmberPoint")</span><span class="sxs-lookup"><span data-stu-id="300fd-110">![Binding AmberPoint](../esb-toolkit/media/ch9-bindingamberpoint.jpg "Ch9-BindingAmberPoint")</span></span>  
  
 <span data-ttu-id="300fd-111">**図 2**</span><span class="sxs-lookup"><span data-stu-id="300fd-111">**Figure 2**</span></span>  
  
 <span data-ttu-id="300fd-112">**受信アダプターにパイプラインを AmberPoint のバインド**</span><span class="sxs-lookup"><span data-stu-id="300fd-112">**Binding an AmberPoint receive pipeline to an adapter**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="300fd-113">AmberPoint SOA 管理システム (SMS) 製品は、BizTalk Server と統合 AmberPoint, Inc. の製品です。</span><span class="sxs-lookup"><span data-stu-id="300fd-113">The AmberPoint SOA Management System (SMS) product is a product from AmberPoint, Inc. that integrates with BizTalk Server.</span></span> <span data-ttu-id="300fd-114">AmberPoint と SOA ガバナンス製品の詳細については、次を参照してください。、 [AmberPoint](http://go.microsoft.com/fwlink/?LinkId=188561) Web サイト。</span><span class="sxs-lookup"><span data-stu-id="300fd-114">For more information about AmberPoint and their SOA governance products, see the [AmberPoint](http://go.microsoft.com/fwlink/?LinkId=188561) Web site.</span></span>