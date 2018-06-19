---
title: WCF サービス モデルを使用して、Siebel アダプターとビジネス サービス メソッドを呼び出す |Microsoft ドキュメント
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
ms.openlocfilehash: 27eafcbfadc353e8aed9430e2d1bed3ef9e16017
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222178"
---
# <a name="invoke-business-service-methods-with-the-siebel-adapter-using-the-wcf-service-model"></a>WCF サービス モデルを使用して、Siebel アダプターとビジネス サービス メソッドを呼び出す
Siebel ビジネス サービスのターゲット メソッドであること、WCF クライアントを作成できます。 WCF クライアントを使用して、Siebel システムでこれらのメソッドを呼び出すことができます。 [ビジネス サービス] ノードに表示された Siebel ビジネス サービス、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。 各ビジネス サービスによって公開されるメソッドは、そのサービスに対応するノードの下に表示されます。 」の手順を行うことができる[Siebel アダプターと WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-siebel/overview-of-the-wcf-service-model-with-the-siebel-adapter.md)ビジネス サービスの WCF クライアントを生成して、サービスのメソッドの呼び出しに使用します。  
  
 次のコードを呼び出す、WCF クライアントを使用して、 **Execute**タイムスタンプ ビジネス サービスのメソッドです。 Siebel サーバーのローカル時刻で返される、タイムスタンプは、コンソールに書き込まれます。 によって生成された構成ファイルからこの例では、WCF クライアントが初期化されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 生成された構成ファイルの例は、次を参照してください。 [Siebel システムの WCF クライアントを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)です。  
  
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