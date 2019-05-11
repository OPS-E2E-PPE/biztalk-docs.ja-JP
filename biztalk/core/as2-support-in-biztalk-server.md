---
title: AS2 BizTalk Server でのサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8ee230e-8f5f-4b51-99e2-0b38acaf5707
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8916f5c33d1d96cf9a1ce579a15e1894e651f89e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358828"
---
# <a name="as2-support-in-biztalk-server"></a>BizTalk Server における AS2 のサポート
このトピックでは、AS2 処理と BizTalk Server がそれを実装する方法の概要を説明します。  
  
## <a name="introduction-to-as2"></a>AS2 の概要  
 EDI のトランスポートには、一般的に付加価値通信網 (VAN) が使用されます。 これらは、正確かつ法的拘束力のある監査記録などの付加価値サービスを提供するプライベート ネットワークです。 しかし、企業は EDI ドキュメントの交換をインターネット上で行うように移行しています。 この方法は、コスト削減、柔軟性や効率性の向上を実現し、冗長性やスケーラビリティの面でも利点があります。  
  
 EDI over the Internet (EDIINT) を実装するための最も一般的な方法として、AS2 (Applicability Statement 2) を使用する方法が挙げられます。 AS2 の仕様では「MIME-Based Secure Peer-to-Peer Business Data Interchange」が定義されています。 MIME データで作成されたエンベロープを含むメッセージは、HTTP over TCP/IP を使用して送信されます。  
  
 AS2 は HTTP POST 操作を使用して EDI や XML などのビジネス データを送信します。 AS2 が実行する処理は EDI データの送信だけではありません。 要求 URI は、メッセージ データのアンパックやハンドリングに使用する AS2 処理を指定します。 Message Disposition Notification (MDN) は、元の送信者の URL に対する HTTP 応答メッセージの本文か、または新しい HTTP POST 操作によって、確認として返されます。  
  
 EDI メッセージングの詳細については、次を参照してください。 [AS2 メッセージング](../core/as2-messaging.md)します。  
  
## <a name="how-as2-is-implemented-in-biztalk-server"></a>BizTalk Server での AS2 の実装方法  
 BizTalk Server には、AS2 のサポートを提供するネイティブ機能が含まれています。 この機能は、アダプターやアクセラレータなどの製品へのアドインではなく、 製品に組み込まれ、次の機能を提供します。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] AS2 で定義されたメソッドを使用して、送信、受信、およびメッセージを確認します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 暗号化、署名、および圧縮によってデータ転送のセキュリティを確保に役立ちます。 これを行うために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は暗号化キー、デジタル署名、および証明書を使用します。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用すると、受信 AS2 メッセージと送信 AS2 メッセージを否認不可ストレージに保存できます。 これには、エンコードまたはデコードされた AS2 メッセージの保存と、MDN の保存も含まれます。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、添付ファイル名を AS2 メッセージの一部として保持することが可能です。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、受信メッセージの重複をチェックできます。  
  
- MDN を返すには、確認されるメッセージと同じ接続を使用して同期的に行うこともできますし、別の接続を使用して非同期的に行うこともできます。  
  
- MDN が指定した時間内に受信されなかった場合に、AS2 メッセージを再送信できます。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、AS2 固有の状態レポートを提供します。 これらのレポートには、インターチェンジに関連付けられた確認を含め、AS2 送信の包括的な状態が含まれます。  
  
- AS2 では、HTTP アダプターが受信側と送信側の両方で使用されていることが必要です。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントごとに証明書を定義して、AS2 メッセージの既定の署名証明書をオーバーライドできます。 パーティの別の証明書を指定する方法については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)します。  
  
## <a name="as2-components-in-biztalk-server"></a>BizTalk Server の AS2 コンポーネント  
 AS2 トランスポートに使用される BizTalk Server コンポーネントを以下に示します。  
  
- AS2 ドキュメントの処理に必要なアイテム (パイプラインとスキーマを含む) を含めた BizTalk EDI アプリケーション。  
  
  > [!NOTE]
  >  BizTalk Server で AS2 機能を構成するときに、構成プログラムは、このアプリケーションを作成します。 AS2 メッセージを処理するアプリケーションを作成する場合は、アプリケーションから BizTalk EDI アプリケーションへの参照を追加する必要があります。 詳細については、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。  
  
- AS2 経由で受信した EDI メッセージについて、AS2 処理、続いて EDI 処理を実行する AS2EdiReceive パイプライン。 詳細については、次を参照してください。 [AS2 の受信コンポーネント](../core/as2-receive-components.md)します。  
  
- AS2 経由で受信した非 EDI メッセージについて、AS2 処理を実行する AS2Receive パイプライン。 詳細については、次を参照してください。 [AS2 の受信コンポーネント](../core/as2-receive-components.md)します。  
  
- AS2 経由で送信している EDI メッセージについて、EDI 処理、続いて AS2 処理を実行する AS2EdiSend パイプライン。 詳細については、次を参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)します。  
  
- AS2 経由で送信している非 EDI メッセージについて、AS2 処理を実行する AS2Send パイプライン。 詳細については、次を参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)します。  
  
- AS2 ドキュメントのトランスポートに関与する取引先の処理プロパティを設定できる取引先管理 (TPM) のユーザー インターフェイス。 詳細については、次を参照してください。 [AS2 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-as2-processing.md)と**EDI および AS2 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
- AS2 インターチェンジおよび関連する確認の包括的な状態を提供する状態レポートのユーザー インターフェイス。 詳細については、次を参照してください。 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)します。  
  
- 移行ツール (パーティ移行ツール) には、BizTalk Server 2006 R2 または BizTalk Server 2009 から BizTalk server の AS2 プロパティを含むパーティ データを移行することができます。 詳細については、次を参照してください。 [EDI アイテムを BizTalk Server の以前のバージョンから移行](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)します。  
  
## <a name="see-also"></a>参照  
 [AS2 ソリューションのアーキテクチャ](../core/as2-solution-architecture.md)   
 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)   
 [BizTalk Server AS2 ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)