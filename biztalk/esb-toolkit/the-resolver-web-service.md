---
title: 競合回避モジュールの Web サービス |Microsoft ドキュメント
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
ms.openlocfilehash: 916181431686ca729c0751d9362570afb7dddeee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295218"
---
# <a name="the-resolver-web-service"></a><span data-ttu-id="7f9e6-102">競合回避モジュールの Web サービス</span><span class="sxs-lookup"><span data-stu-id="7f9e6-102">The Resolver Web Service</span></span>
<span data-ttu-id="7f9e6-103">競合回避モジュールの Web サービスは、ゲートウェイ ESB 動的解決メカニズムに。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-103">The Resolver Web service is a gateway into the ESB dynamic resolution mechanism.</span></span> [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]<span data-ttu-id="7f9e6-104">このサービスの 2 つのバージョンが含まれています: ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) バージョン。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-104"> includes two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="7f9e6-105">サービス名は**ESB です。ResolverServices**と**ESB です。ResolverServices.WCF**、それぞれ、およびサービスは、次のメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-105">The service names are **ESB.ResolverServices** and **ESB.ResolverServices.WCF**, respectively, and the services expose the following methods:</span></span>  
  
-   <span data-ttu-id="7f9e6-106">**解決します。**</span><span class="sxs-lookup"><span data-stu-id="7f9e6-106">**Resolve.**</span></span> <span data-ttu-id="7f9e6-107">このメソッドは、1 つのパラメーターとして受け取り、**文字列**登録されている競合回避モジュールのなどの標準的な接続文字列に準拠した要求の競合回避モジュールの接続文字列を格納している**静的、BRE、UDDI、XPATH、行程、行程静的、BRI、** または**LDAP です。**</span><span class="sxs-lookup"><span data-stu-id="7f9e6-107">This method takes as its single parameter a **String** that contains the resolver connection string for the request, which conforms to the standard connection strings for registered resolvers such as **STATIC, BRE, UDDI, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** or **LDAP.**</span></span>  
  
-   <span data-ttu-id="7f9e6-108">**ResolveMessage です。**</span><span class="sxs-lookup"><span data-stu-id="7f9e6-108">**ResolveMessage.**</span></span> <span data-ttu-id="7f9e6-109">このメソッドが最初のパラメーターとして登録されている競合回避モジュールのなどの標準的な接続文字列に準拠した要求の競合回避モジュールの接続文字列を含む文字列を受け取る**静的、BRE、UDDI、XPATH、行程、行程静的、BRI、** または**LDAP**です。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-109">This method takes as its first parameter a String that contains the resolver connection string for the request, which conforms to the standard connection strings for registered resolvers such as  **STATIC, BRE, UDDI, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** or **LDAP**.</span></span> <span data-ttu-id="7f9e6-110">さらに、このメソッドと省略可能な 2 番目のパラメーターを受け取ります、**文字列**の解決を支援するために、サービスが省略可能なファクトとして使用できる XML メッセージ ドキュメントを含むですたとえば、BRE の競合回避モジュールがメッセージ本文を必要があります。ファクトをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-110">In addition, the method accepts an optional second parameter as a **String** that contains an XML message document that the service can use as optional facts to assist in a resolution; for example, the BRE resolver may require a message body that encapsulates facts.</span></span>  
  
 <span data-ttu-id="7f9e6-111">競合回避モジュールと ResolverDictionary クラスとその使用方法の詳細については、次を参照してください。[ヘルパー クラスを使用して](../esb-toolkit/using-the-helper-classes.md)です。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-111">For more information about the Resolver and ResolverDictionary classes and their usage, see [Using the Helper Classes](../esb-toolkit/using-the-helper-classes.md).</span></span>  
  
## <a name="resolver-connection-strings"></a><span data-ttu-id="7f9e6-112">競合回避モジュールの接続文字列</span><span class="sxs-lookup"><span data-stu-id="7f9e6-112">Resolver Connection Strings</span></span>  
 <span data-ttu-id="7f9e6-113">ESB 動的解決メカニズムでは、前に実行する解決策の種類を示すモニカーで接続文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-113">The ESB dynamic resolution mechanism uses a connection string preceded by a moniker that indicates the type of resolution to perform.</span></span> <span data-ttu-id="7f9e6-114">サポートされているモニカーを含める**静的、BRE、UDDI、UDDI3、XPATH、行程、行程静的、BRI、** と**LDAP**です。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-114">The supported monikers include **STATIC, BRE, UDDI, UDDI3, XPATH, ITINERARY, ITINERARY-STATIC, BRI,** and **LDAP**.</span></span> <span data-ttu-id="7f9e6-115">次の接続文字列の例を示しています、 **UDDI**モニカー。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-115">The following connection string shows an example of a **UDDI** moniker:</span></span>  
  
```  
  
//UDDI  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=PurchaseOrder;serviceProvider=Microsoft.Practices.ESB  
```  
  
 <span data-ttu-id="7f9e6-116">動的解決メカニズムによってサポートされている接続文字列の種類については、次を参照してください。[動的解決の使用とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)です。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-116">For information about the types of connections strings supported by the dynamic resolution mechanism, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f9e6-117">いずれかの Windows 統合セキュリティを使用して、組み込みの NETWORK SERVICE アカウントで実行するこのサービスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-117">You must configure this service to use either Windows Integrated Security and to run under the built-in NETWORK SERVICE account.</span></span>  
>   
>  <span data-ttu-id="7f9e6-118">既定では、競合回避モジュールの Web サービスは (SSL) クライアントによってアクセスされたときに要求するように構成されていません。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-118">By default, the Resolver Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="7f9e6-119">クライアント アクセス用の SSL が要求されるようにサービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec および適切なファイル レベルのアクセスを使用して、BizTalk Server 間の接続を保護する必要があります。リスト (ACL) のアクセス許可を制御します。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-119">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and your BizTalk Server using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span> <span data-ttu-id="7f9e6-120">セキュリティ上のリスクを避けるためには、信頼できるサブシステムの境界の外側には、このサービスを公開することは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="7f9e6-120">To avoid security risks, it is not recommended to expose this service outside the boundary of the trusted subsystem.</span></span>