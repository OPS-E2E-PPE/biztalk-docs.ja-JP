---
title: カスタム スケジュール メッセージング サービスを作成する |Microsoft Docs
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
ms.openlocfilehash: 43c773fcd093035f414fd4824a38e5b675484f51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291496"
---
# <a name="creating-a-custom-itinerary-messaging-service"></a>カスタム スケジュール メッセージング サービスを作成します。
スケジュール オンランプ フレームワークの一部である、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]を実装するクラスを使用してスケジュールの手順の実行をサポート、 **IMessagingService**スケジュール メッセージング サービスを実行するインターフェイス。 次を担当するサービスの場合は、カスタムのメッセージング サービスを実装できます。  
  
- 旅行プランで構成されたカスタム メッセージの検証  
  
- 旅行プランで構成されているカスタム メッセージ変換  
  
- メッセージのカスタム処理  
  
  これらすべてのケースでは、実装するカスタム スケジュール サービスは、インターセプターとして機能しは、ディスパッチャー パイプライン コンポーネントによって呼び出されます。  
  
  カスタム メッセージングに基づくスケジュール オンランプのサービス、またはメッセージング サービスをすべて実装、 **IMessagingService**インターフェイス。 このインターフェイスを公開、**名前**と**SupportsDisassemble**プロパティおよび**Execute**と**ShouldAdvanceStep**メソッド。  
  
  **名前**日程で表示されるプロパティは、サービスの名前です。 スケジュール サービスとして構成 Esb.config ファイルで構成されている名前に一致する必要があります。  
  
  **SupportsDisassemble**プロパティは、サポートを作成するカスタムのメッセージング サービスが逆アセンブルするかどうかと複数の競合回避モジュールの実行を示します。  
  
  **ShouldAdvanceStep**メソッドでは、現在のスケジュール オンランプ手順と現在のメッセージとサービスの実行後に、ディスパッチャーが旅行計画を進める必要があるかどうかを示すブール値を返します。 ほとんどの場合、このメソッドが返す必要があります**true**します。  
  
  **Execute**メソッド メッセージング サービスの最も重要なは、実行時に実行されるロジックが含まれています。 パイプライン コンテキスト、メッセージ、競合回避モジュールの文字列、および現在のスケジュール ステップにかかる更新されたメッセージを返します。  
  
  参照の実装、 **Execute**メソッドは、ESB の RoutingService.cs ファイルにあります。次のコードに示すように Itinerary.Services プロジェクトです。  
  
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
  
 **メッセージング用のカスタム スケジュール サービスを実装するには**  
  
1.  派生するクラスを含むアセンブリを作成**IMessagingService;** で、 **Execute**メソッド (存在する場合)、メッセージまたはメッセージのコンテキストを変更するために必要なすべてのロジックが含まれます。  
  
2.  内のエントリを追加、 **itineraryServices** Esb.config ファイルを追加して、サービスのセクション、 **\<itineraryService\>** と GUID を持つ要素、 **id**属性は、サービスとしての名前、**名前**属性とクラスの完全修飾名、**型**属性、**メッセージング**として、**スコープ**属性、および、許可されているステージ (たとえば、 **OnRampReceive**、 **OnRampSend**、 **OffRampSend**、 **OffRampReceive**、 **AllSend**、 **AllReceive**、または**すべて**) として、**ステージ**属性。  
  
3.  グローバル アセンブリ キャッシュに新しいアセンブリを登録します。