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
# <a name="how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services"></a><span data-ttu-id="f0ef8-102">WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法</span><span class="sxs-lookup"><span data-stu-id="f0ef8-102">How to Throw Fault Exceptions from Orchestrations Published as WCF Services</span></span>
<span data-ttu-id="f0ef8-103">オーケストレーションから送信できる SOAP エラーの 2 つの種類: 型指定されており、SOAP エラーを型指定されていません。</span><span class="sxs-lookup"><span data-stu-id="f0ef8-103">Two types of SOAP faults can be sent from an orchestration: typed and untyped SOAP faults.</span></span> <span data-ttu-id="f0ef8-104">操作が必要がある型指定された SOAP エラーは、 **System.ServiceModel.FaultContractAttribute**カスタム SOAP エラーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0ef8-104">Typed SOAP faults are those in which an operation has a **System.ServiceModel.FaultContractAttribute** that specifies a custom SOAP fault type.</span></span> <span data-ttu-id="f0ef8-105">型指定されていない SOAP エラーは、操作のコントラクトで指定されていないことです。</span><span class="sxs-lookup"><span data-stu-id="f0ef8-105">Untyped SOAP faults are those that are not specified in the contract for an operation.</span></span>  
  
 <span data-ttu-id="f0ef8-106">WCF アダプタでは、WCF サービスとして公開されたオーケストレーションの型指定されたエラー コントラクト例外を処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0ef8-106">WCF adapters do not support processing typed fault contract exceptions for orchestrations published as WCF services.</span></span> <span data-ttu-id="f0ef8-107">ただし、型指定されていない SOAP エラーは、常に、オーケストレーションまたはパイプラインによって返されることができます。</span><span class="sxs-lookup"><span data-stu-id="f0ef8-107">However, untyped SOAP faults can always be returned by orchestrations or pipelines.</span></span> <span data-ttu-id="f0ef8-108">型指定されていない、SOAP エラーを返すには、設定する必要があります、 **System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults**または情報を取得する WCF クライアントを許可するように、構成ファイルで、受信場所でについては、内部サービス操作例外。</span><span class="sxs-lookup"><span data-stu-id="f0ef8-108">To return an untyped SOAP fault, you need to set the **System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults** on the receive location, or in the config file, to permit WCF clients to obtain information about internal service operation exceptions.</span></span>  
  
 <span data-ttu-id="f0ef8-109">次のコードでは、構成ファイルでプロパティを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f0ef8-109">The following code shows how to set the property in a config file:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0ef8-110">参照</span><span class="sxs-lookup"><span data-stu-id="f0ef8-110">See Also</span></span>  
 [<span data-ttu-id="f0ef8-111">オーケストレーションで型指定されたエラー コントラクトを処理する方法</span><span class="sxs-lookup"><span data-stu-id="f0ef8-111">How to Handle Typed Fault Contracts in Orchestrations</span></span>](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)