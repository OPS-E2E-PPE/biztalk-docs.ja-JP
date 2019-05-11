---
title: ESB スケジュール コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 379edc6a-7d53-4338-87a5-47b5238453a4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0e92c62f0ae764ed8123c578d7bc2975d4b10b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399797"
---
# <a name="the-esb-itinerary-component"></a><span data-ttu-id="7360d-102">ESB スケジュール コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7360d-102">The ESB Itinerary Component</span></span>
<span data-ttu-id="7360d-103">ESB スケジュール コンポーネントは、ESB オンランプ入り口に、メッセージと共に送信される SOAP ヘッダー コンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7360d-103">The ESB Itinerary component sets the context properties from the SOAP header sent along with the message to an ESB itinerary on-ramp.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="7360d-104">インストール</span><span class="sxs-lookup"><span data-stu-id="7360d-104">Installation</span></span>  
 <span data-ttu-id="7360d-105">ESB コアを自動的にインストールするインストール、**行程**BizTalk Server パイプライン コンポーネント フォルダー内のパイプライン コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="7360d-105">Installing the ESB Core automatically installs the **Itinerary** pipeline component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="7360d-106">しくみ</span><span class="sxs-lookup"><span data-stu-id="7360d-106">How It Works</span></span>  
 <span data-ttu-id="7360d-107">ESB スケジュール コンポーネントは、受信パイプラインにのみ配置できる Microsoft BizTalk パイプライン コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="7360d-107">The ESB Itinerary component is a Microsoft BizTalk pipeline component that can reside only in a receive pipeline.</span></span> <span data-ttu-id="7360d-108">SOAP メッセージのヘッダーまたはプロパティとしてメッセージ コンテキストにコンポーネントの設定のいずれかから値を昇格します。</span><span class="sxs-lookup"><span data-stu-id="7360d-108">It promotes values from either SOAP message headers or component settings into the message context as properties.</span></span> <span data-ttu-id="7360d-109">提供される日程 Web サービスで SOAP ヘッダーの昇格の例が見つかります[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7360d-109">You can find an example of promoting SOAP headers in the Itinerary On-Ramp Web services provided with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="7360d-110">これらの Web サービス、コントラクトの一部として SOAP ヘッダーを公開して、クライアント アプリケーションは、ヘッダーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7360d-110">These Web services expose SOAP headers as part of their contracts, and client applications must set the headers.</span></span> <span data-ttu-id="7360d-111">コンポーネントは、SOAP ヘッダー プロパティ (書き込み) を昇格し、値を読み取りますメッセージは、受信パイプラインでコンポーネントを通過して、メッセージ コンテキスト プロパティにすることです。</span><span class="sxs-lookup"><span data-stu-id="7360d-111">As the message passes through the component in a receive pipeline, the component reads the SOAP header values and promotes (writes) them to the message context properties.</span></span>  
  
## <a name="using-the-esb-itinerary-component"></a><span data-ttu-id="7360d-112">ESB スケジュール コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="7360d-112">Using the ESB Itinerary Component</span></span>  
 <span data-ttu-id="7360d-113">ESB スケジュール コンポーネントを受信パイプラインに追加し、受信場所のパイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7360d-113">You can add the ESB Itinerary component to a receive pipeline and then use the pipeline in a receive location.</span></span> <span data-ttu-id="7360d-114">コンポーネントには、SOAP ヘッダーの値またはコンポーネントの設定、受信メッセージのコンテキスト プロパティに自動的に昇格させます。</span><span class="sxs-lookup"><span data-stu-id="7360d-114">The component automatically promotes SOAP header values or component settings into the context properties of the incoming message.</span></span>  
  
 <span data-ttu-id="7360d-115">このコンポーネントを使用する方法の例は、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="7360d-115">For an example of how to use this component, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>