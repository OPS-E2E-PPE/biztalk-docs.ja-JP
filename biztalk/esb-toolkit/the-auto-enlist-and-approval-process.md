---
title: 自動登録と承認プロセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfd3e72e-e28b-4ee3-bc4a-89ef3f64e6d5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39dae57d3265ed4e8a383c315276a7e8c510ce37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968147"
---
# <a name="the-auto-enlist-and-approval-process"></a>自動登録と承認プロセス
2 つの方法で Microsoft BizTalk Server のエンドポイントを公開する ESB 管理ポータルを構成することができます。  
  
- それを構成するには承認プロセスを管理者が確認し、登録要求を承認する必要があります。  
  
- 使用して構成できます自動発行ポータルに自動的に公開する要求 Universal Description, Discovery, and Integration (UDDI) のレジストリに管理者の介入なし。  
  
  次の 2 つの手順」の説明に従って、ポータルの UDDI の統合機能の他のいくつかの設定を指定することもできます。  
  
### <a name="to-configure-auto-approval-and-publishing-in-the-esb-management-portal"></a>ESB 管理ポータルでの自動承認と発行を構成するには  
  
1.  BizTalk Server 管理者グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。  
  
2.  ポイントして、**管理者**ポータルのメイン メニューで、タブをクリックして**レジストリ設定**ポータルを開く[レジストリ設定 ページ](../esb-toolkit/registry-settings-page.md)します。  
  
3.  自動承認と発行を有効にするには、上部にあるテキスト ボックスに UDDI サーバーの URL を入力、 **UDDI の詳細**クリックして、ページのセクション、**自動**チェック ボックスをオンします。  
  
4.  自動承認と公開を無効にする、オフ、**自動発行**チェック ボックスをオンします。  
  
### <a name="to-configure-e-mail-and-registry-settings-for-the-uddi-integration-features"></a>UDDI の統合機能の電子メールとレジストリの設定を構成するには  
  
1.  BizTalk Server 管理者アカウントのグループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。  
  
2.  ポイントして、**管理者**ポータルのメイン メニューで、タブをクリックして**レジストリ設定**ポータルを開く[レジストリ設定 ページ](../esb-toolkit/registry-settings-page.md)します。  
  
3.  上部にあるテキスト ボックスに、UDDI サーバーの URL の編集、 **UDDI 詳細**ページのセクション。 既定の UDDI サービスは、ローカルの Microsoft UDDI サービスです。  
  
4.  選択、 **Anonymous**する場合は、UDDI サーバーにアクセスするときに、匿名認証を使用するポータル チェック ボックス。  
  
5.  UDDI 発行時に電子メールで通知するように、要求が承認を待ちを選択する場合は、ポータル、**通知が有効になっている** チェック ボックス、**電子メール通知**ページのセクション。 電子メール サーバー、電子メール メッセージの配信アドレス、適切な「差出人」電子メール アドレス、メッセージの件名、およびメッセージ本文の詳細を入力します。  
  
6.  管理者の連絡先名を入力し、UDDI の受信確認の電子メール アドレスに電子メール メッセージの要求、**既定の設定の**ページのセクション。  
  
### <a name="to-approve-or-decline-a-registration-request-as-an-administrator"></a>承認または管理者としての登録要求を拒否するには  
  
1.  BizTalk Server 管理者グループのメンバーであるアカウントを使用してポータルにログインすることを確認します。  
  
2.  ポイントして、**レジストリ**ポータルのメイン メニューで、タブをクリックして**保留中の要求の管理**ポータルを開く[保留中の要求の管理ページ](../esb-toolkit/manage-pending-requests-page.md)。  
  
3.  保留中の要求を承認するには、クリックして、**承認**一覧でその要求の横にあるアイコン (チェック マーク)。  
  
4.  保留中の要求を拒否する をクリックして、**拒否**一覧でその要求の横にあるアイコン (十字)。  
  
5.  保留中の要求の詳細を表示する をクリックして、**詳細を表示する**アイコン (虫眼鏡) を開く、[レジストリ詳細ページ](../esb-toolkit/registry-details-page.md)します。 発行し、削除、またはこのページで、要求を更新できます。  
  
6.  要求の状態を確認して、以前の要求の一覧を表示、クリックして、**要求履歴を表示する**リンク。