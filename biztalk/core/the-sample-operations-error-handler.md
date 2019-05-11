---
title: サンプル操作エラー ハンドラ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Ops adapters, error handler
- process management solution tutorial, Ops adapters
ms.assetid: e6c55f01-c004-4340-beaa-d77764ae34c1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ad378180fbf6b29ce69c21a5546243d8891fd81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379931"
---
# <a name="the-sample-operations-error-handler"></a>サンプル操作エラー ハンドラ
サンプル操作エラー ハンドラでは、3 つの主要なアセンブリがあります。**OperationsClient**、 **OperationsHandler**、および**OperationsServer**します。  
  
 ソリューションを使用するアダプターの構成、 **OpsClient**オブジェクト、 **OperationsClient**アセンブリ。 想定されるよう、 **OpsClient**オブジェクトの実装、 **IOpsAIC**インターフェイス。  
  
 **OpsClient**オブジェクトで使用、 **IOperationsSystem**インターフェイスを呼び出す、 **OpsHandler**オブジェクト、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]リモート処理機能です。 **IOperationsSystem**インターフェイスが次のように表示されます。  
  
```  
public interface IOperationsSystem  
{  
    void Initialize(string initData);  
    void Post(string originMachine, byte[] message);  
}  
  
```  
  
 **OperationsServer**、コンソール アプリケーションの要求をリッスン、 **OpsHandler**オブジェクトし、サーバーの役割を果たします、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]リモート処理機能です。 呼び出す、 **Execute**のメソッド、 **OpsClient**オブジェクトが順番に呼び出す、 **Post**のメソッド、 **OpsHandler**オブジェクト。  
  
 **OpsHandler**メソッドの応答を使用して、引数文字列を記述することで、**トレース**オブジェクト。 これは、コンソールにエラーを送信します。 詳細については、**トレース**オブジェクト「Trace クラス」を参照してください、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]クラス ライブラリ。  
  
> [!NOTE]
>  ここに示すパターンは、のと同じ、 **OrderHandler**インターフェイスが、クライアントとリモート オブジェクト間のメソッド呼び出しを指定します。 ただし、間にここで間接参照の追加レイヤー、 **OpsClient**と**OpsHandler**します。  
  
## <a name="see-also"></a>参照  
 [Ops アダプター](../core/the-ops-adapter.md)