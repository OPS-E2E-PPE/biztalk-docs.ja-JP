---
title: "SOAP アクションの指定の WCF 送信アダプタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send adapters, mapping
- send adapters, WCF services
- mapping, send adapters
- mapping, WCF send adapters
ms.assetid: fa9878eb-65b5-4ccc-b727-ff7e09ba6302
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385e92f7801dc2512fbd038bd0b005d95c503e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="specifying-soap-actions-for-wcf-send-adapters"></a><span data-ttu-id="78624-102">WCF 送信アダプタ用の SOAP アクションの指定</span><span class="sxs-lookup"><span data-stu-id="78624-102">Specifying SOAP Actions for WCF Send Adapters</span></span>
<span data-ttu-id="78624-103">設定することができます、 **WCF です。アクション**WCF 送信アダプタのトランスポートのプロパティ ダイアログ ボックスまたはオーケストレーションのコンテキスト プロパティ**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="78624-103">You can set the **WCF.Action** context property in the WCF send adapter transport properties dialog box or in the orchestration **Expression** shapes.</span></span> <span data-ttu-id="78624-104">設定した場合、 **WCF です。アクション**オーケストレーションのコンテキスト プロパティのままにする必要があります、**アクション**静的送信ポートの WCF アダプター トランスポートのプロパティ ダイアログ ボックスでフィールドを空白。</span><span class="sxs-lookup"><span data-stu-id="78624-104">If you set the **WCF.Action** context property in the orchestration, you need to leave the **Action** field blank in the WCF adapter transport properties dialog box for the static send ports.</span></span> <span data-ttu-id="78624-105">また、静的送信ポートでアクションを指定する場合、 **WCF です。アクション**オーケストレーションで設定したコンテキスト プロパティは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="78624-105">If you also specify an action in the static send ports, the **WCF.Action** context property you set in the orchestration will be overridden.</span></span>  
  
 <span data-ttu-id="78624-106">さらは、このプロパティを指定する 2 つの方法があります。 シングル アクション形式とアクション マッピング形式です。</span><span class="sxs-lookup"><span data-stu-id="78624-106">Moreover, there are two ways to specify this property: the single action format and the action mapping format.</span></span> <span data-ttu-id="78624-107">このプロパティをシングル アクション形式で指定した場合 (http://MyService/IMyContract/MyAction1 など)、送信メッセージについて WCF 送信アダプタのトランスポートのプロパティを設定するダイアログ ボックスの SOAP アクションは、常にこのプロパティで指定した値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="78624-107">If you set this property in the single action format—for example, http://MyService/IMyContract/MyAction1—the SOAP action in the WCF send adapter transport properties dialog box for outgoing messages is always set to the value specified in this property.</span></span> <span data-ttu-id="78624-108">オーケストレーションでシングル アクション形式を設定する代わりに、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="78624-108">Alternatively, you can set the single action format in the orchestration **Expression** shape.</span></span> <span data-ttu-id="78624-109">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="78624-109">For example,</span></span>  
  
```  
OutboundMessage(WCF.Action)="http://MyService/IMyContract/MyAction1";  
```  
  
 <span data-ttu-id="78624-110">によって送信される SOAP アクションを決定をアクション マッピング形式でこのプロパティを設定する場合、 **BTS です。操作**コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="78624-110">If you set this property in the action mapping format, the outgoing SOAP action is determined by the **BTS.Operation** context property.</span></span> <span data-ttu-id="78624-111">たとえば、このプロパティは、WCF では、次の XML 形式に設定されている場合は、送信アダプター トランスポートのプロパティ ダイアログ ボックスおよび**BTS です。操作**プロパティに設定されている**Operation_1**オーケストレーションの送信ポートで、WCF 送信アダプタは送信 SOAP アクションの http://MyService/IMyContract/MyAction1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="78624-111">For example, if this property is set to the following XML format in the WCF send adapter transport properties dialog box and the **BTS.Operation** property is set to **Operation_1** in the send port in the orchestration, the WCF send adapter uses http://MyService/IMyContract/MyAction1 for the outgoing SOAP action.</span></span>  
  
```  
BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<Operation Name="Operation_1" Action="http://MyService/IMyContract/MyAction1" />  
<Operation Name="Operation_2" Action="http://MyService/IMyContract/MyAction2" />  
<Operation Name="Operation_3" Action="http://MyService/IMyContract/MyAction3" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="78624-112">アクション マッピングを指定**WCF です。アクション**で、**式**図形はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="78624-112">Specifying action mapping for **WCF.Action** in an **Expression** shape is not supported.</span></span> <span data-ttu-id="78624-113">アクション マッピングの指定は、[WCF トランスポートのプロパティ] ダイアログ ボックスで行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="78624-113">You need to specify the action mapping in the WCF transport properties dialog box.</span></span> <span data-ttu-id="78624-114">使用して、WCF アダプターが SOAP アクションを検索し、 **BTS です。操作**コンテキスト プロパティは、オーケストレーションは、メッセージは送信ポートでの操作の名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="78624-114">Then the WCF adapter will look up the SOAP action by using the **BTS.Operation** context property, which the orchestration sets to the name of the operation on the port where the message is sent.</span></span>  
  
 <span data-ttu-id="78624-115">送信メッセージが、コンテンツ ベースのルーティング (CBR) にルーティングされる場合、 **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**プロパティが設定されていない、WCF 送信アダプタは全体のアクションのマッピングを設定送信 WCF メッセージのアクションへの文字列。</span><span class="sxs-lookup"><span data-stu-id="78624-115">If outgoing messages are routed with content-based routing (CBR) where the **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** property is not set, WCF send adapters will set the whole action mapping string to the action of the outgoing WCF messages.</span></span> <span data-ttu-id="78624-116">この問題を回避するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="78624-116">To work around this, you can do one of the following:</span></span>  
  
-   <span data-ttu-id="78624-117">送信ポートのアクション フィールドを http://MyService/IMyContract/MyAction1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="78624-117">Set the action field on the send port to http://MyService/IMyContract/MyAction1.</span></span>  
  
-   <span data-ttu-id="78624-118">設定、 **BTS です。操作**パイプラインのコンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="78624-118">Set the **BTS.Operation** context property in a pipeline.</span></span> <span data-ttu-id="78624-119">たとえばの値を設定**http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**を Operation1 にします。</span><span class="sxs-lookup"><span data-stu-id="78624-119">For example, set the value of **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** to Operation1.</span></span>  
  
-   <span data-ttu-id="78624-120">アクション フィールドを空白のままにして、受信メッセージのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="78624-120">Leave the action field blank and use the action from the incoming message instead.</span></span>  
  
 <span data-ttu-id="78624-121">BizTalk WCF サービス使用ウィザードを使用して、シングル アクションまたはアクション マッピングで WCF サービスを使用 (消費) することもできます。</span><span class="sxs-lookup"><span data-stu-id="78624-121">You can also use the BizTalk WCF Service Consuming Wizard to consume the WCF services with single action or action mapping.</span></span> <span data-ttu-id="78624-122">詳細については、次を参照してください。 [BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="78624-122">For more details, see [How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78624-123">参照</span><span class="sxs-lookup"><span data-stu-id="78624-123">See Also</span></span>  
 [<span data-ttu-id="78624-124">WCF アダプター コンテキスト プロパティを使用して動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="78624-124">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)