---
title: 例外を収集し、修復と再送信のメッセージのルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a61658a-0bac-4802-b506-02e61a3d2a9b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88e76164a26e1dfd227d7fea79cfa8106825f25d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302139"
---
# <a name="collecting-exceptions-and-routing-messages-for-repair-and-resubmit"></a>例外を収集し、修復と再送信のメッセージをルーティングします。
このユース ケースで、カスタム例外ハンドラーが Web サービス経由で受信したエラー メッセージを取得しに含まれている InfoPath テンプレートを使用した互換性のある形式でディスク ファイルにルーティング、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。 ユーザーは Microsoft InfoPath を使用してファイルを開き、メッセージの内容を編集および図 1 に示すように、処理には、メッセージを再実行してください。  
  
 ![例外の修復を収集](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3 CollectingExceptionsRepair")  
  
 **図 1**  
  
 **修復と再送信メッセージのルーティング**  
  
 含まれている修復と再送信のカスタム例外ハンドラーのサンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。 オーケストレーションでのプロセスが検出した場合、エラー、例外ハンドラーで、オーケストレーションを生成、ESB エラー メッセージがパブリッシュされます。 このエラー メッセージが含まれている、ペイロードでメッセージ (BizTalk Server に関連すると、コンテキスト プロパティを含む)"インフライト"であった場合、例外が発生したし、BizTalk オーケストレーション エンジンによって現在の例外がキャッチされました。 サブスクライブするオーケストレーション (カスタム例外ハンドラー) を抽出し、インフライトのメッセージと、システム例外オブジェクトを検査し、元のファイルのフォルダーにインフライトのメッセージをルーティングするキューから取り出された ESB のエラー メッセージがパブリッシュされた後、ユーザーは、InfoPath を使用してメッセージを編集し、処理の BizTalk Server に再送信します。  
  
 詳細については、次を参照してください。[修復と再送信のカスタム例外ハンドラーのサンプルを実行する](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)します。