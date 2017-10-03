---
title: "サンプル操作エラー ハンドラ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Ops adapters, error handler
- process management solution tutorial, Ops adapters
ms.assetid: e6c55f01-c004-4340-beaa-d77764ae34c1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93536733c884b4d5db57ba18619ebabdead17561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-sample-operations-error-handler"></a>サンプル操作エラー ハンドラ
サンプル操作エラー ハンドラが 3 つの主要なアセンブリ: **OperationsClient**、 **OperationsHandler**、および**OperationsServer**です。  
  
 ソリューションを使用するアダプターの構成、 **OpsClient**内のオブジェクト、 **OperationsClient**アセンブリ。 予想できるように、 **OpsClient**オブジェクトを実装して、 **IOpsAIC**インターフェイスです。  
  
 **OpsClient**オブジェクトが使用、 **IOperationsSystem**インターフェイスを呼び出す、 **OpsHandler**オブジェクトを介して、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]リモート処理機能します。 **IOperationsSystem**インターフェイスが次のように表示されます。  
  
```  
public interface IOperationsSystem  
{  
    void Initialize(string initData);  
    void Post(string originMachine, byte[] message);  
}  
  
```  
  
 **OperationsServer**、コンソール アプリケーションの要求を受信、 **OpsHandler**オブジェクトし、サーバーの役割を果たします、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]リモート処理機能します。 呼び出す、 **Execute**のメソッド、 **OpsClient**オブジェクトを呼び出す、 **Post**のメソッド、 **OpsHandler**オブジェクト。  
  
 **OpsHandler**メソッドが応答を使用して、引数文字列を記述して、**トレース**オブジェクト。 これによりコンソールにエラーが送信されます。 詳細については、**トレース**オブジェクト「Trace クラス」を参照してください、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]クラス ライブラリです。  
  
> [!NOTE]
>  ここに示すパターンは、場合と同じで、 **OrderHandler**インターフェイスが、クライアントとリモート オブジェクト間のメソッド呼び出しを指定します。 ただし、追加の間に次に、間接層、 **OpsClient**と**OpsHandler**です。  
  
## <a name="see-also"></a>参照  
 [Ops アダプタ](../core/the-ops-adapter.md)