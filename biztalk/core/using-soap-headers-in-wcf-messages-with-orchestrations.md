---
title: "オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- WCF services, orchestrations
- WCF services, SOAP headers
ms.assetid: 31c01e35-a2a6-4ea9-bdf4-6d4311268dbe
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7492ac6e1f8e43559fa921f9ddd3b60d644fe5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-wcf-messages-with-orchestrations"></a><span data-ttu-id="cacf9-102">オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="cacf9-102">Using SOAP Headers in WCF Messages with Orchestrations</span></span>
<span data-ttu-id="cacf9-103">コンテキスト プロパティを使用するオーケストレーションでの送信 WCF メッセージでは、カスタムの SOAP ヘッダーを送信する**WCF です。OutboundCustomHeaders**です。</span><span class="sxs-lookup"><span data-stu-id="cacf9-103">To send the custom SOAP headers with outgoing WCF messages in orchestrations, you use the context property, **WCF.OutboundCustomHeaders**.</span></span> <span data-ttu-id="cacf9-104">WCF アダプタは、カスタムの SOAP ヘッダーを、WCF インフラストラクチャが WS-Addressing、WS-Security、WS-AtomicTransaction などの Web サービス標準に使用する標準 SOAP ヘッダーと組み合わせて送信します。</span><span class="sxs-lookup"><span data-stu-id="cacf9-104">The WCF adapters send the custom SOAP headers combined with the standard SOAP headers that the WCF infrastructure uses for Web services standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="cacf9-105">使用すると、 **OutboundCustomHeaders**プロパティ、プロパティには、 \<**ヘッダー**> 要素をルート要素として。</span><span class="sxs-lookup"><span data-stu-id="cacf9-105">When you use the **OutboundCustomHeaders** property, the property must have the \<**headers**> element as the root element.</span></span> <span data-ttu-id="cacf9-106">内のすべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー**> 要素。</span><span class="sxs-lookup"><span data-stu-id="cacf9-106">All of the custom SOAP headers must be placed inside the \<**headers**> element.</span></span> <span data-ttu-id="cacf9-107">カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**>\</**ヘッダー**> または\< **ヘッダー**/> に、 **OutboundCustomHeaders**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="cacf9-107">If the custom SOAP header value is an empty string, you must assign \<**headers**>\</**headers**> or \<**headers**/> to the **OutboundCustomHeaders** property.</span></span>  
  
 <span data-ttu-id="cacf9-108">オーケストレーションでは、SOAP ヘッダーのコンテキスト プロパティは、XML データを含む文字列に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cacf9-108">For orchestrations, the SOAP header context properties are set to strings that contain XML data.</span></span> <span data-ttu-id="cacf9-109">BizTalk 式エディターを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="cacf9-109">You set these strings by using BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span> <span data-ttu-id="cacf9-110">WCF アダプタで SOAP ヘッダーを使用する方法の詳細についてを参照してください、with the WCF Adapters」カスタム SOAP ヘッダーを使用して、SDK サンプルから[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)です。</span><span class="sxs-lookup"><span data-stu-id="cacf9-110">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="cacf9-111">次の (メッセージの割り当て図形または式図形の) 例は、コンテキスト プロパティの設定方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cacf9-111">The following example (from a Message Assignment or an Expression shape) shows the string setting the context property:</span></span>  
  
```  
outboundMessageInstance(WCF.OutboundCustomHeaders) = "<headers><Origination>Home</Origination><Destination>Work</Destination></headers>"  
```  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a><span data-ttu-id="cacf9-112">XmlDocument の作成によるコンテキスト プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="cacf9-112">Creating an XmlDocument to set context properties</span></span>  
 <span data-ttu-id="cacf9-113">設定することができます、 **WCF です。OutboundCustomHeaders**コンテキスト プロパティを作成して、 **XmlDocument**と書き込みの文字列値、 **XmlDocument**をコンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="cacf9-113">You can set the **WCF.OutboundCustomHeaders** context property by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span> <span data-ttu-id="cacf9-114">型の変数を宣言する**XMLDocument**し、XML データを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cacf9-114">You declare a variable of type **XMLDocument** and assign the XML data.</span></span>  
  
 <span data-ttu-id="cacf9-115">次の例は、型の変数を宣言することを示しています。 **XMLDocument**と XML データの割り当て。</span><span class="sxs-lookup"><span data-stu-id="cacf9-115">The following example shows declaring a variable of type **XMLDocument** and assigning the XML data:</span></span>  
  
```  
xmlDoc.LoadXml("<headers><Origination>Home</Origination><Destination>Work</Destination></headers>");  
```  
  
 <span data-ttu-id="cacf9-116">次の例は、コンテキスト プロパティの設定方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cacf9-116">The following example shows setting the context property:</span></span>  
  
```  
RequestMessageInstance(WCF.OutboundCustomHeaders) = xmlDoc.OuterXml;  
```  
  
 <span data-ttu-id="cacf9-117">詳細については、BizTalk 式エディターを使用して、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)です。</span><span class="sxs-lookup"><span data-stu-id="cacf9-117">For more information about using BizTalk Expression Editor, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span> <span data-ttu-id="cacf9-118">呼び出し元の詳細については[!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)]クラスを参照してください[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。</span><span class="sxs-lookup"><span data-stu-id="cacf9-118">For more information about calling [!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)] classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cacf9-119">参照</span><span class="sxs-lookup"><span data-stu-id="cacf9-119">See Also</span></span>  
 <span data-ttu-id="cacf9-120">[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="cacf9-120">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 <span data-ttu-id="cacf9-121">[消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="cacf9-121">[SOAP Headers with Consumed WCF Services](../core/soap-headers-with-consumed-wcf-services.md) </span></span>  
 [<span data-ttu-id="cacf9-122">公開済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="cacf9-122">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)