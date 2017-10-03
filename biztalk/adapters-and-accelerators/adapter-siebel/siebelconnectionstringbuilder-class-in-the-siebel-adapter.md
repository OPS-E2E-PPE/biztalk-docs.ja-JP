---
title: "Siebel アダプターの SiebelConnectionStringBuilder クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SiebelConnectionStringBuilder, supported properties and methods
- Data Provider for Siebel, SiebelConnectionStringBuilder
- SiebelConnectionStringBuilder
ms.assetid: 4995fce8-7e62-4af9-a731-47b16438067c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 088748c63983e76e64d32f54b3e999fadd88d23a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="siebelconnectionstringbuilder-class-in-the-siebel-adapter"></a><span data-ttu-id="9d9ec-102">Siebel アダプターの SiebelConnectionStringBuilder クラス</span><span class="sxs-lookup"><span data-stu-id="9d9ec-102">SiebelConnectionStringBuilder class in the Siebel adapter</span></span>
<span data-ttu-id="9d9ec-103">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供、`DbConnectionStringBuilder`ツールの接続プロパティを取得するために環境の実装を SQL Server Integration Services (SSIS) および Visual Studio のエクスプ ローラーを有効にする、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]によって GUI の形式で表示し、PropertyGrid です。</span><span class="sxs-lookup"><span data-stu-id="9d9ec-103">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides a `DbConnectionStringBuilder` implementation to enable SQL Server Integration Services (SSIS) and Visual Studio explorer tools environments to get the connection properties of the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] and display them in the form of a GUI driven by the PropertyGrid.</span></span>  
  
 <span data-ttu-id="9d9ec-104">SiebelConnectionStringBuilder を作成するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d9ec-104">To create a SiebelConnectionStringBuilder, use the following approach:</span></span>  
  
```  
  
//In this example, factory is an instance of SiebelClientFactory  
SiebelConnectionStringBuilder bldr = (SiebelConnectionStringBuilder)factory.CreateConnectionStringBuilder();  
bldr.ConnectionString = connstr;  
```  
  
 <span data-ttu-id="9d9ec-105">または、単に。</span><span class="sxs-lookup"><span data-stu-id="9d9ec-105">Or, simply:</span></span>  
  
```  
  
SiebelConnectionStringBuilder bldr = new SiebelConnectionStringBuilder();  
```  
  
 <span data-ttu-id="9d9ec-106">キーとの一部としてサポートされている値を表示する、`DbConnectionStringBuilder`を参照してください[Siebel 接続文字列のデータ プロバイダーのプロパティ](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)です。</span><span class="sxs-lookup"><span data-stu-id="9d9ec-106">To see the keys and values supported as part of the `DbConnectionStringBuilder`, see [Data Provider properties for the Siebel Connection String](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9ec-107">参照</span><span class="sxs-lookup"><span data-stu-id="9d9ec-107">See Also</span></span>  
 [<span data-ttu-id="9d9ec-108">Siebel アダプターと ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="9d9ec-108">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)