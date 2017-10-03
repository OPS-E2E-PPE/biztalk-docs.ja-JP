---
title: "POP3 アダプターについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- POP3 adapters, availability
- authenticating, POP3 adapters
- POP3 adapters, data duplication
- data duplication
- POP3 adapters, receive adapters
- high availability, POP3 adapters
- POP3 adapters, supported platforms
- POP3 adapters, authenticating
- POP3 adapters, algorithims
- receive adapters, POP3 adapters
ms.assetid: 05e9598b-cdfe-4216-b6bf-1b84f8ddfeae
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 592e0475b607de3f9df528a4bab777aa0fb7635d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-pop3-adapter"></a>POP3 アダプターについて
このセクションでは POP3 受信アダプターについて説明します。  
  
## <a name="pop3-receive-adapter"></a>POP3 受信アダプター  
 POP3 受信アダプターを使用すると、POP3 に対応したメールボックスから BizTalk Server にデータを移動できます。  
  
 POP3 受信アダプターの主な機能は次のとおりです。  
  
-   要求時に POP3 サーバーのメールボックスからファイルを取得します。  
  
-   構成可能なスケジュールに基づいてポーリングを実行します。  
  
-   POP3 サーバーのメールボックスにポーリングし、BizTalk Server にデータを直接送信します。  
  
-   POP3 サーバーのメールボックスを、IP アドレスまたはホスト名、ポート、ユーザー名、およびパスワードで指定します。  
  
-   Secure Sockets Layer (SSL) 接続が必要なメール サーバーから電子メールをダウンロードする機能を提供します。  
  
-   ファイル配信を保証します。  
  
-   暗黙的な MIME 処理を行います。 POP3 アダプターの使用時は、受信パイプラインで MIME デコーダーを使用する必要はありません。  
  
## <a name="pop3-adapter-supported-platforms"></a>POP3 アダプターがサポートされているプラットフォーム  
 POP3 アダプターは、次の RFC に準拠する、すべての POP3 サーバーで動作するように設計されています。  
  
-   **RFC 1939 です。** Post Office Protocol Version 3 (を参照してください[http://go.microsoft.com/fwlink/?LinkId=58808](http://go.microsoft.com/fwlink/?LinkId=58808))  
  
-   **RFC 1734 です。** POP3 AUTHentication command (を参照してください[http://go.microsoft.com/fwlink/?LinkId=58809](http://go.microsoft.com/fwlink/?LinkId=58809))  
  
-   **RFC 2045 です。** Multipurpose Internet Mail Extensions (MIME) Part One: 形式 of Internet Message Bodies (を参照してください[http://go.microsoft.com/fwlink/?LinkId=58810](http://go.microsoft.com/fwlink/?LinkId=58810))  
  
-   **RFC 2046 です。** Multipurpose Internet Mail Extensions (MIME) Part Two: メディアの種類 (を参照してください[http://go.microsoft.com/fwlink/?LinkId=58811](http://go.microsoft.com/fwlink/?LinkId=58811))  
  
-   **RFC 2047 です。** 非 ASCII テキストの MIME (Multipurpose Internet Mail Extensions) Part Three: Message Header Extensions (を参照してください[http://go.microsoft.com/fwlink/?LinkId=58812](http://go.microsoft.com/fwlink/?LinkId=58812))  
  
 POP3 アダプターは、Microsoft Exchange Server 2003 に対して十分にテストされています。  
  
## <a name="considerations-for-preventing-data-duplication-when-using-the-pop3-adapter"></a>POP3 アダプターの使用時にデータの重複を防ぐための考慮事項  
 POP3 アダプターはトランザクション アダプターではないため、同じメッセージの複数のコピーを処理することがあります。これにより、データの重複が発生する場合があります。 次のシナリオでは、POP3 アダプターによってメッセージの重複したコピーが配信される可能性があります。  
  
-   POP3 アダプターは、処理のために電子メールが BizTalk Server に正常に送信された後、POP3 アダプターが監視するように構成されているメールボックスから毎回電子メールを削除します。 POP3 アダプターがメールボックスから電子メールを取得し、処理のために BizTalk Server に送信した後、その電子メールをメールボックスから削除できなかった場合、次に POP3 アダプターからメールボックスへのポーリングが行われるときに、その電子メールは BizTalk Server に再送信されます。  
  
-   異なる BizTalk ホスト インスタンスにある POP3 アダプターの複数のインスタンスで同じメールボックスが同時に監視されていて、POP3 サーバーでメールボックスに対する複数の同時接続が許可されている場合、アダプターがメッセージの重複したコピーを配信することがあります。  
  
## <a name="high-availability-for-the-pop3-adapter"></a>POP3 アダプターの高可用性  
 一部の POP3 サーバーでは、特定のメールボックスに対する複数の同時接続を許可しています。 POP3 アダプターの複数のインスタンスが、そのような POP3 サーバー上のメールボックスからメールを取得するように構成されている場合、データの重複が発生することがあります。 このため、複数の同時接続を許可しているメールボックスからメールを取得するように構成する POP3 アダプターのインスタンスは、1 つのみにする必要があります。  
  
 このシナリオの POP3 アダプターにフォールト トレランスを提供するには、単一の POP3 アダプターの受信ハンドラーを、クラスター化された BizTalk ホストで実行されるように構成する必要があります。 詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。  
  
## <a name="authentication-warnings-when-multiple-instances-of-the-pop3-adapter-connect-to-the-same-mailbox"></a>POP3 アダプターの複数のインスタンスから同じメールボックスへの接続が行われたときに発生する認証警告  
 BizTalk Server が、POP3 アダプターの複数のインスタンスで同じメールボックスからメールを取得するように構成されている場合があります。 そのような場合、一部の POP3 サーバーで使用されているロック メカニズムが原因で、BizTalk Server アプリケーション ログに認証警告が記録される場合があります。 これらの警告による POP3 アダプターの機能への影響はありません。そのため、このシナリオではこれらの警告を無視してもかまいません。  
  
## <a name="encrypted-messages-received-by-the-pop3-adapter-that-are-sent-to-the-suspended-queue-may-be-viewable-in-clear-text"></a>POP3 アダプターで受信して保留キューに送信する暗号化されたメッセージはクリア テキストで表示可能  
 デジタル暗号化された電子メールが POP3 アダプターで復号化されるように構成できます。 これは、設定で、 **MIME デコードの適用**プロパティを**True**の受信場所を使用して、POP3 アダプター。 POP3 アダプターがデジタル暗号化された電子メールを受信した場合、 **MIME デコードの適用**受信場所のプロパティに設定されて**True** POP3 アダプターが、次のように、電子メールの暗号化を解除しようとしています。 その。  
  
-   POP3 アダプターは、電子メールの暗号化に使用されたパブリック証明書に一致するプライベート証明書を検索します。 プライベート証明書は、POP3 受信ハンドラーがバインドされているホスト インスタンスが動作しているサーバーの個人証明書ストアにあります。  
  
-   対応するプライベート証明書が見つかると、POP3 アダプターはその証明書を使用して電子メール メッセージを復号化します。  
  
-   電子メールが復号化され、BizTalk メッセージ ボックスに保存されます。  
  
 復号化されたメッセージが BizTalk メッセージボックスに保存された後で保留されている場合、そのメッセージの内容は、BizTalk 保留キューからクリア テキストで表示できます。  
  
 保留キュー内のセキュリティで保護されたメッセージ テキストを表示不可にする必要がある場合は、次の手順を実行します。  
  
-   設定、 **MIME デコードの適用**プロパティを**False**の受信場所を使用して、POP3 アダプター、SMIME パイプライン コンポーネントは、パイプラインでメッセージを復号化します。  
  
    > [!NOTE]
    >  この方法により、電子メール固有のプロパティをメッセージ コンテキストに昇格させることができなくなります。  
  
-   電子メール固有のプロパティをメッセージ コンテキストに昇格させる必要がある場合は、暗号化されたメッセージが保留キューにルーティングされた後も暗号化された状態を維持できるように、次の手順を実行します。  
  
    -   チェック ボックスをオン**失敗したメッセージの有効化のルーティングを**POP3 アダプタを使用する受信場所を格納する受信ポートにします。  
  
    -   POP3 アダプターを使用する受信場所を格納する受信ポートへの配信が失敗したメッセージをサブスクライブするために、オーケストレーションを作成します。  
  
    -   SMIME パイプライン コンポーネントを使用してパイプライン内のメッセージを暗号化する送信ポートで、オーケストレーションを構成します。  
  
    -   オーケストレーション インスタンスおよびメッセージを保留する中断図形でオーケストレーションを構成します。  
  
    -   オーケストレーションを構築して展開し、展開したオーケストレーションを適切な受信ポートにバインドします。  
  
## <a name="maximum-message-size-supported-by-the-pop3-adapter"></a>POP3 アダプターによってサポートされているメッセージの最大サイズ  
 POP3 アダプターでは、最大 50 MB のメッセージを受信できることをテスト済みで、このサイズがサポートされています。  
  
## <a name="see-also"></a>参照  
 [POP3 アダプター](../core/pop3-adapter.md)