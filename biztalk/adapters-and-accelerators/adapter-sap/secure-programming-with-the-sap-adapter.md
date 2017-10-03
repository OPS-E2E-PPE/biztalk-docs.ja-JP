---
title: "SAP アダプターをセキュリティで保護された使用したプログラミング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, considerations when programming on the adapter
- security, secure data exchange
- security, setting credentials in code
ms.assetid: bd5da271-90f1-4a64-9138-a51048a16648
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2be84abdc7b645d9b2aaeea87e5ccabf0075e76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="secure-programming-with-the-sap-adapter"></a>SAP アダプターをセキュリティで保護された使用したプログラミング
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>どのように保護する資格情報を使用する場合、アダプター サービス参照を Visual Studio プラグインを追加しますか?  
 使用すると、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントを作成するには、ユーザー名と、SAP システムのパスワードを入力する必要があります。 行う必要がありますのみから、**セキュリティ**タブで、**アダプターの構成** ダイアログ ボックス。 SAP を入力してから資格情報を**セキュリティ**に直接の代わりにタブ、 **Uri**フィールドに、次を確認します。  
  
-   資格情報は表示されません、 **Uri**のフィールド、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]  ダイアログ ボックスが、コンピューター画面にアクセスできる人が読み取ることができます。  
  
-   構成では、資格情報は表示されませんファイルを[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
 使用して、WCF クライアントを生成する方法について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください、SAP システムのユーザー名とパスワードを入力する方法を含む[Visual Studio での SAP 操作のメタデータの取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>コードで資格情報の設定のベスト プラクティスとは  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供、 **ClientCredentials**などのクライアント通信オブジェクトの資格情報を構成するためのクラス、 **ChannelFactory**サービスで自身を認証に使用します。 使用して、 **ClientCredentials**クラス、することを確認 WCF はどのような認証メカニズムは、そのオブジェクトのチャネル スタックで指定し、クライアントとサービス間の交換に適用します。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]がホストされている、インプロセスでその処理を行うアプリケーションでは使用する命令型、 **ClientCredentials**クラスを利用するアプリケーションが使用している通信オブジェクトはクライアントで資格情報を設定します。 これを行うことをお勧めただしと見なされます、します。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の使用が推奨、 **ClientCredentials**クラスを通じて、 **AcceptCredentialsInUri**プロパティをバインドします。 このプロパティは、アダプターは、ユーザー名と接続 URI 内の SAP システムのパスワードを受け入れますかどうかを指定します。 **AcceptCredentialsInUri**の既定値は**false**、つまり、接続 URI には、資格情報が含まれている場合に、アダプターが例外をスローします。 設定することができます**AcceptCredentialsInUri**に**true**接続 URI の資格情報を指定します。 実際には、行う必要があります。 特定の場合たとえば、サービス ホストのエンドポイントに対してまたはの接続 URI を指定すると、 **IReplyChannel**受信シナリオでします。  
  
 次の例を使用する方法を示しています、 **ClientCredentials** WCF クライアントでの SAP システムの資格情報を設定するクラス。  
  
```  
SAPBinding binding = new SAPBinding();  
  
// Set endpoint address  
EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
// Create client and set credentials  
RfcClient rfcClient = new RfcClient(binding, endpointAddress);  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>どのことができます提供するにはより安全なデータ交換プロセス境界を越えてしますか。  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]がホストされているアプリケーションまたはサービスを利用するとインプロセスでします。 アダプターがホストされているので、インプロセスでコンシューマーとコンシューマー間で交換されるメッセージのセキュリティを提供する必要はありません、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 ただし、使用のアプリケーションまたはサービスは、別のサービスまたはクライアントにプロセス境界を越えて機密データベースの情報を含むメッセージを送信する場合は、環境内でこのデータの適切な保護対策を提供するメジャーを行う必要があります。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]クライアントとサービス間で送信されるセキュリティで保護されたメッセージに役立つ多くのオプションを提供します。 クライアントとサービス間で送信されるセキュリティで保護されたメッセージに保護の詳細について[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を参照してください[Services のセキュリティ保護とクライアント](https://msdn.microsoft.com/library/ms734736.aspx)です。 セキュリティに関する一般情報についての機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供を参照してください[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)です。  
  
## <a name="see-also"></a>参照  
[SAP アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[SAP アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   