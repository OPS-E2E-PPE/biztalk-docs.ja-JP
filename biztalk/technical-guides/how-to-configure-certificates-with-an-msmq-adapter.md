---
title: MSMQ アダプターでの証明書を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: f36e3d13920982f79fe693a306a8123f089c76e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297914"
---
# <a name="how-to-configure-certificates-with-an-msmq-adapter"></a>MSMQ アダプターでの証明書を構成する方法
MSMQ 送信アダプターを受け付けるか、クライアント証明書を必要とするサーバーとの接続をセキュリティで保護できます。 クライアント証明書が指定されている場合、MSMQ 送信アダプターを必要とするか、クライアント証明書をそのまま使用するサーバーと接続するときに、証明書を使用します。 クライアント証明書が指定されていないと、移行先サーバーには、クライアント証明書が必要です、送信者が認証されていないと、MSMQ 送信アダプターは、メッセージの送信に失敗し、標準の再試行ロジックに従っています。  
  
 MSMQ 送信アダプター、クライアント証明書を使用するアカウントの個人用ストア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスが実行されています。 証明書は拇印によって指定します。 MSMQ 送信アダプターは、何らかの理由で証明書の読み込みに失敗した場合、送信中だったメッセージが中断されます。  
  
 を暗号化または署名されたメッセージを送信する、MSMQ アダプターを使用する場合は、送信ポートの証明書の拇印の MSMQ トランスポートのプロパティを構成します。 このプロパティでは、メッセージの認証に使用する証明書の拇印を指定します。 メッセージを確認するには、[認証の使用] プロパティと組み合わせてこのプロパティを使用します。 キューにアクセスするには、[ユーザー名] プロパティおよび [パスワード] プロパティを使用します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますログインする必要がのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
### <a name="to-configure-biztalk-server-to-send-messages-over-an-msmq-connection"></a>MSMQ 接続を介してメッセージを送信する BizTalk Server を構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、新しい MSMQ 送信ポートを作成または既存の MSMQ 送信ポートのプロパティを開きます。  
  
2.  をクリックして**構成**で、**トランスポート**のセクションで、**送信ポートのプロパティ** ダイアログ ボックス。  
  
3.  **MSMQ トランスポートのプロパティ**] ダイアログ ボックスの**認証**[ **True**です。  
  
4.  **証明書の拇印**、適切な拇印を入力します。  
  
5.  をクリックして **[ok]**、順にクリック**OK**もう一度です。