---
title: Oracle E-business Suite アダプターで WCF サービス モデルの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aeeac8a4-a4bc-4963-951c-0c806e232f1e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b0a76ea41151e50b90d060ea60654b2c3287201
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375051"
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターで WCF サービス モデルの概要
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] WCF サービスとして、Oracle E-business Suite システムを公開します。 、ストアド プロシージャを呼び出す例については、Oracle E-business Suite の成果物に対して操作を実行するには、さらに、Oracle E-business suite 操作を実行すると、アダプターでの操作を呼び出します。 コードは、アダプターによって提示される WCF サービスのクライアントとして機能します。  
  
 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作はこのインターフェイスのメソッドとして表されます。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF アダプターを公開するメタデータからの対象となる操作には、このインターフェイスを生成するためのツールを提供するとします。 これらのツールでは、サービス インターフェイスで公開されている操作の呼び出しに使用できる WCF クライアント クラスも作成します。 クライアント アプリケーションでは、アダプターの操作を呼び出すための WCF クライアント クラスのメソッドを呼び出すことができます。  
  
 次のセクションでは、WCF クライアントでの操作を呼び出す、WCF サービス モデルを使用する方法について説明します。  
  
## <a name="invoking-operations-on-the-oracle-e-business-suite-with-a-wcf-client"></a>WCF クライアントでの Oracle E-business Suite での操作を呼び出す  
 WCF サービス モデルを使用して、操作を呼び出してする、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、まずターゲットの WCF クライアント クラスを生成する必要があります。 WCF クライアントでは、このクラスのインスタンスを作成し、Oracle E-business Suite でこれらの操作を実行するには、そのメソッドを呼び出します。  
  
#### <a name="to-invoke-operations-on-the-oracle-e-business-adapter"></a>Oracle E-business アダプターの操作を呼び出す  
  
1. WCF クライアント クラスとヘルパー コードを生成します。 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) Oracle E-business Suite の成果物を対象とした WCF クライアント クラスを生成する作業します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [Oracle E-business ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。  
  
2. WCF クライアントのインスタンスを作成し、WCF クライアントを構成します。 WCF クライアントを構成するには、バインドと、クライアントが使用するエンドポイント アドレス (URI の接続) を指定する必要があります。 コードで強制的に、または構成で宣言的に、これを行うことができます。 次のコード作成、WCF クライアントを対象とする、**顧客インターフェイス**で同時実行プログラム、 **Receivables** Oracle E-business Suite でのアプリケーション。 また、Oracle E-business Suite の資格情報を設定します。 WCF クライアントは、構成から初期化されます。  
  
   ```  
   ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR"); //picking the binding and address from app.config  
  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
   > [!NOTE]
   >  コードでクライアント バインディングとエンドポイント アドレスを指定するか、app.config 構成ファイルで宣言します。 上記のコード スニペットは、後者は使用します。 いずれかのアプローチを使用する方法の詳細については、次を参照してください。[クライアント バインディングを構成する、Oracle E-business suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)します。  
  
3. WCF クライアントを開きます。  
  
   ```  
   client.Open();  
   ```  
  
4. Oracle E-business suite 操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。 次のコードを呼び出す、**顧客インターフェイス**で同時実行プログラム、 **Receivables** Oracle E-business Suite でのアプリケーション。  
  
   ```  
   string Result = client.RACUST(null, null, null, description, null, recipro_cust, org_id);  
   ```  
  
    **RACUST**顧客インターフェイスの同時実行プログラムの実際の名前を指定します。 **顧客インターフェイス**同時実行プログラムの表示名です。  
  
5. WCF クライアントを閉じます。  
  
   ```  
   client.Close();  
   ```  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションの開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)