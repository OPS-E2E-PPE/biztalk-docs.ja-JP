---
title: "Oracle E-business Suite アダプターで WCF サービス モデルの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aeeac8a4-a4bc-4963-951c-0c806e232f1e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f40b22865ca45cbd10823f6c514f75e5965f1df5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターで WCF サービス モデルの概要
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]を WCF サービスとして、Oracle E-business Suite システムを公開します。 ストアド プロシージャを呼び出す例については、Oracle E-business Suite アイテムに対して操作を実行するには、さらに、Oracle E-business Suite で操作を実行すると、アダプターでの操作を呼び出します。 コードは、アダプターによって提示される WCF サービスのクライアントとして機能します。  
  
 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作は、このインターフェイスのメソッドとして表されます。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF が使用するアダプターを公開するメタデータから対象となる操作について、このインターフェイスを生成するツールを提供します。 これらのツールでは、サービス インターフェイスの公開操作の呼び出しに使用できる WCF クライアント クラスも作成します。 クライアント アプリケーションは、アダプターの操作の呼び出しに WCF クライアント クラスのメソッドを呼び出すことができます。  
  
 次のセクションでは、モデルを使用して、WCF サービスと WCF クライアントの操作を呼び出す方法について説明します。  
  
## <a name="invoking-operations-on-the-oracle-e-business-suite-with-a-wcf-client"></a>WCF クライアントと Oracle E-business Suite での操作を呼び出す  
 モデルを使用して、WCF サービスで操作を呼び出す、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、まず対象の操作用の WCF クライアント クラスを生成する必要があります。 このクラスでは、WCF クライアントのインスタンスを作成し、Oracle E-business Suite でこれらの操作を実行するには、そのメソッドを呼び出すことができます。  
  
#### <a name="to-invoke-operations-on-the-oracle-e-business-adapter"></a>Oracle E-business アダプターの操作を呼び出す  
  
1.  WCF クライアント クラスとヘルパー コードを生成します。 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) Oracle E-business Suite の成果物を対象と WCF クライアント クラスを生成する作業します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [Oracle E ビジネス ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。  
  
2.  WCF クライアント インスタンスを作成し、WCF クライアントを構成します。 WCF クライアントを構成すると、バインディングと、クライアントが使用するエンドポイント アドレス (接続 URI) を指定することがあります。 これは、コードで命令として記述または構成で宣言によって行うことができます。 次のコードを作成する WCF クライアントを対象とする、**顧客インターフェイス**で同時実行プログラム、**債権**Oracle E-business suite アプリケーション。 また、Oracle E-business Suite の資格情報を設定します。 WCF クライアントは、構成から初期化されます。  
  
    ```  
    ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR"); //picking the binding and address from app.config  
  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!NOTE]
    >  コードでクライアントのバインディングとエンドポイント アドレスを指定するか、app.config 構成ファイルで宣言することができます。 上記のコード スニペットは、後者は使用します。 いずれかのアプローチを使用する方法の詳細については、次を参照してください。 [for Oracle E-business Suite には、クライアント バインディングを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)です。  
  
3.  WCF クライアントを開きます。  
  
    ```  
    client.Open();  
    ```  
  
4.  Oracle E-business Suite での操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。 次のコードを呼び出す、**顧客インターフェイス**でプログラムを同時、**債権**Oracle E-business suite アプリケーションです。  
  
    ```  
    string Result = client.RACUST(null, null, null, description, null, recipro_cust, org_id);  
    ```  
  
     **RACUST**顧客インターフェイスの同時実行プログラムの実際の名前を指定します。 **お客様のインターフェイス**同時実行プログラムのわかりやすい名前を指定します。  
  
5.  WCF クライアントを閉じます。  
  
    ```  
    client.Close();  
    ```  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションの開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)