---
title: 送信アダプターの wcf SOAP アクションの指定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send adapters, mapping
- send adapters, WCF services
- mapping, send adapters
- mapping, WCF send adapters
ms.assetid: fa9878eb-65b5-4ccc-b727-ff7e09ba6302
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47781b2b8add675207136248b38b0dadfe6b5610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023496"
---
# <a name="specifying-soap-actions-for-wcf-send-adapters"></a><span data-ttu-id="83ab0-102">WCF 送信アダプタ用の SOAP アクションの指定</span><span class="sxs-lookup"><span data-stu-id="83ab0-102">Specifying SOAP Actions for WCF Send Adapters</span></span>
<span data-ttu-id="83ab0-103">設定することができます、 **WCF です。アクション**WCF 送信アダプターのトランスポートのプロパティ ダイアログ ボックスまたはオーケストレーションのコンテキスト プロパティ**式**図形。</span><span class="sxs-lookup"><span data-stu-id="83ab0-103">You can set the **WCF.Action** context property in the WCF send adapter transport properties dialog box or in the orchestration **Expression** shapes.</span></span> <span data-ttu-id="83ab0-104">設定した場合、 **WCF です。アクション**オーケストレーションのコンテキスト プロパティのままにする必要があります、**アクション**静的送信ポートの WCF アダプター トランスポートのプロパティ ダイアログ ボックスでフィールドを空白。</span><span class="sxs-lookup"><span data-stu-id="83ab0-104">If you set the **WCF.Action** context property in the orchestration, you need to leave the **Action** field blank in the WCF adapter transport properties dialog box for the static send ports.</span></span> <span data-ttu-id="83ab0-105">また、静的送信ポートでアクションを指定した場合、 **WCF です。アクション**オーケストレーションで設定したコンテキスト プロパティは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="83ab0-105">If you also specify an action in the static send ports, the **WCF.Action** context property you set in the orchestration will be overridden.</span></span>  
  
 <span data-ttu-id="83ab0-106">さらは、このプロパティを指定する 2 つの方法があります。 シングル アクション形式とアクション マッピング形式。</span><span class="sxs-lookup"><span data-stu-id="83ab0-106">Moreover, there are two ways to specify this property: the single action format and the action mapping format.</span></span> <span data-ttu-id="83ab0-107">シングル アクション形式では、このプロパティを設定するかどうか: たとえば、 http://MyService/IMyContract/MyAction1: wcf SOAP アクションの送信アダプター トランスポートのプロパティ ダイアログ ボックスは、送信メッセージは、このプロパティで指定された値に設定されて常にします。</span><span class="sxs-lookup"><span data-stu-id="83ab0-107">If you set this property in the single action format—for example, http://MyService/IMyContract/MyAction1—the SOAP action in the WCF send adapter transport properties dialog box for outgoing messages is always set to the value specified in this property.</span></span> <span data-ttu-id="83ab0-108">オーケストレーションで、シングル アクション形式を設定する代わりに、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="83ab0-108">Alternatively, you can set the single action format in the orchestration **Expression** shape.</span></span> <span data-ttu-id="83ab0-109">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="83ab0-109">For example,</span></span>  
  
```  
OutboundMessage(WCF.Action)="http://MyService/IMyContract/MyAction1";  
```  
  
 <span data-ttu-id="83ab0-110">によって送信される SOAP アクションを決定アクション マッピング形式でこのプロパティを設定する場合、 **BTS します。操作**コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="83ab0-110">If you set this property in the action mapping format, the outgoing SOAP action is determined by the **BTS.Operation** context property.</span></span> <span data-ttu-id="83ab0-111">たとえば、このプロパティは、WCF では、次の XML 形式に設定されている場合は、送信アダプター トランスポートのプロパティ ダイアログ ボックスおよび**BTS します。操作**プロパティに設定されて**Operation_1**オーケストレーションの送信ポートの WCF 送信アダプタが使用http://MyService/IMyContract/MyAction1送信 SOAP アクション。</span><span class="sxs-lookup"><span data-stu-id="83ab0-111">For example, if this property is set to the following XML format in the WCF send adapter transport properties dialog box and the **BTS.Operation** property is set to **Operation_1** in the send port in the orchestration, the WCF send adapter uses http://MyService/IMyContract/MyAction1 for the outgoing SOAP action.</span></span>  
  
```  
BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<Operation Name="Operation_1" Action="http://MyService/IMyContract/MyAction1" />  
<Operation Name="Operation_2" Action="http://MyService/IMyContract/MyAction2" />  
<Operation Name="Operation_3" Action="http://MyService/IMyContract/MyAction3" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="83ab0-112">アクション マッピングを指定**WCF です。アクション**で、**式**図形がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="83ab0-112">Specifying action mapping for **WCF.Action** in an **Expression** shape is not supported.</span></span> <span data-ttu-id="83ab0-113">アクション マッピングの指定は、[WCF トランスポートのプロパティ] ダイアログ ボックスで行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="83ab0-113">You need to specify the action mapping in the WCF transport properties dialog box.</span></span> <span data-ttu-id="83ab0-114">WCF アダプターが SOAP アクションを使用して検索し、 **BTS します。操作**コンテキスト プロパティは、オーケストレーションは、メッセージは送信ポートでの操作の名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="83ab0-114">Then the WCF adapter will look up the SOAP action by using the **BTS.Operation** context property, which the orchestration sets to the name of the operation on the port where the message is sent.</span></span>  
  
 <span data-ttu-id="83ab0-115">送信メッセージが、ルーティング コンテンツ ベースのルーティング (CBR) のかどうか、 **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**プロパティが設定されていない、WCF 送信アダプタは、アクション マッピング文字列全体を送信 WCF メッセージのアクションに設定します。</span><span class="sxs-lookup"><span data-stu-id="83ab0-115">If outgoing messages are routed with content-based routing (CBR) where the **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** property is not set, WCF send adapters will set the whole action mapping string to the action of the outgoing WCF messages.</span></span> <span data-ttu-id="83ab0-116">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83ab0-116">To work around this, you can do one of the following:</span></span>  
  
- <span data-ttu-id="83ab0-117">アクション フィールドを設定する送信ポートでhttp://MyService/IMyContract/MyAction1します。</span><span class="sxs-lookup"><span data-stu-id="83ab0-117">Set the action field on the send port to http://MyService/IMyContract/MyAction1.</span></span>  
  
- <span data-ttu-id="83ab0-118">設定、 **BTS します。操作**パイプラインのコンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="83ab0-118">Set the **BTS.Operation** context property in a pipeline.</span></span> <span data-ttu-id="83ab0-119">たとえばの値を設定**http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**を Operation1 にします。</span><span class="sxs-lookup"><span data-stu-id="83ab0-119">For example, set the value of **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** to Operation1.</span></span>  
  
- <span data-ttu-id="83ab0-120">アクション フィールドを空白のままにして、受信メッセージのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="83ab0-120">Leave the action field blank and use the action from the incoming message instead.</span></span>  
  
  <span data-ttu-id="83ab0-121">BizTalk WCF サービス使用ウィザードを使用して、シングル アクションまたはアクション マッピングで WCF サービスを使用 (消費) することもできます。</span><span class="sxs-lookup"><span data-stu-id="83ab0-121">You can also use the BizTalk WCF Service Consuming Wizard to consume the WCF services with single action or action mapping.</span></span> <span data-ttu-id="83ab0-122">詳細については、次を参照してください。 [BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="83ab0-122">For more details, see [How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ab0-123">参照</span><span class="sxs-lookup"><span data-stu-id="83ab0-123">See Also</span></span>  
 [<span data-ttu-id="83ab0-124">WCF アダプター コンテキスト プロパティによる動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="83ab0-124">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)