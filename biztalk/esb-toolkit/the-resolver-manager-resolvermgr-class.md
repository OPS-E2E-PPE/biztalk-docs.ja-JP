---
title: Resolver Manager (ResolverMgr) クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89fa551d-0aca-4777-adbc-2bc46ab8664a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 230a22fa771e0791a705448d2a37fa07563fc603
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399695"
---
# <a name="the-resolver-manager-resolvermgr-class"></a>Resolver Manager (ResolverMgr) クラス
変換およびルーティング サービスの使用のメッセージング、 **ResolverMgr**解決を実行するクラス。 ESB の動的な変換と動的に配信エージェントは使用も、 **ResolverManager** -イン タイム (JIT) の解決を実行するクラス。  
  
 ESB コア インストーラーがインストールおよび登録され、 **Microsoft.Practices.ESB.Resolver.dll**を持つアセンブリ、 **ResolverMgr**グローバル アセンブリ キャッシュ内のクラス。  
  
 このクラスは、エンドポイントやマップの動的な解決を実行する必要がある独自のコードで使用することができます。 カスタム解決方法を使用するには、このクラスを拡張することもできます。 ただし、クラスが既にする必要がある別の解決方法の任意のアルゴリズムに対応する必要が任意のカスタム競合回避モジュール アセンブリが使用できる解決メカニズムをサポートしていることに注意してください。  
  
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
  
 通常、競合回避モジュールの接続文字列には、ルール ポリシー、カスタム アセンブリ、XPath ステートメントでは、Universal Description, Discovery, and Integration (UDDI) のラベルとサーバーの名前など、少なくとも 1 つの解決方法のプロパティ値を指定します。 最後に、カスタム ファクト具体的な競合回避モジュールを簡単に設定されている競合回避モジュールのファクトのコレクションを持つ dictionary オブジェクトを返します。  
  
 ESB の解決メカニズムのしくみの詳細については、次を参照してください。[を使用して動的な解決とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)します。