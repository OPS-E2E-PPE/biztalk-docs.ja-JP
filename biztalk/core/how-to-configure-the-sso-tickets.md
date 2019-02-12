---
title: SSO チケットの構成 |Microsoft Docs
description: SSO 管理者またはコマンドラインを使用してシステム レベル、および BizTalk Server での関連アプリケーション用のエンタープライズ シングル サインオン チケットを検証しています。
ms.custom: ''
ms.date: 01/08/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], configuring tickets
- SSO, tickets
- tickets [SSO], configuring
ms.assetid: 32f0384b-ac79-4cce-b3f5-f4f8a73a673a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3abac3a0d527c6834105db8fd1c74fd934fd821d
ms.sourcegitcommit: 41947648c73d437a201b2190307e0270d61e037a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2019
ms.locfileid: "56087934"
---
# <a name="configure-the-sso-tickets-in-biztalk-server"></a>BizTalk Server で SSO チケットを構成します。
シングル サインオン システム全体のエンタープライズ シングル サインオン (SSO) 管理 mmc スナップインまたはチケットの動作を制御するためのコマンドラインを使用できます。 このツールを使用して、チケットを許可し、SSO チケットを検証できます。  
  
## <a name="before-you-begin"></a>アンインストールの準備

- リモートを行うことができる場合、SSO の管理は、リモートのコンピューターにインストールされて、 [IssueTicket](https://docs.microsoft.com/biztalk/core/technical-reference/issoticket-issueticket-method)操作。 SSO 管理モジュールとランタイム モジュール (ENTSSO サービス) の間のすべてのトラフィックが暗号化されます。  
  
- コマンド ライン ユーティリティ ssomanage.exe を使用して、関連アプリケーション レベルでチケットのタイムアウトを入力できます。 これは、アプリケーションが作成されたときではなく、アプリケーションの更新が行われたときにのみ行うことができます。
  
- SSO 管理者グループのユーザーだけは、SSO システム レベルおよび関連アプリケーション レベルでチケットを構成できます。  
  
- システム レベルでチケットが無効になっている場合は、関連アプリケーション レベルで使用できません。 システム レベルでチケットを有効にして、関連アプリケーション レベルで無効にすることになります。  
  
- システム レベルでは、検証が有効である場合、関連アプリケーション レベルでチケットを検証する必要があります。 システム レベルでの検証を無効にし、関連アプリケーション レベルで有効にすることになります。  
  
- システム レベルと関連アプリケーション レベルでチケットのタイムアウトを入力すると、関連アプリケーション レベルで入力した 1 つは、チケットの有効期間を決定します。  
  
チケットとチケットの検証の詳細については、次を参照してください。 [SSO チケット](../core/sso-tickets.md)します。  
  
## <a name="allow-affiliate-application-tickets-using-sso-administration"></a>SSO の管理を使用して関連アプリケーションのチケットを許可します。  
  
1.  **開始**メニューの **すべてのプログラム** > **Microsoft エンタープライズ シングル サインオン** > **SSO の管理**.
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**関連アプリケーション**ノード。  
  
3.  右クリックして**関連アプリケーション** > **プロパティ**します。  
  
4.  選択、**オプション**タブ。  
  
5.  選択**チケットを許可**し、必要なチケットのタイムアウトを入力します。  
  
## <a name="allow-and-validate-sso-system-level-tickets-using-the-command-line"></a>許可して、コマンドラインを使用して SSO システム レベルのチケットの検証  
  
1. コマンド プロンプトを開き ([スタート] メニュー > 型**コマンド プロンプト**> 選択**コマンド プロンプト**)。

    > [!TIP]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムで管理者特権でコマンド プロンプトを開く必要があります (右クリックして**コマンド プロンプト** > **管理者として実行**)。
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは`\Program Files\Common Files\Enterprise Single Sign-On`します。 たとえば、次のように入力します。 

    `cd C:\Program Files\Common Files\Enterprise Single Sign-On`
  
3. 型`ssomanage -tickets <allowed yes/no> <validate yes/no>`ここで、 *\<許可はい/いいえ\>* チケットを許可するかどうかどうかを示すと*\<はい/いいえの検証\>* チケットを引き換えるがいる後に検証が必要かどうかを示します。  
  
    使用することができます`yes`、 `no`、 `on`、または`off`を許可したり、チケットを検証します。 これらの語は大文字と小文字が区別されないため、言語の設定に関係なく使用してください。
  
## <a name="see-also"></a>参照

[SSO について](../core/understanding-sso.md)   
[SSO の使用](../core/using-sso.md)
