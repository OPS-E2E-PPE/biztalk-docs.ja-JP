---
title: Siebel アダプターで WCF サービス モデルの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke operations on the Siebel system with a WCF client
- WCF service model, overview of
ms.assetid: 0e812473-0f50-4972-8b07-ec8edc2ef000
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efeed6a398787870b4cccefddfbbdd7833c28e86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371242"
---
# <a name="overview-of-the-wcf-service-model-with-the-siebel-adapter"></a>Siebel アダプターで WCF サービス モデルの概要
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] WCF サービスとしての Siebel システムを公開します。 Siebel システム成果物の例では、Siebel ビジネス サービスのメソッドを呼び出すために操作を実行するには、さらに、Siebel システムでの操作を実行すると、アダプターでの操作を呼び出します。 そのため、コードは、アダプターによって提示される WCF サービスのクライアントとして機能します。  
  
 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作はこのインターフェイスのメソッドとして表されます。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF アダプターを公開するメタデータからの対象となる操作には、このインターフェイスを生成するためのツールを提供するとします。 これらのツールでは、サービス インターフェイスで公開されている操作の呼び出しに使用できる WCF クライアント クラスも作成します。 クライアント アプリケーションでは、アダプターの操作を呼び出すための WCF クライアント クラスのメソッドを呼び出すことができます。  
  
 次のセクションでは、WCF クライアントでの操作を呼び出す、WCF サービス モデルを使用する方法について説明します。  
  
## <a name="invoking-operations-on-the-siebel-system-with-a-wcf-client"></a>WCF クライアントで Siebel システムの操作を呼び出す  
 WCF サービス モデルを使用して、操作を呼び出してする、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、まずターゲットの WCF クライアント クラスを生成する必要があります。 WCF クライアントでは、このクラスのインスタンスを作成し、Siebel システムでこれらの操作を実行するには、そのメソッドを呼び出すことができます。  
  
#### <a name="to-invoke-operations-on-the-siebel-adapter"></a>Siebel アダプターの操作を呼び出す  
  
1. WCF クライアント クラスとヘルパー コードを生成します。 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) Siebel システムの成果物を対象とした WCF クライアント クラスを生成する作業します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [Siebel ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)します。  
  
2. WCF クライアントのインスタンスを作成し、WCF クライアントを構成します。 WCF クライアントを構成するには、バインドと、クライアントが使用するエンドポイント アドレス (URI の接続) を指定する必要があります。 コードで強制的に、または構成で宣言的に、これを行うことができます。 WCF クライアントを構成する方法の詳細については、次を参照してください。 [Siebel システムの WCF クライアントを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)します。 次のコードでは、タイムスタンプの Siebel ビジネス サービスを対象とする WCF クライアントを作成します。 また、Siebel システムの資格情報を設定します。 WCF クライアントは、構成から初期化されます。  
  
   ```  
   BusinessServices_TimeStamp_OperationClient client =  
       new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
   client.ClientCredentials.UserName.UserName = "YourUserName";  
   client.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. WCF クライアントを開きます。  
  
   ```  
   client.Open();  
   ```  
  
4. Siebel システムの操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。 次のコードを呼び出す、 **Execute**メソッドを呼び出す、WCF クライアントの**Execute** Siebel システムのタイムスタンプのビジネス サービスのメソッド。  
  
   ```  
   // Create a parameter to hold the results and then invoke the Execute method of the TimeStamp business service.  
   microsoft.lobservices.siebel._2007._03.BusinessServices.TimeStamp.ExecuteResponseRecord er;  
   er = client.Execute();  
   ```  
  
5. WCF クライアントを閉じます。  
  
   ```  
   client.Close();  
   ```  
  
   Siebel ビジネス サービス メソッドの呼び出しの詳細については、次を参照してください[WCF サービス モデルを使用して Siebel アダプターでのビジネス サービス メソッドの呼び出し。](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md) 
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)