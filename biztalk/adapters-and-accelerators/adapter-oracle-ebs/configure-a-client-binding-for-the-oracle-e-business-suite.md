---
title: Oracle E-business suite バインド クライアントの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1347cbca-5567-43f8-a75e-a23b108692bc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c05dadb7265a555a4162b73351b3783203f203d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375725"
---
# <a name="configure-a-client-binding-for-the-oracle-e-business-suite"></a>Oracle E-business suite バインド クライアントを構成します。
WCF クライアント クラスを生成した後は、WCF クライアント (インスタンス) の作成し、使用するメソッドの呼び出し、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
 WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。 エンドポイント アドレスが有効な Oracle E-business Suite 接続 URI を含める必要があり、バインドは、Oracle E-business Suite バインドのインスタンスである必要があります (**OracleEBSBinding**)。 Oracle E-business Suite 接続 URI の詳細については、次を参照してください。 [、Oracle E-business Suite への接続を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)します。 接続 URI の一部としてユーザーの資格情報を指定しないことをお勧めします。 代わりに使用することがあります、 **ClientCredentials**このトピックで説明したように、WCF クライアントのプロパティ。  
  
 コードまたは構成ファイルでは、Oracle E-business Suite バインドおよびエンドポイント アドレスを指定できます。 使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。 このファイルに情報を反映するバインドのプロパティと接続 (資格情報) を除くと Oracle E-business Suite に接続するときに指定した構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>バインディングとエンドポイント アドレスを指定するコード  
 次のコードを使用してコードでバインディングとエンドポイント アドレスを指定することで、WCF クライアントを作成する方法を示しています、 **ClientCredentials** WCF クライアントのプロパティ。  
  
```  
//Create an Oracle EBS binding and set the binding properties  
OracleEBSBinding binding = new OracleEBSBinding();  
binding.OracleUserName = "myOracleEBSUser";  
binding.OraclePassword = "myOracleEBSPassword";  
binding.OracleEBSResponsibilityName = "Responsibility";  
binding.OracleEBSOrganizationId = "204";  
  
//Create the client endpoint   
EndpointAddress address = new EndpointAddress("oracleebs://<oracleebs_instance_name>/");  
  
//Create the client and specify the credentials  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient(binding,address);  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
//Open the client  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>構成ファイルでバインディングとエンドポイント アドレスを指定します。  
 次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定することで、WCF クライアントを作成する方法を示します。  
  
```  
//Create the client by specifying the endpoint name in the app.config. In this case, the binding properties  
//must also be specified in the app.config.  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
//Specify the credentials   
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
client.Open();  
```  
  
 次の XML の作成、構成ファイルを示しています、**顧客インターフェイス**によって同時実行プログラム、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <oracleEBSBinding>  
                <binding openTimeout="00:05:00" name="OracleEBSBinding" closeTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" clientCredentialType="Database"  
                    inboundOperationType="Polling" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" pollWhileDataFound="false" pollingInterval="30"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" notifyOnListenerStart="true"  
                    notificationPort="-1" dataFetchSize="65536" longDatatypeColumnSize="32512"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="20" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="true">  
                    <mlsSettings language="" dateFormat="" dateLanguage="" numericCharacters=""  
                        sort="" territory="" comparison="" currency="" dualCurrency=""  
                        iSOCurrency="" calendar="" lengthSemantics="" nCharConversionException="true"  
                        timeStampFormat="" timeStampTZFormat="" timeZone="" />  
                </binding>  
            </oracleEBSBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracleebs://ebs-70-12/" binding="oracleEBSBinding"  
                bindingConfiguration="OracleEBSBinding" contract="ConcurrentPrograms_AR"  
                name="OracleEBSBinding_ConcurrentPrograms_AR" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 プロジェクトには、複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイントのエントリ。 WCF クライアントの各エントリは、バインド構成とターゲットの Oracle E-business Suite の成果物に基づき、一意の名前になります。 プロジェクトで、WCF クライアントを作成するための複数回を接続する場合は、複数のバインド構成エントリが作成されます、接続ごとに 1 つ。 これらのバインド構成エントリは次の方法で名前が付けられます。OracleEBSBinding、OracleEBSBinding1、しにします。 特定の接続中に作成される各クライアントのエンドポイント エントリは、その接続中に作成されたバインド エントリを参照します。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite アプリケーションの開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)