---
title: Siebel アダプターの SiebelClientFactory クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelClientFactory
- Data Provider for Siebel, SiebelClientFactory
- SiebelClientFactory, supported properties and methods
ms.assetid: f3a807d3-a030-47d8-b145-e18075ec353c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c732d029e1c3866caf5d20f11a790b80bc40cf68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370704"
---
# <a name="siebelclientfactory-class-in-the-siebel-adapter"></a>Siebel アダプターの SiebelClientFactory クラス
ADO.NET クライアントにアクセスする、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]ジェネリックの ADO.NET クラスとインターフェイスを使用します。 この機能を有効にする、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]継承、 **System.Data.Common.DbProviderFactory**クラス。 クライアント プログラムは、次のようにクライアントを使用します。  
  
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
 **SiebelClientFactory**拡張**System.Data.CommonDbProviderFactory**します。  次の表は、メンバーの説明を**SiebelClientFactory**よりも優先されます。  
  
|名前|説明|  
|----------|-----------------|  
|**インスタンス**|これは、メンバー変数です。  SiebelClientFactory のシングルトン インスタンスを提供します。|  
|**CreateCommand()**|SiebelCommand のインスタンスを作成します。|  
|**CreateConnection()**|SiebelConnection のインスタンスを作成します。|  
|**CreateConnectionStringBuilder()**|SiebelConnectionStringBuilder のインスタンスを作成します。|  
|**CreateParameter()**|SiebelParameter のインスタンスを作成します。|  
  
## <a name="see-also"></a>参照  
 [Siebel アダプターを使用した ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)