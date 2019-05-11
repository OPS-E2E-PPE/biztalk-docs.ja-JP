---
title: Siebel アダプターの SiebelConnectionStringBuilder クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelConnectionStringBuilder, supported properties and methods
- Data Provider for Siebel, SiebelConnectionStringBuilder
- SiebelConnectionStringBuilder
ms.assetid: 4995fce8-7e62-4af9-a731-47b16438067c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8824f61fa591636b2c4b43eceb6b1a3aa9e363e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370838"
---
# <a name="siebelconnectionstringbuilder-class-in-the-siebel-adapter"></a>Siebel アダプターの SiebelConnectionStringBuilder クラス
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供、`DbConnectionStringBuilder`ツールの接続プロパティを取得するための環境の SQL Server Integration Services (SSIS) と Visual Studio のエクスプ ローラーを有効にする実装、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]によって GUI の形式で表示して、PropertyGrid します。  
  
 SiebelConnectionStringBuilder を作成するには、次のアプローチを使用します。  
  
```  
  
//In this example, factory is an instance of SiebelClientFactory  
SiebelConnectionStringBuilder bldr = (SiebelConnectionStringBuilder)factory.CreateConnectionStringBuilder();  
bldr.ConnectionString = connstr;  
```  
  
 または、単に。  
  
```  
  
SiebelConnectionStringBuilder bldr = new SiebelConnectionStringBuilder();  
```  
  
 キーとの一部としてサポートされている値を表示する、`DbConnectionStringBuilder`を参照してください[Siebel 接続文字列のデータ プロバイダー プロパティ](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)します。  
  
## <a name="see-also"></a>参照  
 [Siebel アダプターを使用した ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)