---
title: MSMQ アダプターを使用した証明書を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 922a171d-705f-4465-acda-212aa3797c57
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c73c695423ac8b0e9a08ee375e1294f74f832a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972443"
---
# <a name="how-to-configure-certificates-with-an-msmq-adapter"></a>MSMQ アダプターを使用した証明書を構成する方法
MSMQ 送信アダプターを受け付けるか、クライアント証明書を必要とするサーバーとの接続をセキュリティで保護できます。 クライアント証明書が指定されている場合、MSMQ 送信アダプターを必要とするか、クライアント証明書をそのまま使用するサーバーに接続するときに、証明書を使用します。 クライアント証明書が指定されていないと、移行先サーバーには、クライアント証明書が必要です、送信者が認証されていないと、MSMQ 送信アダプターはメッセージを送信に失敗し、標準の再試行ロジックに従います。  

 MSMQ 送信アダプター クライアント証明書を使用するアカウントの個人用ストア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスが実行されています。 証明書は拇印によって指定します。 MSMQ 送信アダプターは、何らかの理由で証明書の読み込みに失敗した場合、送信中だったメッセージは中断されます。  

 を暗号化または署名されたメッセージを送信する、MSMQ アダプターを使用する場合は、送信ポートに証明書の拇印の MSMQ トランスポートのプロパティを構成します。 このプロパティは、メッセージの認証に使用する証明書の拇印を指定します。 メッセージを確認するには、[認証の使用] プロパティと組み合わせてこのプロパティを使用します。 キューにアクセスするには、[ユーザー名] プロパティおよび [パスワード] プロパティを使用します。  

## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  

### <a name="to-configure-biztalk-server-to-send-messages-over-an-msmq-connection"></a>MSMQ 接続経由でメッセージを送信する BizTalk Server を構成するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、新しい MSMQ 送信ポートを作成または既存の MSMQ 送信ポートのプロパティを開きます。  

2. クリックして**構成**で、**トランスポート**のセクション、**送信ポートのプロパティ** ダイアログ ボックス。  

3. **MSMQ トランスポートのプロパティ** ダイアログ ボックスの**認証**を選択します**True**します。  

4. **証明書の拇印**、適切な拇印を入力します。  

5. をクリックして**OK**、順にクリックします**OK**もう一度です。
