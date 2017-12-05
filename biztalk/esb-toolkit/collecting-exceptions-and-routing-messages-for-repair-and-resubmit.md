---
title: "例外の収集と修復と再送信メッセージをルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a61658a-0bac-4802-b506-02e61a3d2a9b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a1d080cc3b87cf371729c51e1b1f26e07ae521e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="collecting-exceptions-and-routing-messages-for-repair-and-resubmit"></a>例外の収集と修復と再送信メッセージをルーティングします。
このユース ケースでのカスタム例外ハンドラーが、Web サービス経由で受信したエラー メッセージを取得しに含まれている InfoPath テンプレートと互換性のある形式でディスク ファイルにルーティング、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。 ユーザーが Microsoft InfoPath を使用して、ファイルを開くことができます、メッセージの内容を編集および図 1 に示すように、処理のためにメッセージを再送信します。  
  
 ![例外の修復を収集](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3 CollectingExceptionsRepair")  
  
 **図 1**  
  
 **修復と再送信メッセージのルーティング**  
  
 含まれている修復と再送信のカスタム例外ハンドラーのサンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 オーケストレーションで処理を検出した場合、エラー、例外ハンドラーで、オーケストレーションを生成、ESB フォールト メッセージを公開します。 このエラー メッセージが含まれている、ペイロード内 (BizTalk Server に関連すると、コンテキスト プロパティを含む)、メッセージには内に"インフライト"であった場合、例外が発生したし、BizTalk オーケストレーション エンジンによって、現在の例外がキャッチされました。 サブスクライブするオーケストレーション (カスタム例外ハンドラー) を抽出し、インフライトのメッセージと、システム例外オブジェクトを検査し、元のファイルのフォルダーにインフライトのメッセージをルーティングするキューから取り出された ESB フォールト メッセージをパブリッシュした後、ユーザーは、InfoPath を使用してメッセージを編集し、処理用に BizTalk Server に再送信します。  
  
 詳細については、次を参照してください。[修復と再送信のカスタム例外ハンドラーのサンプルを実行する](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)です。