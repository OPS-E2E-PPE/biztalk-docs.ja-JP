---
title: BizTalk Server から TIBCO Rendezvous 送信ポートの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 950c4c367fe053195ba14029405f5015381fc6be
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="using-tibco-rendezvous-send-ports"></a>TIBCO Rendezvous の送信ポートの使用
送信ポートはあらゆる種類のメッセージを送信できます。 BizTalk Server で Microsoft BizTalk Adapter for TIBCO Rendezvous を介してメッセージを送信する場合、アダプターはメッセージ コンテキストのプロパティ値に基づいてメッセージを生成するか、既定値を使用して、メッセージを指定されたサブジェクトに送信します。  
  
> [!NOTE]
>  TIBCO Rendezvous のドキュメントに従って、送信サブジェクト名ではワイルドカード文字はサポートされていません。  
  
## <a name="message-handling"></a>メッセージの処理  
 アダプターは状態を維持し、それに従って BizTalk Server の受信メッセージを処理します。  
  
-   トランスポートのエラーでメッセージを送信できない場合、BizTalk Server に対して後で再送信するように指示されます。  
  
-   アダプターがまだ初期化中であるためにメッセージを送信できない場合、BizTalk Server メッセージはキューに配置されます。 初期化に失敗した場合、BizTalk Server は後で再送信するように指示されます。  
  
## <a name="message-generation"></a>メッセージの生成  
 送信アダプターを使用する場合、BizTalk Adapter for TIBCO Rendezvous はメッセージのターゲットの名前空間およびルート要素を無視します。 アダプターがメッセージを送信する場合、アダプターはペイロードをそのまま送信します。 アダプターが構造化 TIBCO Rendezvous メッセージを生成する場合、ルート要素の名前は無視されます (メッセージに名前はありません)。 いずれの場合も、アダプターはコンテキスト プロパティを使用して、メッセージを公開するときに使用するサブジェクトを検索します。  
  
 詳細については、次を参照してください。 [BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)](../core/biztalk-server-message-context-properties-send-handlers.md)と[TIBCO Rendezvous の受信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)です。  

## <a name="using-biztalk-to-send-messages"></a>BizTalk を使用してメッセージを送信するには
Microsoft BizTalk Adapter for TIBCO Rendezvous は、非同期 API (Transport.Send) を使用します。 メッセージ コンテキスト プロパティを使用して、このアダプターが送信するメッセージの種類を指定できます。  
  
-   **構造化された**: アダプターには、BizTalk Server から受信した XML データに基づいて、TIBRVMSG_MSG 構造化されたメッセージが生成されます。 (*)  
  
 BizTalk Server が 127 文字を超える名前を持つフィールドのあるメッセージを送信した場合、BizTalk Adapter for TIBCO Rendezvous は、TIBCO Rendezvous の最大フィールド名サイズ (127 文字) に名前を切り捨てます。  
  
 `reply subject name` プロパティが指定されている場合、このプロパティを使用して TIBCO Rendezvous メッセージの返信の件名が設定されます。 受信ポートが応答を待機して BizTalk Server に転送するように設定されているか、その他の TIBCO Rendezvous プログラムが応答を処理すると想定されています。  
  
 トリプレット (サービス、デーモン、およびネットワーク) がトランスポートの構成を形成します。 トランスポートの構成が空白の場合 (既定)、メッセージは既定のトランスポート オブジェクトを介して送信されます。  
  
 コード ページを指定しない場合、このアダプターは UTF-8 エンコーディング (コード ページ 65001) を使用します。 伝送側では、認定済みメッセージはサポートされません。  
  
## <a name="see-also"></a>参照  
 [送信ポートの作成](../core/creating-send-ports2.md)   
 [TIBCO Rendezvous 送信ハンドラーの作成](../core/creating-tibco-rendezvous-send-handlers.md)