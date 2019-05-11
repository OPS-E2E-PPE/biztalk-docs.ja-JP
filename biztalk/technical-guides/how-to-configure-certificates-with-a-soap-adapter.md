---
title: SOAP アダプターを使用した証明書を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 20ee05c5-9cea-456d-bff6-49dd249f0ff4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e7f45ae5cec3d0921a4fbc32456c5856a8f5159
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253415"
---
# <a name="how-to-configure-certificates-with-a-soap-adapter"></a>SOAP アダプターを使用した証明書を構成する方法
SOAP 送信アダプタを受け付けるか、クライアント証明書を必要とするサーバーとの接続をセキュリティで保護できます。 クライアント証明書を指定する場合、SOAP 送信アダプタが使用、証明書を必要とするか、クライアント証明書をそのまま使用するサーバーに接続するときにします。 クライアント証明書を指定しないと、移行先サーバーには、クライアント証明書が必要です、送信者が認証されていないと、SOAP 送信アダプターはメッセージを送信に失敗し、標準の再試行ロジックに従います。  

 SOAP 送信アダプタのクライアント証明書を使用するアカウントの個人用ストア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスが実行されています。 SOAP アダプターでは、その拇印によって証明書を指定します。 SOAP 送信アダプタは、何らかの理由で証明書の読み込みに失敗した場合、送信中だったメッセージは中断されます。  

 を暗号化または署名されたメッセージを送信する SOAP アダプタを使用する場合は、送信ポートのクライアント証明書の拇印の SOAP トランスポートのプロパティを構成します。  

## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  

### <a name="to-configure-biztalk-server-to-send-messages-over-a-soap-connection"></a>SOAP 接続経由でメッセージを送信する BizTalk Server を構成するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、新しい SOAP 送信ポートを作成または既存の SOAP 送信ポートのプロパティを開きます。  

2. クリックして**構成**で、**トランスポート**のセクション、**送信ポートのプロパティ** ダイアログ ボックス。  

3. **全般**] タブの [**認証の種類**を選択します**Anonymous**、**基本的な**、**ダイジェスト**、または**NTLM**します。  

4. 場合、認証の種類は**基本的な**または**ダイジェスト**、選択するか**シングル サインオンを使用しないでください**後者を指定してください、ユーザー名とパスワード) またはを選択します。**シングル サインオンを使用して、** (この場合、関連アプリケーションを選択する必要があります)。  

5. **SSL クライアント証明書の拇印**、適切な拇印を入力します。  

6. をクリックして**OK**、順にクリックします**OK**もう一度です。
