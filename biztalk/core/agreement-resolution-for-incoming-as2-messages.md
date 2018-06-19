---
title: 受信 AS2 メッセージのアグリーメントの解決 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 746d01af-de6a-4d5d-9433-b0e1a2b41861
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e5e9795979ddf0a8b8f13fe7ab53bd4e783bd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230154"
---
# <a name="agreement-resolution-for-incoming-as2-messages"></a>受信 AS2 メッセージのアグリーメントの解決
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、EDIINT/AS2 でエンコードされたメッセージを HTTP/HTTPS トランスポート経由で受信すると、メッセージを送信した取引先のビジネス プロファイルの特定を試みます。 これは、次の処理を順番に試みることによって行われます。  
  
1.  AS2 の間に一致する-の値で、受信メッセージ ヘッダーから**AS2-から**で、**識別子**一方向の AS2 アグリーメントのページ、 **アグリーメントのプロパティ**  ダイアログ ボックス。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でアグリーメントを特定できない場合は、受信メッセージに設定されている AS2-From コンテキスト プロパティと取引先名を照合します。  
  
> [!NOTE]
>  AS2-From ヘッダーには ASCII 文字しか含めることができないため、取引先名および AS2-From エイリアスにも ASCII 文字のみを使用する必要があります。 完全に一致しない場合、BizTalk では着信メッセージのヘッダーに基づいてアグリーメントを特定できません。  
  
 AS2 受信パイプラインは、アグリーメントが特定された場合にのみメッセージを処理します。 EDI 処理とは異なり、アグリーメントを特定できない場合に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が使用できるフォールバック AS2 プロパティはありません。  
  
 設定を確認は、パイプラインでは、アグリーメントを特定した後、**アグリーメントの代わりにメッセージ ヘッダーの検証および MDN の設定を使用して**プロパティに、**検証**一方向の AS2 のページアグリーメント、**アグリーメント設定** ダイアログ ボックス。 このプロパティがオンになっている場合、受信パイプラインはアグリーメント プロパティを使用してメッセージを処理します。 このプロパティがオフになっている場合、受信パイプラインはメッセージの AS2 ヘッダーの値を使用してメッセージを処理します。  
  
> [!NOTE]
>  アグリーメントの解決時に決定される AS2 アグリーメントは、EDI ペイロードと同じアグリーメントにならない場合があります。 AS2 アグリーメントは、複数のパーティから EDI ドキュメントをルーティングするクリアリングハウスを表す場合があるので、AS2 と EDI が同じアグリーメントを共有する必要はありません。  
  
 受信プロセスの詳細については、次を参照してください。[受信 AS2 メッセージを処理](../core/processing-an-incoming-as2-message.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)