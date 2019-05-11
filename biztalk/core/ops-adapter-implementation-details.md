---
title: Ops アダプター実装の詳細 |Microsoft Docs
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
ms.openlocfilehash: 37e890b7413726993dd28aa21dec0f13e92f90f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323428"
---
# <a name="ops-adapter-implementation-details"></a>Ops アダプター実装の詳細
アダプターを変更する場合は、Ops アダプタの次の側面を理解する役に立つ場合がありますまたはプログラムによって構成します。  
  
> [!NOTE]
>  Ops アダプタは、アダプター フレームワークを使用して構築されています。 アダプタ フレームワークを構築する方法については、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)します。  
  
## <a name="batch-processing"></a>バッチ処理  
 ように各メッセージを個別に処理し、一度に 1 つだけの順序でロールバック操作が完了したら、アダプターは一度に 1 つのメッセージを処理します。 アダプターは、一度に 1 つのメッセージを処理するが、バッチ サイズが 1 つのバッチ処理を使用してそうです。 これにより、アダプターはメッセージをバッチ処理を変更しやすくします。  
  
## <a name="transaction-handling"></a>トランザクションの処理  
 アダプターは、Microsoft によって提供されるトランザクション機能を使用して[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] **System.Transactions**機能します。 新しいアダプターを作成**CommittableTransaction**でこれを使用して、 **TransactionScope**します。 アダプターが、**初期化**と**Execute**このトランザクションのコンテキスト内のメソッド。 呼び出されたアセンブリ内のコードを使用して、トランザクションに参加できる**Transaction.Current**トランザクション コンテキストを取得する静的メソッド。 サンプル エラー ハンドラを行わないのは、この機能を使用します。 詳細については**System.Transactions**、.NET Framework クラス ライブラリのバージョンで"System.Transactions Namespace"を参照してください。  
  
## <a name="handling-data-other-than-error-reports"></a>エラー報告以外のデータの処理  
 ソリューションでは、アダプターは、新しいエラー報告機能からエラー レポート メッセージを処理します。 ただし、ため、 **Execute**メソッドは、唯一の引数としてバイト配列を受け取りを明示的に制限に渡されるものを使用する必要がある、 **Execute**メソッド。  
  
## <a name="using-the-adapter-when-creating-ports-programmatically"></a>ポートをプログラムで作成するときに、アダプターを使用します。  
 コードからポートを作成するときに、アダプターを指定できます。 次の表は、カスタム プロパティ名と表示名に対応する方法を示します。  
  
|カスタム プロパティの名前を送信します。|表示名|  
|-------------------------------|------------------|  
|**DotNetAssemblyStrongName**|**DotNetAssemblyStrongName**|  
|**DotNetClassName**|**DotNetClassName**|  
|**InitializationData**|**InitializationData**|  
|**TransportLocationUri**|該当なし。|  
  
 すべてのプロパティは、文字列値です。 アセンブリ名とクラス名から TransportLocationUri プロパティの値を作成します。 URI が、値は OPS://\<DotNetAssemblyStrongName\>/\<DotNetClassName\>プレース ホルダーは対応するカスタム プロパティの値を置き換えです。  
  
 コードからポートを作成する方法については、次を参照してください。[コードから MSMQ 受信場所の作成と送信ポートを方法](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)します。  
  
## <a name="see-also"></a>参照  
 [Ops アダプター](../core/the-ops-adapter.md)