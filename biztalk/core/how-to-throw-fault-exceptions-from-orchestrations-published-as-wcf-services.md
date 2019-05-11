---
title: WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, WCF services
- WCF services, orchestrations
- WCF services, errors
- orchestrations, WCF services
ms.assetid: 89f57841-d40e-4a5a-90a8-5556a2766c03
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49be352326a789e77d84cb5ecb77fd0f48c5e1f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383692"
---
# <a name="how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services"></a>WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法
オーケストレーションから送信できる SOAP エラーの 2 つの種類: 型指定されており、SOAP エラーを型指定されていません。 操作が必要がある型指定された SOAP エラーは、 **System.ServiceModel.FaultContractAttribute**カスタム SOAP エラーの種類を指定します。 型指定されていない SOAP エラーは、操作のコントラクトで指定されていないことです。  
  
 WCF アダプタでは、WCF サービスとして公開されたオーケストレーションの型指定されたエラー コントラクト例外を処理することはできません。 ただし、型指定されていない SOAP エラーは、常に、オーケストレーションまたはパイプラインによって返されることができます。 型指定されていない、SOAP エラーを返すには、設定する必要があります、 **System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults**または情報を取得する WCF クライアントを許可するように、構成ファイルで、受信場所でについては、内部サービス操作例外。  
  
 次のコードでは、構成ファイルでプロパティを設定する方法を示します。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <serviceBehaviors>  
                <behavior name="ServiceBehaviorConfiguration">  
                    <serviceDebug includeExceptionDetailInFaults="true" />  
                </behavior>  
            </serviceBehaviors>  
        </behaviors>  
</configuration>  
```  
  
## <a name="see-also"></a>参照  
 [オーケストレーションで型指定されたエラー コントラクトを処理する方法](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)