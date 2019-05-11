---
title: AS2 の処理に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 941111d8-b394-4648-a675-e4a8f118a84b
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 389184d177fe1b192db22660bdf382a6e64f37bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329386"
---
# <a name="known-issues-with-as2-processing"></a>AS2 の処理に関する既知の問題
このセクションには、BizTalk Server AS2 ソリューションに関する既知の問題を説明するトピックが含まれています。  
  
## <a name="as2-processing-not-supported-on-64-bit-computers"></a>AS2 処理の 64 ビット コンピューターでサポートされていません  
 BizTalk Server AS2 ソリューションは、64 ビット コンピューターではサポートされていません。 64 ビット コンピューターでの WOW64 エミュレーターで実行されているときに、32 ビット コンピューターで、または AS2 処理のみ機能します。  
  
## <a name="the-as2-receive-pipelines-require-the-account-that-the-biztalk-isolated-host-instance-process-is-running-under-to-be-part-of-the-biztalk-application-users-group"></a>AS2 受信パイプラインが、BizTalk 分離ホスト インスタンス プロセスで実行されているに含まれて、BizTalk アプリケーション ユーザー グループのアカウントが必要です。  
 AS2EdiReceive または AS2Receive パイプラインを使用している場合は、BizTalk 分離ホスト インスタンス プロセスは、BizTalk Application Users グループで実行されているユーザー アカウントを追加する必要があります。 AS2EdiReceive と AS2Receive パイプラインは、BizTalk 分離ホスト インスタンス プロセスで実行します。  
  
## <a name="an-empty-receipt-delivery-option-header-will-cause-an-mdn-to-be-sent-synchronously"></a>Receipt-delivery-option ヘッダーが空白になります、MDN を同期的に送信します。  
 AS2Receive パイプラインが受信メッセージの receipt-delivery-option ヘッダーが空白を非同期 MDN が要求された場合は、パイプラインは、非同期 MDN 要求を無視します。 同期 MDN を代わりに、返信、イベント ログと AS2 状態レポート (有効な) 場合、エラーが送信されます。 これは、「受信メッセージのプロパティを上書きする」プロパティが選択されていない場合に発生します。 そのプロパティを選択した場合は、パーティの Receipt-delivery-option プロパティの値を持つメッセージのメッセージの Receipt-delivery-option ヘッダーを AS2 のプロパティ ダイアログ ボックスの AS2 メッセージの送信者 ページとしてオーバーライドします。  
  
 このインスタンスでの receipt-delivery-option ヘッダーが空であるため、AS2Receive パイプラインはありません非同期接続経由でへの MDN 応答を送信するアドレス。 ただし、パイプラインは、まだ、同期接続が開いてその接続を介して、MDN を送信します。 一方向である場合は、受信ポート、BizTalk Server は、HTTP 200OK メッセージを送信した後で接続を閉じます。  
  
## <a name="use-of-unfolded-and-folded-http-line-headers"></a>展開された、折りたたまれた HTTP 行ヘッダーを使用して  
 最大の相互運用性、AS2 メッセージの展開された HTTP 行ヘッダーを使用する必要があります。 インフォメーション サービス (IIS) 7.0 には、展開された HTTP ヘッダーだけがサポートされています。 IIS 6.0 では、2 つ折りと折りたたまれたヘッダーをサポートします。 ただし、すべてのシステムは、ため、このようなシステムの折りたたまれた行を使用する必要があります、80 以上の文字を 1 行のヘッダーをサポートできます。  
  
 BizTalk Server における AS2 の既定値は、展開された HTTP 行ヘッダーです。  
  
## <a name="party-resolution-can-be-affected-by-a-localized-name"></a>パーティの解決はローカライズされた名前によって影響を受けることができます。  
 BizTalk Server では、送信 AS2 メッセージのパーティの解決を実行し、パーティの解決がメッセージ ヘッダー内のローカライズされた値によって影響を受けることができます。 場合、AS2 の既定では英語のパーティ名、および AS2 の値に設定されているため、AS2 のプロパティ ダイアログ ボックスの AS2 メッセージの受信者 ページで、パーティのプロパティをパーティに-英語以外の名前に設定されているメッセージの AS2 ヘッダーにし、一致が見つかりません。  
  
## <a name="as2-message-size-limitation"></a>AS2 メッセージのサイズ制限  
 暗号化された AS2 メッセージは、処理するために 96 メガバイト数よりも小さい必要があります。 AS2Receive と AS2EdiReceive パイプラインの一部である AS2 デコーダーでは、この制限が適用されます。  
  
 このサイズの制限を回避する方法の 1 つは、AS2 メッセージを圧縮すると、前に、暗号化されているため、圧縮を使用します。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>BizTalk EDI アプリケーションを変更する必要がありません。  
 BizTalk EDI アプリケーションのアイテムを変更または削除する必要があります。 このアプリケーションが変更された場合は、構成を解除し、EDI および AS2 機能を再構成して、元のアプリケーションを復元する方法はありません。  
  
## <a name="partner-may-reject-multipart-messages"></a>パートナーがマルチパート メッセージを拒否します。  
 **現象**  
  
 送信パイプライン、AS2 を使用してマルチパート メッセージを送信する場合、パートナーが不足している Content-type MIME ヘッダーによりメッセージを拒否します。  
  
 **考えられる原因**  
  
 コンテンツの種類は、各ボディ部のマルチパート メッセージに存在することができる省略可能なヘッダーです。 一部のパートナーでは、このヘッダーが各ボディ部、およびセットの特定のコンテンツの種類に存在することが必要です。  
  
> [!NOTE]
>  すべての添付ファイルには、コンテンツの種類プロパティの設定はありません。 ただし、メッセージの本文は、AS2 送信パイプラインで設定するコンテンツの種類プロパティがあります。  
  
 **解決方法**  
  
 パートナーは、各ボディ部の Content-type ヘッダーの値を必要とする場合は、このプロパティを設定するカスタム パイプライン コンポーネントを作成および送信パイプラインでコンポーネントを使用する必要があります。  
  
## <a name="when-receiving-multipart-messages-the-first-part-is-considered-the-body"></a>マルチパート メッセージの受信、最初の部分と見なされるタイミング本文  
 **現象**  
  
 マルチパートの AS2 メッセージの受信時[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能性があります誤認する添付ファイルのいずれかのメッセージ本文として。  
  
 **考えられる原因**  
  
 マルチパート/関連メッセージの MIME ヘッダー、省略可能な場合がありますを指定する部分の 'start' のパラメーターは、パーツのコンテンツ ID を指定して、メッセージの本文として扱う必要があります。 Start パラメーターが存在しない場合は、最初の部分がメッセージの本文を検討してください。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージの本文として最初の部分は常に扱いますが存在する場合は、start パラメーターを考慮しません。  
  
 **解決方法**  
  
 パートナーがマルチパート/関連メッセージの最初の部分として本文を送信できるように、メッセージの本文を正しく識別するパイプライン コンポーネントを作成する必要があります。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)   
 [AS2 ソリューションのアーキテクチャ](../core/as2-solution-architecture.md)   
 [BizTalk Server AS2 ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)