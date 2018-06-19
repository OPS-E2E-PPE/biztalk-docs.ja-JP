---
title: 'WCF アダプター FAQ: WCF エラー処理 |Microsoft ドキュメント'
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
ms.openlocfilehash: efbac0b7aaffd6121cba406031a8330cfd5bbf2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288634"
---
# <a name="wcf-adapter-faq-wcf-error-handling"></a>WCF アダプター FAQ: WCF エラー処理
## <a name="how-do-the-wcf-adapters-handle-errors-and-soap-faults-during-message-processing"></a>WCF アダプターは、メッセージ処理中のエラーや SOAP エラーをどのように処理しますか?  
 受信場所の下にある 2 つのエラー処理オプションのいずれか構成できます、 **Error Handling**セクションで、**メッセージ** タブで、**トランスポートのプロパティ**ダイアログボックスです。  
  
 場合、**エラー発生時に要求メッセージを保留**オプションが選択されている場合、受信要求メッセージは中断されている受信パイプラインで処理エラーやメッセージのルーティングに障害がある必要があります。 これにより、メッセージの送信者は、BizTalk Server への送信を正常に完了し、受信確認 (ACK) メッセージを受け取ることができます。 BizTalk Server はメッセージを中断し、失敗したメッセージの完全なエラー レコードを記録します。 ただしこの場合も、メッセージ例外を送信者に返信することはありません。 このオプションは一方向ポートのみに適用され、オンの場合は ACK を、オフの場合は NACK を送信します。 双方向ポートについては、処理エラーが発生した場合、BizTalk は常に NACK を受信します。  
  
 ただし場合は、クライアントは、障害が発生した例外にアクセスする必要があります、選択、**エラー例外の詳細を含む**オプション。 このオプションを選択した場合、処理エラーが発生した際に、SOAP エラーが呼び出し側に返されます。 これを True に"IncludeExceptionDetailsInFaults"で serviceDebug の動作を指定すると同じ、**動作**Wcf-custom または Wcf-customisolated アダプターのタブです。 例外の詳細がクライアントに送信されるようになります。 このオプションは、運用環境よりもアプリケーションの開発中に使用する方がより実践的で安全です。ほとんどの内部エラー メッセージはサービスの呼び出し側に送信されるべきではないためです。  
  
 双方向の送信ポートのを介してこの転送元の呼び出し元に SOAP エラー メッセージ、送信請求-応答送信ポートを選択するとかどうかを選択できます**エラー メッセージを伝達**です。 このオプションが選択されていない場合、BizTalk Server はまず NACK を生成し、次にメッセージを中断します。 選択されている場合、BizTalk Server はメッセージを外部サービスからの有効な WCF 応答メッセージとして扱います。応答メッセージは伝達されるため、中断されません。  
  
## <a name="how-do-the-wcf-adapters-handle-message-transmission-timing-issues"></a>WCF アダプターは、メッセージ送信タイミングの問題をどのように処理しますか?  
 使用して、WCF アダプタのタイミングの問題を制御することができます、**バインド** タブで、**トランスポートのプロパティ** ダイアログ ボックス。 これらの設定は**開く**、**送信**、および**クローズ タイムアウト**です。 (カスタム アダプターを使用して設定できる [受信タイムアウト] もあります)。これらの設定は、それぞれチャネルを開く、送信する、閉じる (および、カスタムでは受信する) 操作を完了するまでの時間を指定します。 3 つの設定いずれも、既定では最小 1 分 ～ 最大 23:59 です。