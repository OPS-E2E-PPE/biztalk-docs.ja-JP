---
title: "競合回避モジュール マネージャー (ResolverMgr) クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89fa551d-0aca-4777-adbc-2bc46ab8664a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6621ad0c6b9edb5bf93950f9b9d05a7655f0e36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-manager-resolvermgr-class"></a>競合回避モジュール マネージャー (ResolverMgr) クラス
変換およびルーティング サービスが使用するメッセージング、 **ResolverMgr**解決を実行するクラス。 ESB の動的変換と動的な配信エージェント使用しても、 **ResolverManager** ・ イン タイム (JIT) の解決を実行するクラス。  
  
 ESB コア インストーラーがインストールおよび登録され、 **Microsoft.Practices.ESB.Resolver.dll**を持つアセンブリ、 **ResolverMgr**グローバル アセンブリ キャッシュ内のクラスです。  
  
 このクラスは、エンドポイントやマップの動的な解決を実行する必要がある独自のコードで使用できます。 カスタムな解決方法を使用するには、このクラスを拡張することもできます。 ただし、クラスが既に必要な任意の別の解決方法のアルゴリズムに対応する必要があります任意のカスタム競合回避モジュール アセンブリが使用できる解決メカニズムをサポートすることに注意してください。  
  
 次のコード例を使用する方法を示しています、 **ResolverMgr**エンドポイントを解決するのにはクラスです。  
  
```csharp  
// Move to retrieve the first resolver.  
resolvers = itineraryStep.ResolverCollection;  
resolver = resolvers.Current;  
  
// Pass the resolver configuration to the Resolver Manager for resolution.  
resolverDictionary = Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage, resolver);  
  
// Set transport properties.  
transportLocation = resolverDictionary.Item("Resolver.TransportLocation");  
transportType = resolverDictionary.Item("Resolver.TransportType");  
```  
  
 通常、競合回避モジュールの接続文字列は、ルール ポリシー、カスタム アセンブリ、XPath ステートメントでは、Universal Description, Discovery, and Integration (UDDI) のラベルとサーバー名などの少なくとも 1 つの解決方法のプロパティ値を指定します。 最後に、具体的な競合回避モジュールからのカスタム ファクトに簡単に設定されている競合回避モジュールのファクトのコレクションをディクショナリ オブジェクトを返します。  
  
 ESB の解決メカニズムのしくみの詳細については、次を参照してください。[動的解決の使用とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)です。