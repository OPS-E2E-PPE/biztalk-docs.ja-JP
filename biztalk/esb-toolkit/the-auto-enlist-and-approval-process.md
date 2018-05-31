---
title: 自動参加および承認プロセス |Microsoft ドキュメント
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
ms.openlocfilehash: 333e1403ffd45f80a98d3eb17f5d3aa2b63c7798
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295626"
---
# <a name="the-auto-enlist-and-approval-process"></a>自動参加と承認のプロセス
2 つの方法で Microsoft BizTalk Server のエンドポイントを公開する、ESB の管理ポータルを構成できます。  
  
-   これは、管理者のことを確認して登録要求を承認する必要がありますここで、承認プロセスを構成できます。  
  
-   使用して構成できます自動発行が、ここで、ポータルに自動的に公開要求 Universal Description, Discovery, and Integration (UDDI) のレジストリに管理者の介入なし。  
  
 次の 2 つの手順で説明されても、ポータルの UDDI の統合機能の他のいくつかの設定を指定できます。  
  
### <a name="to-configure-auto-approval-and-publishing-in-the-esb-management-portal"></a>ESB の管理ポータルで自動承認と公開を構成するには  
  
1.  BizTalk Server 管理者グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。  
  
2.  をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**レジストリ設定**を開くには、ポータル[レジストリ設定 ページ](../esb-toolkit/registry-settings-page.md)です。  
  
3.  自動承認と公開を有効にするには、上部にあるテキスト ボックスに、UDDI サーバーの URL を入力、 **UDDI 詳細**クリックし、ページのセクション、**自動**チェック ボックスをオンします。  
  
4.  自動承認と公開を無効にする、オフ、**自動発行**チェック ボックスをオンします。  
  
### <a name="to-configure-e-mail-and-registry-settings-for-the-uddi-integration-features"></a>UDDI の統合機能の電子メールとレジストリの設定を構成するには  
  
1.  BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。  
  
2.  をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**レジストリ設定**を開くには、ポータル[レジストリ設定 ページ](../esb-toolkit/registry-settings-page.md)です。  
  
3.  上部にあるテキスト ボックスに、UDDI サーバーの URL を編集、 **UDDI 詳細**ページのセクションです。 既定の UDDI サービスは、ローカルの Microsoft UDDI サービスです。  
  
4.  選択、**匿名**する場合は、ポータル UDDI サーバーにアクセスするときに、匿名認証を使用する チェック ボックスです。  
  
5.  要求が承認を待ち、UDDI 発行時に電子メールで通知するように、選択する場合は、ポータル、**通知が有効になっている** チェック ボックス、**電子メール通知**ページのセクションです。 電子メール サーバー、電子メール メッセージの配信アドレス、適切な"from"電子メール アドレス、メッセージの件名、およびメッセージ本文の詳細を入力します。  
  
6.  管理者の連絡先の名前を入力し、UDDI の受信確認の電子メール アドレスに電子メール メッセージの要求、**既定の設定の**ページのセクションです。  
  
### <a name="to-approve-or-decline-a-registration-request-as-an-administrator"></a>承認または管理者としての登録要求を拒否するには  
  
1.  BizTalk Server 管理者グループのメンバーであるアカウントを使用してポータルにログインしていることを確認してください。  
  
2.  をポイント、**レジストリ**ポータルのメイン メニュー タブをクリックして**保留中の要求の管理**を開くには、ポータル[保留中の要求 ページの管理](../esb-toolkit/manage-pending-requests-page.md)です。  
  
3.  保留中の要求を承認するには、クリックして、**承認**一覧にその要求の横にあるアイコン (チェック マーク)。  
  
4.  保留中の要求を拒否する をクリックして、**拒否**一覧にその要求の横にあるアイコン (クロス マーク)。  
  
5.  保留中の要求の詳細を表示する をクリックして、**詳細を表示する**アイコン (虫眼鏡) を開くには、[レジストリ詳細 ページ](../esb-toolkit/registry-details-page.md)です。 発行し、削除、またはこのページで、要求を更新できます。  
  
6.  要求の状態を確認して、以前の要求の一覧を表示をクリックして、**要求履歴を表示する**リンクします。