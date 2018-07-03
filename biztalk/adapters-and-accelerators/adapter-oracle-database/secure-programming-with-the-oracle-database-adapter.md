---
title: Oracle データベース アダプターを使用したプログラミングにセキュリティで保護された |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- credentials
- adapter, security considerations when programming on
- credentials, setting in code
- credentials, protecting
- security
ms.assetid: 06213c14-42b8-4d4a-b238-0aedbc27ab6a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15860ad8a0e1f4417229da2a87c83b0a54ea0120
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008187"
---
# <a name="secure-programming-with-the-oracle-database-adapter"></a><span data-ttu-id="446f5-102">Oracle データベース アダプターを使用したプログラミングをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="446f5-102">Secure programming with the Oracle Database adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="446f5-103">保護するには資格情報を使用する場合、アダプター サービス参照を Visual Studio プラグインを追加しますか?</span><span class="sxs-lookup"><span data-stu-id="446f5-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="446f5-104">使用すると、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントを作成するには、ユーザー名と Oracle データベースのパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="446f5-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you must supply a user name and password for the Oracle database.</span></span> <span data-ttu-id="446f5-105">これからをのみ行う必要があります、**セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="446f5-105">You should only do this from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="446f5-106">Oracle を入力してから資格情報を**セキュリティ**に直接の代わりにタブ、 **URI の構成**フィールドに、以下を確認すること。</span><span class="sxs-lookup"><span data-stu-id="446f5-106">By entering the Oracle credentials from the **Security** tab instead of directly into the **Configure a URI** field, you ensure the following:</span></span>  
  
- <span data-ttu-id="446f5-107">資格情報は表示されません、 **Uri**のフィールド、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ダイアログ ボックスで、コンピューターの画面にアクセスできる人が読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="446f5-107">The credentials will not be displayed in the **Uri** field of the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] dialog box where anyone with access to your computer screen can read them.</span></span>  
  
- <span data-ttu-id="446f5-108">資格情報は、構成には表示されませんファイルを[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="446f5-108">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="446f5-109">使用して WCF クライアントを生成する方法について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください、Oracle データベースのユーザー名とパスワードを入力する方法を含む[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)します。</span><span class="sxs-lookup"><span data-stu-id="446f5-109">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the Oracle database, see [Get metadata for Oracle Database operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md).</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="446f5-110">コードで資格情報の設定のベスト プラクティスとは</span><span class="sxs-lookup"><span data-stu-id="446f5-110">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="446f5-111"> 提供します、 **ClientCredentials**などのクライアント通信オブジェクトを資格情報を構成するためのクラス、 **ChannelFactory**を使用して、サービスで自身を認証します。</span><span class="sxs-lookup"><span data-stu-id="446f5-111"> provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="446f5-112">使用して、 **ClientCredentials**クラス、することを確認 WCF はどのような認証メカニズムは、そのオブジェクトのチャネル スタックで指定された、クライアントとサービス間の交換に適用します。</span><span class="sxs-lookup"><span data-stu-id="446f5-112">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="446f5-113">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]がホストされているプロセス内のコンシューマー側アプリケーションを使用する命令型、 **ClientCredentials**コンシューマー側アプリケーションが使用する通信オブジェクトをクライアントの資格情報を設定するクラス。</span><span class="sxs-lookup"><span data-stu-id="446f5-113">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="446f5-114">ただし、これを行うことをお勧めと捉えられます、します。</span><span class="sxs-lookup"><span data-stu-id="446f5-114">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="446f5-115">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の使用が推奨、 **ClientCredentials**クラス。</span><span class="sxs-lookup"><span data-stu-id="446f5-115">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] encourages the use of the **ClientCredentials** class.</span></span> <span data-ttu-id="446f5-116">このプロパティは、アダプターは、ユーザー名と URI の接続で Oracle データベースのパスワードを受け入れますかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="446f5-116">This property specifies whether the adapter will accept the user name and password for the Oracle database in the connection URI.</span></span> <span data-ttu-id="446f5-117">**AcceptCredentialsInUri**の既定値は**false**、つまり、接続 URI には、資格情報が含まれている場合に、アダプターが例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="446f5-117">**AcceptCredentialsInUri** defaults to **false**, which means that the adapter will throw an exception if the connection URI contains credentials.</span></span> <span data-ttu-id="446f5-118">設定することができます**AcceptCredentialsInUri**に**true**接続 URI の資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="446f5-118">You can set **AcceptCredentialsInUri** to **true** to supply credentials in the connection URI.</span></span>  
  
 <span data-ttu-id="446f5-119">次の例は、使用する方法を示します、**資格情報**で Oracle データベースの資格情報を設定するプロパティを**ChannelFactory**します。</span><span class="sxs-lookup"><span data-stu-id="446f5-119">The following example shows how to use the **Credentials** property to set credentials for the Oracle database on a **ChannelFactory**.</span></span>  
  
```  
// Create binding and endpoint  
OracleDBBinding binding = new OracleDBBinding();  
EndpointAddress endpointAddress = new EndpointAddress("oracleDB://Adapter");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open the channel factory  
factory.Open();  
```  
  
 <span data-ttu-id="446f5-120">次の例は、使用する方法を示します、 **ClientCredentials** WCF クライアントでの Oracle データベースの資格情報を設定するクラス。</span><span class="sxs-lookup"><span data-stu-id="446f5-120">The following example shows how to use the **ClientCredentials** class to set credentials for the Oracle database on a WCF client.</span></span>  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
SQLEXECUTEClient sqlExecuteClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE");  
  
// Set user name and password  
sqlExecuteClient.ClientCredentials.UserName.UserName = "SCOTT";  
sqlExecuteClient.ClientCredentials.UserName.Password = "TIGER";  
  
// Open the client  
sqlExecuteClient.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="446f5-121">な方法はより安全なデータの交換プロセスの境界を越えてでしょうか。</span><span class="sxs-lookup"><span data-stu-id="446f5-121">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="446f5-122">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]がホストされているアプリケーションまたはサービスで使用することでインプロセスでします。</span><span class="sxs-lookup"><span data-stu-id="446f5-122">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="446f5-123">アダプターがホストされるため、インプロセスで、コンシューマーとコンシューマー間で交換されるメッセージのセキュリティを提供する必要はありません、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="446f5-123">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="446f5-124">ただし、使用するアプリケーションまたはサービスを別のサービスまたはクライアントのプロセス境界を越えて機密性の高いデータベースの情報を含むメッセージを送信する場合は、環境内でこのデータを適切に保護を提供するメジャーを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="446f5-124">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="446f5-125"> セキュリティで保護されたメッセージがクライアントとサービス間で送信する際に役立つ多くのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="446f5-125"> provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="446f5-126">セキュリティで保護されたメッセージがクライアントとサービスの間で送信することの詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を参照してください[Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="446f5-126">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see [Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx).</span></span> <span data-ttu-id="446f5-127">セキュリティに関する一般的な情報の機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますを参照してください[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="446f5-127">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="446f5-128">参照</span><span class="sxs-lookup"><span data-stu-id="446f5-128">See Also</span></span>  
<span data-ttu-id="446f5-129">[Oracle データベース アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md) </span><span class="sxs-lookup"><span data-stu-id="446f5-129">[Secure your Oracle Database applications](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md) </span></span>  
[<span data-ttu-id="446f5-130">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="446f5-130">Best Practices</span></span>](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)