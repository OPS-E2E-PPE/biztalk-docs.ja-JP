---
title: カスタムの例外 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, compensation blocks
- compensation blocks, process management solutions
- process management solution tutorial, custom exceptions
- Terminate shape [Orchestration Designer], called orchestrations
- process management solution tutorial, errors
ms.assetid: 0c923303-82ad-4a20-9c7c-5e38c477993a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5118de4dc75d65f328838d9e7cecf4d51875db1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353396"
---
# <a name="custom-exceptions"></a>カスタム例外
場合、ビジネス プロセス管理ソリューションが例外ハンドラとカスタム例外の組み合わせを使用して回復不能なエラーがあります。  
  
## <a name="handling-exceptions"></a>例外の処理  
 使用してではなく**Terminate**呼び出されたオーケストレーションに図形をルート オーケストレーションで処理される例外をスローする方式を使用できます。 これにより、例外の処理に関する決定を行うコンテキストの最も幅の広い知識を持つオーケストレーションです。 カスタム例外をスローする下位のオーケストレーションには、ルート オーケストレーションにより具体的な情報を通信することができます。  
  
 ビジネス プロセス管理ソリューションでは、このパターンに従います。 次の 4 つのルートがあるソリューションのオーケストレーションが呼び出されていない、または。**OrderBroker**、 **OrderManager**、 **CableOrder1**、および**CableOrder2**します。 3 つのルート オーケストレーションが表示され、カスタム例外を処理します。**OrderManager**、 **CableOrder1**、および**CableOrder2**します。  
  
 ルート オーケストレーションの一部を使用ことに注意してください、 **Terminate**図形と、 **Terminate**図形がオーケストレーションの通常の終了ポイントの直前に表示されます。 オーケストレーションはまだ使用して、 **Terminate**図形のエラーが発生した場合、終了すると、オーケストレーションを記録するではなく完了したが、エラー メッセージ。 これにより、エラーを記録するだけでなく簡単に失敗したインスタンスを追跡するソリューションです。  
  
 詳細については、 **Terminate**図形は、「[終了図形を構成する方法](../core/how-to-configure-the-terminate-shape.md)します。 詳細については、 **ThrowException**図形は、「[例外のスロー図形を構成する方法](../core/how-to-configure-the-throw-exception-shape.md)します。  
  
## <a name="the-custom-exceptions"></a>カスタム例外  
 次の 3 つのカスタム例外の同じパターンに従います。 さまざまな例外を区別するためにコードを個別の型を持つできます。  
  
|例外|スローされる (オーケストレーション)|  
|---------------|---------------------------------|  
|**ActivateException**|**変更**|  
|**CableOrderException**|**アクティブ化**、 **CableOrder1**|  
|**InterruptException**|**CableOrder1**、 **CheckInterrupt**、 **ErrorHandlerOrch**|  
  
 定義されているすべてのカスタム例外は、**ユーティリティ**アセンブリ。 カスタム例外は、すべての .NET クラスです。 .NET からのすべてのカスタム例外クラスを継承**ApplicationException**から継承するクラス、 **System.Exception**クラス。 例外が退避される可能性の可能性があるため、(シリアル化され、データベースに格納されている)、例外する必要があります逆シリアル化コンス トラクターを実装します。 逆シリアル化コンス トラクターは 2 つの引数を受け取るコンス トラクター: SerializationInfo オブジェクトと StreamingContext オブジェクト。 逆シリアル化コンス トラクターは、例外のリハイド レート中に使用されます。 **ApplicationException**クラスは、シリアル化解除コンストラクタを既に実装して、カスタムの例外のコンス トラクターは、ベース (ApplicationException) の逆シリアル化コンス トラクターを呼び出すだけです。 たとえば、 **InterruptException**次のコンス トラクターが含まれています。  
  
```  
// "info" is the object holding the serialized object data.  
// "context" is the contextual information about the source  
// or destination.  
public InterruptException(SerializationInfo info,  
                  StreamingContext context) : base(info, context) { }  
```  
  
 詳細については、カスタムのシリアル化でカスタムのシリアル化を参照してください、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]開発者ガイド。  
  
## <a name="nested-exception-handlers-and-compensation-blocks"></a>入れ子になった例外ハンドラーや補正ブロック  
 特殊な例外としての機能、に加えてさまざまな場所でのカスタム例外はソート フラグとしても機能します。 **変更**オーケストレーションは 2 つの場所で取り消し操作をロールバックする必要があります。  
  
> [!NOTE]
>  このセクションを参照することも、**変更**オーケストレーションは、Visual Studio で開きます。  
  
 オーケストレーションの上部にある場合への呼び出し、**キャンセル**オーケストレーションが失敗した、 **CancelCompensation**ブロックが実行して、ロールバック、**キャンセル**トランザクション。 オーケストレーションを呼び出す場合、すべてうまくいけば、 **Activate**オーケストレーションします。  
  
 場合、 **Activate**操作が失敗、**キャンセル**トランザクションは、戻るもロールバックする必要があります。 ただし、例外ハンドラーへの呼び出しを**Activate**認識していません、**キャンセル**トランザクション。 これを処理するには、オーケストレーション全体の例外ハンドラーです。 このハンドラーが含まれています、**キャンセル**スコープを認識、**キャンセル**トランザクション。 ハンドラーからスローされた例外のキャッチ、 **Activate**スコープ (、 **ActivateException**)、ロールバック、**キャンセル**トランザクション、例外を再度スローしますオーケストレーションが呼び出されるように、**変更**オーケストレーションは、追加の処理を実行できます。  
  
 この設計を補正のみに注意してください、**キャンセル**場合、 **Activate**が失敗します。 場合、**キャンセル**が失敗し、例外がスロー、**キャンセル**ことはありませんが行われ、補正しない必要があります。  
  
 補正ブロックの詳細については、**補正**図形は、「[補正図形を構成する方法](../core/how-to-configure-the-compensate-shape.md)します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md)   
 [ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)