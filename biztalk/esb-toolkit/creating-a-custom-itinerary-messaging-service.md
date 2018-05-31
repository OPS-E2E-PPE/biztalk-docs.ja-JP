---
title: カスタム Itinerary メッセージング サービスを作成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2de44c21-68ca-4cf1-a117-bcb35af1b4a9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f08168e69e26d56cb39fb5c05cc53c3cbb51202
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973736"
---
# <a name="creating-a-custom-itinerary-messaging-service"></a>カスタム Itinerary メッセージング サービスを作成します。
Itinerary フレームワークの一部である、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]を実装するクラスを使用して、itinerary 手順の実行をサポートしている、 **IMessagingService** itinerary メッセージング サービスを実行するインターフェイスです。 サービスで、次を担当するときに、カスタムのメッセージング サービスを実装できます。  
  
-   Itinerary で構成されているカスタム メッセージの検証  
  
-   Itinerary で構成されているカスタム メッセージ変換  
  
-   メッセージのカスタム処理  
  
 これらすべてのケースでは、実装するカスタムの itinerary サービスは、インターセプターとして機能し、ディスパッチャー パイプライン コンポーネントによって呼び出されます。  
  
 カスタム メッセージに基づく itinerary のサービス、またはメッセージング サービス、すべての実装、 **IMessagingService**インターフェイスです。 このインターフェイスを公開、**名前**と**SupportsDisassemble**プロパティおよび**Execute**と**ShouldAdvanceStep**メソッドです。  
  
 **名前**プロパティは、サービスの名前、行程に表示されます。 Itinerary サービス構成 Esb.config ファイルで構成されている名前と一致している必要があります。  
  
 **SupportsDisassemble**プロパティは、サポートを作成するカスタムのメッセージング サービスを逆アセンブルするかどうかと複数の競合回避モジュールの実行を示します。  
  
 **ShouldAdvanceStep**メソッドは、現在の itinerary ステップと現在のメッセージでは取得し、サービスの実行後に、ディスパッチャーが旅行計画を進める必要があるかどうかを示すブール値を返します。 ほとんどの場合、このメソッドが返す**true**です。  
  
 **Execute**メソッド メッセージング サービスの最も重要なは、実行時に実行されるロジックを含んでいます。 パイプラインのコンテキスト、メッセージ、競合回避モジュールの文字列および現在の itinerary ステップにかかる更新されたメッセージを返します。  
  
 参照の実装、 **Execute**メソッドは、ESB の RoutingService.cs ファイルで検出されたことができます。次のコードに示すように Itinerary.Services プロジェクトです。  
  
```csharp  
public IBaseMessage ExecuteRoute(IPipelineContext context, IBaseMessage msg, string resolverString)  
        {  
            if (context == null)  
                throw new ArgumentNullException("context");  
            if (msg == null)  
                throw new ArgumentNullException("msg");  
            if (string.IsNullOrEmpty(resolverString))  
                throw new ArgumentException(Properties.Resources.ArgumentStringRequired, "resolverString");  
            try  
            {  
                ResolverInfo info = ResolverMgr.GetResolverInfo(ResolutionType.Endpoint, resolverString);  
                if (!info.Success)  
                    throw new RoutingException(Properties.Resources.ResolverStringInvalid, resolverString);  
  
                // Resolve configuration for routing.  
                Dictionary<string, string> resolverDictionary = ResolverMgr.Resolve(info, msg, context);  
  
                if (string.IsNullOrEmpty(resolverDictionary["Resolver.TransportLocation"]))  
                    throw new RoutingException(Properties.Resources.TransportLocationNotResolved, resolverString);  
  
                AdapterMgr.SetEndpoint(resolverDictionary, msg.Context);  
  
                return msg;  
            }  
            catch (System.Exception ex)  
            {  
                EventLogger.Write(MethodInfo.GetCurrentMethod(), ex);  
                throw;  
            }        
        }  
```  
  
 **メッセージングのカスタム itinerary サービスを実装するには**  
  
1.  派生するクラスを含むアセンブリを作成**IMessagingService;** で、 **Execute**メソッド (存在する場合)、メッセージまたはメッセージのコンテキストを変更するために必要なすべてのロジックが含まれます。  
  
2.  内のエントリを追加、 **itineraryServices** Esb.config ファイルを追加して、サービスのセクションで、  **\<itineraryService\>** と GUID を持つ要素、 **id**属性をサービスとしての名前、**名前**属性とクラスの完全修飾名、**型**属性、**メッセージング**として、**スコープ**属性、および、許可されているステージ (たとえば、 **OnRampReceive**、 **OnRampSend**、 **OffRampSend**、 **OffRampReceive**、 **AllSend**、 **AllReceive**、または**すべて**) として、**ステージ**属性。  
  
3.  グローバル アセンブリ キャッシュに新しいアセンブリを登録します。