---
title: "Siebel アダプターをセキュリティで保護された使用したプログラミング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security considerations, when programming on the adapter
- credentials, best practices for setting in code
- credentials, protecting when using the Add Adapter Service Reference Visual Studio Plug-in
- security, best practices for setting credentials in code
ms.assetid: 8c2b6b36-7bd9-4678-a9c2-450e818f607a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aebe93918741b2603b8090add7ff40ed731097d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="secure-programming-with-the-siebel-adapter"></a><span data-ttu-id="884c4-102">Siebel アダプターをセキュリティで保護された使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="884c4-102">Secure programming with the Siebel adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="884c4-103">どのように保護する資格情報を使用する場合、アダプター サービス参照を Visual Studio プラグインを追加しますか?</span><span class="sxs-lookup"><span data-stu-id="884c4-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="884c4-104">使用すると、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントを作成するには、ユーザー名と Siebel システムのパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="884c4-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you must supply a user name and password for the Siebel system.</span></span> <span data-ttu-id="884c4-105">行う必要がありますのみから、**セキュリティ**タブで、**アダプターの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="884c4-105">You should only do this from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="884c4-106">Siebel を入力してから資格情報を**セキュリティ**に直接の代わりにタブ、 **Uri**フィールドに、次を確認します。</span><span class="sxs-lookup"><span data-stu-id="884c4-106">By entering the Siebel credentials from the **Security** tab instead of directly into the **Uri** field, you ensure the following:</span></span>  
  
-   <span data-ttu-id="884c4-107">資格情報は表示されません、 **Uri**のフィールド、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]  ダイアログ ボックスが、コンピューター画面にアクセスできる人が読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="884c4-107">The credentials will not be displayed in the **Uri** field of the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] dialog box where anyone with access to your computer screen can read them.</span></span>  
  
-   <span data-ttu-id="884c4-108">構成では、資格情報は表示されませんファイルを[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="884c4-108">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
 <span data-ttu-id="884c4-109">使用して、WCF クライアントを生成する方法について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください、Siebel システムのユーザー名とパスワードを入力する方法を含む[Siebel 操作の Visual Studio でのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="884c4-109">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the Siebel system, see [Get Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="884c4-110">コードで資格情報の設定のベスト プラクティスとは</span><span class="sxs-lookup"><span data-stu-id="884c4-110">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="884c4-111">提供、 **ClientCredentials**などのクライアント通信オブジェクトの資格情報を構成するためのクラス、 **ChannelFactory**サービスで自身を認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="884c4-111"> provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="884c4-112">使用して、 **ClientCredentials**クラス、することを確認 WCF はどのような認証メカニズムは、そのオブジェクトのチャネル スタックで指定し、クライアントとサービス間の交換に適用します。</span><span class="sxs-lookup"><span data-stu-id="884c4-112">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="884c4-113">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]がホストされている、インプロセスでその処理を行うアプリケーションでは使用する命令型、 **ClientCredentials**クラスを利用するアプリケーションが使用している通信オブジェクトはクライアントで資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="884c4-113">Because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="884c4-114">これを行うことをお勧めただしと見なされます、します。</span><span class="sxs-lookup"><span data-stu-id="884c4-114">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="884c4-115">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]の使用が推奨、 **ClientCredentials**クラスを通じて、 **AcceptCredentialsInUri**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="884c4-115">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] encourages the use of the **ClientCredentials** class through the **AcceptCredentialsInUri** binding property.</span></span> <span data-ttu-id="884c4-116">このプロパティは、アダプターは、ユーザー名と接続 URI で Siebel システムのパスワードを受け入れますかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="884c4-116">This property specifies whether the adapter will accept the user name and password for the Siebel system in the connection URI.</span></span> <span data-ttu-id="884c4-117">**AcceptCredentialsInUri**の既定値は**false**、つまり、接続 URI には、資格情報が含まれている場合に、アダプターが例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="884c4-117">**AcceptCredentialsInUri** defaults to **false**, which means that the adapter will throw an exception if the connection URI contains credentials.</span></span> <span data-ttu-id="884c4-118">設定することができます**AcceptCredentialsInUri**に**true**接続 URI の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="884c4-118">You can set **AcceptCredentialsInUri** to **true** to supply credentials in the connection URI.</span></span> <span data-ttu-id="884c4-119">実際には、行う必要があります。 特定の場合たとえば、ときに使用する、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) WCF クライアント クラスを生成するのに Siebel システムの成果物のためです。</span><span class="sxs-lookup"><span data-stu-id="884c4-119">In fact, you must do this in certain cases; for example, when you use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class for Siebel system artifacts.</span></span>  
  
 <span data-ttu-id="884c4-120">次の例を使用する方法を示しています、**資格情報**Siebel システムの資格情報を設定するクラス、 **ChannelFactory**です。</span><span class="sxs-lookup"><span data-stu-id="884c4-120">The following example shows how to use the **Credentials** class to set credentials for the Siebel system on a **ChannelFactory**.</span></span>  
  
```  
// Create binding and endpoint  
SiebelBinding binding = new SiebelBinding();  
EndpointAddress endpointAddress = new EndpointAddress("siebel://Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=entserver&Language=enu ");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 <span data-ttu-id="884c4-121">次の例を使用する方法を示しています、 **ClientCredentials** WCF クライアントで Siebel システムの資格情報を設定するクラス。</span><span class="sxs-lookup"><span data-stu-id="884c4-121">The following example shows how to use the **ClientCredentials** class to set credentials for the Siebel system on a WCF client.</span></span>  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
BusinessObjects_Account_Account_OperationClient accountAccountClient = new BusinessObjects_Account_Account_OperationClient ("SiebelBinding_BusinessObjects_Account_Account_Operation");  
  
// Set user name and password  
accountAccountClient.ClientCredentials.UserName.UserName = "YourUserName";  
accountAccountClient.ClientCredentials.UserName.Password = "YourPassword";  
  
// Open the client  
accountAccountClient.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="884c4-122">どのことができます提供するにはより安全なデータ交換プロセス境界を越えてしますか。</span><span class="sxs-lookup"><span data-stu-id="884c4-122">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="884c4-123">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]がホストされているアプリケーションまたはサービスを利用するとインプロセスでします。</span><span class="sxs-lookup"><span data-stu-id="884c4-123">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="884c4-124">アダプターがホストされているので、インプロセスでコンシューマーとコンシューマー間で交換されるメッセージのセキュリティを提供する必要はありません、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="884c4-124">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="884c4-125">ただし、使用のアプリケーションまたはサービスは、別のサービスまたはクライアントにプロセス境界を越えて機密データベースの情報を含むメッセージを送信する場合は、環境内でこのデータの適切な保護対策を提供するメジャーを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="884c4-125">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="884c4-126">クライアントとサービス間で送信されるセキュリティで保護されたメッセージに役立つ多くのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="884c4-126"> provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="884c4-127">クライアントとサービス間で送信されるセキュリティで保護されたメッセージに保護の詳細について[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を参照してください[Services のセキュリティ保護とクライアント](https://msdn.microsoft.com/library/ms734736.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="884c4-127">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see [Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx).</span></span> <span data-ttu-id="884c4-128">セキュリティに関する一般情報についての機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供を参照してください[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="884c4-128">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="884c4-129">参照</span><span class="sxs-lookup"><span data-stu-id="884c4-129">See Also</span></span>  
 [<span data-ttu-id="884c4-130">Siebel アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="884c4-130">Secure your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)  
[<span data-ttu-id="884c4-131">Siebel アダプターをセキュリティで保護するベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="884c4-131">Best practices to secure the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)