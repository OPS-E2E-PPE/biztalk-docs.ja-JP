---
title: インターセプター EventSource 要素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d78846c1-3984-43af-a13f-9d5c0a66d3b5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 001dfe8c2e4fe09b71bcdd8c053f59938be76cc4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382020"
---
# <a name="interceptor-eventsource-element"></a><span data-ttu-id="be7dd-102">インターセプタ EventSource 要素</span><span class="sxs-lookup"><span data-stu-id="be7dd-102">Interceptor EventSource Element</span></span>
<span data-ttu-id="be7dd-103">**EventSource**要素が 1 つ以上のインターセプター構成ファイルに表示されるイベントのソースに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="be7dd-103">The **EventSource** element provides information about the source of one or more of the events appearing in the interceptor configuration file.</span></span> <span data-ttu-id="be7dd-104">イベント ソース名だけでなく、テクノロジと、ソース マニフェストを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be7dd-104">In addition to an event source name, you need to indicate the technology and a manifest for the source.</span></span>  
  
## <a name="format"></a><span data-ttu-id="be7dd-105">形式</span><span class="sxs-lookup"><span data-stu-id="be7dd-105">Format</span></span>  
 <span data-ttu-id="be7dd-106">`EventSource`要素が 3 つの属性と可能性がありますまたはスキーマが含まれていますに応じて子要素がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="be7dd-106">The `EventSource` element has three attributes and may or may not have child elements depending upon which schemas are included.</span></span> <span data-ttu-id="be7dd-107">たとえば、WCF スキーマ WcfInterceptorConfiguration.xsd 提供の`NamespaceMapping`要素。</span><span class="sxs-lookup"><span data-stu-id="be7dd-107">For example, the WCF schema WcfInterceptorConfiguration.xsd provides for the `NamespaceMapping` element.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be7dd-108">属性</span><span class="sxs-lookup"><span data-stu-id="be7dd-108">Attributes</span></span>  
  
|<span data-ttu-id="be7dd-109">属性名</span><span class="sxs-lookup"><span data-stu-id="be7dd-109">Attribute name</span></span>|<span data-ttu-id="be7dd-110">説明</span><span class="sxs-lookup"><span data-stu-id="be7dd-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="be7dd-111">名前</span><span class="sxs-lookup"><span data-stu-id="be7dd-111">Name</span></span>|<span data-ttu-id="be7dd-112">このイベント ソースの名前です。</span><span class="sxs-lookup"><span data-stu-id="be7dd-112">Name for this event source.</span></span> <span data-ttu-id="be7dd-113">この名前を使って**OnEvent**エントリをソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be7dd-113">This name is used by **OnEvent** entries to refer to the source.</span></span>|  
|<span data-ttu-id="be7dd-114">テクノロジ</span><span class="sxs-lookup"><span data-stu-id="be7dd-114">Technology</span></span>|<span data-ttu-id="be7dd-115">マニフェストで指定されたイベント ソースをホストしているテクノロジの種類。</span><span class="sxs-lookup"><span data-stu-id="be7dd-115">Technology type hosting the event source indicated in the manifest.</span></span> <span data-ttu-id="be7dd-116">Windows Communication Framework for Windows Workflow Foundation と"WCF"を"WF"を使用します。</span><span class="sxs-lookup"><span data-stu-id="be7dd-116">Use "WF" for Windows Workflow Foundation and "WCF" for Windows Communication Framework.</span></span>|  
|<span data-ttu-id="be7dd-117">マニフェスト</span><span class="sxs-lookup"><span data-stu-id="be7dd-117">Manifest</span></span>|<span data-ttu-id="be7dd-118">イベント ソースとして使用する型のアセンブリ修飾クラス名。</span><span class="sxs-lookup"><span data-stu-id="be7dd-118">Assembly-qualified class name of the type to use as an event source.</span></span> <span data-ttu-id="be7dd-119">例を次に示します。 `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`</span><span class="sxs-lookup"><span data-stu-id="be7dd-119">For example, `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`</span></span><br /><br /> <span data-ttu-id="be7dd-120">使用して、公開キー トークンがない、`PublicKeyToken=null`します。</span><span class="sxs-lookup"><span data-stu-id="be7dd-120">If you do not have a public key token, use `PublicKeyToken=null`.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="be7dd-121">例</span><span class="sxs-lookup"><span data-stu-id="be7dd-121">Example</span></span>  
 <span data-ttu-id="be7dd-122">次の例には 2 つ**EventSource**要素、1 つのターゲットとなる WF と WCF が 1 つ。</span><span class="sxs-lookup"><span data-stu-id="be7dd-122">The following example contains two **EventSource** elements, one targeting WF and one targeting WCF.</span></span>  
  
```  
<!-- WF -->  
<ic:EventSource Name="OrderWorkflow" Technology="WF" Manifest="SimpleWorkflow.OrderWorkflow, SimpleWorkflow, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
<!-- WCF -->  
<ic:EventSource Name="PurchaseService" Technology="WCF" Manifest="Service.IProcessPOContract, DuplexService, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
```