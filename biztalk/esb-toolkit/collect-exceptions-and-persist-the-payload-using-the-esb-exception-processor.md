---
title: 例外の収集および ESB 例外プロセッサを使用してペイロードを保持する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52650eed-e760-4ade-bc3f-2b5b2a1c43ff
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdbffb24052e1dd926f74252c68a621fe92c5ab6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302202"
---
# <a name="collecting-exceptions-and-persisting-the-payload-using-the-esb-exception-processor"></a>例外の収集および ESB 例外プロセッサを使用してペイロードを保持します。
このユース ケースでは、オーケストレーションの例外ハンドラーを BizTalk Server メッセージ ボックスに、ESB エラー メッセージを発行するか、または BizTalk 失敗のメッセージのルーティング メカニズムには、エラー メッセージが生成されます。 ESB 例外エンコーダー パイプライン コンポーネントを事前構成済み、送信ポートは、エラー メッセージの種類の両方をサブスクライブします。 エラー メッセージを処理し、それらを表示、InfoPath を使用して図 1 に示すようにディスク ファイルとしてが引き続き発生します。  
  
 ![収集のペイロードの例外](../esb-toolkit/media/ch3-collectingexceptionspayload.gif "Ch3 CollectingExceptionsPayload")  
  
 **図 1**  
  
 **エラー メッセージをキャプチャし、ディスク ファイルを永続化します。**  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次が含まれています。  
  
- **ESB エラー プロセッサの送信パイプラインを使用するポートを構成済みに送信します。** 独自の要件に従って、この送信ポートを構成できます。  
  
- **メッセージの永続化カスタム例外ハンドラーのサンプルです。** この例では、疎結合の汎用的な例外ハンドラーが、エラー メッセージを受信する方法を含む、正規化に、メッセージを強化およびファイル システムにディスク ファイルとして書き込むが、BizTalk Server メッセージを抽出します。  
  
- **メッセージのルーティングに失敗しました BizTalk サンプルです。** このサンプルでは、ESB 例外管理フレームワークの正規化および BizTalk Server の失敗のメッセージのルーティング メカニズムによって生成されたネイティブ フォールト メッセージを強化する方法を示します。  
  
  詳細については、次を参照してください。[メッセージの永続化カスタム例外ハンドラー サンプルを実行している](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)と[BizTalk できませんでしたメッセージ ルーティング ESB 処理サンプルを実行している](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)します。