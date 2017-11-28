---
title: "インターセプタ EventSource 要素 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d78846c1-3984-43af-a13f-9d5c0a66d3b5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b5cd6b2e872f689988f3d10d18df002f66d6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interceptor-eventsource-element"></a><span data-ttu-id="439b1-102">インターセプタ EventSource 要素</span><span class="sxs-lookup"><span data-stu-id="439b1-102">Interceptor EventSource Element</span></span>
<span data-ttu-id="439b1-103">**EventSource**要素が 1 つ以上のインターセプター構成ファイルに表示されるイベントのソースに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="439b1-103">The **EventSource** element provides information about the source of one or more of the events appearing in the interceptor configuration file.</span></span> <span data-ttu-id="439b1-104">イベント ソース名だけでなく、ソースのテクノロジとマニフェストを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="439b1-104">In addition to an event source name, you need to indicate the technology and a manifest for the source.</span></span>  
  
## <a name="format"></a><span data-ttu-id="439b1-105">Format</span><span class="sxs-lookup"><span data-stu-id="439b1-105">Format</span></span>  
 <span data-ttu-id="439b1-106">`EventSource` 要素には 3 つの属性があり、含まれているスキーマに応じて子要素がある場合とない場合があります。</span><span class="sxs-lookup"><span data-stu-id="439b1-106">The `EventSource` element has three attributes and may or may not have child elements depending upon which schemas are included.</span></span> <span data-ttu-id="439b1-107">たとえば、WCF スキーマである WcfInterceptorConfiguration.xsd には、`NamespaceMapping` 要素が用意されています。</span><span class="sxs-lookup"><span data-stu-id="439b1-107">For example, the WCF schema WcfInterceptorConfiguration.xsd provides for the `NamespaceMapping` element.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="439b1-108">属性</span><span class="sxs-lookup"><span data-stu-id="439b1-108">Attributes</span></span>  
  
|<span data-ttu-id="439b1-109">属性名</span><span class="sxs-lookup"><span data-stu-id="439b1-109">Attribute name</span></span>|<span data-ttu-id="439b1-110">Description</span><span class="sxs-lookup"><span data-stu-id="439b1-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="439b1-111">名前</span><span class="sxs-lookup"><span data-stu-id="439b1-111">Name</span></span>|<span data-ttu-id="439b1-112">イベント ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="439b1-112">Name for this event source.</span></span> <span data-ttu-id="439b1-113">この名前は使用**OnEvent**エントリをソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="439b1-113">This name is used by **OnEvent** entries to refer to the source.</span></span>|  
|<span data-ttu-id="439b1-114">テクノロジ</span><span class="sxs-lookup"><span data-stu-id="439b1-114">Technology</span></span>|<span data-ttu-id="439b1-115">マニフェストで指定されたイベント ソースをホストするテクノロジの種類。</span><span class="sxs-lookup"><span data-stu-id="439b1-115">Technology type hosting the event source indicated in the manifest.</span></span> <span data-ttu-id="439b1-116">Windows Workflow Foundation には "WF"、Windows Communication Framework には "WCF" を使用します。</span><span class="sxs-lookup"><span data-stu-id="439b1-116">Use "WF" for Windows Workflow Foundation and "WCF" for Windows Communication Framework.</span></span>|  
|<span data-ttu-id="439b1-117">Manifest</span><span class="sxs-lookup"><span data-stu-id="439b1-117">Manifest</span></span>|<span data-ttu-id="439b1-118">イベント ソースとして使用する種類のアセンブリ修飾クラス名。</span><span class="sxs-lookup"><span data-stu-id="439b1-118">Assembly-qualified class name of the type to use as an event source.</span></span> <span data-ttu-id="439b1-119">たとえば、IPv4 アドレスの場合、「 `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`</span><span class="sxs-lookup"><span data-stu-id="439b1-119">For example, `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`</span></span><br /><br /> <span data-ttu-id="439b1-120">公開キー トークンがない場合は、`PublicKeyToken=null` を使用します。</span><span class="sxs-lookup"><span data-stu-id="439b1-120">If you do not have a public key token, use `PublicKeyToken=null`.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="439b1-121">例</span><span class="sxs-lookup"><span data-stu-id="439b1-121">Example</span></span>  
 <span data-ttu-id="439b1-122">次の例には 2 つ**EventSource**要素、1 つのターゲットとなる WF および WCF が 1 つです。</span><span class="sxs-lookup"><span data-stu-id="439b1-122">The following example contains two **EventSource** elements, one targeting WF and one targeting WCF.</span></span>  
  
```  
<!-- WF -->  
<ic:EventSource Name="OrderWorkflow" Technology="WF" Manifest="SimpleWorkflow.OrderWorkflow, SimpleWorkflow, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
<!-- WCF -->  
<ic:EventSource Name="PurchaseService" Technology="WCF" Manifest="Service.IProcessPOContract, DuplexService, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
```