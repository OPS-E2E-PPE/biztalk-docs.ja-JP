---
title: HTTP アダプターを使用した証明書を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc2f454f-22b5-4113-9a23-e00a816d5e48
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520204a6c0f411f8f622838b846a3af41b6c60a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007099"
---
# <a name="how-to-configure-certificates-with-an-http-adapter"></a>HTTP アダプターを使用した証明書を構成する方法
HTTP 送信アダプターを受け付けるか、クライアント証明書を必要とするサーバーとの接続をセキュリティで保護できます。 クライアント証明書を指定した場合、HTTP 送信アダプタではクライアント証明書を必要とするか受け付けるサーバーに接続するときに、この証明書を使用します。 クライアント証明書が指定されていない、移行先サーバーにクライアント証明書が必要な場合は、送信者が認証されていないと、HTTP 送信アダプターがメッセージの送信に失敗して、標準の再試行ロジックに従います。  

 HTTP 送信アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスの実行に使用されているアカウントの個人用ストアにあるクライアント証明書を使用します。 証明書は拇印によって指定します。 HTTP 送信アダプタによる証明書の読み込みが何らかの理由で失敗した場合、送信中だったメッセージは中断されます。  

 を暗号化または署名されたメッセージを送信する HTTP アダプターを使用する場合は、SSL 証明書の拇印の送信ポートの HTTP トランスポートのプロパティを構成します。 このプロパティは、メッセージの認証に使用する証明書の拇印を指定します。  

## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  

### <a name="to-configure-biztalk-server-to-send-messages-over-an-http-connection"></a>HTTP 接続経由でメッセージを送信する BizTalk Server を構成するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、新しい HTTP 送信ポートを作成または既存の HTTP 送信ポートのプロパティを開きます。  

2. クリックして**構成**のトランスポート セクションで、**送信ポートのプロパティ** ダイアログ ボックス。  

3. クリックして**認証**で、 **HTTP トランスポートのプロパティ** ダイアログ ボックス。  

4. **認証の種類**、**匿名**、**基本的な**、**ダイジェスト**、または**Kerberos**します。  

5. 場合、認証の種類は**基本的な**または**ダイジェスト**、選択するか**シングル サインオンを使用しないでください**後者を指定してください、ユーザー名とパスワード) またはを選択します。**シングル サインオンを使用して、** (この場合、関連アプリケーションを選択する必要があります)。  

6. **SSL クライアント証明書の拇印**、適切な拇印を入力します。  

7. をクリックして**OK**、順にクリックします**OK**もう一度です。
