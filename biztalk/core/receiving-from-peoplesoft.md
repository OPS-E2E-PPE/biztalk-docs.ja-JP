---
title: PeopleSoft からの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9acc71ec-05b8-4490-b3ba-0ce7f27a5a6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3861d885188762b69a08359fbaf9161e02aa5759
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398088"
---
# <a name="receiving-from-peoplesoft"></a><span data-ttu-id="c2f7d-102">PeopleSoft からの受信</span><span class="sxs-lookup"><span data-stu-id="c2f7d-102">Receiving from PeopleSoft</span></span>
<span data-ttu-id="c2f7d-103">Microsoft Adapter for PeopleSoft Enterprise は、送信アダプターです。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-103">The Microsoft Adapter for PeopleSoft Enterprise is a send adapter.</span></span> <span data-ttu-id="c2f7d-104">アダプターは、クエリを送信し、応答を受け取るように、送信請求-応答をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-104">The adapter supports solicit-response, so that you can send a query and get back a response.</span></span> <span data-ttu-id="c2f7d-105">ただし、PeopleSoft からデータを受信するだけの場合は、2 つの追加手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-105">However, if you want only to receive data from PeopleSoft, you must take two additional steps:</span></span>  
  
1.  <span data-ttu-id="c2f7d-106">Namespace の設定パイプライン コンポーネントを使用してカスタム受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-106">Create a custom receive pipeline using the Set Namespace pipeline component.</span></span>  
  
2.  <span data-ttu-id="c2f7d-107">受信ポートの作成アクセス可能な PeopleSoft から (HTTP アダプターを使用するポートなど)。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-107">Create a receive port accessible from PeopleSoft such as a port using the HTTP Adapter.</span></span> <span data-ttu-id="c2f7d-108">受信ポートでは、カスタム受信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-108">Use the custom receive pipeline with the receive port.</span></span>  
  
## <a name="set-namespace-pipeline-component"></a><span data-ttu-id="c2f7d-109">Namespace パイプライン コンポーネントを設定します。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-109">Set Namespace Pipeline Component</span></span>  
 <span data-ttu-id="c2f7d-110">PeopleSoft から受信したメッセージは、名前空間を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-110">Messages received from PeopleSoft do not include namespaces.</span></span> <span data-ttu-id="c2f7d-111">Namespace の設定パイプライン コンポーネントでは、受信メッセージに名前空間を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-111">The Set Namespace pipeline component enables you to add a namespace to the incoming message.</span></span>  
  
 <span data-ttu-id="c2f7d-112">Namespace の設定パイプライン コンポーネントの既定の場所は C:\Program files \microsoft BizTalk Adapters Enterprise applications \pipeline Component for です。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-112">The default location for the Set Namespace pipeline component is C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline Component.</span></span> <span data-ttu-id="c2f7d-113">Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll コンポーネントを BizTalk で使用されるパイプライン コンポーネント ディレクトリにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-113">You need to copy the component, Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll, to the Pipeline Component directory used by BizTalk.</span></span> <span data-ttu-id="c2f7d-114">また、パイプライン デザイナーで使用するには、Visual Studio のツールボックスにコンポーネントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-114">You also need to add the component to the Visual Studio Toolbox in order to use it in the Pipeline Designer.</span></span>  
  
 <span data-ttu-id="c2f7d-115">コンポーネントをインストールする場所については、次を参照してください。[パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-115">For information about where to install the component, see [Deploying Pipeline Components](../core/deploying-pipeline-components.md).</span></span>  
  
 <span data-ttu-id="c2f7d-116">Visual Studio ツールボックスにコンポーネントを追加する方法の詳細については、次を参照してください。[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-116">For information about adding the component to the Visual Studio Toolbox, see [How to Use the Toolbox](../core/how-to-use-the-toolbox.md).</span></span>  
  
## <a name="configure-the-set-namespace-pipeline-component"></a><span data-ttu-id="c2f7d-117">セット Namespace パイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-117">Configure the Set Namespace Pipeline Component</span></span>  
 <span data-ttu-id="c2f7d-118">Namespace の設定パイプライン コンポーネントには、2 つのプロパティを設定することがあります。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-118">The Set Namespace pipeline component has two properties you can set:</span></span>  
  
|<span data-ttu-id="c2f7d-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2f7d-119">Use this</span></span>|<span data-ttu-id="c2f7d-120">目的</span><span class="sxs-lookup"><span data-stu-id="c2f7d-120">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="c2f7d-121">**既定のターゲット Namespace**</span><span class="sxs-lookup"><span data-stu-id="c2f7d-121">**Default Target Namespace**</span></span>|<span data-ttu-id="c2f7d-122">受信メッセージには、固定の名前空間を配置します。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-122">Put a fixed namespace in the incoming message.</span></span>|  
|<span data-ttu-id="c2f7d-123">**Target Namespace XPath**</span><span class="sxs-lookup"><span data-stu-id="c2f7d-123">**Target Namespace XPath**</span></span>|<span data-ttu-id="c2f7d-124">名前空間は、XPath で指定された場所から取得された受信メッセージから抽出します。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-124">Extract the namespace from the incoming message taking it from the location specified by the XPath.</span></span> <span data-ttu-id="c2f7d-125">有効な名前空間が見つからない場合、アプリケーション イベント ログに警告を記録し、指定されている場合は、ターゲットの既定の Namespace を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-125">If the component does not find a valid namespace, it logs a warning in the Application Event Log and, if it is specified, uses the Default Target Namespace.</span></span>|  
  
 <span data-ttu-id="c2f7d-126">両方のプロパティを空白のままにした場合、コンポーネントが受信したメッセージに名前空間を割り当てられませんが、アプリケーション イベント ログに警告を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c2f7d-126">If you leave both properties blank, the component does not assign namespaces to incoming messages but does write warnings to the Application Event Log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f7d-127">参照</span><span class="sxs-lookup"><span data-stu-id="c2f7d-127">See Also</span></span>  
 [<span data-ttu-id="c2f7d-128">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="c2f7d-128">Developing Applications</span></span>](../core/developing-applications4.md)