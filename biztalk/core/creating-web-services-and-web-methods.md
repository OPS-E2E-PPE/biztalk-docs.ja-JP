---
title: Web サービスと Web メソッドの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, schemas
- orchestrations, naming conventions
- Web services, naming conventions
- schemas, Web services
ms.assetid: a7c47000-501c-47b1-bafa-82370585c1db
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22d93635ce23f4ce8899f3d9f6d95dfca2010ea7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389854"
---
# <a name="creating-web-services-and-web-methods"></a><span data-ttu-id="1abd3-102">Web サービスと Web メソッドの作成</span><span class="sxs-lookup"><span data-stu-id="1abd3-102">Creating Web Services and Web Methods</span></span>
<span data-ttu-id="1abd3-103">Web サービスとしてのスキーマを発行するときに、Web サービスと、BizTalk Web サービス公開ウィザードで Web メソッドの作成を制御します。</span><span class="sxs-lookup"><span data-stu-id="1abd3-103">When you publish schemas as a Web service, you control the creation of Web services and Web methods in the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="1abd3-104">Web サービスの説明、Web サービスおよび Web サービス ページに表示されるツリー内の Web メソッドの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="1abd3-104">You can rename the Web service description, Web service and Web method inside the tree available on the Web Services page.</span></span> <span data-ttu-id="1abd3-105">追加し、Web サービスと Web メソッドを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="1abd3-105">You can add and remove Web services and Web methods.</span></span> <span data-ttu-id="1abd3-106">ウィザードでは、入力パラメーター名として選択した要求スキーマのルート要素名を使用します。</span><span class="sxs-lookup"><span data-stu-id="1abd3-106">The wizard uses the root element names of the selected request schemas as the input parameter name.</span></span> <span data-ttu-id="1abd3-107">Web メソッドの戻り値は、応答スキーマを返します。</span><span class="sxs-lookup"><span data-stu-id="1abd3-107">The Web method return value returns the response schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1abd3-108">ASP.NET Web クライアントは、in、out、同じ型のパラメーターを組み合わせることで Web メソッドのシグネチャを変更することがあります。</span><span class="sxs-lookup"><span data-stu-id="1abd3-108">ASP.NET Web clients may change the Web method signature by combining the in and out parameters of the same type.</span></span> <span data-ttu-id="1abd3-109">ASP.NET Web クライアント可能性がありますから BizTalk Web メソッドを変更するなど、 **myService (文字列部分) を文字列**に**void myService (ref 文字列部分)** します。</span><span class="sxs-lookup"><span data-stu-id="1abd3-109">For example, an ASP.NET Web client may change a BizTalk Web method from **string myService(string part)** to **void myService(ref string part)**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1abd3-110">場合、受信ポートが一方向として定義されている、Web メソッドの応答の種類は**void** Web クライアントに情報は返されません。</span><span class="sxs-lookup"><span data-stu-id="1abd3-110">If your receive port is defined as one-way, the Web method response type is **void** and no information is returned to the Web client.</span></span> <span data-ttu-id="1abd3-111">SOAP アダプタおよびオーケストレーション、Web クライアントにスローされる例外は返されません。</span><span class="sxs-lookup"><span data-stu-id="1abd3-111">The SOAP adapter and orchestration do not return thrown exceptions to the Web client.</span></span>  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a><span data-ttu-id="1abd3-112">Web サービスの公開されたオーケストレーションの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="1abd3-112">Web services naming conventions for published orchestrations</span></span>  
 <span data-ttu-id="1abd3-113">BizTalk Web サービス公開ウィザードでは、Web サービス ページで定義する Web サービスの説明に基づく Web サービス (.asmx) ファイル名を生成します。</span><span class="sxs-lookup"><span data-stu-id="1abd3-113">The BizTalk Web Services Publishing Wizard generates Web service (.asmx) file names based on the Web services description that you define in the Web Service page.</span></span> <span data-ttu-id="1abd3-114">次の表では、Web サービスのファイル名の既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="1abd3-114">The following table shows the default values for the Web service file names.</span></span>  
  
|<span data-ttu-id="1abd3-115">生成された Web サービス</span><span class="sxs-lookup"><span data-stu-id="1abd3-115">Generated Web service</span></span>|<span data-ttu-id="1abd3-116">ファイル名</span><span class="sxs-lookup"><span data-stu-id="1abd3-116">File name</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="1abd3-117">BizTalkWebService</span><span class="sxs-lookup"><span data-stu-id="1abd3-117">BizTalkWebService</span></span>|<span data-ttu-id="1abd3-118">Visual Studio Web サービス プロジェクトの名前</span><span class="sxs-lookup"><span data-stu-id="1abd3-118">Visual Studio Web Service project name</span></span>|  
|<span data-ttu-id="1abd3-119">WebService1</span><span class="sxs-lookup"><span data-stu-id="1abd3-119">WebService1</span></span>|<span data-ttu-id="1abd3-120">Web サービス (.asmx) ファイル名</span><span class="sxs-lookup"><span data-stu-id="1abd3-120">Web service (.asmx) file name</span></span>|  
|<span data-ttu-id="1abd3-121">WebMethod1</span><span class="sxs-lookup"><span data-stu-id="1abd3-121">WebMethod1</span></span>|<span data-ttu-id="1abd3-122">Web メソッド名</span><span class="sxs-lookup"><span data-stu-id="1abd3-122">Web method name</span></span>|  
  
 <span data-ttu-id="1abd3-123">生成された Web サービスでは、残りのノードの名前が反映されません。</span><span class="sxs-lookup"><span data-stu-id="1abd3-123">The generated Web service does not reflect the names of the remaining nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1abd3-124">参照</span><span class="sxs-lookup"><span data-stu-id="1abd3-124">See Also</span></span>  
 <span data-ttu-id="1abd3-125">[Web サービスとしてのスキーマの公開](../core/publishing-schemas-as-a-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="1abd3-125">[Publishing Schemas as a Web Service](../core/publishing-schemas-as-a-web-service.md) </span></span>  
 [<span data-ttu-id="1abd3-126">BizTalk Web サービス公開ウィザードを使用してスキーマを Web サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="1abd3-126">How to Use the BizTalk Web Services Publishing Wizard to Publish Schemas as a Web Service</span></span>](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)