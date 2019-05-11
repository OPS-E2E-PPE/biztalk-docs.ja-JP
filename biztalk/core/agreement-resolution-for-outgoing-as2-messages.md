---
title: 送信 AS2 メッセージのアグリーメントの解決 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 578d7565-534c-4c13-b473-975f347f3a9b
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5722e128a23e5836357ec0503a24be9676e8131
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359305"
---
# <a name="agreement-resolution-for-outgoing-as2-messages"></a>送信 AS2 メッセージのアグリーメントの解決
AS2 送信パイプラインは、HTTP/HTTPS トランスポート経由の送信 EDIINT/AS2 エンコード メッセージを処理するときに、メッセージを解決するアグリーメントを決定します。 その後、それらのアグリーメントのプロパティを使用して送信メッセージを処理します。 送信パイプラインは、次の条件 (優先度順) を使用してアグリーメントを決定します。  
  
1. 送信パイプラインは、AS2From および AS2To コンテキスト プロパティと、アグリーメント プロパティの一部として指定された AS2From および AS2To の値との照合を試みます。  
  
2. 送信パイプラインは、送信メッセージの AS2To コンテキスト プロパティで、その他のアグリーメント リゾルバーとして設定される、AS2To プロパティの値と一致しようとして、前の手順に失敗した場合、**識別子**アグリーメントのタブプロパティ。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、AS2To プロパティをコンテキストに書き込みません。 AS2To コンテキスト プロパティでアグリーメント解決を実行する場合は、アグリーメント解決を実行するカスタム オーケストレーションまたはカスタム パイプライン コンポーネントを組み込む必要があります。 詳細については、次を参照してください。[送信パーティ解決の AS2 コンテキスト プロパティの書き込み](../core/writing-as2-context-properties-for-outbound-party-resolution.md)します。  
   > 
   > [!NOTE]
   >  動的送信ポートを使用している場合は、アグリーメント解決のためのコンテキストに AS2To プロパティを書き込む必要があります。  
  
3. 前の手順が失敗した場合、送信パイプラインは、アグリーメントに関連付けられている送信ポートと、メッセージをサブスクライブしている送信ポートとの照合を試みます。 送信ポートがアグリーメントに関連付け、**送信ポート**の一方向の AS2 アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
   > [!NOTE]
   >  EDI 処理とは異なり、アグリーメントを特定できない場合に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が使用できるフォールバック AS2 プロパティはありません。 ただし、MDN の送信に使用される既定のアグリーメントがあります。 また、送信ポートも Http.UserHttpHeaders コンテキスト プロパティも、MDN のアグリーメントの解決には使用されません。 詳細については、の「アグリーメント解決の MDN」セクションを参照してください。[送信 MDN の送信](../core/sending-an-outgoing-mdn.md)します。  
   > 
   > [!NOTE]
   >  場合、AS2 のアグリーメントのプロパティを**識別子**の一方向の AS2 アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックスは既定では英語のパーティ名、および AS2 の値に設定-ヘッダーas2 メッセージは英語以外の名前を設定し、一致が見つかりません。  
  
> [!NOTE]
>  AS2 経由で EDI を送信する場合、EDI と AS2 の両方に個別のアグリーメントを使用する必要があります。  
  
 送信プロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)