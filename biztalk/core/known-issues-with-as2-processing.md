---
title: "AS2 処理に関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 941111d8-b394-4648-a675-e4a8f118a84b
caps.latest.revision: "40"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64899c184f8cbe405684387b8f1c2a6230204624
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-as2-processing"></a>AS2 の処理に関する既知の問題
ここには、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] AS2 ソリューションの既知の問題について説明するトピックが含まれています。  
  
## <a name="as2-processing-not-supported-on-64-bit-computers"></a>AS2 処理が 64 ビット コンピューターに対応していない  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] AS2 ソリューションは、64 ビット コンピューターに対応していません。 AS2 処理を正しく行えるのは、32 ビット コンピューターで実行する場合、または 64 ビット コンピューター上の WOW64 エミュレーターで実行する場合のみです。  
  
## <a name="the-as2-receive-pipelines-require-the-account-that-the-biztalk-isolated-host-instance-process-is-running-under-to-be-part-of-the-biztalk-application-users-group"></a>AS2 受信パイプラインでは、BizTalk 分離ホスト インスタンス プロセスの実行に使用するアカウントが BizTalk アプリケーション ユーザー グループに含まれていることが必要  
 AS2EdiReceive パイプラインまたは AS2Receive パイプラインを使用する場合は、BizTalk Application Users グループに、BizTalk 分離ホスト インスタンス プロセスが実行されているユーザー アカウントを追加する必要があります。 AS2EdiReceive パイプラインと AS2Receive パイプラインは、BizTalk 分離ホスト インスタンス プロセスで実行されます。  
  
## <a name="an-empty-receipt-delivery-option-header-will-cause-an-mdn-to-be-sent-synchronously"></a>Receipt-Delivery-Option ヘッダーを空白にすると、MDN が同期送信される  
 Receipt-Delivery-Option ヘッダーが空白のメッセージを AS2Receive パイプラインが受信した場合に、非同期 MDN が要求されると、このパイプラインは非同期 MDN 要求を無視します。 パイプラインは、代わりに同期 MDN を返して、イベント ログと AS2 状態レポート (有効になっている場合) にエラーを送信します。 この問題は、"受信メッセージのプロパティを上書きする" プロパティが選択されていない場合に発生します。 このプロパティを選択した場合、メッセージ内の Receipt-Delivery-Option ヘッダーは、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの送信者] ページにある Receipt-Delivery-Option プロパティの値で上書きされます。  
  
 この場合、Receipt-Delivery-Option ヘッダーが空白なので、AS2Receive パイプラインには非同期接続を介した MDN 応答の送信先アドレスが指定されていません。 ただし、パイプラインの同期接続は開かれたままなので、MDN は同期接続を介して送り返されます。 これが一方向の受信ポートの場合、BizTalk Server は、HTTP 200OK メッセージを送信した後で接続を閉じます。  
  
## <a name="use-of-unfolded-and-folded-http-line-headers"></a>展開された HTTP 行ヘッダーと折りたたまれた HTTP 行ヘッダーの使用  
 相互運用性を最大化するには、展開された HTTP 行ヘッダーを AS2 メッセージに対して使用します。 インフォメーション サービス (IIS) 7.0 は展開された HTTP ヘッダーにのみ対応しています。 IIS 6.0 は展開されたヘッダーと折りたたまれたヘッダーに対応しています。 ただし、一部のシステムは、1 行あたりの文字数が 80 を上回るヘッダーに対応していません。そのため、これらのシステムでは、折りたたまれた行を使用する必要があります。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の AS2 の既定値は展開された HTTP 行ヘッダーです。  
  
## <a name="party-resolution-can-be-affected-by-a-localized-name"></a>ローカライズされた名前がパーティの解決に影響する場合がある  
 BizTalk Server が送信 AS2 メッセージに対してパーティの解決を実行すると、メッセージ ヘッダー内のローカライズされた値がパーティの解決に影響する場合があります。 [AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページにある AS2-To パーティ プロパティが既定で英語のパーティ名に設定されている場合に、AS2 メッセージの AS2-To ヘッダー内の値が英語以外の名前に設定されていると、一致した項目は見つかりません。  
  
## <a name="as2-message-size-limitation"></a>AS2 メッセージのサイズ制限  
 暗号化された AS2 メッセージは、サイズが 96 MB 未満でないと処理されません。 この制限は、AS2Receive パイプラインと AS2EdiReceive パイプラインに含まれている AS2 デコーダーによるものです。  
  
 AS2 メッセージは圧縮されてから暗号化されるので、圧縮機能を使用すると、このサイズ制限を回避できます。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>BizTalk EDI アプリケーションを変更できない  
 BizTalk EDI アプリケーション内のアイテムは、変更または削除できません。 このアプリケーションを変更すると、EDI 機能や AS2 機能の構成を解除して再構成しても、元のアプリケーションを復元することはできません。  
  
## <a name="partner-may-reject-multipart-messages"></a>パートナーがマルチパート メッセージを拒否することがある  
 **現象**  
  
 AS2 送信パイプラインを使用してマルチパート メッセージを送信する場合、Content-Type MIME ヘッダーがないため、パートナーがメッセージを拒否することがあります。  
  
 **考えられる原因**  
  
 Content-Type は、マルチパート メッセージの各ボディ部に配置できる省略可能なヘッダーです。 パートナーによっては、このヘッダーが各ボディ部に存在し、特定のコンテンツの種類に設定されていることを要求します。  
  
> [!NOTE]
>  メッセージの本文には AS2 送信パイプラインによって Content-Type プロパティが設定されますが、添付ファイルには Content-Type プロパティが設定されません。  
  
 **解決策**  
  
 パートナーが各ボディ部の Content-Type ヘッダー値を要求する場合、このプロパティを設定するカスタム パイプライン コンポーネントを作成し、送信パイプラインでこのコンポーネントを使用する必要があります。  
  
## <a name="when-receiving-multipart-messages-the-first-part-is-considered-the-body"></a>マルチパート メッセージの受信時に最初の部分が本文と見なされる  
 **現象**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、マルチパート AS2 メッセージの受信時に、添付ファイルの 1 つを間違ってメッセージ本文と識別することがあります。  
  
 **考えられる原因**  
  
 マルチパート/関連メッセージの MIME ヘッダーには、どの部分をメッセージの本文として扱うかを示す、省略可能な "start" パラメーターが含まれていることがあります (その部分の Content-ID を指定)。 Start パラメーターが存在しない場合は、最初の部分がメッセージの本文を考慮してください。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存在し、メッセージの本文として最初の部分を処理は常には、start パラメーターを考慮しません。  
  
 **解決策**  
  
 パートナーがマルチパート/関連メッセージの最初の部分として本文を送信できない場合、メッセージの本文を正しく識別するパイプライン コンポーネントを作成する必要があります。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)   
 [AS2 ソリューションのアーキテクチャ](../core/as2-solution-architecture.md)   
 [開発と BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)