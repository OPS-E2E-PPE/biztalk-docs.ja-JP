---
title: "カスタム例外ハンドラーの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 401aec8d-d9ca-4a88-9e5b-d3ab605dc0a1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91f725084c838d026f9028f0ac2e684ec2d727c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-custom-exception-handlers"></a>カスタム例外ハンドラーの作成
例外を検出して処理するアプリケーションは、開発者は、例外ハンドラーを提供する必要があります。 この例外ハンドラーは、例外メッセージの単一の型と、システムまたはアプリケーションの一部またはすべての部分から生成された例外メッセージをサブスクライブできます。 たとえば、(など、例外、給与支払いシステムで発生している)、特定のシステムからのすべてのメッセージを 1 つのハンドラーのみが必要な場合があります。 か (チェック プロセスを印刷することを検出するなどの特定のエラーのハンドラーを対象となる代わりにあります。失敗する)。  
  
 特定の種類の例外をサブスクライブするには、次の例で示すようにフィルターを持つ、アクティブ化受信図形 オーケストレーションを使用します。  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.Schemas.Property.FaultCode == "1000";  
```  
  
 フィルター条件は、メッセージが特定のフィルター条件を満たしている場合、ファイル システムまたは電子メール メッセージを送信する送信ポートでもあります。  
  
## <a name="sample-exception-handling-projects"></a>例外処理のサンプル プロジェクト  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外処理を示すいくつかのサンプル BizTalk アプリケーションが含まれています。 これらのサンプルは、\Source\Samples\Exception 処理フォルダーで確認できます。  
  
 次の 4 つ BizTalk プロジェクト、GlobalBank.ESB.Samples.ExceptionHandling ソリューション内にある、ESB 失敗オーケストレーション例外ルーティング機構を使用する方法を示すもあります。 GlobalBank.ESB BizTalk アプリケーションに展開するのには、これらのプロジェクトがあらかじめ設定されています。 次のプロジェクトに示します。  
  
-   **ESB です。ExceptionHandling.Schemas です。** このプロジェクトには、サンプル オーケストレーションに使用するスキーマが含まれています。  
  
-   **ESB です。ExceptionHandling.Pipelines です。** このプロジェクトには、すべての例外をサブスクライブする送信ポートで使用される、例外のプロセッサで構成されている送信パイプラインが含まれています。 これには、BizTalk、および例外管理フレームワークによって生成される例外によって生成される例外が含まれます。  
  
-   **ESB です。ExceptionHandling.Processes です。** このプロジェクトには、0 との呼び出しで除算しようとして例外をシミュレートする EAIProcess.odx オーケストレーションが含まれています、 **CreateFaultMessage**と**AddMessage**適切なを生成する方法図 1 に示すエラー メッセージ。  
  
     ![オーケストレーションで処理サンプル](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "Ch4 OrchestrationProcessesSample")  
  
     **図 1**  
  
 **プロセスのサンプル プロジェクトで EAIProcess.odx オーケストレーション**  
  
-   **ESB です。ExceptionHandling.Handlers です。** このプロジェクトに呼び出す EAIGenericHandler.odx オーケストレーションが含まれています、 **GetMessages**メソッドを繰り返し処理して、 **MessageCollection**を使用して、 **MoveNext**メソッド、図 2 に示すようにします。  
  
 ![オーケストレーション ハンドラーのサンプル ジェネリック](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "Ch4 OrchestrationHandlersSampleGeneric")  
  
 **図 2**  
  
 **ハンドラーのサンプル プロジェクトで EAIGenericHandler.odx オーケストレーション**  
  
 ESB です。ExceptionHandling.Handlers プロジェクトには、呼び出す EAIProcessHandler.odx オーケストレーションも含まれています、 **GetMessage**と**GetException**メソッド、図 3 に示すようにします。  
  
 ![オーケストレーション ハンドラーのサンプル プロセス](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "Ch4 OrchestrationHandlersSampleProcess")  
  
 **図 3**  
  
 **ハンドラーのサンプル プロジェクトで EAIProcessHandler.odx オーケストレーション**