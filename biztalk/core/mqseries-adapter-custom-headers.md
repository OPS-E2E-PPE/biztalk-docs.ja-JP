---
title: MQSeries アダプターのカスタム ヘッダー |Microsoft ドキュメント
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
ms.openlocfilehash: 09a05b8c73cd7be84af01eb4465681816e429bc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263090"
---
# <a name="mqseries-adapter-custom-headers"></a><span data-ttu-id="8ba55-102">MQSeries アダプターのカスタム ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8ba55-102">MQSeries Adapter Custom Headers</span></span>
<span data-ttu-id="8ba55-103">MQSeries メッセージで使用されるヘッダー構造が原因で、使用するカスタム ヘッダーの管理が必要になります。</span><span class="sxs-lookup"><span data-stu-id="8ba55-103">Because of the header structures used in MQSeries messages, you must manage any custom headers you want to use.</span></span> <span data-ttu-id="8ba55-104">カスタム ヘッダーは、MQSeries ヘッダーの処理に影響を与えないように、メッセージ本文の一部にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ba55-104">Custom headers must be part of the message body to avoid interfering with the processing of the MQSeries headers.</span></span> <span data-ttu-id="8ba55-105">自動的に昇格されたプロパティは降格させないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8ba55-105">Make sure that you avoid demoting any one of the automatically promoted properties.</span></span> <span data-ttu-id="8ba55-106">自動的に昇格されるプロパティの詳細については、次を参照してください。 [MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="8ba55-106">For more information about automatically promoted properties, see [MQSeries Adapter Properties](../core/mqseries-adapter-properties.md).</span></span>  
  
 <span data-ttu-id="8ba55-107">上記の内容から、カスタム ヘッダーをメッセージ本文に組み込むには、追加処理が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ba55-107">In turn, the incorporation of custom headers in the message body requires additional processing.</span></span> <span data-ttu-id="8ba55-108">1 つの解決策は、カスタム ヘッダーをアプリケーションのパイプラインで処理することです。</span><span class="sxs-lookup"><span data-stu-id="8ba55-108">One solution is to handle the custom headers in the pipelines of the application.</span></span> <span data-ttu-id="8ba55-109">受信パイプラインでは、カスタム ヘッダー情報を抽出し、その情報をコンテキスト プロパティとして昇格させます。</span><span class="sxs-lookup"><span data-stu-id="8ba55-109">A receive pipeline extracts the custom header information and promotes the information as context properties.</span></span> <span data-ttu-id="8ba55-110">同様に、送信パイプラインでは、カスタム ヘッダーに対応するコンテキスト プロパティを取得し、それらのプロパティをメッセージ本文内に降格させます。</span><span class="sxs-lookup"><span data-stu-id="8ba55-110">Similarly, the send pipeline takes the context properties corresponding to the custom header and demotes the properties in the body of the message.</span></span>  
  
 <span data-ttu-id="8ba55-111">パイプライン コンポーネントでカスタム ヘッダーの使用の例は、次を参照してください。 [MQSSendPipelineComponent (BizTalk Server サンプル)](../core/mqssendpipelinecomponent-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="8ba55-111">For an example of using custom headers in a pipeline component, see [MQSSendPipelineComponent (BizTalk Server Sample)](../core/mqssendpipelinecomponent-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba55-112">参照</span><span class="sxs-lookup"><span data-stu-id="8ba55-112">See Also</span></span>  
 [<span data-ttu-id="8ba55-113">MQSeries アダプターのプロパティ</span><span class="sxs-lookup"><span data-stu-id="8ba55-113">MQSeries Adapter Properties</span></span>](../core/mqseries-adapter-properties.md)