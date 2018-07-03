---
title: SAP アダプターを使用した安全なプログラミング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, considerations when programming on the adapter
- security, secure data exchange
- security, setting credentials in code
ms.assetid: bd5da271-90f1-4a64-9138-a51048a16648
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7fbdd561c739e6312ca1300bc9b886afdee5376
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015707"
---
# <a name="secure-programming-with-the-sap-adapter"></a><span data-ttu-id="e9bc8-102">SAP アダプターを使用した安全なプログラミング</span><span class="sxs-lookup"><span data-stu-id="e9bc8-102">Secure programming with the SAP adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="e9bc8-103">保護するには資格情報を使用する場合、アダプター サービス参照を Visual Studio プラグインを追加しますか?</span><span class="sxs-lookup"><span data-stu-id="e9bc8-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="e9bc8-104">使用すると、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントを作成するには、ユーザー名と SAP システムのパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you must supply a user name and password for the SAP system.</span></span> <span data-ttu-id="e9bc8-105">これからをのみ行う必要があります、**セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-105">You should only do this from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="e9bc8-106">SAP を入力してから資格情報を**セキュリティ**に直接のタブの代わりに、 **Uri**フィールドに、以下を確認すること。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-106">By entering the SAP credentials from the **Security** tab instead of directly into the **Uri** field, you ensure the following:</span></span>  
  
- <span data-ttu-id="e9bc8-107">資格情報は表示されません、 **Uri**のフィールド、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ダイアログ ボックスで、コンピューターの画面にアクセスできる人が読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-107">The credentials will not be displayed in the **Uri** field of the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] dialog box where anyone with access to your computer screen can read them.</span></span>  
  
- <span data-ttu-id="e9bc8-108">資格情報は、構成には表示されませんファイルを[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-108">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="e9bc8-109">使用して WCF クライアントを生成する方法について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください、SAP システムのユーザー名とパスワードを入力する方法を含む[Visual Studio で SAP 操作のメタデータの取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="e9bc8-109">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the SAP system, see [Get Metadata for SAP Operations in Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="e9bc8-110">コードで資格情報の設定のベスト プラクティスとは</span><span class="sxs-lookup"><span data-stu-id="e9bc8-110">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="e9bc8-111"> 提供します、 **ClientCredentials**などのクライアント通信オブジェクトを資格情報を構成するためのクラス、 **ChannelFactory**を使用して、サービスで自身を認証します。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-111"> provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="e9bc8-112">使用して、 **ClientCredentials**クラス、することを確認 WCF はどのような認証メカニズムは、そのオブジェクトのチャネル スタックで指定された、クライアントとサービス間の交換に適用します。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-112">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="e9bc8-113">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]がホストされているプロセス内のコンシューマー側アプリケーションを使用する命令型、 **ClientCredentials**コンシューマー側アプリケーションが使用する通信オブジェクトをクライアントの資格情報を設定するクラス。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-113">Because the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="e9bc8-114">ただし、これを行うことをお勧めと捉えられます、します。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-114">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="e9bc8-115">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の使用が推奨、 **ClientCredentials**クラスを通じて、 **AcceptCredentialsInUri**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-115">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] encourages the use of the **ClientCredentials** class through the **AcceptCredentialsInUri** binding property.</span></span> <span data-ttu-id="e9bc8-116">このプロパティは、ユーザー名とパスワード、接続 URI 内の SAP システムをアダプターを受け入れるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-116">This property specifies whether the adapter will accept the user name and password for the SAP system in the connection URI.</span></span> <span data-ttu-id="e9bc8-117">**AcceptCredentialsInUri**の既定値は**false**、つまり、接続 URI には、資格情報が含まれている場合に、アダプターが例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-117">**AcceptCredentialsInUri** defaults to **false**, which means that the adapter will throw an exception if the connection URI contains credentials.</span></span> <span data-ttu-id="e9bc8-118">設定することができます**AcceptCredentialsInUri**に**true**接続 URI の資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-118">You can set **AcceptCredentialsInUri** to **true** to supply credentials in the connection URI.</span></span> <span data-ttu-id="e9bc8-119">実際、行う必要があります。 特定の場合たとえば、サービス ホスト エンドポイントに対してまたはの接続 URI を指定すると、 **IReplyChannel**受信シナリオでします。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-119">In fact, you must do this in certain cases; for example, when you specify a connection URI for a service host endpoint or for an **IReplyChannel** in inbound scenarios.</span></span>  
  
 <span data-ttu-id="e9bc8-120">次の例は、使用する方法を示します、 **ClientCredentials** WCF クライアントでの SAP システムの資格情報を設定するクラス。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-120">The following example shows how to use the **ClientCredentials** class to set credentials for the SAP system on a WCF client.</span></span>  
  
```  
SAPBinding binding = new SAPBinding();  
  
// Set endpoint address  
EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
// Create client and set credentials  
RfcClient rfcClient = new RfcClient(binding, endpointAddress);  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="e9bc8-121">な方法はより安全なデータの交換プロセスの境界を越えてでしょうか。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-121">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="e9bc8-122">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]がホストされているアプリケーションまたはサービスで使用することでインプロセスでします。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-122">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="e9bc8-123">アダプターがホストされるため、インプロセスで、コンシューマーとコンシューマー間で交換されるメッセージのセキュリティを提供する必要はありません、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-123">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="e9bc8-124">ただし、使用するアプリケーションまたはサービスを別のサービスまたはクライアントのプロセス境界を越えて機密性の高いデータベースの情報を含むメッセージを送信する場合は、環境内でこのデータを適切に保護を提供するメジャーを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-124">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="e9bc8-125"> セキュリティで保護されたメッセージがクライアントとサービス間で送信する際に役立つ多くのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-125"> provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="e9bc8-126">セキュリティで保護されたメッセージがクライアントとサービスの間で送信することの詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を参照してください[Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-126">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see [Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx).</span></span> <span data-ttu-id="e9bc8-127">セキュリティに関する一般的な情報の機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますを参照してください[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="e9bc8-127">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9bc8-128">参照</span><span class="sxs-lookup"><span data-stu-id="e9bc8-128">See Also</span></span>  
[<span data-ttu-id="e9bc8-129">SAP アダプターをセキュリティで保護するベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="e9bc8-129">Best practices to secure the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[<span data-ttu-id="e9bc8-130">SAP アプリケーションをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="e9bc8-130">Secure your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   