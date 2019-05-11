---
title: オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- WCF services, orchestrations
- WCF services, SOAP headers
ms.assetid: 31c01e35-a2a6-4ea9-bdf4-6d4311268dbe
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 664f009c1dbbbc37c619f81471ad1675ddd258c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395199"
---
# <a name="using-soap-headers-in-wcf-messages-with-orchestrations"></a><span data-ttu-id="1cc0a-102">オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="1cc0a-102">Using SOAP Headers in WCF Messages with Orchestrations</span></span>
<span data-ttu-id="1cc0a-103">オーケストレーションの送信 WCF メッセージでは、カスタムの SOAP ヘッダーを送信する、コンテキスト プロパティを使用して**WCF です。OutboundCustomHeaders**します。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-103">To send the custom SOAP headers with outgoing WCF messages in orchestrations, you use the context property, **WCF.OutboundCustomHeaders**.</span></span> <span data-ttu-id="1cc0a-104">WCF アダプタは、WCF インフラストラクチャが Ws-addressing などの Web サービス標準を使用する標準 SOAP ヘッダーと組み合わせるカスタム SOAP ヘッダーを送信し、Ws-security、WS-AtomicTransaction します。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-104">The WCF adapters send the custom SOAP headers combined with the standard SOAP headers that the WCF infrastructure uses for Web services standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="1cc0a-105">使用すると、 **OutboundCustomHeaders**プロパティ、プロパティには、 \<**ヘッダー** \>ルート要素としての要素。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-105">When you use the **OutboundCustomHeaders** property, the property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="1cc0a-106">内ですべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-106">All of the custom SOAP headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="1cc0a-107">カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**\>\</**ヘッダー** \>または\<**ヘッダー** / \>を**OutboundCustomHeaders**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-107">If the custom SOAP header value is an empty string, you must assign \<**headers**\>\</**headers**\> or \<**headers**/\> to the **OutboundCustomHeaders** property.</span></span>  
  
 <span data-ttu-id="1cc0a-108">オーケストレーションで SOAP ヘッダー コンテキスト プロパティは、XML データを含む文字列に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-108">For orchestrations, the SOAP header context properties are set to strings that contain XML data.</span></span> <span data-ttu-id="1cc0a-109">BizTalk 式エディタを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-109">You set these strings by using BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span> <span data-ttu-id="1cc0a-110">WCF アダプタで SOAP ヘッダーを使用する方法の詳細についてを参照してください、WCF アダプタでのカスタム SOAP ヘッダーの使用の SDK サンプルから[ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-110">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="1cc0a-111">(メッセージの割り当てまたは式図形) から次の例は、コンテキスト プロパティを設定する文字列を示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-111">The following example (from a Message Assignment or an Expression shape) shows the string setting the context property:</span></span>  
  
```  
outboundMessageInstance(WCF.OutboundCustomHeaders) = "<headers><Origination>Home</Origination><Destination>Work</Destination></headers>"  
```  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a><span data-ttu-id="1cc0a-112">コンテキスト プロパティを設定する XmlDocument の作成</span><span class="sxs-lookup"><span data-stu-id="1cc0a-112">Creating an XmlDocument to set context properties</span></span>  
 <span data-ttu-id="1cc0a-113">設定することができます、 **WCF です。OutboundCustomHeaders**コンテキスト プロパティを作成して、 **XmlDocument**との文字列値を書き込み、 **XmlDocument**をコンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-113">You can set the **WCF.OutboundCustomHeaders** context property by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span> <span data-ttu-id="1cc0a-114">型の変数を宣言する**XMLDocument**し、XML データを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-114">You declare a variable of type **XMLDocument** and assign the XML data.</span></span>  
  
 <span data-ttu-id="1cc0a-115">次の例は、型の変数を宣言することを示しています。 **XMLDocument**と XML データの割り当て。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-115">The following example shows declaring a variable of type **XMLDocument** and assigning the XML data:</span></span>  
  
```  
xmlDoc.LoadXml("<headers><Origination>Home</Origination><Destination>Work</Destination></headers>");  
```  
  
 <span data-ttu-id="1cc0a-116">次の例では、コンテキスト プロパティの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-116">The following example shows setting the context property:</span></span>  
  
```  
RequestMessageInstance(WCF.OutboundCustomHeaders) = xmlDoc.OuterXml;  
```  
  
 <span data-ttu-id="1cc0a-117">詳細については、BizTalk 式エディターを使用して、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-117">For more information about using BizTalk Expression Editor, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span> <span data-ttu-id="1cc0a-118">呼び出し元の詳細については[!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)]クラスを参照してください[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="1cc0a-118">For more information about calling [!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)] classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc0a-119">参照</span><span class="sxs-lookup"><span data-stu-id="1cc0a-119">See Also</span></span>  
 <span data-ttu-id="1cc0a-120">[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1cc0a-120">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 <span data-ttu-id="1cc0a-121">[消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="1cc0a-121">[SOAP Headers with Consumed WCF Services](../core/soap-headers-with-consumed-wcf-services.md) </span></span>  
 [<span data-ttu-id="1cc0a-122">公開済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="1cc0a-122">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)