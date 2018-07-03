---
title: Oracle EBS アダプターを使用したプログラミングにセキュリティで保護された |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35b494f8-cb21-45c2-9bb4-097ba59ec52c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eae7e2c1be56a886578f7bba83901f218c42b94e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972179"
---
# <a name="secure-programming-with-the-oracle-ebs-adapter"></a>Oracle EBS アダプターを使用した安全なプログラミング
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>保護するには資格情報を使用する場合、アダプター サービス参照を Visual Studio プラグインを追加しますか?  
 使用すると、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントを作成する必要がありますユーザー名とパスワードの入力、Oracle E-business Suite。 これからをのみ行う必要があります、**セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。 Oracle を入力してから資格情報を**セキュリティ**に直接の代わりにタブ、 **URI の構成**フィールドに、以下を確認すること。  
  
- 資格情報は表示されません、 **URI の構成**のフィールド、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ダイアログ ボックスで、コンピューターの画面にアクセスできる人が読み取ることができます。  
  
- 資格情報は、構成には表示されませんファイルを[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
  使用して WCF クライアントを生成する方法について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください、Oracle E-business Suite のユーザー名とパスワードを入力する方法を含む[のVisualStudioでのOracleE-businessSuite操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>コードで資格情報の設定のベスト プラクティスとは  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 提供します、 **ClientCredentials**などのクライアント通信オブジェクトを資格情報を構成するためのクラス、 **ChannelFactory**を使用して、サービスで自身を認証します。 使用して、 **ClientCredentials**クラス、することを確認 WCF はどのような認証メカニズムは、そのオブジェクトのチャネル スタックで指定された、クライアントとサービス間の交換に適用します。  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]がホストされているプロセス内のコンシューマー側アプリケーションを使用する命令型、 **ClientCredentials**コンシューマー側アプリケーションが使用する通信オブジェクトをクライアントの資格情報を設定するクラス。 ただし、これを行うことをお勧めと捉えられます、します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の使用が推奨、 **ClientCredentials**クラス。 このプロパティは、アダプターは、ユーザー名と URI の接続で Oracle データベースのパスワードを受け入れますかどうかを指定します。 **AcceptCredentialsInUri**の既定値は**false**、つまり、接続 URI には、資格情報が含まれている場合に、アダプターが例外をスローします。 設定することができます**AcceptCredentialsInUri**に**true**クライアント アプリケーションで必要な場合は、接続 URI での資格情報を提供します。  
  
 次の例は、使用する方法を示します、**資格情報**Oracle E-business suite の資格情報を設定するプロパティを**ChannelFactory**します。  
  
```  
// Create binding and endpoint  
OracleEBSBinding binding = new OracleEBSBinding();  
EndpointAddress address = new EndpointAddress("oracleebs://ebs-instance");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 次の例は、使用する方法を示します、 **ClientCredentials** WCF クライアントで、Oracle E-business Suite の資格情報を設定するクラス。  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
ConcurrentPrograms_ARClient client =   
  new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>な方法はより安全なデータの交換プロセスの境界を越えてでしょうか。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]がホストされているアプリケーションまたはサービスで使用することでインプロセスでします。 アダプターがホストされるため、インプロセスで、コンシューマーとコンシューマー間で交換されるメッセージのセキュリティを提供する必要はありません、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 ただし、使用するアプリケーションまたはサービスを別のサービスまたはクライアントのプロセス境界を越えて機密性の高いデータベースの情報を含むメッセージを送信する場合は、環境内でこのデータを適切に保護を提供するメジャーを行う必要があります。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] セキュリティで保護されたメッセージがクライアントとサービス間で送信する際に役立つ多くのオプションを提供します。 セキュリティで保護されたメッセージがクライアントとサービスの間で送信することの詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]で「サービスとクライアントのセキュリティで保護する」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=89725](http://go.microsoft.com/fwlink/?LinkId=89725)します。 セキュリティに関する一般的な情報が機能するの[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますが、「Windows Communication Foundation Security」をご覧[ http://go.microsoft.com/fwlink/?LinkId=89726](http://go.microsoft.com/fwlink/?LinkId=89726)します。  
  
## <a name="see-also"></a>参照  
 [Oracle EBS アプリケーションをセキュリティで保護する](secure-your-oracle-ebs-applications.md)