---
title: アラート キューのオプションと通知の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f78afbf9-6e27-4887-8424-f265fbd8448a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0938ceed9adcf117bcc54433eff1e9d7cd06ab8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302122"
---
# <a name="configuring-alert-queue-options-and-notifications"></a>アラート キューのオプションと通知の構成
ESB 管理ポータルでは、ポータルから、エラー メッセージが到着し、ESB の通知サービスを使用してキューにし、アラートにサブスクライブするユーザーにアラート通知を送信、アラートを生成するのに、ESB アラート サービスを使用します。 ESB 管理ポータルでこれらのサービスによって使用される設定を編集することができます。  
  
### <a name="to-configure-the-settings-for-the-esb-alert-service"></a>ESB アラート サービスの設定を構成するには  
  
1.  (ポータル管理者の自動的にメンバー)、Microsoft BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。  
  
2.  をポイント、**管理者**ポータルのメイン メニューで、タブをクリックして**フォールト設定**ポータルを開く[エラー設定ページ](../esb-toolkit/fault-settings-page.md)します。  
  
3.  **アラート キュー オプション**セクション、オンまたはオフ、 **Queue サービスのアラートを有効にする**を有効にするか、サービスを無効にする チェック ボックス。  
  
4.  サービスを有効にした場合、要件に合わせて、残りのコントロール内の値を編集します。 サービスは、LDAP (ライトウェイト ディレクトリ アクセス プロトコル) の適切な接続文字列を指定する必要がありますので、Microsoft Active Directory と対話します。 バッチ サイズのキューおよびポーリング間隔を指定することもできます。  
  
5.  クリックして**保存**新しい設定を保存します。  
  
### <a name="to-configure-the-settings-for-the-esb-alert-email-notification-service"></a>ESB アラート電子メール通知サービスの設定を構成するには  
  
1.  (ポータル管理者の自動的にメンバー)、BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。  
  
2.  をポイント、**管理者**ポータルのメイン メニューで、タブをクリックして**フォールト設定**ポータルを開く[エラー設定ページ](../esb-toolkit/fault-settings-page.md)します。  
  
3.  **アラートの電子メール オプション**セクション、オンまたはオフ、**アラートの電子メール サービスを有効にする**チェック ボックスを有効または、サービスを無効にします。  
  
4.  サービスを有効にした場合、要件に合わせて、残りのコントロール内の値を編集します。 電子メール サーバー名と「差出人」アドレス指定、必要に応じて、ポーリング間隔とバッチ サイズを変更し、サービスが使用する拡張可能なスタイル シート言語変換 (XSLT) ファイルへのパスを指定します。  
  
5.  クリックして**保存**新しい設定を保存します。