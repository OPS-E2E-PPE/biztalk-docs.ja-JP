---
title: メッセージ キューのキュー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [MSMQ adapters], queue paths
- naming conventions, MSMQ adapters
- configuring [MSMQ adapters], naming conventions
- messages, queuing
- MSMQ adapters, troubleshooting
- MSMQ adapters, message queues
- configuring [MSMQ adapters], troubleshooting
- troubleshooting, queue paths [MSMQ adapters]
- naming conventions, queue paths [MSMQ adapters]
- configuring [MSMQ adapters], message queues
ms.assetid: b802348e-8543-4b06-a6e4-149b86139fb1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2f5c2d4861a59ded7c19da84d0ca0e6ded9ddfe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394560"
---
# <a name="message-queuing-queues"></a>メッセージ キューのキュー
このセクションでは、MSMQ アダプターを使用するときに、Microsoft メッセージ キュー (MSMQ とも呼ばれます) のキューを指定する方法について説明します。 パスを指定する規則について説明し、キューの指定にパスを変換することで形式名の役割についても説明します。  
  
## <a name="queue-path-naming-conventions"></a>キューのパスの名前付け規則  
 キュー名は、パスが参照されている場合は、次の表に、名前付け規則を使用します。  
  
|**[キューの種類]**|**パスの構文**|  
|--------------------|-------------------------|  
|パブリック キュー|*Computername*\QueueName|  
|専用キュー|*Computername*\Private$\QueueName|  
|ジャーナル キュー|*Computername*\QueueName\Journal$|  
|コンピューター ジャーナル キュー**に注意してください。** 受信キューにのみ使用します。|*Computername*\Journal$|  
|コンピューター配信不能キュー**に注意してください。** 受信キューにのみ使用します。|*Computername*\Deadletter$|  
|コンピューター トランザクション配信不能キュー**に注意してください。** 受信キューにのみ使用します。|*Computername*\XactDeadletter$|  
  
> [!NOTE]
>  キューのパスは一意である必要があります。  
  
 キュー名は、形式名が参照されている場合を示すかどうか、キュー、パブリックまたはプライベート キューとその他の識別子の GUID を生成後に、必要に応じて文字列の形式になります。 次の表に、名前付け規則を使用します。  
  
|**形式の種類**|**形式名の構文**|  
|---------------------|--------------------------------|  
|パブリック|*FormatName*:Public=QueueGUID|  
|[直接]|*FormatName*:DIRECT=SPX:NetworkNumber:HostNumber\QueueName<br /><br /> *FormatName*:DIRECT=TCP:IPAddress\QueueName<br /><br /> *FormatName*:DIRECT=OS:ComputerName\QueueName|  
  
 送信ポートのキューのパスが配布リストの場合は、キューのパスの構文は。  
  
 DL = DistributionListGUID  
  
 場合、送信または受信キューのパスが、HTTP または HTTPS の URL では、構文。  
  
 形式名:direct = http://\<クライアント名\>/msmq/\<キュー名\>  
  
 形式名:direct = https://\<クライアント名\>/msmq/\<キュー名\>  
  
> [!NOTE]
>  "msmq"は、メッセージ キューでは、インターネット インフォメーション サービス (IIS) が作成される仮想フォルダーです。  
  
> [!NOTE]
>  メッセージを送信するのにのみ HTTP を使用できます。 キューが HTTP の直接形式名を使用して開かれている場合は、リモート コンピューター上のキューでメッセージを読み取ることができません。 ただし、まだメッセージを受信できます SOAP (形式の) リモート キューから HTTP を使用しないプライベートまたはパブリック キューのパスを使用しています。  
  
 キュー名はわかりやすいテキストを参照している場合、キューの指定した管理者をラベル付けし、ラベルを参照するキューのパスの構文は。  
  
 ラベル: MyQueue  
  
> [!NOTE]
>  ラベルは常に一意ではありません。 そのため、そのラベルを使用して、特定のキューに接続しようとすると、名前の競合が存在する場合、エラーが表示されます。  
  
> [!NOTE]
>  ラベルは、アダプターの必須のトランスポート フィールドです。  
  
## <a name="role-of-the-format-name"></a>形式名の役割  
 メッセージ キューは、キューを識別するために、それにアクセスする方法を決定する、形式名を使用します。 メッセージ キューは、キューに形式名を割り当てます。  
  
 たとえばパス名の構文を使用してキューを指定すると、myMachine\myQueue、メッセージ キューは関連付けられている形式名を検索するパスを検索します。 後、メッセージ キューは、その形式名を使用して、キューにアクセスします。 形式名を指定する場合はメッセージ キューを使用する形式名を使用します。  
  
 形式名の詳細については、.NET Framework クラス ライブラリのヘルプ「「MessageQueue.FormatName プロパティ」を参照してください。  
  
## <a name="troubleshooting-queue-paths"></a>キューのパスのトラブルシューティング  
  
-   例外は、指定されたキューのパスの構文は「キューのパスの名前付け規則」で既に説明した形式のいずれかが一致しない場合に発生します。  
  
-   次に、いないキューのパスでコンピューター名の有効な文字。  
  
     \ ; , + "  
  
     例外は、コンピューター名が数値の場合に発生します。 例 :234\private$\queue.  
  
-   コンピューター配信不能メッセージ キュー、コンピュータ ジャーナル キュー、およびコンピューター トランザクション配信不能キューは、ユーザーの送信先のキューととしてシステム キューのいずれかが指定されている場合、例外が発生しました。  
  
-   **System.Messaging.MessageQueue.Exists**リモート キューは機能しません。 詳細については、.NET Framework クラス ライブラリのヘルプ「「MessageQueue.Exists メソッド」を参照してください。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)