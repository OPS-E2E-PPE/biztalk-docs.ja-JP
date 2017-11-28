---
title: "WCF LOB Adapter SDK の WSDL プロキシを使用して名前空間を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 781d20fa-83e3-42fa-866e-5650d5eb71a7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc85d47da81d2d7425c7db4aad90ea32389f7d84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="738b5-102">WCF LOB Adapter SDK の WSDL プロキシで使用する名前空間</span><span class="sxs-lookup"><span data-stu-id="738b5-102">Use namespaces with the WSDL-Proxy in the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="738b5-103">[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] WSDL とプロキシを使用して、開発者によって指定された値を使用してアダプターを生成、 [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)] SERVICENAMESPACE プライベート変数の変更を使用してコードで指定されているか、または`Namespace`アダプターのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="738b5-103">The [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] generates WSDL and proxies for an adapter using values supplied by the developer using the [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)] or specified in code through modification of the SERVICENAMESPACE private variable and/or the `Namespace` property of the adapter.</span></span>  
  
 <span data-ttu-id="738b5-104">内で定義されている要素とスキーマ型、 \<wsdl:types >\<スキーマ > 既定では、{OperationNamespace} を使用します。</span><span class="sxs-lookup"><span data-stu-id="738b5-104">The schema types and elements defined within the \<wsdl:types>\<schema> use the {OperationNamespace} by default.</span></span> <span data-ttu-id="738b5-105">特定の種類、オーバーライドされた TypeNamespace 設定がある場合、 **TypeMetadata**オブジェクト、その名前空間は複合型の使用やまたは要素の定義。</span><span class="sxs-lookup"><span data-stu-id="738b5-105">If a particular type has an overridden TypeNamespace set in the **TypeMetadata** object, that namespace is used for the complex type and/or or element definition.</span></span>  
  
## <a name="impact-on-wsdl"></a><span data-ttu-id="738b5-106">WSDL に与える影響</span><span class="sxs-lookup"><span data-stu-id="738b5-106">Impact on WSDL</span></span>  
 <span data-ttu-id="738b5-107">次の表では、カスタム アダプターに異なる名前空間が、対応する WSDL に与える影響を示します。</span><span class="sxs-lookup"><span data-stu-id="738b5-107">The following table shows how the different namespaces in a custom adapter affect the corresponding WSDL.</span></span> <span data-ttu-id="738b5-108">表内の ~ {OperationNamespace} は、URI のクラスの名前空間のマッピングたとえば、{OperationNamespace} は"myscheme://a.b/c"~ {OperationNamespace} myscheme.a.b.c になります。</span><span class="sxs-lookup"><span data-stu-id="738b5-108">In the table, ~{OperationNamespace} is the class namespace mapping of a URI; for example, if {OperationNamespace} is "myscheme://a.b/c", ~{OperationNamespace} will be myscheme.a.b.c.</span></span>  
  
|<span data-ttu-id="738b5-109">WSDL のコンストラクト</span><span class="sxs-lookup"><span data-stu-id="738b5-109">WSDL Construct</span></span>|<span data-ttu-id="738b5-110">構文</span><span class="sxs-lookup"><span data-stu-id="738b5-110">Syntax</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="738b5-111">WSDL の targetNamespace</span><span class="sxs-lookup"><span data-stu-id="738b5-111">WSDL targetNamespace,</span></span><br /><br /> <span data-ttu-id="738b5-112">Xmlns:ts</span><span class="sxs-lookup"><span data-stu-id="738b5-112">Xmlns:ts</span></span>|<span data-ttu-id="738b5-113">{Custom}Adapter.Namespace</span><span class="sxs-lookup"><span data-stu-id="738b5-113">{Custom}Adapter.Namespace</span></span>|  
|<span data-ttu-id="738b5-114">\<wsdl:portType ></span><span class="sxs-lookup"><span data-stu-id="738b5-114">\<wsdl:portType></span></span>|<span data-ttu-id="738b5-115">{スキーム}. 最大 {OperationNamespace}</span><span class="sxs-lookup"><span data-stu-id="738b5-115">{scheme}.~{OperationNamespace}</span></span>|  
|<span data-ttu-id="738b5-116">WSDL 入力メッセージ名</span><span class="sxs-lookup"><span data-stu-id="738b5-116">WSDL Input Message Name</span></span>|<span data-ttu-id="738b5-117">{スキーム}. 最大 {OperationNamespace} _ {OperationName} _InputMessage</span><span class="sxs-lookup"><span data-stu-id="738b5-117">{scheme}.~{OperationNamespace}_{OperationName}_InputMessage</span></span>|  
|<span data-ttu-id="738b5-118">WSDL の出力メッセージ名</span><span class="sxs-lookup"><span data-stu-id="738b5-118">WSDL Output Message Name</span></span>|<span data-ttu-id="738b5-119">{スキーム}. 最大 {OperationNamespace} _ {OperationName} _OutputMessage</span><span class="sxs-lookup"><span data-stu-id="738b5-119">{scheme}.~{OperationNamespace}_{OperationName}_OutputMessage</span></span>|  
|<span data-ttu-id="738b5-120">\<wsdl:types >\<スキーマ > targetNamespace</span><span class="sxs-lookup"><span data-stu-id="738b5-120">\<wsdl:types>\<schema> targetNamespace</span></span>|<span data-ttu-id="738b5-121">{スキーム}://{OperationNamespace}</span><span class="sxs-lookup"><span data-stu-id="738b5-121">{scheme}://{OperationNamespace}</span></span>|  
|<span data-ttu-id="738b5-122">\<要素 >\<complexType ></span><span class="sxs-lookup"><span data-stu-id="738b5-122">\<element>\<complexType></span></span>|<span data-ttu-id="738b5-123">その値が null または空でない場合は、{TypeNamespace} を使用します。</span><span class="sxs-lookup"><span data-stu-id="738b5-123">Use {TypeNamespace} if its value is not null or empty.</span></span>|  
  
## <a name="impact-on-proxy"></a><span data-ttu-id="738b5-124">プロキシへの影響</span><span class="sxs-lookup"><span data-stu-id="738b5-124">Impact on Proxy</span></span>  
 <span data-ttu-id="738b5-125">名前空間では、プロキシ内の次の 3 つの異なる属性が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="738b5-125">Three different attributes in the proxy are affected by namespaces:</span></span>  
  
-   <span data-ttu-id="738b5-126">[**System.ServiceModel.ServiceContractAttribute**(名前 ="{スキーム}. 最大 {OperationNamespace}"、Namespace="{Custom}Adapter.Namespace"]</span><span class="sxs-lookup"><span data-stu-id="738b5-126">[**System.ServiceModel.ServiceContractAttribute**(Name="{scheme}.~{OperationNamespace}", Namespace="{Custom}Adapter.Namespace”]</span></span>  
  
-   <span data-ttu-id="738b5-127">[**System.ServiceModel.MessageContractAttribute**(WrapperName WrapperNamespace"DivideResponse"= =「{スキーム}://{OperationNamespace}」、IsWrapped = true)]</span><span class="sxs-lookup"><span data-stu-id="738b5-127">[**System.ServiceModel.MessageContractAttribute**(WrapperName="DivideResponse", WrapperNamespace="{scheme}://{OperationNamespace}", IsWrapped=true)]</span></span>  
  
-   <span data-ttu-id="738b5-128">[**System.ServiceModel.MessageBodyMemberAttribute**(Namespace =「{スキーム}://{TypeNamespace}」、順序 = 0)]</span><span class="sxs-lookup"><span data-stu-id="738b5-128">[**System.ServiceModel.MessageBodyMemberAttribute**(Namespace="{scheme}://{TypeNamespace}", Order=0)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738b5-129">参照</span><span class="sxs-lookup"><span data-stu-id="738b5-129">See Also</span></span>  
 [<span data-ttu-id="738b5-130">WCF LOB Adapter SDK を使用して、開発のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="738b5-130">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)