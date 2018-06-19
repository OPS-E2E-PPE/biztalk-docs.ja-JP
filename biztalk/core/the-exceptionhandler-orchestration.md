---
title: ExceptionHandler オーケストレーション |Microsoft ドキュメント
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
ms.openlocfilehash: a1b79a1c6d9e6fada206ba0298913fe8f369783c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280026"
---
# <a name="the-exceptionhandler-orchestration"></a>ExceptionHandler オーケストレーション
ビジネス プロセス管理ソリューションで 2 つの種類の例外を使用します。 システム例外とアプリケーションの例外。 システム例外を含めるようなリソース エラー: ネットワーク接続の失敗、例を示します。 このような問題は、時間が経つと自然に解決する可能性があるので、ソリューションはシステム例外の原因となったすべての操作を再試行します。 アプリケーション例外は、論理エラーや不整合など、自然に解決する可能性の少ない事象を原因として生じます。 ソリューションを使用して、 **ExceptionHandlerOrch**システムとアプリケーションの両方のエラーを処理するオーケストレーションです。  
  
 注文処理ステージ (**CableOrder1**、 **CableOrder2**) とそれらのサテライト オーケストレーション (**Activate**、**分析**、 **キャンセル**、**変更**、**完了**、**検証**) すべての使用**ExceptionHandlerOrch**です。  
  
> [!NOTE]
>  このセクションを参照することも、 **ExceptionHandlerOrch**オーケストレーションは、マイクロソフトで開く[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。  
  
## <a name="application-errors"></a>アプリケーション エラー  
 例外ハンドラーでは呼び出すことによって、エラーがログ記録最初、 **PostError**のメソッド、 **ErrorHandler**内のオブジェクト、**ユーティリティ**アセンブリ。 次に例外ハンドラはそのエラーがシステム エラーかアプリケーション エラーかを調べます。 次のスクリーンショットは、アプリケーション例外を処理するオーケストレーションの分岐です。  
  
 ![ExceptionHandler オーケストレーションのアプリケーション分岐](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")  
  
 アプリケーション エラーの場合は、オーケストレーションがエラーと呼び出しを表す文字列を構築、 **ErrorHandlerOrch**オーケストレーションです。 このオーケストレーションは、エラーを修正するか操作を終了するかをオペレータが決定できるように、エラーを操作元に送ります。 オペレータがエラーを修正した場合は、ErrorHandlerOrch オーケストレーションからエラー修正のメッセージが返され、操作が再試行されます。 例外ハンドラーは、呼び出すことによって、 **Invoke**のメソッド、 **Recaller**内のオブジェクト、**ユーティリティ**アセンブリ。 **Recaller**オブジェクトでは、リフレクションを使用して、エラーの原因となったコードを呼び出します。  
  
 場合に呼び出し**Invoke**成功すると、例外ハンドラは終了します。 それ以外の場合、ƒvƒoƒbƒn しへの呼び出しを試みる**Invoke**もう一度です。 詳細については、 **Recaller**オブジェクトを参照してください[Recaller Object](../core/the-recaller-object.md)です。  
  
## <a name="system-errors"></a>システム エラー  
 次の図は、システム エラー分岐の**ExceptionHandler**オーケストレーション。  
  
 ![ExceptionHandler オーケストレーションのシステム エラー](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")  
  
 システム エラーを例外ハンドラー最初の呼び出し、 **CheckInterrupt**オーケストレーションを 1 分間待機します。 再試行する前に、ネットワーク接続の問題のように一時的な短時間のエラーが解決するのを待つためです。 リモートの呼び出しでは常にネットワーク障害の可能性があります。  
  
> [!NOTE]
>  割り込み可能なデザインでは、通常、割り込みがあったかどうかを待機期間中またはその直後に調べます。  
  
 ハンドラーを使用して、待機した後、 **Invoke**のメソッド、 **Recaller**オブジェクトを元のコードを実行します。 呼び出しに成功すると、例外ハンドラは終了します。 失敗すると、元のコードの実行を 2 度試みます。 エラー文字列と呼び出し 3 つすべての試行が失敗する場合、ハンドラーを構築、 **ErrorHandlerOrch**オーケストレーションです。  
  
 システム例外の処理で発生した例外は、例外ブロックがキャッチします。  
  
 ![システム エラー分岐の例外ハンドラー](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")  
  
 例外ハンドラは例外の種類を調べて、システム例外の場合は再試行カウンタをカウント ダウンします。アプリケーション例外の場合は、そのフラグを設定します。  
  
## <a name="the-errorhandlerorch-orchestration"></a>ErrorHandlerOrch オーケストレーション  
 次の図の最初の部分を示しています、 **ErrorHandlerOrch**オーケストレーション。  
  
 ![エラー ハンドラー オーケストレーション、最初の部分](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")  
  
 **ErrorHandlerOrch**オーケストレーションの最初のテスト、 **IsBadOrder**パラメーターを参照してエラーが不適切な順序 (**IsBadOrder**が true) またはその他のエラーです。 注文が無効である場合は、元の注文の返信先アドレスをメッセージの送信先に指定してメッセージをカスタマ サービス システムに返します。 注文に問題がない場合は、オーケストレーションが注文エラー メッセージを作成して操作システムに送ります。  
  
 どちらのエラーでも、オーケストレーションは次に応答メッセージまたは割り込みメッセージを待機します。  
  
 ![エラー ハンドラーの 2 番目の部分](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")  
  
 オーケストレーションは応答を受け取ると、呼び出し元に返します。 オーケストレーションは割り込みメッセージを受け取る場合を割り込みポートにメッセージを渡しますされ、カスタムのスロー **InterruptException**です。  
  
 ソリューションでを使用する方法と、割り込みを処理する方法の詳細については、次を参照してください。[ビジネス プロセス管理ソリューションでの処理を中断](../core/interrupt-handling-in-the-business-process-management-solution.md)です。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md)   
 [カスタム例外](../core/custom-exceptions.md)   
 [ビジネス プロセス管理ソリューションでの処理を中断します。](../core/interrupt-handling-in-the-business-process-management-solution.md)   
 [Recaller オブジェクト](../core/the-recaller-object.md)