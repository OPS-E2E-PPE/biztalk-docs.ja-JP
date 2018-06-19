---
title: カスタム アダプターの開発 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44765fbb-b24d-43b6-a40c-d28e319b90a5
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c13aba7e378d67523ec755837ac65b26989730a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239914"
---
# <a name="developing-custom-adapters"></a>カスタム アダプターの開発
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、外部のシステム、アプリケーション、およびエンティティとメッセージを交換するために、アダプターの概念を使用します。 アダプターは、COM または[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]ビジネス エンドユーザーからのメッセージを転送するコンポーネントです。 さまざまな通信プロトコルを使用して、(ファイル システム、データベース、カスタム ビジネス アプリケーションなど) のポイント。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]さまざまなプロトコルをサポートするネイティブ アダプターを提供します。 たとえば、次のオブジェクトにアクセスできます。  
  
-   ファイルの場所からのメッセージの送受信をサポートするファイル アダプター  
  
-   EDI、FTP、HTTP、MSMQ、SMTP、POP3、および SOAP プロトコルのアダプター  
  
-   [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] のアダプター  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はメッセージを特定のカスタム アプリケーションに送信したり、ネイティブ アダプターが存在しないプロトコルを使用する必要がある場合があります。 サードパーティの企業は、追加のプロトコルをサポートするアダプターを作成しています。 カスタム アダプターの作成を決定する前に、プロトコルに対するアダプターが存在するかどうかを確認することをお勧めします。 アダプターと関連するベンダーの一覧については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=47140](http://go.microsoft.com/fwlink/?LinkId=47140)です。 通信要件をサポートするためのアダプターが見つからない場合は、独自のカスタム アダプターを開発できます。  
  
 カスタム アダプターの作成は、難しい作業になる場合があります。 このプロセスを簡略化するために、マイクロソフトはアダプター フレームワークと呼ばれる基礎を開発しました。 このフレームワークを、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK のサンプルのアダプター ソース コードと共に開発の基礎として使用できます。  
  
 このセクションのトピックでは、カスタム アダプターの開発のヒントや推奨事項を示します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプター フレームワークとは何ですか。](../core/what-is-the-adapter-framework.md)  
  
-   [BizTalk Server にアダプターがインスタンス化する方法](../core/how-biztalk-server-instantiates-an-adapter.md)  
  
-   [メッセージ バッチ](../core/message-batches.md)  
  
-   [トランザクション メッセージ バッチ](../core/transactional-message-batches.md)  
  
-   [開発、受信アダプター](../core/developing-a-receive-adapter.md)  
  
-   [送信アダプターの開発](../core/developing-a-send-adapter.md)  
  
-   [分離アダプターをインスタンス化します。](../core/instantiating-isolated-adapters.md)  
  
-   [アダプターのデザインに関する問題](../core/adapter-design-issues.md)  
  
-   [アダプターがサイズの大きいメッセージを処理する方法](../core/how-adapters-handle-large-messages.md)  
  
-   [アダプターの障害を処理する方法](../core/how-to-handle-adapter-failures.md)  
  
-   [アダプターを終了する方法](../core/how-to-terminate-an-adapter.md)  
  
-   [パフォーマンスの高いアダプターを設計する方法](../core/how-to-design-a-performant-adapter.md)  
  
-   [カスタム アダプターを展開する方法](../core/how-to-deploy-a-custom-adapter.md)  
  
-   [テストおよびアダプターをデバッグする方法](../core/how-to-test-and-debug-an-adapter.md)  
  
-   [アダプター メタデータを BizTalk プロジェクトに追加する方法](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md)  
  
-   [アダプターのローカリゼーションの問題](../core/adapter-localization-issues.md)  
  
-   [アダプターのデザインに関するヒント](../core/tips-for-designing-your-adapter.md)  
  
-   [アダプター デザイン時の構成](../core/adapter-design-time-configuration.md)  
  
## <a name="see-also"></a>参照  
 [カスタム コンポーネントの開発](../core/developing-custom-components.md)