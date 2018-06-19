---
title: Ops アダプタの実装の詳細 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, Ops adapters
- Ops adapters, batching
- Ops adapters, creating ports
- Ops adapters, implementing
- Ops adapters, transaction handling
- process management solution tutorial, Ops adapters
ms.assetid: dbca31ca-c3d8-4a25-9356-ef4bbab671e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3172759541f46ec6c3c8c2b3e684086747036f37
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970784"
---
# <a name="ops-adapter-implementation-details"></a>Ops アダプタの実装の詳細
次に示す Ops アダプタの特性を理解すると、アダプタを変更したりプログラムによって構成する場合に役立ちます。  
  
> [!NOTE]
>  Ops アダプタはアダプタ フレームワークを使用して構築されています。 フレームワークでアダプタのビルドについては、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)です。  
  
## <a name="batch-processing"></a>バッチ処理  
 このアダプタでは、それぞれのメッセージが別々に処理されるように、一度に 1 つのメッセージだけが処理されます。また、ロールバック操作も一度に 1 注文ずつ行われます。 このアダプタで一度に処理されるメッセージは 1 つだけですが、その場合には、バッチ サイズが 1 のバッチ処理が使用されています。 これにより、メッセージをバッチ処理する場合にアダプタを変更する作業が容易になります。  
  
## <a name="transaction-handling"></a>トランザクションの処理  
 アダプターは、Microsoft によって提供されるトランザクション機能を使用して[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] **System.Transactions**機能します。 新しいアダプターを作成**CommittableTransaction**でそれを使用して、 **TransactionScope**です。 アダプターが、**初期化**と**Execute**このトランザクションのコンテキスト内のメソッドです。 呼び出されたアセンブリ内のコードを使用して、トランザクションに参加できる**Transaction.Current**トランザクション コンテキストを取得する静的メソッドです。 サンプル エラー ハンドラでは、この機能を使用していません。 詳細については**System.Transactions**、.NET Framework クラス ライブラリのバージョンで「System.Transactions Namespace」を参照してください。  
  
## <a name="handling-data-other-than-error-reports"></a>エラー報告以外のデータの処理  
 ソリューション内で、このアダプタは新しいエラー報告機能を使用してエラー報告メッセージを処理します。 ただし、ため、 **Execute**メソッドは、唯一の引数としてバイト配列を受け取りに渡される内容を明示的に制限がある、 **Execute**メソッドです。  
  
## <a name="using-the-adapter-when-creating-ports-programmatically"></a>プログラムによりポートを作成した場合のアダプタの使用  
 コードからポートを作成する場合に、このアダプタを指定することができます。 次の表は、カスタム プロパティ名とそれらに対応する表示名を示します。  
  
|送信カスタム プロパティ名|表示名|  
|-------------------------------|------------------|  
|**DotNetAssemblyStrongName**|**DotNetAssemblyStrongName**|  
|**DotNetClassName**|**DotNetClassName**|  
|**InitializationData**|**InitializationData**|  
|**TransportLocationUri**|該当なし。|  
  
 すべてのプロパティは文字列値です。 TransportLocationUri プロパティの値は、アセンブリ名とクラス名から構築されます。 URI の値は OPS://\<DotNetAssemblyStrongName\>/\<DotNetClassName\>プレース ホルダーは、対応するカスタム プロパティの値を置き換えです。  
  
 コードからポートを作成する方法の詳細については、次を参照してください。[コードから MSMQ 受信場所の作成と送信ポートを方法](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)です。  
  
## <a name="see-also"></a>参照  
 [Ops アダプター](../core/the-ops-adapter.md)