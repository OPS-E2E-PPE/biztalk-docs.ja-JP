---
title: SMTP 送信ハンドラを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 2015-10-22
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, SMTP adapters
- SMTP adapters, send handlers
- configuring [SMTP adapters], send handlers
ms.assetid: b68a36ce-f0a5-4302-a405-bb154c935f47
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9712b4c3b8730b78f1dae9a27eab4dfafe25dfce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386391"
---
# <a name="how-to-configure-an-smtp-send-handler"></a>SMTP 送信ハンドラを構成する方法
BizTalk 管理コンソールで、SMTP 送信ハンドラのプロパティを設定できます。 送信ポートをこれらの送信ハンドラ プロパティは、個別の SMTP プロパティが設定されていない場合、送信ポートの構成値として使用されます。  

### <a name="to-change-global-variables-for-an-smtp-send-handler"></a>グローバル変数を SMTP 送信ハンドラーを変更するには  

1. BizTalk Server 管理コンソールで  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。  

2. 展開したアダプターの一覧でクリックして**SMTP**、右側のウィンドウで、構成する送信ハンドラーを右クリックし をクリック、**プロパティ**します。  

3. **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**いる送信ハンドラー、関連付けられているとする をクリックし、ホストを選択します**プロパティ**します。  

4. **SMTP トランスポートのプロパティ** ダイアログ ボックスの 、**プロパティ** タブで、次の操作を行います。  


   |             プロパティ              |                                                                                                                                                                                                                                                             目的                                                                                                                                                                                                                                                             |
   |-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **SMTP サーバー名と TCP ポート** | **[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]**<br /><br /> 必須。 SMTP サーバー名とメッセージを送信するときに使用する (省略可能) の TCP ポート番号を入力します。 たとえば、次のように入力することができます。<br /><br /> -   mySMTPserver<br />-   mySMTPserver.internet.com:2525<br /><br /> **以前のバージョンの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  (BizTalk Server 2013) を含む、SMTP サーバー名のみを入力します。 TCP ポート 25 では、ハード コーディングします。<br /><br /> 最大長:256 |
   |     **差出人 (電子メール アドレス)**     |                                                                                                                                                                                                               必須。 SMTP に配置する電子メール アドレスを入力**から**ヘッダー。<br /><br /> 最大長:256                                                                                                                                                                                                               |
   |      **認証の種類**      |                                                                                                                                          SMTP サーバーで使用する認証の種類を入力します。<br /><br /> オプション:<br /><br /> -   **認証なし**<br />-   **基本認証**<br />-   **プロセス アカウント (NTLM)**<br /><br /> 既定値:プロセス アカウント (NTLM)                                                                                                                                          |
   |           **ユーザー名**           |                                                                                                                                                SMTP サーバーで認証に使用するユーザー名を入力します。<br /><br /> このプロパティには、値がある場合は**認証の種類**は**基本認証**します。<br /><br /> 最小長:0<br /><br /> 最大長:256                                                                                                                                                |
   |           **Password**            |                                                                                                                                                SMTP サーバーでの認証に使用するパスワードを入力します。<br /><br /> このプロパティには、値がある場合は**認証の種類**は**基本認証**します。<br /><br /> 最小長:0<br /><br /> 最大長:256                                                                                                                                                 |


5. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [SMTP アダプターの構成](../core/configuring-the-smtp-adapter.md)