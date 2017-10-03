---
title: "例外の収集および ESB 例外プロセッサを使用して、ペイロードを保持する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52650eed-e760-4ade-bc3f-2b5b2a1c43ff
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec3ca7a33b5a38b625894e391c5bf014eb824414
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="collecting-exceptions-and-persisting-the-payload-using-the-esb-exception-processor"></a>例外の収集および ESB 例外プロセッサを使用して、ペイロードを保持します。
このユース ケースにオーケストレーションの例外ハンドラーが、ESB フォールト メッセージを発行、[!INCLUDE[prague](../includes/prague-md.md)]メッセージ ボックス、または BizTalk 失敗のメッセージのルーティング メカニズムは、エラー メッセージを生成します。 ESB 例外エンコーダ パイプライン コンポーネントでは、事前に構成されて、送信ポートは、エラー メッセージの種類の両方をサブスクライブします。 エラー メッセージを処理し、表示できる、InfoPath を使用して図 1 に示すようにディスク ファイルとが引き続き発生することです。  
  
 ![例外のペイロードの収集](../esb-toolkit/media/ch3-collectingexceptionspayload.gif "Ch3 CollectingExceptionsPayload")  
  
 **図 1**  
  
 **エラー メッセージをキャプチャし、ディスク ファイルに永続化します。**  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次が含まれています。  
  
-   **ESB フォールト プロセッサ送信パイプラインを使用するポートを構成済みに送信します。** 特定の要件に基づいて、この送信ポートを構成することができます。  
  
-   **メッセージの永続化のカスタム例外ハンドラーのサンプルです。** このサンプルは、疎結合の一般的な例外ハンドラーがエラー メッセージを受信する方法を示しています。 これらが含まれて正規化と、拡充、調査メッセージ、ファイル システムにディスク ファイルとして書き込む BizTalk Server メッセージを抽出します。  
  
-   **メッセージのルーティングに失敗しました BizTalk サンプルです。** このサンプルでは、ESB 例外管理フレームワークを正規化し、BizTalk Server でメッセージのルーティングに失敗しましたメカニズムによってネイティブに生成されたエラー メッセージの強化方法を示します。  
  
 詳細については、次を参照してください。[メッセージのカスタム例外ハンドラーの永続化サンプルを実行している](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)と[サンプルを実行する BizTalk できませんでしたメッセージ ルーティング ESB 処理](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)です。