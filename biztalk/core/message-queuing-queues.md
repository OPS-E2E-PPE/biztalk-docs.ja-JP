---
title: メッセージ キューのキュー |Microsoft ドキュメント
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
ms.openlocfilehash: fa8d2521a8cf434c7a0ea56f749f9df3f032551e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971464"
---
# <a name="message-queuing-queues"></a>メッセージ キューのキュー
このセクションでは、Microsoft メッセージ キュー (MSMQ) アダプタを使用する際に、MSMQ キューを指定する方法について説明します。 パスを指定するための名前付け規則、およびパスをキューの指定に変換するときの形式名の役割についても説明します。  
  
## <a name="queue-path-naming-conventions"></a>キューのパスの名前付け規則  
 キュー名でパスを参照する場合、次の表の名前付け規則を使用します。  
  
|**[キューの種類]**|**パスの構文**|  
|--------------------|-------------------------|  
|パブリック キュー|*Computername*\QueueName|  
|専用キュー|*Computername*\Private$\QueueName|  
|ジャーナル キュー|*Computername*\QueueName\Journal$|  
|コンピューター ジャーナル キュー**注:** 受信キューにのみ使用します。|*Computername*\Journal$|  
|コンピューターの配信不能キュー**注:** 受信キューにのみ使用します。|*Computername*\Deadletter$|  
|コンピューター トランザクション配信不能キュー**注:** 受信キューにのみ使用します。|*Computername*\XactDeadletter$|  
  
> [!NOTE]
>  キューのパスは、一意である必要があります。  
  
 キュー名で形式名を参照する場合、形式名は、キューがパブリックかプライベートかを示す文字列から始まり、キューに対して生成された GUID、および必要に応じてその他の識別子が続きます。 次の表の名前付け規則を使用してください。  
  
|**形式の種類**|**形式名の構文**|  
|---------------------|--------------------------------|  
|パブリック|*FormatName*: パブリック:public =|  
|[直接]|*FormatName*: DIRECT = SPX:NetworkNumber:HostNumber\QueueName<br /><br /> *FormatName*: DIRECT = TCP:IPAddress\QueueName<br /><br /> *FormatName*: DIRECT = OS:ComputerName\QueueName|  
  
 送信ポートのキューのパスが同報リストである場合、キューのパスの構文は次のとおりです。  
  
 DL=同報リストの GUID  
  
 送信または受信キューのパスが、HTTP または HTTPS の URL である場合、構文は次のとおりです。  
  
 形式名:direct = http://\<クライアント名\>/msmq/\<キュー名\>  
  
 形式名:direct = https://\<クライアント名\>/msmq/\<キュー名\>  
  
> [!NOTE]
>  "msmq" は、メッセージ キューによってインターネット インフォメーション サービス (IIS) に作成される仮想フォルダです。  
  
> [!NOTE]
>  HTTP は、メッセージの送信のみに使用できます。 リモート コンピューターのキューのメッセージは、キューが HTTP の直接形式名を使用して開かれている場合は、読み取ることができません。 HTTP を使用しない専用キューまたはパブリック キューのパスを使用して、リモート キューの SOAP (形式の) メッセージを受信することはできます。  
  
 管理者がキューに指定した説明的なテキスト ラベルをキュー名で参照している場合、そのラベルを参照するキューのパスの構文は次のとおりです。  
  
 LABEL:MyQueue  
  
> [!NOTE]
>  ラベルは一意とは限りません。 そのため、ラベルを使用して特定のキューに接続しようとしたときに名前の競合があると、エラーが返されます。  
  
> [!NOTE]
>  ラベルはアダプタの必須のトランスポート フィールドです。  
  
## <a name="role-of-the-format-name"></a>形式名の役割  
 形式名は、キューを識別し、キューへのアクセス方法を特定するために使用されます。 形式名はメッセージ キューによってキューに割り当てられます。  
  
 "コンピュータ名\キュー名" など、パス名の構文を使用してキューを指定するとき、メッセージ キューはパスを検索して関連する形式名を検出します。 その後、形式名を使用してキューにアクセスします。 形式名を指定すると、メッセージ キューではその形式名が使用されます。  
  
 形式名の詳細については、.NET Framework クラス ライブラリ ヘルプの「MessageQueue.FormatName プロパティ」を参照してください。  
  
## <a name="troubleshooting-queue-paths"></a>キューのパスに関するトラブルシューティング  
  
-   指定したキューのパスの構文が、前半の「キューのパスの名前付け規則」に記載した形式のいずれとも一致しない場合、例外が発生します。  
  
-   キューのパスのコンピュータ名には、以下の文字は無効です。  
  
     \ ; , + "  
  
     コンピュータ名が数字である場合、例外が発生します。 例: 234\private$ \queue です。  
  
-   コンピュータの配信不能キュー、コンピュータ ジャーナル キュー、およびコンピュータのトランザクション配信不能キューを使用する場合、ユーザーが送信先のキューとしてシステム キューを指定すると、例外が発生します。  
  
-   **System.Messaging.MessageQueue.Exists**リモート キューでは機能しません。 詳細については、.NET Framework クラス ライブラリ ヘルプの「MessageQueue.Exists メソッド」を参照してください。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)