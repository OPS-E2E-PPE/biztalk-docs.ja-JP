---
title: リゾルバー Web サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 236cff15-562a-41d5-bfdc-d250186fb616
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cd153a8ceeba983c71854d02854e37ed046e1bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987531"
---
# <a name="the-resolver-web-service"></a><span data-ttu-id="0d6a4-102">リゾルバー Web サービス</span><span class="sxs-lookup"><span data-stu-id="0d6a4-102">The Resolver Web Service</span></span>
<span data-ttu-id="0d6a4-103">リゾルバー Web サービスは、ESB の動的な解決メカニズムにゲートウェイです。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-103">The Resolver Web service is a gateway into the ESB dynamic resolution mechanism.</span></span> [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] <span data-ttu-id="0d6a4-104">このサービスの 2 つのバージョンが含まれています。 ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) のバージョン。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-104">includes two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="0d6a4-105">サービス名は**ESB します。ResolverServices**と**ESB します。ResolverServices.WCF**、それぞれ、サービスは、次のメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-105">The service names are **ESB.ResolverServices** and **ESB.ResolverServices.WCF**, respectively, and the services expose the following methods:</span></span>  
  
- <span data-ttu-id="0d6a4-106">**解決します。**</span><span class="sxs-lookup"><span data-stu-id="0d6a4-106">**Resolve.**</span></span> <span data-ttu-id="0d6a4-107">このメソッドは、1 つのパラメーターとして、**文字列**競合回避モジュールの登録などの標準的な接続文字列に準拠した、要求に競合回避モジュールの接続文字列を格納している**静的、BRE、UDDI、XPATH、日程表、日程静的、BRI、** または**LDAP です。**</span><span class="sxs-lookup"><span data-stu-id="0d6a4-107">This method takes as its single parameter a **String** that contains the resolver connection string for the request, which conforms to the standard connection strings for registered resolvers such as **STATIC, BRE, UDDI, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** or **LDAP.**</span></span>  
  
- <span data-ttu-id="0d6a4-108">**ResolveMessage します。**</span><span class="sxs-lookup"><span data-stu-id="0d6a4-108">**ResolveMessage.**</span></span> <span data-ttu-id="0d6a4-109">このメソッドは最初のパラメーターとして、競合回避モジュールの登録などの標準的な接続文字列に準拠した要求に競合回避モジュールの接続文字列を含む文字列**静的、BRE、UDDI、XPATH、日程、静的、日程 BRI、** または**LDAP**します。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-109">This method takes as its first parameter a String that contains the resolver connection string for the request, which conforms to the standard connection strings for registered resolvers such as  **STATIC, BRE, UDDI, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** or **LDAP**.</span></span> <span data-ttu-id="0d6a4-110">さらに、メソッドとして省略可能な 2 番目のパラメーターを受け取ります、**文字列**の解決を支援するために省略可能な事実として、サービスが使用できる XML メッセージ ドキュメントを格納しているたとえば、BRE の競合回避モジュールがメッセージ本文を必要があります。ファクトをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-110">In addition, the method accepts an optional second parameter as a **String** that contains an XML message document that the service can use as optional facts to assist in a resolution; for example, the BRE resolver may require a message body that encapsulates facts.</span></span>  
  
  <span data-ttu-id="0d6a4-111">競合回避モジュールと ResolverDictionary クラスとその用途の詳細については、[ヘルパー クラスを使用して](../esb-toolkit/using-the-helper-classes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-111">For more information about the Resolver and ResolverDictionary classes and their usage, see [Using the Helper Classes](../esb-toolkit/using-the-helper-classes.md).</span></span>  
  
## <a name="resolver-connection-strings"></a><span data-ttu-id="0d6a4-112">競合回避モジュールの接続文字列</span><span class="sxs-lookup"><span data-stu-id="0d6a4-112">Resolver Connection Strings</span></span>  
 <span data-ttu-id="0d6a4-113">ESB 動的解決の機構では、前に実行する解決の種類を示すモニカーの接続文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-113">The ESB dynamic resolution mechanism uses a connection string preceded by a moniker that indicates the type of resolution to perform.</span></span> <span data-ttu-id="0d6a4-114">サポートされているモニカーが含まれます**静的、BRE、UDDI、UDDI3、XPATH、日程表、日程静的、BRI、** と**LDAP**します。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-114">The supported monikers include **STATIC, BRE, UDDI, UDDI3, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** and **LDAP**.</span></span> <span data-ttu-id="0d6a4-115">次の接続文字列の例を示しています、 **UDDI**モニカー。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-115">The following connection string shows an example of a **UDDI** moniker:</span></span>  
  
```  
  
//UDDI  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=PurchaseOrder;serviceProvider=Microsoft.Practices.ESB  
```  
  
 <span data-ttu-id="0d6a4-116">動的解決の機構によってサポートされている接続文字列の種類については、[を使用して動的な解決とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-116">For information about the types of connections strings supported by the dynamic resolution mechanism, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d6a4-117">いずれかの Windows 統合セキュリティを使用して、組み込みの NETWORK SERVICE アカウントで実行するこのサービスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-117">You must configure this service to use either Windows Integrated Security and to run under the built-in NETWORK SERVICE account.</span></span>  
>   
>  <span data-ttu-id="0d6a4-118">既定では、競合回避モジュールの Web サービスはセキュリティで保護の Sockets Layer (SSL) クライアントがアクセスするときに要求するように構成されていません。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-118">By default, the Resolver Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="0d6a4-119">クライアント アクセス用の SSL が要求されるように、サービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec と適切なファイル レベルのアクセスを使用して、BizTalk Server 間の接続を保護する必要があります。リスト (ACL) のアクセス許可を制御します。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-119">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and your BizTalk Server using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span> <span data-ttu-id="0d6a4-120">セキュリティ上のリスクを回避するために、信頼できるサブシステムの境界の外側には、このサービスを公開することは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="0d6a4-120">To avoid security risks, it is not recommended to expose this service outside the boundary of the trusted subsystem.</span></span>