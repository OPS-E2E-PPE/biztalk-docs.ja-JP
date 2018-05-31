---
title: 競合回避モジュール マネージャー (ResolverMgr) クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 6621ad0c6b9edb5bf93950f9b9d05a7655f0e36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294746"
---
# <a name="the-resolver-manager-resolvermgr-class"></a><span data-ttu-id="a6752-102">競合回避モジュール マネージャー (ResolverMgr) クラス</span><span class="sxs-lookup"><span data-stu-id="a6752-102">The Resolver Manager (ResolverMgr) Class</span></span>
<span data-ttu-id="a6752-103">変換およびルーティング サービスが使用するメッセージング、 **ResolverMgr**解決を実行するクラス。</span><span class="sxs-lookup"><span data-stu-id="a6752-103">The Transform and Routing messaging services use the **ResolverMgr** class to perform resolution.</span></span> <span data-ttu-id="a6752-104">ESB の動的変換と動的な配信エージェント使用しても、 **ResolverManager** ・ イン タイム (JIT) の解決を実行するクラス。</span><span class="sxs-lookup"><span data-stu-id="a6752-104">The ESB dynamic transformation and dynamic delivery agents also use the **ResolverManager** class to perform just-in-time (JIT) resolution.</span></span>  
  
 <span data-ttu-id="a6752-105">ESB コア インストーラーがインストールおよび登録され、 **Microsoft.Practices.ESB.Resolver.dll**を持つアセンブリ、 **ResolverMgr**グローバル アセンブリ キャッシュ内のクラスです。</span><span class="sxs-lookup"><span data-stu-id="a6752-105">The ESB Core installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with the **ResolverMgr** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="a6752-106">このクラスは、エンドポイントやマップの動的な解決を実行する必要がある独自のコードで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6752-106">You can use this class in your own code where you need to perform dynamic resolution of endpoints or maps.</span></span> <span data-ttu-id="a6752-107">カスタムな解決方法を使用するには、このクラスを拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6752-107">You can also extend this class to use a custom resolution method.</span></span> <span data-ttu-id="a6752-108">ただし、クラスが既に必要な任意の別の解決方法のアルゴリズムに対応する必要があります任意のカスタム競合回避モジュール アセンブリが使用できる解決メカニズムをサポートすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6752-108">However, keep in mind that the class already supports a resolution mechanism that can use any custom resolver assembly, which should accommodate any alternative resolution algorithm you may require.</span></span>  
  
 <span data-ttu-id="a6752-109">次のコード例を使用する方法を示しています、 **ResolverMgr**エンドポイントを解決するのにはクラスです。</span><span class="sxs-lookup"><span data-stu-id="a6752-109">The following code example shows how to use the **ResolverMgr** class to resolve an endpoint.</span></span>  
  
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
  
 <span data-ttu-id="a6752-110">通常、競合回避モジュールの接続文字列は、ルール ポリシー、カスタム アセンブリ、XPath ステートメントでは、Universal Description, Discovery, and Integration (UDDI) のラベルとサーバー名などの少なくとも 1 つの解決方法のプロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6752-110">Usually, your resolver connection string specifies the property values for at least one resolution method, such as a rules policy, custom assembly, XPath statement, or Universal Description, Discovery, and Integration (UDDI) label and server name.</span></span> <span data-ttu-id="a6752-111">最後に、具体的な競合回避モジュールからのカスタム ファクトに簡単に設定されている競合回避モジュールのファクトのコレクションをディクショナリ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a6752-111">Finally, it returns a dictionary object with a collection of resolver facts, which can be easily populated with custom facts from a concrete resolver.</span></span>  
  
 <span data-ttu-id="a6752-112">ESB の解決メカニズムのしくみの詳細については、次を参照してください。[動的解決の使用とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6752-112">For more information about how the ESB resolution mechanism works, see [Using Dynamic Resolution and Routing](../esb-toolkit/using-dynamic-resolution-and-routing.md).</span></span>