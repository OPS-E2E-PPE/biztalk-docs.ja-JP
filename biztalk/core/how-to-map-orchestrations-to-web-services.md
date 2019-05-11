---
title: Web サービスにオーケストレーションをマップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, Web services
- BizTalk Web Services Publishing Wizard, naming conventions
- Web services, orchestrations
- orchestrations, naming conventions
- Web services, naming conventions
ms.assetid: e6a58978-c81c-49f3-9428-9bff60f1ded7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96fafc1179644b3299b674fe1b863a8ee8f9477d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336298"
---
# <a name="how-to-map-orchestrations-to-web-services"></a><span data-ttu-id="85e08-102">Web サービスにオーケストレーションをマップする方法</span><span class="sxs-lookup"><span data-stu-id="85e08-102">How to Map Orchestrations to Web Services</span></span>
<span data-ttu-id="85e08-103">オーケストレーションには、複数のポートを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="85e08-103">An orchestration can have multiple receive ports.</span></span> <span data-ttu-id="85e08-104">BizTalk Web サービス公開ウィザードを使用して、選択した Web サービスとして公開するポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="85e08-104">Using the BizTalk Web Services Publishing Wizard, you select receive ports to publish as Web services.</span></span> <span data-ttu-id="85e08-105">ウィザードは、受信ポートごとに 1 つの Web サービス (.asmx ファイル) を作成します。</span><span class="sxs-lookup"><span data-stu-id="85e08-105">The wizard creates one Web service (.asmx file) for each receive port.</span></span> <span data-ttu-id="85e08-106">同じ受信ポートの種類がある場合、ウィザードはすべての受信ポートの 1 つの Web サービスを作成もできます (一方向または要求/応答)。</span><span class="sxs-lookup"><span data-stu-id="85e08-106">The wizard can also create one Web service for all of the receive ports if they are the same receive port type (one-way or request/response).</span></span> <span data-ttu-id="85e08-107">操作では、関数呼び出しになります。</span><span class="sxs-lookup"><span data-stu-id="85e08-107">Operations become function calls.</span></span> <span data-ttu-id="85e08-108">受信ポート内の各操作では、Web メソッドになります。</span><span class="sxs-lookup"><span data-stu-id="85e08-108">Each operation in the receive port becomes a Web method.</span></span> <span data-ttu-id="85e08-109">要求操作では、入力パラメーターになります。</span><span class="sxs-lookup"><span data-stu-id="85e08-109">Request operations become input parameters.</span></span> <span data-ttu-id="85e08-110">応答操作では、戻り値の型になります。</span><span class="sxs-lookup"><span data-stu-id="85e08-110">Response operations become return types.</span></span>  
  
 <span data-ttu-id="85e08-111">要求と応答の操作が同じ Web メッセージの種類の場合は、入力パラメーターは次のようになります。、 **ref**戻り値の型と**void**します。</span><span class="sxs-lookup"><span data-stu-id="85e08-111">If the request and response operations are the same Web message type, the input parameter becomes a **ref** and the return type is **void**.</span></span> <span data-ttu-id="85e08-112">ASP.NET Web クライアントは、in、out、同じ型のパラメーターを組み合わせることで Web メソッドのシグネチャを変更することがあります。</span><span class="sxs-lookup"><span data-stu-id="85e08-112">ASP.NET Web clients may change the Web method signature by combining the in and out parameters of the same type.</span></span> <span data-ttu-id="85e08-113">ASP.NET Web クライアント可能性がありますから BizTalk Web メソッドを変更するなど、 **myService (文字列部分) を文字列**に**void myService (ref 文字列部分)** します。</span><span class="sxs-lookup"><span data-stu-id="85e08-113">For example, an ASP.NET Web client may change a BizTalk Web method from **string myService(string part)** to **void myService(ref string part)**.</span></span>  
  
 <span data-ttu-id="85e08-114">操作メッセージの種類は、Web メソッドのシグネチャを定義します。</span><span class="sxs-lookup"><span data-stu-id="85e08-114">The operation message types define the Web method signatures.</span></span> <span data-ttu-id="85e08-115">各メッセージの種類の部分は、Web メソッドのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="85e08-115">Each message type part is a parameter in the Web method.</span></span>  
  
## <a name="message-type-part-names-and-target-namespaces"></a><span data-ttu-id="85e08-116">メッセージ型の要素の名前とターゲットの名前空間</span><span class="sxs-lookup"><span data-stu-id="85e08-116">Message type part names and target namespaces</span></span>  
 <span data-ttu-id="85e08-117">ドキュメント スキーマとユーザー定義のクラスを**XmlRootAttribute**メッセージを指定されたターゲットの名前空間が定義されている種類の部分。</span><span class="sxs-lookup"><span data-stu-id="85e08-117">Document schemas and user defined classes with **XmlRootAttribute** specified are message type parts that have defined target namespaces.</span></span> <span data-ttu-id="85e08-118">EDI スキーマ、せず、ユーザー定義クラス**XmlRootAttribute**指定、および組み込み型など**System.String**が定義されているターゲットの名前空間なしのメッセージの種類の部分。</span><span class="sxs-lookup"><span data-stu-id="85e08-118">EDI schemas, user-defined classes without **XmlRootAttribute** specified, and built-in types, such as **System.String** are message type parts without defined target namespaces.</span></span>  
  
|<span data-ttu-id="85e08-119">メッセージの種類の部分名がある場合、</span><span class="sxs-lookup"><span data-stu-id="85e08-119">If the message type part name has a</span></span>|<span data-ttu-id="85e08-120">使用されるパラメーター名</span><span class="sxs-lookup"><span data-stu-id="85e08-120">Parameter Name Used</span></span>|  
|-----------------------------------------|-------------------------|  
|<span data-ttu-id="85e08-121">定義済みのターゲットの名前空間</span><span class="sxs-lookup"><span data-stu-id="85e08-121">Defined target namespace</span></span>|<span data-ttu-id="85e08-122">ルート要素名</span><span class="sxs-lookup"><span data-stu-id="85e08-122">Root element name</span></span>|  
|<span data-ttu-id="85e08-123">定義されたターゲット名前空間がないです。</span><span class="sxs-lookup"><span data-stu-id="85e08-123">No defined target namespace</span></span>|<span data-ttu-id="85e08-124">メッセージの種類の部分名</span><span class="sxs-lookup"><span data-stu-id="85e08-124">Message type part name</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="85e08-125">応答メッセージでマルチパート メッセージの種類を使用すると、BizTalk Web サービス公開ウィザードでは、戻り値の最初のメッセージ部分と残りのメッセージ部分が出力パラメーターとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="85e08-125">When a multipart message type is used for the response message, the BizTalk Web Services Publishing Wizard uses the first message part for the return value and the remaining message parts are used as out parameters.</span></span>  
  
## <a name="orchestrations-with-multiple-operations"></a><span data-ttu-id="85e08-126">複数の操作とオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="85e08-126">Orchestrations with multiple operations</span></span>  
 <span data-ttu-id="85e08-127">1 つの受信ポートが複数ではなく、オーケストレーションを設計する必要があります、オーケストレーションに複数の操作がある場合は、受信ポート。</span><span class="sxs-lookup"><span data-stu-id="85e08-127">If your orchestration has multiple operations, you should design your orchestrations to have one receive port instead of several receive ports.</span></span> <span data-ttu-id="85e08-128">この設計は、BizTalk Web サービス公開ウィザードが複数の Web サービス (.asmx) ファイルを作成するを防ぐし、すべての操作が同じ呼び出しパターンがある場合にのみ機能-すべての一方向操作またはすべての要求-応答操作。</span><span class="sxs-lookup"><span data-stu-id="85e08-128">This design prevents the BizTalk Web Services Publishing Wizard from creating multiple Web service (.asmx) files and only works when all the operations have the same calling pattern—all one-way operations or all request-response operations.</span></span> <span data-ttu-id="85e08-129">受信ポートを 1 つの一方向の両方を含めることはできませんと要求/応答操作。</span><span class="sxs-lookup"><span data-stu-id="85e08-129">A single receive port cannot contain both one-way and request/response operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85e08-130">BizTalk Web サービス公開ウィザードが表示されますのパブリックの受信ポート。</span><span class="sxs-lookup"><span data-stu-id="85e08-130">The BizTalk Web Services Publishing Wizard displays public receive ports.</span></span> <span data-ttu-id="85e08-131">パブリックの受信ポートがパブリック型修飾子でポートの種類。</span><span class="sxs-lookup"><span data-stu-id="85e08-131">Public receive ports are port types with a public type modifier.</span></span> <span data-ttu-id="85e08-132">Web サービスとして、パブリック ポートのみを発行できます。</span><span class="sxs-lookup"><span data-stu-id="85e08-132">You can publish only public ports as a Web service.</span></span> <span data-ttu-id="85e08-133">既定のポートの種類は内部です。</span><span class="sxs-lookup"><span data-stu-id="85e08-133">The default port type is internal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85e08-134">場合、受信ポートが一方向として定義されている、Web メソッドの応答の種類は**void** Web クライアントに情報は返されません。</span><span class="sxs-lookup"><span data-stu-id="85e08-134">If your receive port is defined as one-way, the Web method response type is **void** and no information is returned to the Web client.</span></span> <span data-ttu-id="85e08-135">SOAP アダプターまたはオーケストレーションによってスローされた例外は、Web クライアントに返されません。</span><span class="sxs-lookup"><span data-stu-id="85e08-135">Exceptions thrown by the SOAP adapter or an orchestration are not returned to the Web client.</span></span>  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a><span data-ttu-id="85e08-136">Web サービスの公開されたオーケストレーションの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="85e08-136">Web services naming conventions for published orchestrations</span></span>  
 <span data-ttu-id="85e08-137">BizTalk Web サービス公開ウィザードには、アンダー スコア、オーケストレーションの名前空間に基づく Web サービス (.asmx) ファイル名が生成されます (*)、その後にアンダー スコア、型名 (\\*)、および後に受信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="85e08-137">The BizTalk Web Services Publishing Wizard generates Web service (.asmx) file names based on the orchestrations namespace, followed by an underscore (*), followed by the type name, followed by an underscore (\\*), and followed by the name of the receive port.</span></span> <span data-ttu-id="85e08-138">アンダー スコア (\_) ピリオドを含む部分で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="85e08-138">An underscore (\_) replaces any of the parts that contain periods.</span></span> <span data-ttu-id="85e08-139">Web サービスの名前は、常にポートの名前を持ちます。</span><span class="sxs-lookup"><span data-stu-id="85e08-139">The name of the Web service always has the port name appended.</span></span>  
  
 <span data-ttu-id="85e08-140">次の表では、BizTalk Web サービス公開ウィザードが Web サービス名がどのように生成するかを示します。</span><span class="sxs-lookup"><span data-stu-id="85e08-140">The following table shows how the BizTalk Web Services Publishing Wizard generates Web service names.</span></span>  
  
|<span data-ttu-id="85e08-141">Web ポートとオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="85e08-141">Orchestration(s) with Web port(s)</span></span>|<span data-ttu-id="85e08-142">生成された Web サービスの名前</span><span class="sxs-lookup"><span data-stu-id="85e08-142">Generated Web service name</span></span>|  
|-------------------------------------------|--------------------------------|  
|<span data-ttu-id="85e08-143">1 つの Web ポートの 1 つのオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="85e08-143">One orchestration with one Web port</span></span>|<span data-ttu-id="85e08-144">orchestration1_port1.asmx</span><span class="sxs-lookup"><span data-stu-id="85e08-144">orchestration1_port1.asmx</span></span>|  
|<span data-ttu-id="85e08-145">2 つの Web ポートの 1 つのオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="85e08-145">One orchestration with two Web ports</span></span>|<span data-ttu-id="85e08-146">orchestration1_port1.asmx and orchestration1_port2.asmx</span><span class="sxs-lookup"><span data-stu-id="85e08-146">orchestration1_port1.asmx and orchestration1_port2.asmx</span></span>|  
|<span data-ttu-id="85e08-147">各ポートの 1 つの Web の 2 つのオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="85e08-147">Two orchestrations with one Web port each</span></span>|<span data-ttu-id="85e08-148">orchestration1_port1.asmx and orchestration2_port2.asmx</span><span class="sxs-lookup"><span data-stu-id="85e08-148">orchestration1_port1.asmx and orchestration2_port2.asmx</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85e08-149">参照</span><span class="sxs-lookup"><span data-stu-id="85e08-149">See Also</span></span>  
 <span data-ttu-id="85e08-150">[Web サービスとしてのオーケストレーションの公開](../core/publishing-an-orchestration-as-a-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="85e08-150">[Publishing an Orchestration as a Web Service](../core/publishing-an-orchestration-as-a-web-service.md) </span></span>  
 [<span data-ttu-id="85e08-151">BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="85e08-151">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)