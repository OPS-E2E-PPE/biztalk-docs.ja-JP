---
title: BizTalk Server Integration2 |Microsoft ドキュメント
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
ms.openlocfilehash: c47976873fcdd4efbb63bbceca653802cb8b9962
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007083"
---
# <a name="biztalk-server-integration"></a><span data-ttu-id="0bbf8-102">BizTalk Server の統合</span><span class="sxs-lookup"><span data-stu-id="0bbf8-102">BizTalk Server Integration</span></span>
<span data-ttu-id="0bbf8-103">AmberPoint は、カスタム BizTalk パイプライン コンポーネントとして、Microsoft BizTalk Server の統合製品をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="0bbf8-103">AmberPoint packages its Microsoft BizTalk Server integration product as a custom BizTalk pipeline component.</span></span> <span data-ttu-id="0bbf8-104">図 1 に示すように、Visual Studio を使用して、既存のカスタム パイプラインにこのコンポーネントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0bbf8-104">You can add this component to your existing custom pipelines using Visual Studio, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="0bbf8-105">![VisualStudio パイプライン](../esb-toolkit/media/ch9-visualstudiopipeline.jpg "Ch9 VisualStudioPipeline")</span><span class="sxs-lookup"><span data-stu-id="0bbf8-105">![VisualStudio Pipeline](../esb-toolkit/media/ch9-visualstudiopipeline.jpg "Ch9-VisualStudioPipeline")</span></span>  
  
 <span data-ttu-id="0bbf8-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="0bbf8-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="0bbf8-107">**送信パイプラインに AmberPoint コンポーネントをインストールします。**</span><span class="sxs-lookup"><span data-stu-id="0bbf8-107">**Installing the AmberPoint component into a send pipeline**</span></span>  
  
 <span data-ttu-id="0bbf8-108">さらに、AmberPoint 船 4 つ定義済みパイプライン既存に直接バインドできる受信場所および送信ポートが BizTalk 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="0bbf8-108">In addition, AmberPoint ships four predefined pipelines that you can bind directly to existing receive locations and send ports using the BizTalk Administration Console.</span></span> <span data-ttu-id="0bbf8-109">図 2 は、アダプターに、受信パイプラインのバインディングを示します。</span><span class="sxs-lookup"><span data-stu-id="0bbf8-109">Figure 2 shows the binding of a receive pipeline to an adapter.</span></span>  
  
 <span data-ttu-id="0bbf8-110">![AmberPoint のバインド](../esb-toolkit/media/ch9-bindingamberpoint.jpg "Ch9 BindingAmberPoint")</span><span class="sxs-lookup"><span data-stu-id="0bbf8-110">![Binding AmberPoint](../esb-toolkit/media/ch9-bindingamberpoint.jpg "Ch9-BindingAmberPoint")</span></span>  
  
 <span data-ttu-id="0bbf8-111">**図 2**</span><span class="sxs-lookup"><span data-stu-id="0bbf8-111">**Figure 2**</span></span>  
  
 <span data-ttu-id="0bbf8-112">**受信アダプターにパイプラインの AmberPoint のバインド**</span><span class="sxs-lookup"><span data-stu-id="0bbf8-112">**Binding an AmberPoint receive pipeline to an adapter**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bbf8-113">AmberPoint SOA 管理システム (SMS) の製品は、BizTalk Server と統合 AmberPoint, Inc. の製品です。</span><span class="sxs-lookup"><span data-stu-id="0bbf8-113">The AmberPoint SOA Management System (SMS) product is a product from AmberPoint, Inc. that integrates with BizTalk Server.</span></span> <span data-ttu-id="0bbf8-114">AmberPoint や、SOA ガバナンス製品に関する詳細については、次を参照してください。、 [AmberPoint](http://go.microsoft.com/fwlink/?LinkId=188561) Web サイトです。</span><span class="sxs-lookup"><span data-stu-id="0bbf8-114">For more information about AmberPoint and their SOA governance products, see the [AmberPoint](http://go.microsoft.com/fwlink/?LinkId=188561) Web site.</span></span>