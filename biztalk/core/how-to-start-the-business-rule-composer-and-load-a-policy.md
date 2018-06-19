---
title: ビジネス ルール作成ツールを起動し、ポリシーの読み込みする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, loading
- opening, Busines Rule Composer
- Business Rule Composer, policies
- Business Rule Composer, opening
ms.assetid: 34a6034d-90b3-4ce0-9770-3790763affe3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 420517c51fd6c7a6c854afe161a11a58f952db83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255866"
---
# <a name="how-to-start-the-business-rule-composer-and-load-a-policy"></a>ビジネス ルール作成ツールを起動し、ポリシーの読み込みする方法
このセクションでは、ビジネス ルール作成ツールの起動方法とポリシーの読み込み方法について説明します。  
  
### <a name="to-start-the-business-rule-composer"></a>ビジネス ルール作成ツールを起動するには  
  
-   **開始** メニューのをポイント**すべてのプログラム**、microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリック**ビジネス ルール作成ツール**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
### <a name="to-load-a-policy"></a>ポリシーを読み込むには  
  
1.  ビジネス ルール作成ツールでの**ルール ストア** メニューのをクリックして**ロード**です。  
  
2.  **ルール ストア** ダイアログ ボックスで、 **SQL Server**ドロップダウン リストで、接続する SQL Server™ コンピューターを選択します。  
  
3.  **データベース**ドロップダウン リストで、開きたいルール ストアを含むデータベースを選択します。  
  
> [!NOTE]
>  既定のデータベースがインストールされているルール ストアを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は**BizTalkRuleEngineDb**です。  
  
> [!NOTE]
>  新しく作成された SQL Server があるアカウントを使用するかどうか、**パスワードの期限を適用する**と**ユーザーは次回ログイン時にパスワードを変更する必要があります**オプションのセット、ビジネス ルール作成ツールは、ルールへの接続に失敗しますエンジンのデータベースです。