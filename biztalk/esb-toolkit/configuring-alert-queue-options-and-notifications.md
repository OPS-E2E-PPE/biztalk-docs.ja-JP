---
title: "警告キュー オプションおよび通知の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f78afbf9-6e27-4887-8424-f265fbd8448a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914af88b989c73444e16acedf43b9a236897859d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-alert-queue-options-and-notifications"></a>警告キュー オプションの構成と通知
ESB の管理ポータルでは、アラートを生成するようにキューに置き、アラートにサブスクライブするユーザーに、アラート通知を送信、ESB Notification Service を使用して、ポータルにエラー メッセージが到着 ESB Alert サービスを使用します。 ESB の管理ポータルでこれらのサービスで使用する設定を編集することができます。  
  
### <a name="to-configure-the-settings-for-the-esb-alert-service"></a>ESB アラート サービスの設定を構成するには  
  
1.  (そのうちポータル管理者は自動的にメンバー)、Microsoft BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。  
  
2.  をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**フォールト設定**を開くには、ポータル[フォールトの設定 ページ](../esb-toolkit/fault-settings-page.md)です。  
  
3.  **キューのアラート オプション**セクションで、オンまたはオフ、**キュー サービスのアラートを有効にする**有効にするにまたはサービスを無効にする チェック ボックスです。  
  
4.  サービスを有効にした場合は、この要件に合わせて他のコントロールの値を編集します。 サービスは、適切な LDAP (ライトウェイト ディレクトリ アクセス プロトコル) 接続文字列を指定する必要がありますので、Microsoft Active Directory と対話します。 キュー バッチ サイズとポーリング間隔を指定することもできます。  
  
5.  をクリックして**保存**新しい設定を保存します。  
  
### <a name="to-configure-the-settings-for-the-esb-alert-email-notification-service"></a>ESB アラートの電子メール通知サービスの設定を構成するには  
  
1.  (そのうちポータル管理者は自動的にメンバー)、BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。  
  
2.  をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**フォールト設定**を開くには、ポータル[フォールトの設定 ページ](../esb-toolkit/fault-settings-page.md)です。  
  
3.  **アラートの電子メール オプション**セクションで、オンまたはオフ、**アラートの電子メール サービスを有効にする**有効にするにまたはサービスを無効にする チェック ボックスです。  
  
4.  サービスを有効にした場合は、この要件に合わせて他のコントロールの値を編集します。 電子メール サーバー名と「差出人」アドレスを指定、必要に応じて、ポーリング間隔とバッチ サイズを変更し、サービスで使用される XSLT Extensible Stylesheet Language Transformations () ファイルへのパスを指定します。  
  
5.  をクリックして**保存**新しい設定を保存します。