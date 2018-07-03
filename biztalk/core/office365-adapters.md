---
title: Office 365 Outlook メール アダプターを使用して、|Microsoft Docs
description: Office 365 Outlook のアダプターを BizTalk server で電子メール、予定表、連絡先などを使用してメッセージを送受信することの概要
ms.custom: ''
ms.date: 06/19/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: ribarua
manager: dougeby
ms.openlocfilehash: 2002ab6859a71a930ef9166f9b3a5a072ba77948
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946237"
---
# <a name="office-365-outlook-adapters-in-biztalk"></a>BizTalk での office 365 Outlook のアダプター

## <a name="overview"></a>概要
**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]機能パック 3**、BizTalk Server と Office 365 Outlook の機能の間でメッセージを送受信できます。 機能パック 3 では、次のアダプターが含まれています。

- [Office 365 Outlook メール アダプター](office365-mail-adapter.md)
- [Office 365 Outlook の予定表のアダプター](office365-calendar-adapter.md)
- [Office 365 Outlook の連絡先のアダプター](office365-contact-adapter.md)

## <a name="prerequisites"></a>前提条件

* [Office 365 アカウント](https://outlook.office365.com)
* インストール[Feature Pack 3](https://aka.ms/bts2016fp3) BizTalk Server で
* SSO 管理者グループのメンバーであるアカウントを使用して、

## <a name="tms-overview"></a>TMS の概要

BizTalk Server TMS は、BizTalk で使用される Office 365 の OAuth トークンを更新するサービスです。 トークンが有効なが常にあることを確認、定期的にトークンを更新します。 エンタープライズ シングル サインオン サービス (ENT SSO) に依存しているし、マスター シークレット サーバーをホストするコンピューターにインストールする必要があります。 

## <a name="install-biztalk-server-tms"></a>BizTalk Server TMS をインストールします。

1. インストール[Feature Pack 3](https://aka.ms/bts2016fp3)します。
2. `\Program Files (x86)\Microsoft BizTalk Server <your version>`BizTalkTMS.msi を実行します。
3. ユーザー名と SSO 管理者グループのメンバーであるユーザーのパスワードを入力します。 

![BizTalk Server TMS のセットアップ](../core/media/BizTalk-TMS.png)

## <a name="sign-in-to-office-365"></a>Office 365 にサインイン

作成する際、[送信ポート](how-to-create-a-send-port2.md)または[受信場所](how-to-create-a-receive-location.md)BizTalk 管理コンソールで実行できます**でサインインしています.** を Office 365 アカウント。

  ![Office 365 のサインイン](../core/media/office365-signin.png)

Office 365 の資格情報を入力し、アクセス許可を確認します。 これらの資格情報は、BizTalk には、接続を承認し、Office 365 アカウントへのアクセスします。 次の例では、Office 365 Outlook の予定表のアクセス許可が表示されます。

  ![Office 365 カレンダーのアクセス許可](../core/media/office365-calendar-permissions.png)

## <a name="get-started"></a>作業開始
BizTalk Server TMS をインストールした後は、成果物を作成し、アダプターの使用を開始する準備ができました。

- [Office 365 Outlook メール アダプター](./office365-mail-adapter.md)
- [Office 365 Outlook の予定表のアダプター](./office365-calendar-adapter.md)
- [Office 365 Outlook の連絡先のアダプター](./office365-contact-adapter.md)
