---
title: ビジネス ルール作成ツールを起動し、ポリシーの読み込みする方法 |Microsoft Docs
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
ms.openlocfilehash: e56d3d2c1dde771d86f8de345d6e3b249ab394b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977051"
---
# <a name="how-to-start-the-business-rule-composer-and-load-a-policy"></a>ビジネス ルール作成ツールを起動し、ポリシーの読み込みする方法
このセクションでは、ビジネス ルール作成ツールの起動方法とポリシーの読み込み方法について説明します。  
  
### <a name="to-start-the-business-rule-composer"></a>ビジネス ルール作成ツールを起動するには  
  
- **開始**メニューで、**すべてのプログラム**、microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。  
  
  > [!NOTE]
  >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
### <a name="to-load-a-policy"></a>ポリシーを読み込むには  
  
1.  ビジネス ルール作成ツールで、上、**ルール ストア** メニューのをクリックして**ロード**します。  
  
2.  **ルール ストア** ダイアログ ボックスで、 **SQL Server**ドロップダウン リストで、接続する SQL Server™ コンピューターを選択します。  
  
3.  **データベース**ドロップダウン リストで、開きたいルール ストアを含むデータベースを選択します。  
  
> [!NOTE]
>  既定のデータベースがインストールされているルール ストアを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は**BizTalkRuleEngineDb**します。  
> 
> [!NOTE]
>  持つ、新しく作成された SQL Server アカウントを使用するかどうか、**パスワードの有効期限を適用する**と**ユーザーは次回ログイン時にパスワードを変更する必要があります**オプション セットでは、ビジネス ルール作成ツールは、ルールへの接続に失敗しますエンジンのデータベースです。