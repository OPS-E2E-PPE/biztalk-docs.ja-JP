---
title: "TIBCO Rendezvous アダプターでメッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12699550-22e7-4a11-a024-2302570970af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b9c3aa4aeb613ea65f7e0d7385871c639afb6d8
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="messages-in-biztalk-adapter-for-tibco-rendezvous"></a>BizTalk Adapter for TIBCO Rendezvous のメッセージ
BizTalk Adapter for TIBCO Rendezvous は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と TIBCO Rendezvous 間に双方向の接続を提供します。 このアダプターは、TIBCO Rendezvous API と BizTalk Adapter Framework API の両方を使用して、緊密な統合を提供します。  
  
## <a name="about-tibco-rendezvous"></a>TIBCO Rendezvous について  
 TIBCO Rendezvous は、エンタープライズ アプリケーション統合 (EAI) のメッセージ バスを提供するプログラムです。 TIBCO では、C、C++、Java、Visual Basic および Microsoft Office Excel ワークシートにデータ フィードとその他の任意のアプリケーションを受信する Microsoft .NET Framework のメッセージング Api を提供します。 詳細については、次を参照してください。 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)です。  
  
## <a name="message-passing"></a>メッセージ パッシング  
 メッセージを渡す概念はとても簡単です。  
  
-   メッセージには、ピリオドで区切られた要素で構成される 1 つのサブジェクトがあります。 メッセージは 1 つの Rendezous デーモンに送信されますが、最終的に他の複数のデーモンに配信される場合があります。  
  
-   リスナーは、待機しているサブジェクトを (基本的なワイルドカード機能を使用して) デーモンに通知します。 2 つのデーモンが相互に接続されている場合、または 2 つのデーモンが実際には同一のデーモンである場合は、一致するサブジェクトを持つメッセージがリスナーに配信されます。  
  
 必要に応じて、この上に重要な "エンタープライズ" 機能を配置できます。そのためには、指定可能なフォールト トレランス、信頼性、または認定済みのオプションを使用します。すべてのオプションは基礎になる基本メッセージをとおして実装されます。  
  
 メッセージ自体は、型指定された名前と値のフィールドまたは数字と値のフィールドとして表示できます (1 つのメッセージで 2 つの識別メカニズムを混在させ、特定の制約と照合できます)。 メッセージはサブメッセージを含むことができ、そのサブメッセージがサブメッセージを含むことができます。  
  
 サブジェクト名は、ドット記号 (ピリオド) で区切った 1 つ以上の要素で構成されます。 それらの要素は、アプリケーション システム内の情報の構造を反映したサブジェクト名階層を実装します。 次の文字列は有効なサブジェクト名の例です。  
  
-   RUN.HOME  
  
-   RUN.for.Elected_Office  
  
 BizTalk Adapter for TIBCO Rendezvous は、TIBCO Rendezvous SDK を使用して、TIBCO Rendezvous サブジェクトにメッセージを発行し、TIBCO Rendezvous イベントに登録します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 関連クラスは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターでホストされます。 別のプロセス (ランタイム エージェント) が開始されて Rendezvous プログラムとして機能し、.NET Framework リモート処理を使用して両者間のメッセージ交換が行われます。  
  
-   情報レベル、警告レベル、およびエラー レベルのメッセージが Windows イベント ログに送信されます。  
  
-   デバッグ レベルを含むすべてのレベルのメッセージが Windows トレース ログに送信されます。  
  
## <a name="transmitter"></a>送信元  
 BizTalk Adapter for TIBCO Rendezvous は、送信ポートごとに 1 つのランタイム エージェントを起動します。 TIBCO Rendezvous .NET Framework API を使用すると、グローバル スコープで文字エンコードを設定できます。 そのため、ポート構成オプションの 1 つはコード ページ番号です。 コード ページごとに異なるプロセスを開始することによって、アダプターはグローバル化に対して、より優れたサポートを提供できます。  
  
## <a name="receiver"></a>受信元  
 BizTalk Adapter for TIBCO Rendezvous は、受信場所ごとに 1 つのランタイム エージェントを起動します。  
  
## <a name="transactions"></a>トランザクション  
 TIBCO Rendezvous 製品はトランザクション対応ではありません。 TIBCO Rendezvous TX という別の製品が必要です。 BizTalk Adapter for TIBCO Rendezvous のこのリリースでは、トランザクションはサポートされていません。  
  
## <a name="security"></a>セキュリティ  
 TIBCO Rendezvous は、TIBCO Rendezvous プログラムとデーモンの間の認証のみをサポートします。 承認または暗号化は実行しません。 TIBCO Rendezvous DataSecurity という別の製品が必要です。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)