---
title: "ESB Itinerary コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 379edc6a-7d53-4338-87a5-47b5238453a4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80aa7c1ef4bc53ad2e2821eaf8dc4184777900a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-itinerary-component"></a><span data-ttu-id="e168e-102">ESB Itinerary コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e168e-102">The ESB Itinerary Component</span></span>
<span data-ttu-id="e168e-103">ESB 行程コンポーネントは、ESB itinerary 入り口に、メッセージと共に送信される SOAP ヘッダー コンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e168e-103">The ESB Itinerary component sets the context properties from the SOAP header sent along with the message to an ESB itinerary on-ramp.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="e168e-104">インストール</span><span class="sxs-lookup"><span data-stu-id="e168e-104">Installation</span></span>  
 <span data-ttu-id="e168e-105">ESB コアを自動的にインストールするとインストール、**行程**BizTalk Server パイプライン コンポーネント フォルダー内のパイプライン コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e168e-105">Installing the ESB Core automatically installs the **Itinerary** pipeline component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="e168e-106">しくみ</span><span class="sxs-lookup"><span data-stu-id="e168e-106">How It Works</span></span>  
 <span data-ttu-id="e168e-107">ESB 行程コンポーネントは、受信パイプラインにのみ存在でく Microsoft BizTalk パイプライン コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e168e-107">The ESB Itinerary component is a Microsoft BizTalk pipeline component that can reside only in a receive pipeline.</span></span> <span data-ttu-id="e168e-108">SOAP メッセージのヘッダーまたはプロパティとしてメッセージ コンテキストにコンポーネントの設定のいずれかの値を昇格します。</span><span class="sxs-lookup"><span data-stu-id="e168e-108">It promotes values from either SOAP message headers or component settings into the message context as properties.</span></span> <span data-ttu-id="e168e-109">提供される行程ランプで Web サービスで SOAP ヘッダーを昇格させるの例を見つけることができます[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e168e-109">You can find an example of promoting SOAP headers in the Itinerary On-Ramp Web services provided with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="e168e-110">これらの Web サービス、コントラクトの一部として SOAP ヘッダーを公開して、クライアント アプリケーションがヘッダーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e168e-110">These Web services expose SOAP headers as part of their contracts, and client applications must set the headers.</span></span> <span data-ttu-id="e168e-111">コンポーネントが、SOAP ヘッダーの値し、(書き込み) を昇格させますを読み取るように、メッセージは、受信パイプラインのコンポーネントを通過して、メッセージ コンテキスト プロパティにします。</span><span class="sxs-lookup"><span data-stu-id="e168e-111">As the message passes through the component in a receive pipeline, the component reads the SOAP header values and promotes (writes) them to the message context properties.</span></span>  
  
## <a name="using-the-esb-itinerary-component"></a><span data-ttu-id="e168e-112">ESB Itinerary コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e168e-112">Using the ESB Itinerary Component</span></span>  
 <span data-ttu-id="e168e-113">ESB 行程コンポーネントは、受信パイプラインに追加し、受信場所、パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e168e-113">You can add the ESB Itinerary component to a receive pipeline and then use the pipeline in a receive location.</span></span> <span data-ttu-id="e168e-114">コンポーネントは、SOAP ヘッダーの値または受信メッセージのコンテキスト プロパティにコンポーネントの設定を自動的に昇格させます。</span><span class="sxs-lookup"><span data-stu-id="e168e-114">The component automatically promotes SOAP header values or component settings into the context properties of the incoming message.</span></span>  
  
 <span data-ttu-id="e168e-115">このコンポーネントを使用する方法の例は、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="e168e-115">For an example of how to use this component, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>