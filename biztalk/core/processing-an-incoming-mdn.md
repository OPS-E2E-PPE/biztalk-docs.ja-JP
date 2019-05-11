---
title: 受信 MDN の処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd78e84c-4989-47e4-b95b-80582084ddec
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63d575f78d41fdf4cb6e3902354bf218579faad7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299878"
---
# <a name="processing-an-incoming-mdn"></a>受信 MDN の処理
AS2 は、アグリーメントのプロパティとして、AS2 メッセージ受信者のパーティのに基づいて受信 MDN をパイプライン (AS2EDIReceive と AS2Receive) プロセスを受信します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信 AS2 メッセージに対して MDN が自動的に関連付けられます。  
  
 各パイプラインの実行手順は次のとおりです。  
  
-   AS2 を照合することによって、送信元パーティを決定します-メッセージの AS2 ヘッダーの値が AS2 の値からのリストから、**識別子**の一方向の AS2 アグリーメント タブのページ、 **アグリーメントのプロパティ**  ダイアログ ボックス。 一致が見つからない場合、パイプラインは処理を中止し、例外を発生させます。  
  
-   コンテキストには、次の AS2 プロパティを昇格するには。  
  
    -   IsAS2FailedMessage  
  
    -   DispositionType  
  
    -   GenerateAsynchronous200OKOnly  
  
    -   IsAS2MdnResponseMessage  
  
    -   IsAS2MessageSigned  
  
    -   OriginalMessageId  
  
    -   ReceivedContentMic  
  
    -   DispositionMode  
  
    -   メッセージ Id  
  
-   メッセージのすべての HTTP ヘッダーに InboundHttpHeaders プロパティを設定して、メッセージのコンテキストに昇格させます。  
  
-   MDN のコピー (ワイヤ形式) を作成し、一方向の AS2 アグリーメント プロパティで有効になっている場合は、否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) にコピーを格納します。  
  
-   MDN が署名されている場合、署名の検証を含む MIME 処理を実行します。  
  
-   (該当する) 場合、元のメッセージを送信された場合、AS2Send パイプラインによって計算されたデータ ストア内の MIC MDN の MIC (メッセージ整合性チェック) を比較します。 詳細については、次を参照してください。 [MDN メッセージ](../core/mdn-messages.md)します。  
  
-   否認不可データベースに関連付けのエントリを作成します。  
  
-   場合を除き、MDN を削除、 **MessageBox にルーティング/配信の受信 MDN を処理する**プロパティで設定されて、**送信者の MDN 設定**の一方向の AS2 アグリーメント タブのページ、 **アグリーメントのプロパティ** ダイアログ ボックス。  
  
-   場合、 **MessageBox にルーティング/配信の受信 MDN を処理する**プロパティで設定されて、**送信者の MDN 設定**の一方向の AS2 アグリーメント タブのページ、**アグリーメントのプロパティ**  ダイアログ ボックスで、受信パイプラインが MDN をパススルー メッセージとして AS2 デコーダを経由してワイヤ形式でルーティングし、を MessageBox にドロップします。 MDN ワイヤ形式にはには、すべての HTTP ヘッダーが含まれています。  
  
    > [!NOTE]
    >  MessageBox にドロップされた受信 MDN をサブスクライブする送信ポートを設定することができます。 受信 MDN をサブスクライブ送信ポート フィルターを設定します。`IsAS2MdnResponseMessage==True`します。  
  
    > [!NOTE]
    >  場合は、AS2EdiReceive パイプラインを使用して受信 MDN を処理することはできません MDN をルーティングするメッセージ ボックスに設定して、 **MessageBox にルーティング/配信の受信 MDN を処理する**プロパティ、**送信者の MDN設定**の一方向の AS2 アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。 操作を実行しようと、MDN は、MDN を処理できない EDI デコーダーに渡されるために、EDI エラーが発生するがします。 メッセージ ボックスに MDN が送信されない場合、AS2Decoder は EDI デコーダーに渡されませんので、MDN を消費します。  
  
## <a name="message-integrity-check"></a>メッセージの整合性チェック  
 メッセージ整合性チェック (MIC) は、MDN が元の送信メッセージに関連付けられている検証に使用されます。 AS2Send 送信パイプラインは、元の AS2 メッセージを生成し、MIC をデータ ストアに格納する場合にメッセージ ペイロードから MIC を計算します。 MDN が必要な場合は、元のメッセージの受信者は MIC を生成し、MDN に追加します。 AS2MdnReceive 受信と受信パイプラインが MDN を署名付き MDN が要求された場合、データ ストア内の MIC と、MDN 内の MIC と比較します。  
  
 MDN 内の MIC とデータ ストア内の MIC の不一致は、送信または受信側パーティによるメッセージの受信中にエラーがあったことを示します。 このようなエラーで報告された値以下のとおりです。  
  
-   AS2DispositionType:失敗  
  
-   AS2DispositionModifierExtensionType:[エラー]  
  
-   AS2DispositionModifierExtensionDescription:整合性チェックに失敗しました  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)   
 [MDN メッセージ](../core/mdn-messages.md)