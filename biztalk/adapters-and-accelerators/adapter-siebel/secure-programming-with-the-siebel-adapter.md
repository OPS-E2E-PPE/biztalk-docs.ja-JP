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
# <a name="secure-programming-with-the-siebel-adapter"></a>Siebel アダプターをセキュリティで保護された使用したプログラミング
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>どのように保護する資格情報を使用する場合、アダプター サービス参照を Visual Studio プラグインを追加しますか?  
 使用すると、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントを作成するには、ユーザー名と Siebel システムのパスワードを入力する必要があります。 行う必要がありますのみから、**セキュリティ**タブで、**アダプターの構成** ダイアログ ボックス。 Siebel を入力してから資格情報を**セキュリティ**に直接の代わりにタブ、 **Uri**フィールドに、次を確認します。  
  
-   資格情報は表示されません、 **Uri**のフィールド、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]  ダイアログ ボックスが、コンピューター画面にアクセスできる人が読み取ることができます。  
  
-   構成では、資格情報は表示されませんファイルを[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
 使用して、WCF クライアントを生成する方法について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください、Siebel システムのユーザー名とパスワードを入力する方法を含む[Siebel 操作の Visual Studio でのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)です。  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>コードで資格情報の設定のベスト プラクティスとは  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供、 **ClientCredentials**などのクライアント通信オブジェクトの資格情報を構成するためのクラス、 **ChannelFactory**サービスで自身を認証に使用します。 使用して、 **ClientCredentials**クラス、することを確認 WCF はどのような認証メカニズムは、そのオブジェクトのチャネル スタックで指定し、クライアントとサービス間の交換に適用します。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]がホストされている、インプロセスでその処理を行うアプリケーションでは使用する命令型、 **ClientCredentials**クラスを利用するアプリケーションが使用している通信オブジェクトはクライアントで資格情報を設定します。 これを行うことをお勧めただしと見なされます、します。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]の使用が推奨、 **ClientCredentials**クラスを通じて、 **AcceptCredentialsInUri**プロパティをバインドします。 このプロパティは、アダプターは、ユーザー名と接続 URI で Siebel システムのパスワードを受け入れますかどうかを指定します。 **AcceptCredentialsInUri**の既定値は**false**、つまり、接続 URI には、資格情報が含まれている場合に、アダプターが例外をスローします。 設定することができます**AcceptCredentialsInUri**に**true**接続 URI の資格情報を指定します。 実際には、行う必要があります。 特定の場合たとえば、ときに使用する、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) WCF クライアント クラスを生成するのに Siebel システムの成果物のためです。  
  
 次の例を使用する方法を示しています、**資格情報**Siebel システムの資格情報を設定するクラス、 **ChannelFactory**です。  
  
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
  
 次の例を使用する方法を示しています、 **ClientCredentials** WCF クライアントで Siebel システムの資格情報を設定するクラス。  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
BusinessObjects_Account_Account_OperationClient accountAccountClient = new BusinessObjects_Account_Account_OperationClient ("SiebelBinding_BusinessObjects_Account_Account_Operation");  
  
// Set user name and password  
accountAccountClient.ClientCredentials.UserName.UserName = "YourUserName";  
accountAccountClient.ClientCredentials.UserName.Password = "YourPassword";  
  
// Open the client  
accountAccountClient.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>どのことができます提供するにはより安全なデータ交換プロセス境界を越えてしますか。  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]がホストされているアプリケーションまたはサービスを利用するとインプロセスでします。 アダプターがホストされているので、インプロセスでコンシューマーとコンシューマー間で交換されるメッセージのセキュリティを提供する必要はありません、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 ただし、使用のアプリケーションまたはサービスは、別のサービスまたはクライアントにプロセス境界を越えて機密データベースの情報を含むメッセージを送信する場合は、環境内でこのデータの適切な保護対策を提供するメジャーを行う必要があります。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]クライアントとサービス間で送信されるセキュリティで保護されたメッセージに役立つ多くのオプションを提供します。 クライアントとサービス間で送信されるセキュリティで保護されたメッセージに保護の詳細について[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を参照してください[Services のセキュリティ保護とクライアント](https://msdn.microsoft.com/library/ms734736.aspx)です。 セキュリティに関する一般情報についての機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供を参照してください[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)です。
  
## <a name="see-also"></a>参照  
 [Siebel アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)  
[Siebel アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)