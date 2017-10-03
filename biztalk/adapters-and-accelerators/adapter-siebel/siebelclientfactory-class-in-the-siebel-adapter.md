---
title: "Siebel アダプターの SiebelClientFactory クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SiebelClientFactory
- Data Provider for Siebel, SiebelClientFactory
- SiebelClientFactory, supported properties and methods
ms.assetid: f3a807d3-a030-47d8-b145-e18075ec353c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50e47b22c1d5a2575b0da3fae432acd79886e2c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="siebelclientfactory-class-in-the-siebel-adapter"></a>Siebel アダプターの SiebelClientFactory クラス
ADO.NET クライアントにアクセスする、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]ジェネリック ADO.NET クラスとインターフェイスを使用します。 この機能を有効にする、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]継承、 **System.Data.Common.DbProviderFactory**クラスです。 クライアント プログラムは、次のようにクライアントを使用します。  
  
```  
  
DbProviderFactory factory = DbProviderFactories.GetFactory("Microsoft.Data.SiebelClient");  
DbConnection connection = factory.CreateConnection();  
```  
  
 その他の方法は次のとおりです。  
  
```  
SiebelClientFactory factory = SiebelClientFactory.Instance;  
DbConnection connection = factory.CreateConnection();  
```  
  
 SiebelClientFactory は Microsoft.Data.SiebelClient 名前空間に存在します。  
  
## <a name="supported-members"></a>サポートされているメンバー  
 **SiebelClientFactory**拡張**System.Data.CommonDbProviderFactory**です。  次の表の説明、メンバーを**SiebelClientFactory**をオーバーライドします。  
  
|名前|Description|  
|----------|-----------------|  
|**インスタンス**|これは、メンバー変数です。  SiebelClientFactory のシングルトン インスタンスを提供します。|  
|**CreateCommand()**|SiebelCommand のインスタンスを作成します。|  
|**CreateConnection()**|SiebelConnection のインスタンスを作成します。|  
|**CreateConnectionStringBuilder()**|SiebelConnectionStringBuilder のインスタンスを作成します。|  
|**CreateParameter()**|SiebelParameter のインスタンスを作成します。|  
  
## <a name="see-also"></a>参照  
 [Siebel アダプターと ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)