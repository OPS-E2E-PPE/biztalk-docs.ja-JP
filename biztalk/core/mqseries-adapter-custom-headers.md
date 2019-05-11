---
title: MQSeries アダプターのカスタム ヘッダー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, custom headers
ms.assetid: b0e18203-a33f-4d50-8483-396699cdff23
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 758b0bb33be70f681d4d7ef732e50555d6eca026
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323790"
---
# <a name="mqseries-adapter-custom-headers"></a><span data-ttu-id="e1d12-102">MQSeries アダプターのカスタム ヘッダー</span><span class="sxs-lookup"><span data-stu-id="e1d12-102">MQSeries Adapter Custom Headers</span></span>
<span data-ttu-id="e1d12-103">MQSeries メッセージで使用されるヘッダー構造、ために使用するカスタム ヘッダーを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1d12-103">Because of the header structures used in MQSeries messages, you must manage any custom headers you want to use.</span></span> <span data-ttu-id="e1d12-104">カスタム ヘッダーは、MQSeries ヘッダーの処理を妨げることを回避するために、メッセージ本文の一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1d12-104">Custom headers must be part of the message body to avoid interfering with the processing of the MQSeries headers.</span></span> <span data-ttu-id="e1d12-105">自動的に昇格されたプロパティの降格を避けることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1d12-105">Make sure that you avoid demoting any one of the automatically promoted properties.</span></span> <span data-ttu-id="e1d12-106">自動的に昇格されるプロパティの詳細については、次を参照してください。 [MQSeries アダプター プロパティ](../core/mqseries-adapter-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1d12-106">For more information about automatically promoted properties, see [MQSeries Adapter Properties](../core/mqseries-adapter-properties.md).</span></span>  
  
 <span data-ttu-id="e1d12-107">さらに、メッセージの本文にカスタム ヘッダーを組み込むことでは、追加の処理が必要です。</span><span class="sxs-lookup"><span data-stu-id="e1d12-107">In turn, the incorporation of custom headers in the message body requires additional processing.</span></span> <span data-ttu-id="e1d12-108">1 つのソリューションでは、アプリケーションのパイプラインでカスタム ヘッダーを処理します。</span><span class="sxs-lookup"><span data-stu-id="e1d12-108">One solution is to handle the custom headers in the pipelines of the application.</span></span> <span data-ttu-id="e1d12-109">受信パイプラインは、カスタム ヘッダー情報を抽出し、コンテキスト プロパティと情報を昇格させます。</span><span class="sxs-lookup"><span data-stu-id="e1d12-109">A receive pipeline extracts the custom header information and promotes the information as context properties.</span></span> <span data-ttu-id="e1d12-110">同様に、送信パイプラインでは、カスタム ヘッダーに対応するコンテキスト プロパティは、し、メッセージの本文のプロパティを降格させます。</span><span class="sxs-lookup"><span data-stu-id="e1d12-110">Similarly, the send pipeline takes the context properties corresponding to the custom header and demotes the properties in the body of the message.</span></span>  
  
 <span data-ttu-id="e1d12-111">パイプライン コンポーネントでカスタム ヘッダーの使用の例は、次を参照してください。 [MQSSendPipelineComponent (BizTalk Server サンプル)](../core/mqssendpipelinecomponent-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1d12-111">For an example of using custom headers in a pipeline component, see [MQSSendPipelineComponent (BizTalk Server Sample)](../core/mqssendpipelinecomponent-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d12-112">参照</span><span class="sxs-lookup"><span data-stu-id="e1d12-112">See Also</span></span>  
 [<span data-ttu-id="e1d12-113">MQSeries アダプター プロパティ</span><span class="sxs-lookup"><span data-stu-id="e1d12-113">MQSeries Adapter Properties</span></span>](../core/mqseries-adapter-properties.md)