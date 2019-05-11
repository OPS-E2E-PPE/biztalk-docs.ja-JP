---
title: ExceptionHandler オーケストレーション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, systems
- errors, applications
- applications, errors
- orchestrations, errors [process management solutions]
- process management solution tutorial, errors
ms.assetid: ac154e76-9dfe-433a-948b-e098df705fe5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fd1a3fccf72b73271528d93bb03060aa259a39
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298740"
---
# <a name="the-exceptionhandler-orchestration"></a>ExceptionHandler オーケストレーション
ビジネス プロセス管理ソリューションは 2 種類の例外を使用して: システム例外とアプリケーションの例外。 システム例外は、リソースのエラーなどを含める-ネットワーク接続の失敗などです。 このような問題は自動的に解決一定の間隔、ソリューションは、システム例外が発生するすべての操作を再試行するための可能性はあります。 アプリケーションの例外は、モ ノの論理エラーや矛盾の何らかの形式などは、解決する可能性が低くによって生成されます。 ソリューションを使用して、 **ExceptionHandlerOrch**システムとアプリケーションの両方のエラーを処理するオーケストレーションです。  
  
 注文処理ステージ (**CableOrder1**、 **CableOrder2**) とそれらのサテライト オーケストレーション (**Activate**、**分析**、 **キャンセル**、**変更**、**完了**、**検証**) すべての使用**ExceptionHandlerOrch**します。  
  
> [!NOTE]
>  このセクションを参照することも、 **ExceptionHandlerOrch**オーケストレーションは、Microsoft で開く[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
## <a name="application-errors"></a>アプリケーション エラー  
 例外ハンドラーは、呼び出すことによって、エラーを記録する最初の**PostError**のメソッド、 **ErrorHandler**オブジェクト、**ユーティリティ**アセンブリ。 例外ハンドラーは、システム エラーまたはアプリケーション エラー、エラーがあったかどうかをテストします。 次のスクリーン ショットは、アプリケーション例外を処理するオーケストレーションの分岐を示しています。  
  
 ![ExceptionHandler オーケストレーションのアプリケーション分岐](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")  
  
 アプリケーション エラーの場合は、オーケストレーションは、エラーと呼び出しを記述する文字列を構築、 **ErrorHandlerOrch**オーケストレーションします。 このオーケストレーションは、オペレーターを決定して、操作を終了またはエラーを修正するかどうかの操作に、エラーを送信します。 演算子は、エラーを修正する場合、は、ErrorHandlerOrch オーケストレーションからのメッセージがバックアップし、操作を再試行します。 例外ハンドラーは呼び出すことによって、 **Invoke**のメソッド、 **Recaller**オブジェクト、**ユーティリティ**アセンブリ。 **Recaller**オブジェクトでは、リフレクションを使用して、エラーが発生したコードを呼び出します。  
  
 場合に呼び出し**Invoke**成功すると、例外ハンドラは終了します。 それ以外の場合、バックアップ ループしへの呼び出しを試みる**Invoke**もう一度です。 詳細については、 **Recaller**オブジェクトを参照してください[「Recaller オブジェクト](../core/the-recaller-object.md)します。  
  
## <a name="system-errors"></a>システム エラー  
 次の図は、システム エラー分岐、 **ExceptionHandler**オーケストレーション。  
  
 ![ExceptionHandler オーケストレーションのシステム エラー](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")  
  
 例外ハンドラーの最初の呼び出し、システム エラーが発生して、 **CheckInterrupt**オーケストレーションを呼び出して 1 分間待機します。 待機は、ネットワーク接続の問題など、一時的、短期的なエラーを再試行する前にオフにできます。 リモート呼び出しを行うときに、ネットワークの問題の可能性は常にあります。  
  
> [!NOTE]
>  割り込み可能なデザインでは、一般的な規則としてする中または割り込みが発生したかどうかに表示するには、すべて待機期間後すぐに、割り込みをテストします。  
  
 ハンドラーを使用して、待機した後、 **Invoke**のメソッド、 **Recaller**オブジェクトを元のコードを実行します。 呼び出しが成功した場合、ハンドラーを終了します。 それ以外の場合、ハンドラーが、元のコードを実行するさらに 2 回試行されます。 エラー文字列と呼び出しの 3 つすべての試行が失敗する場合、ハンドラーを構築します、 **ErrorHandlerOrch**オーケストレーションします。  
  
 システム例外の処理、例外発生すると、その例外ブロックがキャッチされます。  
  
 ![システム エラー分岐の例外ハンドラー](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")  
  
 例外ハンドラーは、システム例外、またはアプリケーションの例外を示すフラグを設定する場合に、カウント ダウンし、例外の種類の再試行回数をテストします。  
  
## <a name="the-errorhandlerorch-orchestration"></a>ErrorHandlerOrch オーケストレーション  
 次の図の最初の部分を示しています、 **ErrorHandlerOrch**オーケストレーション。  
  
 ![エラー ハンドラー オーケストレーション、最初の部分](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")  
  
 **ErrorHandlerOrch**オーケストレーションの最初のテスト、 **IsBadOrder** 、エラーが不適切な順序であるかどうかをパラメーター (**IsBadOrder**が true) またはその他のエラー。 エラーが不適切な順序である場合は、元の順序の戻りアドレスからのメッセージの送信先を割り当てます、メッセージをカスタマ サービス システムに送信します。 エラーが不適切な順序でない場合は、オーケストレーションが注文エラー メッセージを作成し、操作システムに送信します。  
  
 いずれかのエラー後に、オーケストレーションは応答メッセージまたは割り込みメッセージがリッスンします。  
  
 ![エラー ハンドラーの 2 番目の部分](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")  
  
 オーケストレーションでは、応答を受信する場合は、呼び出し元に返します。 オーケストレーションでは、割り込みメッセージを受信する場合を割り込みポートにメッセージを渡し、カスタムをスローします**InterruptException**します。  
  
 ソリューションでを使用する方法と、割り込みを処理する方法の詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションでの処理を中断](../core/interrupt-handling-in-the-business-process-management-solution.md)します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md)   
 [カスタム例外](../core/custom-exceptions.md)   
 [ビジネス プロセス管理ソリューションでの処理を中断します。](../core/interrupt-handling-in-the-business-process-management-solution.md)   
 [Recaller オブジェクト](../core/the-recaller-object.md)