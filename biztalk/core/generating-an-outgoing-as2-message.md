---
title: 送信 AS2 メッセージの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 288c8101-9a96-4f98-ae18-df43c7cdb3a0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd96debd3099eee795ebb661a9f5828d7de6f10f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387773"
---
# <a name="generating-an-outgoing-as2-message"></a>送信 AS2 メッセージの生成
AS2EDISend および AS2Send 送信パイプラインは次のように、送信メッセージを生成します。 各パイプラインの一方向アグリーメント タブでプロパティを使用して、**アグリーメントのプロパティ** ダイアログ ボックスで、送信 AS2 メッセージを生成します。  
  
## <a name="agreement-destination-and-messageid-determination"></a>アグリーメント、送信先、および MessageID の決定  
 AS2 送信パイプラインは、次のように AS2 メッセージの送信に使用されるアグリーメントおよび送信先を決定します。  
  
-   送信メッセージの処理に使用するアグリーメントを特定するには、AS2 エンコーダー照合しようと、AS2 のメッセージとパーティのビジネス プロファイル、または送信ポートの AS2Identity のプロパティをサブスクライブする送信ポートでメッセージに関連付けられています。アグリーメント。 このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-outgoing-as2-messages.md)します。  
  
-   メッセージの送信先を確認するのには、動的送信ポートで送信パイプラインは、OutboundTransportLocation プロパティは、書き込まれるか、動的送信ポートを機能させるためのバックエンド アプリケーションで、コンテキストに昇格させる必要がありますを使用します。 静的送信パイプラインで送信パイプラインは、AS2 から変換先を決定の AS2 アグリーメントのプロパティとビジネス プロファイルのプロパティの id プロパティ。  
  
-   AS2 エンコーダーは、送信 AS2 メッセージの MessageId ヘッダーを設定する必要があります。 送信パイプラインが MessageId をからいずれかを決定します、`EdiIntAS.MessageId`コンテキスト プロパティまたは`HTTP.UserHttpHeaders`コンテキスト プロパティ。 エンコーダーから値を使用してどちらのコンテキスト プロパティが設定されている場合、`HTTP.UserHttpHeaders`コンテキスト プロパティ。 設定されている場合、送信パイプラインによって値 MessageID のです。  
  
## <a name="outgoing-message-processing"></a>送信メッセージの処理  
 送信 AS2 メッセージの処理で、AS2 送信パイプラインを使用する手順は次のとおりです。  
  
-   ネイティブ形式は、メッセージのコピーを作成し、AS2 メッセージの否認がアグリーメント プロパティで有効になっている場合は、コピーを否認不可データベースに格納します。  
  
-   AS2 エンコーダーに HTTP (および AS2) ヘッダーをビルド、`HTTP.UserHttpHeaders`コンテキスト プロパティ。 このプロセスの詳細については、次を参照してください。 [AS2 経由で送信 EDI メッセージの送信側の処理](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)します。  
  
-   書き込みます`HTTP.UserHttpHeaders`コンテキストにします。  
  
-   有効になっている場合は、送信のメッセージを圧縮します。  
  
-   メッセージの暗号化を含む MIME 処理を実行します (有効な場合に、**メッセージを暗号化する必要があります**アグリーメント プロパティ) とデジタル署名の適用 (で有効になっている場合、**メッセージは署名付きをする必要があります**アグリーメントのプロパティ)。 AS2Send パイプラインは、アグリーメントの設定に基づき、署名を適用するのに、SHA1 または MD5 を使用します。  
  
-   Content-disposition MIME を作成します。 場合、指定した値を含むヘッダー ファイルを送信するアグリーメントのプロパティの名前が有効になっています。  
  
-   暗号化されたメッセージのコピー (ワイヤ形式) を作成し、有効な場合に、コピーを否認不可データベースに格納、**エンコードされた送信の AS2 メッセージに対して有効な NRR**アグリーメント プロパティ。  
  
-   MDN が必要な場合は、MIC 値を計算し、データ ストアに格納されます。  
  
-   UserHTTPHeaders コンテキスト プロパティから、送信 AS2 メッセージにヘッダーの書き込みを行う HTTP アダプターにメッセージが配信されます。  
  
-   信頼性の高いメッセージングが必要な場合は、MDN が受信されるまで、メッセージを再送信します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 送信コンポーネント](../core/as2-send-components.md)