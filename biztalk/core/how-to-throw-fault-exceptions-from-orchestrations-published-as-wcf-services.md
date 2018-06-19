---
title: WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 9bf64501f619e74991fafa59b2ab1c2a3e62cbca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255738"
---
# <a name="how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services"></a>WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法
オーケストレーションから送信できる SOAP エラーには、型指定された SOAP エラーと型指定されていない SOAP エラーという 2 種類があります。 型指定された SOAP エラーとは、操作が必要がある、 **System.ServiceModel.FaultContractAttribute**カスタム SOAP エラーの種類を指定します。 型指定されていない SOAP エラーとは、操作のコントラクトで指定されていないエラーのことです。  
  
 WCF アダプタでは、WCF サービスとして公開されたオーケストレーションに関する型指定されたエラー コントラクト例外を処理できません。 ただし、型指定されていない SOAP エラーは、オーケストレーションまたはパイプラインによって常に返すことができます。 型指定されていない SOAP エラーを返すには、設定する必要があります、 **System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults**受信場所で、または情報を取得する WCF クライアントを許可するように、構成ファイルに内部サービス操作例外。  
  
 次のサンプル コードで、構成ファイルにプロパティを設定する方法を示します。  
  
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