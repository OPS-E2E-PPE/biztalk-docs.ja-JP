---
title: Windows Communication Foundation での操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1728d2f-ac74-446e-a36f-4b645a6e042a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c6b5344b8fb2c5a5ba7a68b112adb50133198c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263770"
---
# <a name="operations-in-windows-communication-foundation"></a>Windows Communication Foundation での操作
このセクションでは、BAM WCF インターセプタによってサポートされているカスタム操作について説明します。  
  
 操作名要素に Action 属性が含まれている場合は、以下のようになります。  
  
1.  操作名は、クライアントとサーバーの両方の name 属性によって識別される名前です。  
  
2.  応答パス (コールバック応答)、クライアント応答、およびサービス応答の場合、操作名は同じ属性によって識別されます。  
  
> [!NOTE]
>  応答メッセージに含まれているノードには、name 属性によって指定された名前に単語 "Result" を追加した名前が付けられます。 XPath がこの命名規則に従っていることを確認する必要があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [AutoGenerateCorrelationToken](../core/autogeneratecorrelationtoken.md)  
  
-   [GetContextProperty](../core/getcontextproperty1.md)  
  
-   [GetEndpointName](../core/getendpointname.md)  
  
-   [GetOperationName](../core/getoperationname.md)  
  
-   [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md)  
  
-   [XPath](../core/xpath.md)