---
title: "送信 AS2 メッセージのアグリーメントの解決 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 578d7565-534c-4c13-b473-975f347f3a9b
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cf35a15ca7d0e27ba0c2bf1a05781d6512e0bef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="agreement-resolution-for-outgoing-as2-messages"></a>送信 AS2 メッセージのアグリーメントの解決
AS2 送信パイプラインは、HTTP/HTTPS トランスポート経由の送信 EDIINT/AS2 エンコード メッセージを処理するときに、メッセージを解決するアグリーメントを決定します。 その後、それらのアグリーメントのプロパティを使用して送信メッセージを処理します。 送信パイプラインは、次の条件 (優先度順) を使用してアグリーメントを決定します。  
  
1.  送信パイプラインは、AS2From および AS2To コンテキスト プロパティと、アグリーメント プロパティの一部として指定された AS2From および AS2To の値との照合を試みます。  
  
2.  送信パイプラインは内の他のアグリーメント リゾルバーとして設定されている、AS2To プロパティの値を持つ、送信メッセージの AS2To コンテキスト プロパティと一致しようとして、前の手順に失敗した場合、**識別子**アグリーメントのタブプロパティ。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、AS2To プロパティをコンテキストに書き込みません。 AS2To コンテキスト プロパティでアグリーメント解決を実行する場合は、アグリーメント解決を実行するカスタム オーケストレーションまたはカスタム パイプライン コンポーネントを組み込む必要があります。 詳細については、次を参照してください。[送信パーティの解決の AS2 コンテキスト プロパティの書き込み](../core/writing-as2-context-properties-for-outbound-party-resolution.md)です。  
  
    > [!NOTE]
    >  動的送信ポートを使用している場合は、アグリーメント解決のためのコンテキストに AS2To プロパティを書き込む必要があります。  
  
3.  前の手順が失敗した場合、送信パイプラインは、アグリーメントに関連付けられている送信ポートと、メッセージをサブスクライブしている送信ポートとの照合を試みます。 送信ポートがアグリーメントに関連付け、**送信ポート**の一方向の AS2 アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
    > [!NOTE]
    >  EDI 処理とは異なり、アグリーメントを特定できない場合に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が使用できるフォールバック AS2 プロパティはありません。 ただし、MDN の送信に使用される既定のアグリーメントがあります。 また、送信ポートも Http.UserHttpHeaders コンテキスト プロパティも、MDN のアグリーメントの解決には使用されません。 詳細については、の「アグリーメント解決 MDN の」セクションを参照してください。 [、送信 MDN を送信する](../core/sending-an-outgoing-mdn.md)です。  
  
    > [!NOTE]
    >  場合、AS2 のアグリーメント プロパティに、**識別子**の一方向の AS2 アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックスは既定では、英語のパーティ名、および AS2 の値に設定-ヘッダーにAS2 のメッセージが英語以外の名前に設定してから、一致は検出されません。  
  
> [!NOTE]
>  AS2 経由で EDI を送信する場合、EDI と AS2 の両方に個別のアグリーメントを使用する必要があります。  
  
 送信処理の詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)