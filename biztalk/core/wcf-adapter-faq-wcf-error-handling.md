---
title: WCF アダプターに関する FAQ:WCF エラー処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdbd1ea6-4898-415c-ac5e-f804565759a8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f43e7eaccfdb13324d374833ee27fe7144abb9cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379849"
---
# <a name="wcf-adapter-faq-wcf-error-handling"></a>WCF アダプターに関する FAQ:WCF エラー処理
## <a name="how-do-the-wcf-adapters-handle-errors-and-soap-faults-during-message-processing"></a>WCF アダプターの処理方法エラーや SOAP エラー メッセージの処理中にしますか。  
 受信場所を下の 2 つのエラー処理オプションのいずれかを構成できます、**エラー処理**セクションで、**メッセージ** タブで、**トランスポートのプロパティ**ダイアログボックス。  
  
 場合、**エラー発生時に要求メッセージを保留**オプションが選択されている着信要求メッセージは中断されます場合、受信パイプラインで処理エラーまたはメッセージのルーティングの障害が存在する必要があります。 これにより、BizTalk Server への送信に成功し、受信確認 (ACK) メッセージを受信するメッセージの送信者ができます。 BizTalk Server は、メッセージと、失敗したメッセージの完全なエラー レコードのレコードを中断します。 ただしも送信しませんメッセージ例外、送信者に送り返すここでします。 これは一方向ポートのみに適用され、ACK の送信とオンにした場合、オフにした場合は NACK を送信します。 双方向のポート、処理に失敗した場合、BizTalk は NACK を常を受信します。  
  
 ただし場合は、クライアントは、障害が発生した例外にアクセスする必要があります、選択、**エラー例外の詳細を含む**オプション。 選択した場合、この SOAP エラー、呼び出し元に戻ります処理エラーが発生した場合。 これは、"IncludeExceptionDetailsInFaults"にして serviceDebug の動作を True に指定した場合と同じ、**動作**Wcf-custom または Wcf-customisolated アダプターのタブ。 例外の詳細は、クライアントに送信しました。 このオプションより実践的で安全に内部エラー メッセージほとんどの場合は送信されないためするサービスの呼び出し元に運用環境よりもアプリケーションの開発時に使用します。  
  
 双方向の送信ポートの送信請求-応答の上の最初の呼び出し元に SOAP エラー メッセージを送信ポート転送 を選択するかどうかを選択できます**エラー メッセージを伝達**します。 このオプションが選択されていない BizTalk Server はまず、NACK を生成し、メッセージを中断します。 選択されている場合は、BizTalk Server は、外部サービスから有効な WCF 応答メッセージとしてメッセージを処理する、および伝達されるため、応答メッセージは中断されません。  
  
## <a name="how-do-the-wcf-adapters-handle-message-transmission-timing-issues"></a>WCF アダプタは、メッセージ送信タイミングの問題をどのように処理するのでしょうか。  
 使用して、WCF アダプタのタイミングの問題を制御することができます、**バインド** タブで、**トランスポートのプロパティ** ダイアログ ボックス。 これらの設定は**オープン**、**送信**、および**クローズ タイムアウト**します。 (はもカスタム アダプターを使用して設定できる受信タイムアウト) です。これらの設定は、それぞれを開く、送信、チャネルとチャネルを閉じる (およびカスタムの受信) の時間操作が終了します。 1 分 23:59 までの最大期間を最小に 3 つすべての既定です。