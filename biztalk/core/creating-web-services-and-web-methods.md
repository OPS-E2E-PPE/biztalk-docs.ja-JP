---
title: "Web サービスと Web メソッドの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, schemas
- orchestrations, naming conventions
- Web services, naming conventions
- schemas, Web services
ms.assetid: a7c47000-501c-47b1-bafa-82370585c1db
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74065489e427ae0612897f1f333e3c8e154a535f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-web-services-and-web-methods"></a><span data-ttu-id="0fc8a-102">Web サービスと Web メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-102">Creating Web Services and Web Methods</span></span>
<span data-ttu-id="0fc8a-103">スキーマを Web サービスとして公開すると、BizTalk Web サービス公開ウィザードで Web サービスおよび Web メソッドの作成を制御できます。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-103">When you publish schemas as a Web service, you control the creation of Web services and Web methods in the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="0fc8a-104">[Web サービス] ページに表示されるツリー内で、Web サービスの説明、Web サービス、および Web メソッドの名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-104">You can rename the Web service description, Web service and Web method inside the tree available on the Web Services page.</span></span> <span data-ttu-id="0fc8a-105">Web サービスと Web メソッドの追加および削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-105">You can add and remove Web services and Web methods.</span></span> <span data-ttu-id="0fc8a-106">ウィザードは、選択した要求スキーマのルート要素名を入力パラメータ名として使用します。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-106">The wizard uses the root element names of the selected request schemas as the input parameter name.</span></span> <span data-ttu-id="0fc8a-107">Web メソッドの戻り値は、応答スキーマを返します。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-107">The Web method return value returns the response schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fc8a-108">ASP.NET Web クライアントは、同じ種類の入力および出力パラメータを組み合わせて、Web メソッドの署名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-108">ASP.NET Web clients may change the Web method signature by combining the in and out parameters of the same type.</span></span> <span data-ttu-id="0fc8a-109">ASP.NET Web クライアントはから BizTalk Web メソッドを変更するなど、 **myService (文字列部分) を文字列**に**void myService (ref 文字列部分)**です。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-109">For example, an ASP.NET Web client may change a BizTalk Web method from **string myService(string part)** to **void myService(ref string part)**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fc8a-110">場合、受信ポートが一方向として定義されている、Web メソッドの応答の種類は**void**され、Web クライアントに情報は返されません。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-110">If your receive port is defined as one-way, the Web method response type is **void** and no information is returned to the Web client.</span></span> <span data-ttu-id="0fc8a-111">SOAP アダプタおよびオーケストレーションは、スローされた例外を Web クライアントに返しません。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-111">The SOAP adapter and orchestration do not return thrown exceptions to the Web client.</span></span>  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a><span data-ttu-id="0fc8a-112">公開オーケストレーションの Web サービスの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="0fc8a-112">Web services naming conventions for published orchestrations</span></span>  
 <span data-ttu-id="0fc8a-113">BizTalk Web サービス公開ウィザードでは、[Web サービス] ページで定義された Web サービスの説明に基づいて、Web サービス (.asmx) のファイル名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-113">The BizTalk Web Services Publishing Wizard generates Web service (.asmx) file names based on the Web services description that you define in the Web Service page.</span></span> <span data-ttu-id="0fc8a-114">次の表は、Web サービス ファイル名の既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-114">The following table shows the default values for the Web service file names.</span></span>  
  
|<span data-ttu-id="0fc8a-115">生成された Web サービス</span><span class="sxs-lookup"><span data-stu-id="0fc8a-115">Generated Web service</span></span>|<span data-ttu-id="0fc8a-116">ファイル名</span><span class="sxs-lookup"><span data-stu-id="0fc8a-116">File name</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="0fc8a-117">BizTalkWebService</span><span class="sxs-lookup"><span data-stu-id="0fc8a-117">BizTalkWebService</span></span>|<span data-ttu-id="0fc8a-118">Visual Studio Web サービス プロジェクト名</span><span class="sxs-lookup"><span data-stu-id="0fc8a-118">Visual Studio Web Service project name</span></span>|  
|<span data-ttu-id="0fc8a-119">WebService1</span><span class="sxs-lookup"><span data-stu-id="0fc8a-119">WebService1</span></span>|<span data-ttu-id="0fc8a-120">Web サービス (.asmx) ファイル名</span><span class="sxs-lookup"><span data-stu-id="0fc8a-120">Web service (.asmx) file name</span></span>|  
|<span data-ttu-id="0fc8a-121">WebMethod1</span><span class="sxs-lookup"><span data-stu-id="0fc8a-121">WebMethod1</span></span>|<span data-ttu-id="0fc8a-122">Web メソッド名</span><span class="sxs-lookup"><span data-stu-id="0fc8a-122">Web method name</span></span>|  
  
 <span data-ttu-id="0fc8a-123">生成された Web サービスには、残りのノードの名前が反映されません。</span><span class="sxs-lookup"><span data-stu-id="0fc8a-123">The generated Web service does not reflect the names of the remaining nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc8a-124">参照</span><span class="sxs-lookup"><span data-stu-id="0fc8a-124">See Also</span></span>  
 <span data-ttu-id="0fc8a-125">[Web サービスとしてのスキーマの公開](../core/publishing-schemas-as-a-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="0fc8a-125">[Publishing Schemas as a Web Service](../core/publishing-schemas-as-a-web-service.md) </span></span>  
 [<span data-ttu-id="0fc8a-126">BizTalk Web サービス公開ウィザードを使用してスキーマを Web サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="0fc8a-126">How to Use the BizTalk Web Services Publishing Wizard to Publish Schemas as a Web Service</span></span>](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)