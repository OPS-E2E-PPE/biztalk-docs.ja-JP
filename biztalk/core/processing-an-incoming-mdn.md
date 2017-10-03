---
title: "受信 MDN の処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd78e84c-4989-47e4-b95b-80582084ddec
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e599e9ebbc7a05a466cc047d891699222c2dabac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="processing-an-incoming-mdn"></a>受信 MDN の処理
AS2 受信パイプライン (AS2EDIReceive と AS2Receive) は、AS2 メッセージ受信者であるパーティのアグリーメント プロパティに基づいて受信 MDN を処理します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] により、送信 AS2 メッセージに対して MDN が自動的に関連付けられます。  
  
 各パイプラインが実行する手順は次のとおりです。  
  
-   AS2 を照合することによって、送信元パーティを決定-メッセージの AS2 ヘッダーの値が AS2 の値からのリストから、**識別子**の一方向の AS2 アグリーメント タブのページ、 **アグリーメントのプロパティ**  ダイアログ ボックス。 一致するものが見つからない場合、パイプラインは処理を中止し、例外を発生させます。  
  
-   次の AS2 プロパティをコンテキストに昇格します。  
  
    -   IsAS2FailedMessage  
  
    -   DispositionType  
  
    -   GenerateAsynchronous200OKOnly  
  
    -   IsAS2MdnResponseMessage  
  
    -   IsAS2MessageSigned  
  
    -   OriginalMessageId  
  
    -   ReceivedContentMic  
  
    -   DispositionMode  
  
    -   MessageId  
  
-   メッセージのすべての HTTP ヘッダーに InboundHttpHeaders プロパティを設定し、メッセージのコンテキストに昇格させます。  
  
-   MDN のコピー (ワイヤ形式) を作成し、否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) に保存します (一方向の AS2 アグリーメントのプロパティで有効になっている場合)。  
  
-   署名の確認を含む MIME 処理を実行します (署名付き MDN の場合)。  
  
-   MDN のメッセージ整合性チェック (MIC) を、元のメッセージが送信されるときに AS2Send パイプラインによって算出されたデータ ストアの MIC と比較します (該当する場合)。 詳細については、次を参照してください。 [MDN メッセージ](../core/mdn-messages.md)です。  
  
-   否認不可データベースに関連付けのエントリを作成します。  
  
-   場合を除き、MDN を削除、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**にプロパティを設定、**送信者の MDN 設定**の一方向の AS2 アグリーメント タブのページ、 **アグリーメントのプロパティ** ダイアログ ボックス。  
  
-   場合、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**にプロパティを設定、**送信者の MDN 設定**の一方向の AS2 アグリーメント タブのページ、**アグリーメントのプロパティ**ダイアログ ボックスで、受信パイプラインをパススルー メッセージとして AS2 デコーダーを経由してワイヤ形式で MDN をルーティングし、MessageBox にドロップします。 ワイヤ形式の MDN には、すべての HTTP ヘッダーが含まれます。  
  
    > [!NOTE]
    >  送信ポートを設定して、メッセージ ボックスにドロップされた受信 MDN へのサブスクライブを行うようにできます。 受信された MDN をサブスクライブするには、送信ポート フィルターを `IsAS2MdnResponseMessage==True` に設定します。  
  
    > [!NOTE]
    >  受信 MDN の処理に AS2EdiReceive パイプラインを使用する場合することはできませんに MDN をルーティング、メッセージ ボックス データベースを設定して、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**プロパティに、**送信者の MDN設定**の一方向の AS2 アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。 操作を行うとすると、MDN を処理できない EDI デコーダーに対して MDN が渡されるために、EDI エラーが発生するされます。 MDN がメッセージ ボックスに送信されないと、AS2 デコーダーは MDN を利用 (消費) するため、MDN は EDI デコーダーに渡されません。  
  
## <a name="message-integrity-check"></a>メッセージ整合性チェック  
 メッセージ整合性チェック (MIC) は、MDN が元の送信メッセージに関連付けられていることを検証するために使用されます。 AS2Send 送信パイプラインは、元の AS2 メッセージを生成するときにメッセージ ペイロードから MIC を計算し、算出した MIC をデータ ストアに格納します。 MDN が要求されている場合、元のメッセージの受信者は MIC を生成して MDN に追加します。 AS2MdnReceive 受信パイプラインが MDN を受信したとき、署名付き MDN が要求されている場合は、MDN 内の MIC がデータ ストア内の MIC に対して比較されます。  
  
 MDN 内の MIC とデータ ストア内の MIC が一致しない場合、転送中または受信パーティがメッセージを受信するときにエラーが発生したことを示します。 このようなエラーの場合、次の値が報告されます。  
  
-   AS2DispositionType: 失敗  
  
-   AS2DispositionModifierExtensionType: エラー  
  
-   AS2DispositionModifierExtensionDescription: 整合性チェックに失敗しました  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)   
 [MDN メッセージ](../core/mdn-messages.md)