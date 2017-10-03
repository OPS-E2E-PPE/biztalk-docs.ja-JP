---
title: "カスタム例外 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, compensation blocks
- compensation blocks, process management solutions
- process management solution tutorial, custom exceptions
- Terminate shape [Orchestration Designer], called orchestrations
- process management solution tutorial, errors
ms.assetid: 0c923303-82ad-4a20-9c7c-5e38c477993a
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfead2aadc237d27e0fb8ed28a776dd1e4f5c6f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="custom-exceptions"></a>カスタム例外
回復できないエラーが発生すると、ビジネス プロセス管理ソリューションは、例外ハンドラとカスタム例外を組み合わせて使用します。  
  
## <a name="handling-exceptions"></a>例外の処理  
 使用するのではなく**Terminate**呼び出されたオーケストレーションに図形をルート オーケストレーションで処理される例外をスローする方式を使用することができます。 これにより、最も強力なコンテキストのオーケストレーションで例外処理を判断できます。 下位のオーケストレーションがカスタム例外をスローすると、ルート オーケストレーションの詳細な情報と通信できます。  
  
 ビジネス プロセス管理ソリューションは、この方式に従います。 次の 4 つのルートがあるか、ソリューションのオーケストレーションが、呼び出さ: **OrderBroker**、 **OrderManager**、 **CableOrder1**、および**CableOrder2**. 3 つのルート オーケストレーションを受け取り、カスタム例外を処理します。 **OrderManager**、 **CableOrder1**、および**CableOrder2**です。  
  
 ルート オーケストレーションの一部を使用、 **Terminate**図形と、 **Terminate**図形がオーケストレーションの通常の終了ポイントの直前に表示されます。 オーケストレーションが現在も使用して、 **Terminate**終了すると、オーケストレーションが記録するようではなく完了したが、エラー メッセージ、エラーが発生した場合の図形です。 これにより、このソリューションは、エラーの記録に加えて、失敗したインスタンスを簡単に追跡できます。  
  
 詳細については、 **Terminate**図形は、「[終了図形を構成する方法](../core/how-to-configure-the-terminate-shape.md)です。 詳細については、 **ThrowException**図形は、「[例外のスロー図形を構成する方法](../core/how-to-configure-the-throw-exception-shape.md)です。  
  
## <a name="the-custom-exceptions"></a>カスタム例外  
 次の 3 つのカスタム例外は、同じ方式に従います。 異なる種類を使用すると、コードは、各種の例外を区別できます。  
  
|例外|スローされる (オーケストレーション)|  
|---------------|---------------------------------|  
|**ActivateException**|**変更**|  
|**CableOrderException**|**アクティブ化**、 **CableOrder1**|  
|**InterruptException**|**CableOrder1**、 **CheckInterrupt**、 **ErrorHandlerOrch**|  
  
 定義されているすべてのカスタム例外は、**ユーティリティ**アセンブリ。 カスタム例外は、すべて .NET クラスです。 すべてのカスタム例外クラス継承した .NET **ApplicationException**から継承するクラス、 **System.Exception**クラスです。 例外が退避されている (シリアル化されてデータベースに格納されている) 可能性があるので、シリアル化解除コンストラクタが例外に実装されている必要があります。 シリアル化解除コンストラクタは、2 つの引数 (SerializationInfo オブジェクトと StreamingContext オブジェクト) を使用するコンストラクタです。 例外の退避中に、シリアル化解除コンストラクタが使用されます。 **ApplicationException**クラスは、シリアル化解除コンストラクタを既に実装して、カスタムの例外のコンス トラクターは、ベース (ApplicationException) の逆シリアル化コンス トラクターを呼び出すだけです。 たとえば、 **InterruptException**次のコンス トラクターが含まれています。  
  
```  
// "info" is the object holding the serialized object data.  
// "context" is the contextual information about the source  
// or destination.  
public InterruptException(SerializationInfo info,  
                  StreamingContext context) : base(info, context) { }  
```  
  
 カスタムのシリアル化の詳細については、『[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 開発者ガイド』の「シリアル化のカスタマイズ」を参照してください。  
  
## <a name="nested-exception-handlers-and-compensation-blocks"></a>入れ子になっている例外ハンドラと補正ブロック  
 特殊な例外としての機能に加えて、一部の場所のカスタム例外は、ソート フラグとしての役割も果たします。 **変更**オーケストレーション、取り消し操作をロールバックする必要が 2 つの場所があります。  
  
> [!NOTE]
>  このセクションを参照することも、**変更**Visual Studio でオーケストレーションを開きます。  
  
 オーケストレーションの上部にある場合はへの呼び出し、**キャンセル**オーケストレーションが失敗した、 **CancelCompensation**ブロックが実行され、ロールバック、**キャンセル**トランザクションです。 オーケストレーションを呼び出す場合はすべてうまく行けば、 **Activate**オーケストレーションです。  
  
 場合、 **Activate**操作が失敗、**キャンセル**トランザクションもロールバックする必要があります。 ただし、例外ハンドラーへの呼び出しの**Activate**について何ら、**キャンセル**トランザクションです。 これに対処するには、オーケストレーション全体の例外ハンドラを使用します。 このハンドラーが含まれているため、**キャンセル**スコープを認識、**キャンセル**トランザクションです。 スローされた例外をキャッチするハンドラー、 **Activate**スコープ (、 **ActivateException**)、ロールバック、**キャンセル**トランザクション、し、再度、例外をスローオーケストレーションが呼び出されるように、**変更**オーケストレーションは、追加の処理を実行できます。  
  
 補正するだけこの設計に注意してください、**キャンセル**場合、 **Activate**は失敗します。 場合、**キャンセル**は失敗し、例外がスロー、**キャンセル**ことはありませんが行われ、補正いない必要があります。  
  
 補正ブロックの詳細については、**補正**図形は、「[補正図形を構成する方法](../core/how-to-configure-the-compensate-shape.md)です。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md)   
 [ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)