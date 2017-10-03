---
title: "PeopleSoft からの受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9acc71ec-05b8-4490-b3ba-0ce7f27a5a6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11c5add7e71e56f250b95736d97f0434adf72282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receiving-from-peoplesoft"></a><span data-ttu-id="ab4cb-102">PeopleSoft からの受信</span><span class="sxs-lookup"><span data-stu-id="ab4cb-102">Receiving from PeopleSoft</span></span>
<span data-ttu-id="ab4cb-103">Microsoft Adapter for PeopleSoft Enterprise は送信アダプターです。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-103">The Microsoft Adapter for PeopleSoft Enterprise is a send adapter.</span></span> <span data-ttu-id="ab4cb-104">アダプターでは送信請求 - 応答をサポートしているため、クエリを送信し、応答を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-104">The adapter supports solicit-response, so that you can send a query and get back a response.</span></span> <span data-ttu-id="ab4cb-105">ただし、データを PeopleSoft からのみ受信する場合は、さらに 2 つの手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-105">However, if you want only to receive data from PeopleSoft, you must take two additional steps:</span></span>  
  
1.  <span data-ttu-id="ab4cb-106">名前空間の設定パイプライン コンポーネントを使用してカスタム受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-106">Create a custom receive pipeline using the Set Namespace pipeline component.</span></span>  
  
2.  <span data-ttu-id="ab4cb-107">HTTP アダプターを使用するポートなど、PeopleSoft からアクセスできる受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-107">Create a receive port accessible from PeopleSoft such as a port using the HTTP Adapter.</span></span> <span data-ttu-id="ab4cb-108">受信ポートと共にカスタム受信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-108">Use the custom receive pipeline with the receive port.</span></span>  
  
## <a name="the-set-namespace-pipeline-component"></a><span data-ttu-id="ab4cb-109">名前空間の設定パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ab4cb-109">The Set Namespace Pipeline Component</span></span>  
 <span data-ttu-id="ab4cb-110">PeopleSoft から受信されるメッセージには名前空間は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-110">Messages received from PeopleSoft do not include namespaces.</span></span> <span data-ttu-id="ab4cb-111">名前空間の設定パイプライン コンポーネントを使用すると、名前空間を受信メッセージに追加できます。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-111">The Set Namespace pipeline component enables you to add a namespace to the incoming message.</span></span>  
  
 <span data-ttu-id="ab4cb-112">名前空間の設定パイプライン コンポーネントの既定の場所は C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline Component です。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-112">The default location for the Set Namespace pipeline component is C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline Component.</span></span> <span data-ttu-id="ab4cb-113">Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll コンポーネントを BizTalk によって使用されるパイプライン コンポーネント ディレクトリにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-113">You need to copy the component, Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll, to the Pipeline Component directory used by BizTalk.</span></span> <span data-ttu-id="ab4cb-114">また、コンポーネントをパイプライン デザイナーで使用するため、Visual Studio ツールボックスにコンポーネントを追加する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-114">You also need to add the component to the Visual Studio Toolbox in order to use it in the Pipeline Designer.</span></span>  
  
 <span data-ttu-id="ab4cb-115">コンポーネントをインストールする方法については、次を参照してください。[パイプライン コンポーネントの配置](../core/deploying-pipeline-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-115">For information about where to install the component, see [Deploying Pipeline Components](../core/deploying-pipeline-components.md).</span></span>  
  
 <span data-ttu-id="ab4cb-116">Visual Studio ツールボックスにコンポーネントを追加する方法の詳細については、次を参照してください。[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)です。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-116">For information about adding the component to the Visual Studio Toolbox, see [How to Use the Toolbox](../core/how-to-use-the-toolbox.md).</span></span>  
  
## <a name="configuring-the-set-namespace-pipeline-component"></a><span data-ttu-id="ab4cb-117">名前空間の設定パイプライン コンポーネントの構成</span><span class="sxs-lookup"><span data-stu-id="ab4cb-117">Configuring the Set Namespace Pipeline Component</span></span>  
 <span data-ttu-id="ab4cb-118">名前空間の設定パイプライン コンポーネントには、設定可能な 2 つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-118">The Set Namespace pipeline component has two properties you can set:</span></span>  
  
|<span data-ttu-id="ab4cb-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ab4cb-119">Use this</span></span>|<span data-ttu-id="ab4cb-120">目的</span><span class="sxs-lookup"><span data-stu-id="ab4cb-120">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="ab4cb-121">**既定のターゲット Namespace**</span><span class="sxs-lookup"><span data-stu-id="ab4cb-121">**Default Target Namespace**</span></span>|<span data-ttu-id="ab4cb-122">受信メッセージに固定の名前空間を入れます。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-122">Put a fixed namespace in the incoming message.</span></span>|  
|<span data-ttu-id="ab4cb-123">**Target Namespace XPath**</span><span class="sxs-lookup"><span data-stu-id="ab4cb-123">**Target Namespace XPath**</span></span>|<span data-ttu-id="ab4cb-124">XPath で指定された場所から取得された名前空間を受信メッセージから抽出します。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-124">Extract the namespace from the incoming message taking it from the location specified by the XPath.</span></span> <span data-ttu-id="ab4cb-125">有効な名前空間が見つからない場合、アプリケーション イベント ログに警告が記録されます。指定した場合、既定のターゲットの名前空間が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-125">If the component does not find a valid namespace, it logs a warning in the Application Event Log and, if it is specified, uses the Default Target Namespace.</span></span>|  
  
 <span data-ttu-id="ab4cb-126">両方のプロパティを空にした場合、コンポーネントでは受信メッセージに名前空間を割り当てませんが、アプリケーション イベント ログに警告を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-126">If you leave both properties blank, the component does not assign namespaces to incoming messages but does write warnings to the Application Event Log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab4cb-127">参照</span><span class="sxs-lookup"><span data-stu-id="ab4cb-127">See Also</span></span>  
 [<span data-ttu-id="ab4cb-128">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="ab4cb-128">Developing Applications</span></span>](../core/developing-applications4.md)