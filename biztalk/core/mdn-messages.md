---
title: MDN メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16ac6253-0be5-4636-b102-bf5af8956261
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2ac015986c78f97082321171ca2fcd01a4854e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380012"
---
# <a name="mdn-messages"></a>MDN メッセージ
Message Disposition Notification (MDN) は、AS2 メッセージに対する応答として送信される受信確認です。 MDN を有効にすると、MDN の受信と検証が完了するまで、AS2 による送信は完了しません。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 常に、AS2 メッセージの処理で、エラーが発生した場合でも、メッセージ処理のステータスを示す MDN の返信を試みます。  
  
 MDN により、以下のことを検証できます。  
  
-   **受信側のパーティによって受信された元のメッセージが正常が**します。 元のメッセージの送信者は、送信メッセージの MessageID と、受信者が MDN に格納した original-message-id フィールドを比較することによって、これを検証します。  
  
-   **交換されるデータの整合性が受信者によって検証されたこと**します。 元のメッセージの送信者は、送信メッセージ ペイロードから算出した MIC と、受信者が受信メッセージ ペイロードを基に算出し、MDN の Received-content-MIC フィールドに格納した MIC を比較することによって、これを検証します (署名付き MDN の場合)。  
  
-   **確認メッセージの非否認が**します。 送信者は、受信者の公開キーを使用して署名付きの MDN を検証し、MDN 内の返された MIC の値が、否認不可データベースに格納された元のメッセージ ペイロードの MIC と同じであることを確認することによって、これを検証します。  
  
    > [!NOTE]
    >  同期 MDN は、HTTP 応答 ("200 OK" など) としても機能します。  
  
    > [!NOTE]
    >  Mdn の受信側の処理の詳細については、次を参照してください。[受信 MDN の処理](../core/processing-an-incoming-mdn.md)します。 Mdn の送信側の処理の詳細については、次を参照してください。[送信 MDN の送信](../core/sending-an-outgoing-mdn.md)します。  
  
## <a name="properties-used-to-generate-the-mdn"></a>MDN の生成に使用されるプロパティ  
 AS2Receive 受信パイプラインは、パーティの AS2 アグリーメントのプロパティを使用する場合、MDN を生成、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**で一方向アグリーメントタブでプロパティが選択されています。**アグリーメントのプロパティ** ダイアログ ボックス。 この場合、MDN の生成時にメッセージ ヘッダーの AS2-From プロパティが使用されますが、他のプロパティはパーティの AS2 アグリーメント設定から取得されます。  
  
 AS2 プロパティをオーバーライドするオプションが選択されていない場合や、パーティの AS2 プロパティが使用可能な場合は、受信パイプラインは受信メッセージの AS2 ヘッダー タグを使用して MDN を生成します。  
  
 MDN には署名を付加できますが、MDN を暗号化または圧縮することはできません。  
  
## <a name="mdn-context-properties"></a>MDN のコンテキスト プロパティ  
 MDN メッセージの処理に使用されるコンテキスト プロパティには、昇格できるプロパティや非公開のプロパティが含まれますが、これらのプロパティは中断されたメッセージや追跡メッセージで表示できます。 これらのコンテキスト プロパティの一覧は、次を参照してください。 [AS2 コンテキスト プロパティ](../core/as2-context-properties.md)します。  
  
 MDN を生成するには、DispositionMode および DispositionType の両コンテキスト プロパティを昇格させる必要があります。 AS2 または EDI ペイロードでエラーが発生すると、DispositionType プロパティによってエラーが通知されます。 このプロパティを表示、**メッセージの詳細**で中断されたサービス インスタンスから (サービスの詳細 ダイアログ ボックス) を使用して表示されるダイアログ ボックス、**グループ ハブ**のページ、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 ヘッダーでエラーが発生すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は DispositionType プロパティによってエラーを通知し、MDN の送信を試みますが、エラーによっては MDN を送信できない場合があります。  
  
## <a name="mdn-headers"></a>MDN のヘッダー  
 MDN には次のヘッダーが含まれます。  
  
- **Http/as2 ヘッダー**します。 詳細については、次を参照してください。 [AS2 メッセージ](../core/as2-messages.md)します。  
  
- **転送層**します。 これには、Content-Type ヘッダー ("signed multipart message" を含む)、MIC のアルゴリズム、署名の書式設定プロトコル、および最も外側のマルチパート境界サブヘッダーが含まれます。  
  
- **第 1 部**します。 マルチパートの署名付きメッセージの第 1 部は、添付された MDN です。 これは人間が判読できます。  
  
- **2 番目の部分**します。 マルチパートの署名付きメッセージの第 2 部は、デジタル署名、元のメッセージへの参照、配置の種類と状態、および MIC の値で構成されます。 これはコンピューターによる処理が可能な形式です。  
  
  AS2-From ヘッダー、AS2-To ヘッダー、および MessageID コンテキスト プロパティは、MDN を応答対象の AS2 メッセージに関連付けるために使用されます。 MDN の Original-Message-ID ヘッダーは、MDN の応答対象である AS2 メッセージの Message-ID ヘッダーから取得されます。  
  
## <a name="mic"></a>MIC  
 メッセージ整合性チェック (MIC) は、MDN が元の送信メッセージ ペイロードに関連付けられていることを検証するために使用されます。 MIC ダイジェストは、マルチパートの署名付き MDN メッセージの第 2 部にある Received-Content-MIC 拡張フィールドに格納されます。  
  
 MDN を有効にすると、AS2 送信パイプラインは、送信メッセージの処理時にメッセージ ペイロードから MICHashValue を計算します。 送信パイプラインは、このハッシュ値を BizTalkMsgBoxDb データベースの EdiInt_Mic テーブルに保存します。 AS2 メッセージの追跡はこのテーブルで行われ、AS2From、AS2To、および MessageID の各値と、テーブル内の MICHashValue 列によって一意に識別されます。 メッセージの受信者は、メッセージ ペイロードの処理時に MIC ハッシュ値を計算し、返信する MDN にそのハッシュ値を格納します。 元のメッセージの送信者は、受信した MDN 内の MIC ハッシュ値と、保存されているハッシュ値を比較します。 両者が一致すると、元のメッセージの送信者は MDN を廃棄し、EdiInt_Mic テーブル内のエントリを削除します。これで送信が完了します。  
  
 MIC は base64 でエンコードされます。 MIC に適用されるアルゴリズムは、SHA1 または MD5 です。 決定されます、**署名アルゴリズム**ドロップダウン (場合に有効**署名付き MDN を要求**プロパティがチェックされます) で、**送信者の MDN 設定**一方向のアグリーメントのページタブで、**アグリーメントのプロパティ** ダイアログ ボックス。 また、元のメッセージの Signed-Receipt-MICalg AS2 ヘッダーからも決定されます。  
  
## <a name="see-also"></a>参照  
 [AS2 メッセージ](../core/as2-messages.md)   
 [受信 MDN の処理](../core/processing-an-incoming-mdn.md)   
 [送信 MDN の送信](../core/sending-an-outgoing-mdn.md)