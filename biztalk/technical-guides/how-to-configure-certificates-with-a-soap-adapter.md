---
title: "SOAP アダプターと証明書を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20ee05c5-9cea-456d-bff6-49dd249f0ff4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e382fa9084fd728e04efa29900fb0222d8b05ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-certificates-with-a-soap-adapter"></a>SOAP アダプターと証明書を構成する方法
SOAP 送信アダプタを受け付けるか、クライアント証明書を必要とするサーバーとの接続をセキュリティで保護できます。 クライアント証明書を指定した場合、SOAP 送信アダプタではクライアント証明書を必要とするか受け付けるサーバーに接続するときに、この証明書を使用します。 クライアント証明書を指定しないと、移行先サーバーには、クライアント証明書が必要です、送信者が認証されていないと、SOAP 送信アダプターは、メッセージの送信に失敗し、標準の再試行ロジックに従っています。  
  
 SOAP 送信アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスの実行に使用されているアカウントの個人用ストアにあるクライアント証明書を使用します。 SOAP アダプタは拇印によって証明書を特定します。 SOAP 送信アダプタによる証明書の読み込みが何らかの理由で失敗した場合、送信中だったメッセージは中断されます。  
  
 を暗号化または署名されたメッセージを送信する、SOAP アダプターを使用する場合は、送信ポートのクライアント証明書の拇印の SOAP トランスポートのプロパティを構成します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますログインする必要がのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
### <a name="to-configure-biztalk-server-to-send-messages-over-a-soap-connection"></a>SOAP 接続経由でメッセージを送信する BizTalk Server を構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、新しい SOAP 送信ポートを作成または既存の SOAP 送信ポートのプロパティを開きます。  
  
2.  をクリックして**構成**で、**トランスポート**のセクションで、**送信ポートのプロパティ** ダイアログ ボックス。  
  
3.  **全般** タブの **認証の種類****匿名**、**基本的な**、**ダイジェスト**、または**NTLM**です。  
  
4.  認証の種類は場合**基本的な**または**ダイジェスト**を選択するか**シングル サインオンを使用しないでください**後者を指定してください、ユーザー名とパスワード) またはを選択**シングル サインオンを使用して**(この場合、関連アプリケーションを選択する必要があります)。  
  
5.  **SSL クライアント証明書の拇印**、適切な拇印を入力します。  
  
6.  をクリックして**[ok]**、順にクリック**OK**もう一度です。