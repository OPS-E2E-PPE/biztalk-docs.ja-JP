---
title: カスタム例外ハンドラーの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 401aec8d-d9ca-4a88-9e5b-d3ab605dc0a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f2e1daaa0877ea1dc4e9abc24b8b1b36463cd7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400804"
---
# <a name="creating-custom-exception-handlers"></a>カスタム例外ハンドラーの作成
例外を検出して対処するアプリケーション、開発者は、例外ハンドラーを提供する必要があります。 この例外ハンドラーには、例外メッセージの 1 つの型またはシステムまたはアプリケーションの一部またはすべてのパーツから生成される例外メッセージをサブスクライブできます。 たとえば、(すべての例外、給与支払いシステムで発生している) などの特定のシステムからのすべてのメッセージ ハンドラーは 1 つのみを必要となるまたは (チェック プロセスを印刷することを検出するなどの特定のエラーのハンドラーを対象となる代わりにあります。失敗)。  
  
 例外の特定の種類を購読するには、次の例に示すようをアクティブ化の受信図形にフィルターを含むオーケストレーションを使用します。  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.Schemas.Property.FaultCode == "1000";  
```  
  
 フィルター条件は、メッセージが特定のフィルター条件を満たしている場合、ファイル システムまたは電子メール メッセージを送信する送信ポートでもあります。  
  
## <a name="sample-exception-handling-projects"></a>例外処理のサンプル プロジェクト  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外処理を示すいくつかのサンプル BizTalk アプリケーションが含まれています。 これらのサンプルは、\Source\Samples\Exception 処理フォルダーにあります。  
  
 4 つ BizTalk プロジェクトの場合、GlobalBank.ESB.Samples.ExceptionHandling ソリューション内にある ESB 失敗オーケストレーションの例外ルーティング メカニズムを使用する方法を示すもあります。 GlobalBank.ESB BizTalk アプリケーションに展開するのには、これらのプロジェクトが事前構成済み。 次のプロジェクトに示します。  
  
- **ESB します。ExceptionHandling.Schemas します。** このプロジェクトには、サンプル オーケストレーションでは、使用するスキーマが含まれています。  
  
- **ESB します。ExceptionHandling.Pipelines します。** このプロジェクトには、すべての例外をサブスクライブする送信ポートで使用される、例外のプロセッサで構成されている送信パイプラインが含まれています。 これには、BizTalk、および例外管理フレームワークによって生成される例外によって生成される例外が含まれます。  
  
- **ESB します。ExceptionHandling.Processes します。** このプロジェクトには、0 からの呼び出しで除算しようとして例外をシミュレートする EAIProcess.odx オーケストレーションが含まれています、 **CreateFaultMessage**と**AddMessage**適切なを生成する方法図 1 に示すエラー メッセージ。  
  
   ![オーケストレーション プロセス サンプル](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "Ch4 OrchestrationProcessesSample")  
  
   **図 1**  
  
  **プロセスのサンプル プロジェクトで EAIProcess.odx オーケストレーション**  
  
- **ESB します。ExceptionHandling.Handlers します。** このプロジェクトには、呼び出す EAIGenericHandler.odx オーケストレーションが含まれています、 **GetMessages**メソッドを反復処理し、 **MessageCollection**を使用して、 **MoveNext**メソッド、図 2 に示すようにします。  
  
  ![オーケストレーション ハンドラーのサンプル ジェネリック](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "Ch4 OrchestrationHandlersSampleGeneric")  
  
  **図 2**  
  
  **ハンドラーのサンプル プロジェクトで EAIGenericHandler.odx オーケストレーション**  
  
  ESB します。ExceptionHandling.Handlers プロジェクトには、呼び出す EAIProcessHandler.odx オーケストレーションも含まれています、 **GetMessage**と**GetException**メソッド、図 3 に示すようにします。  
  
  ![オーケストレーション ハンドラーのサンプル プロセス](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "Ch4 OrchestrationHandlersSampleProcess")  
  
  **図 3**  
  
  **ハンドラーのサンプル プロジェクトで EAIProcessHandler.odx オーケストレーション**