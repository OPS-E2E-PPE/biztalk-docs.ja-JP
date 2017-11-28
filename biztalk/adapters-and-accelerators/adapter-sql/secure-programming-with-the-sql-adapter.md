---
title: "SQL アダプタをセキュリティで保護された使用したプログラミング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c84744a-6595-4d93-afe7-39a7ccf1b6a0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44886b490ce63e8c34e1a5bdb41554c96a0873ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="secure-programming-with-the-sql-adapter"></a><span data-ttu-id="d3097-102">SQL アダプタをセキュリティで保護された使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="d3097-102">Secure programming with the SQL adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="d3097-103">どのように保護する資格情報を使用する場合、アダプター サービス参照を Visual Studio プラグインを追加しますか?</span><span class="sxs-lookup"><span data-stu-id="d3097-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="d3097-104">使用すると、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントを作成するには、ユーザー名と SQL Server データベースのパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3097-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you might have to supply a user name and password for the SQL Server database.</span></span> <span data-ttu-id="d3097-105">資格情報を入力する必要があります、**セキュリティ**タブで、**アダプターの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d3097-105">You must enter credentials from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="d3097-106">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI の一部として、ユーザー名とパスワードを指定するオプションが用意されていません。</span><span class="sxs-lookup"><span data-stu-id="d3097-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not provide an option to specify the user name and password as part of the connection URI.</span></span> <span data-ttu-id="d3097-107">これにより、次に。</span><span class="sxs-lookup"><span data-stu-id="d3097-107">This ensures the following:</span></span>  
  
-   <span data-ttu-id="d3097-108">資格情報は表示されません、 **URI の構成**のフィールド、**アダプター サービス参照のプラグインの追加** ダイアログ ボックスが、コンピューター画面にアクセスできる人が読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="d3097-108">The credentials will not be displayed in the **Configure a URI** field of the **Add Adapter Service Reference Plug-in** dialog box where anyone with access to your computer screen can read them.</span></span>  
  
-   <span data-ttu-id="d3097-109">構成では、資格情報は表示されませんファイルを[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d3097-109">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
 <span data-ttu-id="d3097-110">使用して、WCF クライアントを生成する方法について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください、SQL Server データベースのユーザー名とパスワードを入力する方法を含む[SQLアダプターを使用してVisualStudioでのSQLServer操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="d3097-110">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the SQL Server database, see [Get metadata for SQL Server operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="d3097-111">コードで資格情報の設定のベスト プラクティスとは</span><span class="sxs-lookup"><span data-stu-id="d3097-111">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="d3097-112">提供、 **ClientCredentials**などのクライアント通信オブジェクトの資格情報を構成するためのクラス、 **ChannelFactory**サービスで自身を認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="d3097-112"> provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="d3097-113">使用して、 **ClientCredentials**クラス、することを確認 WCF はどのような認証メカニズムは、そのオブジェクトのチャネル スタックで指定し、クライアントとサービス間の交換に適用します。</span><span class="sxs-lookup"><span data-stu-id="d3097-113">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="d3097-114">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がホストされている、インプロセスでその処理を行うアプリケーションでは使用する命令型、 **ClientCredentials**クラスを利用するアプリケーションが使用している通信オブジェクトはクライアントで資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="d3097-114">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="d3097-115">これを行うことをお勧めただしと見なされます、します。</span><span class="sxs-lookup"><span data-stu-id="d3097-115">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="d3097-116">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の使用を要求、 **ClientCredentials**をプログラムで資格情報を渡すためのクラスです。</span><span class="sxs-lookup"><span data-stu-id="d3097-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requires the use of the **ClientCredentials** class for programmatically passing credentials.</span></span> <span data-ttu-id="d3097-117">**AcceptCredentialsInUri**プロパティのバインドでは無視されます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] URI 内の資格情報を渡すようにします。</span><span class="sxs-lookup"><span data-stu-id="d3097-117">The **AcceptCredentialsInUri** binding property is ignored by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to prevent passing credentials in the URI.</span></span>  
  
 <span data-ttu-id="d3097-118">次の例を使用する方法を示しています、**資格情報**で SQL Server データベースの資格情報を設定するプロパティ、 **ChannelFactory**です。</span><span class="sxs-lookup"><span data-stu-id="d3097-118">The following example shows how to use the **Credentials** property to set credentials for the SQL Server database on a **ChannelFactory**.</span></span>  
  
```  
// Create binding and endpoint  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 <span data-ttu-id="d3097-119">次の例を使用する方法を示しています、 **ClientCredentials** WCF クライアントで SQL Server データベースの資格情報を設定するクラス。</span><span class="sxs-lookup"><span data-stu-id="d3097-119">The following example shows how to use the **ClientCredentials** class to set credentials for the SQL Server database on a WCF client.</span></span>  
  
```  
// Initialize a new client for the SELECT operation on the Employee table   
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient(binding,address);  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="d3097-120">どのことができます提供するにはより安全なデータ交換プロセス境界を越えてしますか。</span><span class="sxs-lookup"><span data-stu-id="d3097-120">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="d3097-121">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がホストされているアプリケーションまたはサービスを利用するとインプロセスでします。</span><span class="sxs-lookup"><span data-stu-id="d3097-121">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="d3097-122">アダプターがホストされているので、インプロセスでコンシューマーとコンシューマー間で交換されるメッセージのセキュリティを提供する必要はありません、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d3097-122">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="d3097-123">ただし、使用のアプリケーションまたはサービスは、別のサービスまたはクライアントにプロセス境界を越えて機密データベースの情報を含むメッセージを送信する場合は、環境内でこのデータの適切な保護対策を提供するメジャーを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3097-123">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="d3097-124">クライアントとサービス間で送信されるセキュリティで保護されたメッセージに役立つ多くのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3097-124"> provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="d3097-125">クライアントとサービス間で送信されるセキュリティで保護されたメッセージに保護の詳細について[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を参照してください[Services のセキュリティ保護とクライアント](https://msdn.microsoft.com/library/ms734736.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="d3097-125">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see [Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx).</span></span> <span data-ttu-id="d3097-126">セキュリティに関する一般情報についての機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供を参照してください[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="d3097-126">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d3097-127">参照</span><span class="sxs-lookup"><span data-stu-id="d3097-127">See Also</span></span>  
[<span data-ttu-id="d3097-128">SQL アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="d3097-128">Secure your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[<span data-ttu-id="d3097-129">SQL アダプタをセキュリティで保護するベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="d3097-129">Best practices to secure the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)