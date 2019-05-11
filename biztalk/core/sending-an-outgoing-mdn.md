---
title: 送信 MDN の送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dce7620-d354-4b76-bcbc-f97dc93c3fc3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dbe1365681fe40ef81b1634307d1535c325ad5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399052"
---
# <a name="sending-an-outgoing-mdn"></a>送信 MDN の送信
送信 MDN は AS2EDIReceive によって生成または AS2Receive 受信パイプラインと AS2Send パイプラインで送信します。 このトピックでは、MDN を送信する方法について説明します。 MDN を生成する方法の詳細については、次を参照してください。[送信 MDN の生成](../core/generating-an-outgoing-mdn.md)します。  
  
> [!NOTE]
>  AS2EDISend 送信パイプラインは、そのパイプラインの EDI アセンブラーは、MDN の処理で使用されていないため、送信 MDN の送信には使用されません。  
  
## <a name="agreement-resolution-for-an-mdn"></a>MDN のアグリーメントの解決  
 MDN はセルフ ルーティングです。 目的のアグリーメントにルーティングするために必要な情報が含まれています。 送信パイプラインは AS2 アグリーメントのプロパティを使用して送信 MDN を処理します。 ただし、MDN は、パーティにルーティングするために解決されるアグリーメントにはありません。  
  
 AS2Send パイプラインは、送信 MDN を処理するときに、AS2 を使用して、MDN を処理するアグリーメントのプロパティを取得するメッセージ コンテキストの値にします。 これは、AS2 を照合することによっての AS2 コンテキスト プロパティに-アグリーメントのプロパティを**識別子**ページでは、一方向の AS2 アグリーメント タブで、**アグリーメントのプロパティ** ダイアログ ボックス。 場合、MDN のこのアグリーメントの解決が失敗する、AS2-にアグリーメントの値が設定されていません。 アグリーメントを特定できない場合は、既定のアグリーメントが MDN の生成に使用されます。  
  
 送信 MDN の既定のアグリーメントでは、証明書解決の一覧の検証が実行されます。 この検証を実行しないようにする場合、ことを確認します。 適切な AS2 のアグリーメントにプロパティが設定されて、受信側パーティを解決できると、アグリーメントのプロパティを特定できるようにします。 そうである場合、証明書の解像度リストの検証を要求する既定のアグリーメントは使用されません。 無効にする必要がありますも、**証明書失効リストのチェック**プロパティを**検証**一方向の AS2 アグリーメント タブのページ、**アグリーメントのプロパティ**ダイアログ ボックス。  
  
## <a name="synchronous-and-asynchronous-transmission"></a>同期および非同期の送信  
 既定の AS2 処理では、MDN が同期的に送信されます。 MDN の送信ポートに関連付けられた双方向の受信ポートによって送信します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP POST に対する HTTP 応答として、または同じ TCP/IP 接続での HTTPS post に対する HTTPS 応答として MDN を送信します。 MDN は、HTTP 応答コマンドのメッセージの本文に含まれます。  
  
 MDN が非同期に送信する場合、メッセージ ボックスから MDN を取得する別の送信ポートで、MDN を送信する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 個別の元の AS2 メッセージを配信するために使用される一意な TCP/IP 接続で配信される HTTP Post として MDN を送信します。 個別の HTTP Post として MDN を設定すると、場合でもは HTTP 応答コマンドは、投稿が必要です。  
  
 非同期 MDN は、元の AS2 メッセージの Receipt-delivery-option ヘッダーの URL に通常送信されます。 ただし場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティが設定されて、上、**検証**一方向の AS2 アグリーメント タブのページ、**アグリーメントプロパティ**、MDN は送信 URL にダイアログ ボックスを **- Receipt-delivery-option (URL)** アグリーメント プロパティに設定します。  
  
## <a name="how-the-send-pipeline-processes-an-outgoing-mdn"></a>送信パイプラインが送信 MDN を処理する方法  
 送信 MDN AS2Send パイプライン プロセスは次のとおりです。  
  
-   AS2 の一方向のアグリーメント プロパティで有効になっている場合、デジタル署名の適用を含む MIME 処理を実行します。  
  
-   否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) には、相関関係のエントリを作成します。  
  
-   MDN のコピー (ワイヤ形式) を作成し、否認不可データベースに保存で有効になっている場合、**送信 MDN の NRR の有効化**アグリーメントのプロパティ。  
  
-   MDN を HTTP アダプターに配信します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 送信コンポーネント](../core/as2-send-components.md)