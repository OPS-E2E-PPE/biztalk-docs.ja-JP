---
title: クライアントの Oracle データベースのバインドの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- client binding, specifying in code
- WCF client, creating
- client binding, specifying in configuration file
ms.assetid: f18c7296-c28a-4dec-9514-5299c8c2dffe
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59cec0ed0891a749b886e80937059198af50cc82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376753"
---
# <a name="configure-a-client-binding-for-the-oracle-database"></a>クライアントの Oracle データベースのバインドを構成します。
WCF クライアント クラスを生成した後は、WCF クライアント (インスタンス) の作成し、使用するメソッドの呼び出し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 操作のための WCF クライアント クラスとヘルパー コードを生成する方法についてを[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公開を参照してください[Oracle データベース ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。  
  
 WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。 エンドポイント アドレスが有効な Oracle 接続 URI を含める必要があり、バインドは、Oracle DB のバインドのインスタンスである必要があります (**OracleDBBinding**)。 Oracle の接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。 接続 URI の一部としてユーザーの資格情報を指定しないことをお勧めします。 代わりに使用することがあります、 **ClientCredentials**このトピックで説明したように、WCF クライアントのプロパティ。  
  
 コードまたは構成ファイルでは、Oracle DB のバインドとエンドポイント アドレスを指定できます。 使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。 このファイルに情報を反映するバインドのプロパティと接続 (資格情報) を除くと Oracle データベースに接続するときに指定した構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>バインディングとエンドポイント アドレスを指定するコード  
 次のコードでは、コードでバインディングとエンドポイント アドレスを指定することで、WCF クライアントを作成する方法を示します。 使用して Oracle 資格情報を指定することをお勧め、 **ClientCredentials**接続エンドポイントのアドレスの指定された URI ではなく、WCF クライアントのプロパティ。  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by using a binding object and endpoint address  
OracleDBBinding odbBinding = new OracleDBBinding();  
EndpointAddress odbAddress = new EndpointAddress("OracleDb://ADAPTER");  
  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient(odbBinding, odbAddress);  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>構成ファイルでバインディングとエンドポイント アドレスを指定します。  
 次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定することで、WCF クライアントを作成する方法を示します。  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by specifying the client endpoint information in app.config  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient("OracleDBBinding_SCOTT.Table.EMP");  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
 次の XML は、EMP テーブルの作成、構成ファイル、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00"  
                    dataFetchSize="65536" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" longDatatypeColumnSize="32767" pollingStatement=""  
                    postPollStatement="" pollingInterval="500" useOracleConnectionPool="false"  
                    minPoolSize="1" maxPoolSize="100" incrPoolSize="5" decrPoolSize="1"  
                    connectionLifetime="0" transactionIsolationLevel="ReadCommitted"  
                    enablePerformanceCounters="false" acceptCredentialsInUri="false"  
                    enableBizTalkCompatibilityMode="false" />  
            </oracleDBBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracledb://adapter/" binding="oracleDBBinding"  
                bindingConfiguration="OracleDBBinding" contract="SCOTTTableEMP"  
                name="OracleDBBinding_SCOTT.Table.EMP" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
 プロジェクトには、複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイントのエントリ。 WCF クライアントの各エントリは、バインド構成とターゲットの Oracle データベース アイテム; に基づいて一意の名前になりますたとえば、"OracleDBBinding_SCOTT します。Table.EMP"。 プロジェクトで、WCF クライアントを作成するための複数回を接続する場合は、複数のバインド構成エントリが作成されます、接続ごとに 1 つ。 これらのバインド構成エントリは次の方法で名前が付けられます。OracleDBBinding1、OracleDBBinding2、しにします。 特定の接続中に作成される各クライアントのエンドポイント エントリは、その接続中に作成されたバインド エントリを参照します。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベースのアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)   
 [Oracle データベース ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)   
 [Oracle Database 接続 URI を作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)   
 [WCF チャネル モデルを使用して Oracle データベースのアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)