---
title: SMTP 送信ハンドラを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 99dc71cf04d8a80b3a88630908a814957c83b8cb
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "22248498"
---
# <a name="how-to-configure-an-smtp-send-handler"></a>SMTP 送信ハンドラを構成する方法
SMTP 送信ハンドラのプロパティは、BizTalk 管理コンソールで設定できます。 個別の SMTP 送信ポートでプロパティが設定されていない場合は、これらの送信ハンドラのプロパティが送信ポートの構成値として使用されます。  
  
### <a name="to-change-global-variables-for-an-smtp-send-handler"></a>SMTP 送信ハンドラのグローバル変数を変更するには  
  
1.  BizTalk Server 管理コンソールで、展開[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。  
  
2.  展開したアダプターの一覧でクリックして **SMTP**, 、右側のペインで、構成する送信ハンドラーを右クリックしをクリック **プロパティ**します。  
  
3.  **アダプター ハンドラーのプロパティ**  ダイアログ ボックスの 、 **全般的な**  タブで、 **ホスト名** 一覧で、使用する送信ハンドラー、関連付けられているとする をクリックし、ホストを選択 **プロパティ**します。  
  
4.  **SMTP トランスポートのプロパティ**  ダイアログ ボックスで、 **プロパティ**  タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**SMTP サーバー名と TCP ポート**|**[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]**<br /><br /> 必須。 SMTP サーバー名とメッセージを送信するときに使用する (省略可能) の TCP ポート番号を入力します。 たとえば、次のように入力することができます。<br /><br /> -mySMTPserver<br />-mySMTPserver.internet.com:2525<br /><br /> **以前のバージョンの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  (BizTalk Server 2013) を含むのみ、SMTP サーバー名を入力します。 TCP ポート 25 では、ハード コードされます。<br /><br /> 最大長: 256|  
    |**差出人 (電子メール アドレス)**|必須。 SMTP に配置する電子メール アドレスを入力 **から** ヘッダー。<br /><br /> 最大長: 256|  
    |**認証の種類**|SMTP サーバーで使用する認証の種類を入力します。<br /><br /> オプション：<br /><br /> -   **[認証なし]**<br />-   **基本認証**<br />-   **プロセス アカウント (NTLM)**<br /><br /> 既定値: プロセス アカウント (NTLM)|  
    |**ユーザー名**|SMTP サーバーで認証を使用するユーザー名を入力します。<br /><br /> 場合、このプロパティが値を必要と **認証の種類** は **基本認証**します。<br /><br /> 最小長: 0<br /><br /> 最大長: 256|  
    |**パスワード**|SMTP サーバーで認証を使用するパスワードを入力します。<br /><br /> 場合、このプロパティが値を必要と **認証の種類** は **基本認証**します。<br /><br /> 最小長: 0<br /><br /> 最大長: 256|  
  
5.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [SMTP アダプターの構成](../core/configuring-the-smtp-adapter.md)