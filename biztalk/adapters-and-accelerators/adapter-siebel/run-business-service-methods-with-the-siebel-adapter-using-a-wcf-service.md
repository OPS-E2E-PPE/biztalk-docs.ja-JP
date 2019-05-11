---
title: WCF サービス モデルを使用して Siebel アダプターでのビジネス サービス メソッドの呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, invoking business service methods
- business service methods, invoking by using the WCF service model
ms.assetid: b41cf944-efdc-453f-824b-70581e7143e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49ac29960477d3b8d3a845699a2ecf813664b7b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371141"
---
# <a name="invoke-business-service-methods-with-the-siebel-adapter-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Siebel アダプターでのビジネス サービス メソッドの呼び出し
Siebel ビジネス サービスのターゲット メソッドであること、WCF クライアントを作成できます。 WCF クライアントを使用して、Siebel システムでこれらのメソッドを呼び出すことができます。 Siebel ビジネス サービスがビジネス サービス ノードの下に表示される、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 各ビジネス サービスによって公開されるメソッドは、そのサービスに対応するノードの下に表示されます。 」の手順を利用できる[Siebel アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md)ビジネス サービスの WCF クライアントを生成して、サービスのメソッドを呼び出すために使用します。  
  
 次のコードを呼び出す、WCF クライアントを使用して、 **Execute**タイムスタンプのビジネス サービスのメソッド。 Siebel サーバーのローカル時刻で返される、タイムスタンプがコンソールに書き込まれます。 この例では、WCF クライアントがによって生成された構成ファイルから初期化される、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 生成された構成ファイルの例は、次を参照してください。 [Siebel システムの WCF クライアントを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)します。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using microsoft.lobservices.siebel._2007._03.BusinessServices.TimeStamp;  
  
namespace Business_Service  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BusinessServices_TimeStamp_OperationClient client = null;  
  
            try  
            {  
                client =  
                     new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
                client.ClientCredentials.UserName.UserName = "YourUserName";  
                client.ClientCredentials.UserName.Password = "YourPassword";  
                client.Open();  
  
                ExecuteResponseRecord er = client.Execute();  
                Console.WriteLine(er.Time);  
  
                Console.WriteLine("\nHit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine(e.Message);  
            }  
            finally  
            {  
                // Close the client.  
                if (client != null)  
                {  
                    if (client.State == CommunicationState.Opened)  
                        client.Close();  
                    else  
                        client.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)