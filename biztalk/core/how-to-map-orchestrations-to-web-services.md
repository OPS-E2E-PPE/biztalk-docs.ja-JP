---
title: "オーケストレーションを Web サービスにマップする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, Web services
- BizTalk Web Services Publishing Wizard, naming conventions
- Web services, orchestrations
- orchestrations, naming conventions
- Web services, naming conventions
ms.assetid: e6a58978-c81c-49f3-9428-9bff60f1ded7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f101a9a9ab6c0d99e9895433401de08b1380d1e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-orchestrations-to-web-services"></a><span data-ttu-id="32d90-102">オーケストレーションを Web サービスにマップする方法</span><span class="sxs-lookup"><span data-stu-id="32d90-102">How to Map Orchestrations to Web Services</span></span>
<span data-ttu-id="32d90-103">オーケストレーションには、複数の受信ポートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="32d90-103">An orchestration can have multiple receive ports.</span></span> <span data-ttu-id="32d90-104">BizTalk Web サービス公開ウィザードを使用して、Web サービスとして公開する受信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="32d90-104">Using the BizTalk Web Services Publishing Wizard, you select receive ports to publish as Web services.</span></span> <span data-ttu-id="32d90-105">このウィザードでは、受信ポートごとに 1 つの Web サービス (.asmx ファイル) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="32d90-105">The wizard creates one Web service (.asmx file) for each receive port.</span></span> <span data-ttu-id="32d90-106">また、すべての受信ポートに対して 1 つの Web サービスが作成されます (すべて同じ種類 (一方向または要求 - 応答) の受信ポートである場合)。</span><span class="sxs-lookup"><span data-stu-id="32d90-106">The wizard can also create one Web service for all of the receive ports if they are the same receive port type (one-way or request/response).</span></span> <span data-ttu-id="32d90-107">操作は関数呼び出しになります。</span><span class="sxs-lookup"><span data-stu-id="32d90-107">Operations become function calls.</span></span> <span data-ttu-id="32d90-108">受信ポートでの各操作は Web メソッドになり、</span><span class="sxs-lookup"><span data-stu-id="32d90-108">Each operation in the receive port becomes a Web method.</span></span> <span data-ttu-id="32d90-109">要求操作は入力パラメータになります。</span><span class="sxs-lookup"><span data-stu-id="32d90-109">Request operations become input parameters.</span></span> <span data-ttu-id="32d90-110">応答操作は戻り値の型になります。</span><span class="sxs-lookup"><span data-stu-id="32d90-110">Response operations become return types.</span></span>  
  
 <span data-ttu-id="32d90-111">要求と応答の操作が同じ Web メッセージの種類の場合は、入力パラメーターは次のようになります。、 **ref**戻り値の型と**void**です。</span><span class="sxs-lookup"><span data-stu-id="32d90-111">If the request and response operations are the same Web message type, the input parameter becomes a **ref** and the return type is **void**.</span></span> <span data-ttu-id="32d90-112">ASP.NET Web クライアントは、同じ種類の入力および出力パラメータを組み合わせて、Web メソッドの署名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="32d90-112">ASP.NET Web clients may change the Web method signature by combining the in and out parameters of the same type.</span></span> <span data-ttu-id="32d90-113">ASP.NET Web クライアントはから BizTalk Web メソッドを変更するなど、 **myService (文字列部分) を文字列**に**void myService (ref 文字列部分)**です。</span><span class="sxs-lookup"><span data-stu-id="32d90-113">For example, an ASP.NET Web client may change a BizTalk Web method from **string myService(string part)** to **void myService(ref string part)**.</span></span>  
  
 <span data-ttu-id="32d90-114">操作メッセージの種類によって Web メソッドの署名が定義されます。</span><span class="sxs-lookup"><span data-stu-id="32d90-114">The operation message types define the Web method signatures.</span></span> <span data-ttu-id="32d90-115">また、各メッセージの種類の部分が Web メソッドのパラメータになります。</span><span class="sxs-lookup"><span data-stu-id="32d90-115">Each message type part is a parameter in the Web method.</span></span>  
  
## <a name="message-type-part-names-and-target-namespaces"></a><span data-ttu-id="32d90-116">メッセージの種類の部分名とターゲットの名前空間</span><span class="sxs-lookup"><span data-stu-id="32d90-116">Message type part names and target namespaces</span></span>  
 <span data-ttu-id="32d90-117">ドキュメント スキーマとユーザー定義クラス**XmlRootAttribute**メッセージをターゲットの名前空間を定義済みの種類の部分は指定します。</span><span class="sxs-lookup"><span data-stu-id="32d90-117">Document schemas and user defined classes with **XmlRootAttribute** specified are message type parts that have defined target namespaces.</span></span> <span data-ttu-id="32d90-118">EDI スキーマ、せず、ユーザー定義のクラス**XmlRootAttribute**指定、および組み込み型など**System.String**メッセージの種類定義のターゲットの名前空間なし部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="32d90-118">EDI schemas, user-defined classes without **XmlRootAttribute** specified, and built-in types, such as **System.String** are message type parts without defined target namespaces.</span></span>  
  
|<span data-ttu-id="32d90-119">メッセージの種類の部分名に設定されている内容</span><span class="sxs-lookup"><span data-stu-id="32d90-119">If the message type part name has a</span></span>|<span data-ttu-id="32d90-120">使用されるパラメータ名</span><span class="sxs-lookup"><span data-stu-id="32d90-120">Parameter Name Used</span></span>|  
|-----------------------------------------|-------------------------|  
|<span data-ttu-id="32d90-121">ターゲットの名前空間が定義されている</span><span class="sxs-lookup"><span data-stu-id="32d90-121">Defined target namespace</span></span>|<span data-ttu-id="32d90-122">ルート要素名</span><span class="sxs-lookup"><span data-stu-id="32d90-122">Root element name</span></span>|  
|<span data-ttu-id="32d90-123">ターゲットの名前空間が定義されていない</span><span class="sxs-lookup"><span data-stu-id="32d90-123">No defined target namespace</span></span>|<span data-ttu-id="32d90-124">メッセージの種類の部分名</span><span class="sxs-lookup"><span data-stu-id="32d90-124">Message type part name</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="32d90-125">応答メッセージにマルチパート メッセージの種類が使用されていると、BizTalk Web サービス公開ウィザードは、最初のメッセージ部分を戻り値に使用し、残りのメッセージ部分は出力パラメータとして使用します。</span><span class="sxs-lookup"><span data-stu-id="32d90-125">When a multipart message type is used for the response message, the BizTalk Web Services Publishing Wizard uses the first message part for the return value and the remaining message parts are used as out parameters.</span></span>  
  
## <a name="orchestrations-with-multiple-operations"></a><span data-ttu-id="32d90-126">複数の操作を含むオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="32d90-126">Orchestrations with multiple operations</span></span>  
 <span data-ttu-id="32d90-127">オーケストレーションに複数の操作が含まれる場合、複数の送信ポートではなく 1 つの送信ポートを使用するようにオーケストレーションを設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d90-127">If your orchestration has multiple operations, you should design your orchestrations to have one receive port instead of several receive ports.</span></span> <span data-ttu-id="32d90-128">この設計は、BizTalk Web サービス公開ウィザードが複数の Web サービス (.asmx) ファイルを作成することを防止され、すべての操作が同じ呼び出しパターンがある場合にのみ機能: すべての一方向操作またはすべての要求-応答操作します。</span><span class="sxs-lookup"><span data-stu-id="32d90-128">This design prevents the BizTalk Web Services Publishing Wizard from creating multiple Web service (.asmx) files and only works when all the operations have the same calling pattern—all one-way operations or all request-response operations.</span></span> <span data-ttu-id="32d90-129">単一の受信ポートに、一方向の操作と要求 - 応答操作の両方を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="32d90-129">A single receive port cannot contain both one-way and request/response operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32d90-130">BizTalk Web サービス公開ウィザードは、パブリックの受信ポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="32d90-130">The BizTalk Web Services Publishing Wizard displays public receive ports.</span></span> <span data-ttu-id="32d90-131">パブリックの受信ポートは、パブリックの型修飾子を持つ種類のポートです。</span><span class="sxs-lookup"><span data-stu-id="32d90-131">Public receive ports are port types with a public type modifier.</span></span> <span data-ttu-id="32d90-132">パブリック ポートは、Web サービスとしてのみ公開できます。</span><span class="sxs-lookup"><span data-stu-id="32d90-132">You can publish only public ports as a Web service.</span></span> <span data-ttu-id="32d90-133">既定のポートの種類は "内部" です。</span><span class="sxs-lookup"><span data-stu-id="32d90-133">The default port type is internal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32d90-134">場合、受信ポートが一方向として定義されている、Web メソッドの応答の種類は**void**され、Web クライアントに情報は返されません。</span><span class="sxs-lookup"><span data-stu-id="32d90-134">If your receive port is defined as one-way, the Web method response type is **void** and no information is returned to the Web client.</span></span> <span data-ttu-id="32d90-135">SOAP アダプタやオーケストレーションによってスローされる例外は、Web クライアントには返されません。</span><span class="sxs-lookup"><span data-stu-id="32d90-135">Exceptions thrown by the SOAP adapter or an orchestration are not returned to the Web client.</span></span>  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a><span data-ttu-id="32d90-136">公開オーケストレーションの Web サービスの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="32d90-136">Web services naming conventions for published orchestrations</span></span>  
 <span data-ttu-id="32d90-137">BizTalk Web サービス公開ウィザードには、アンダー スコア (_)、アンダー スコア、型名を続けて、オーケストレーションの名前空間に基づく Web サービス (.asmx) ファイル名が生成されます (\_)、その後に、受信の名とポートです。</span><span class="sxs-lookup"><span data-stu-id="32d90-137">The BizTalk Web Services Publishing Wizard generates Web service (.asmx) file names based on the orchestrations namespace, followed by an underscore (_), followed by the type name, followed by an underscore (\_), and followed by the name of the receive port.</span></span> <span data-ttu-id="32d90-138">アンダー スコア (\_) ピリオドを含む部分で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="32d90-138">An underscore (\_) replaces any of the parts that contain periods.</span></span> <span data-ttu-id="32d90-139">Web サービスの名前には、必ず、ポート名が付加されます。</span><span class="sxs-lookup"><span data-stu-id="32d90-139">The name of the Web service always has the port name appended.</span></span>  
  
 <span data-ttu-id="32d90-140">次の表を使用して、BizTalk Web サービス公開ウィザードが Web サービス名を生成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="32d90-140">The following table shows how the BizTalk Web Services Publishing Wizard generates Web service names.</span></span>  
  
|<span data-ttu-id="32d90-141">オーケストレーションの数 (含まれる Web ポートの数)</span><span class="sxs-lookup"><span data-stu-id="32d90-141">Orchestration(s) with Web port(s)</span></span>|<span data-ttu-id="32d90-142">生成される Web サービス名</span><span class="sxs-lookup"><span data-stu-id="32d90-142">Generated Web service name</span></span>|  
|-------------------------------------------|--------------------------------|  
|<span data-ttu-id="32d90-143">1 つのオーケストレーション (1 つの Web ポートを含む)</span><span class="sxs-lookup"><span data-stu-id="32d90-143">One orchestration with one Web port</span></span>|<span data-ttu-id="32d90-144">orchestration1_port1.asmx</span><span class="sxs-lookup"><span data-stu-id="32d90-144">orchestration1_port1.asmx</span></span>|  
|<span data-ttu-id="32d90-145">1 つのオーケストレーション (2 つの Web ポートを含む)</span><span class="sxs-lookup"><span data-stu-id="32d90-145">One orchestration with two Web ports</span></span>|<span data-ttu-id="32d90-146">orchestration1_port1.asmx と orchestration1_port2.asmx</span><span class="sxs-lookup"><span data-stu-id="32d90-146">orchestration1_port1.asmx and orchestration1_port2.asmx</span></span>|  
|<span data-ttu-id="32d90-147">2 つのオーケストレーション (それぞれ 1 つの Web ポートを含む)</span><span class="sxs-lookup"><span data-stu-id="32d90-147">Two orchestrations with one Web port each</span></span>|<span data-ttu-id="32d90-148">orchestration1_port1.asmx と orchestration2_port2.asmx</span><span class="sxs-lookup"><span data-stu-id="32d90-148">orchestration1_port1.asmx and orchestration2_port2.asmx</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32d90-149">参照</span><span class="sxs-lookup"><span data-stu-id="32d90-149">See Also</span></span>  
 <span data-ttu-id="32d90-150">[Web サービスとしてのオーケストレーションの公開](../core/publishing-an-orchestration-as-a-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="32d90-150">[Publishing an Orchestration as a Web Service](../core/publishing-an-orchestration-as-a-web-service.md) </span></span>  
 [<span data-ttu-id="32d90-151">BizTalk Web サービス公開ウィザードを使用してオーケストレーションを Web サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="32d90-151">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)