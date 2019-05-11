---
title: SSO データベース情報を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], viewing SSO database
- SSO database, viewing
- viewing, SSO database
ms.assetid: 0ebadd2e-6ea5-460c-b0a8-f48589e6bf1c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d90da02edcde220f2f36e0329ba001300ff5443b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385188"
---
# <a name="how-to-display-the-sso-database-information"></a>SSO データベース情報を表示する方法
MMC スナップインまたはコマンドライン (ssomanage) ユーティリティを使用して SSO データベース情報を表示することができます。  
  
### <a name="to-display-the-sso-database-information-using-the-mmc-snap-in"></a>MMC スナップインを使用して SSO データベース情報を表示するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリックして**システム**、 をクリックし、**プロパティ**します。  
  
4.  タブをクリックし、**システム プロパティ**ダイアログ ボックスに SSO データベース情報を表示します。  
  
### <a name="to-display-the-sso-database-information-using-the-command-line"></a>コマンドラインを使用して、SSO データベース情報を表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – displaydb**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-display-the-sso-database-the-sso-server-is-connected-to-using-the-command-line"></a>SSO データベースの SSO サーバーを表示するのには、コマンドラインを使用してに接続されています。  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型**ssomanage – showdb**します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
   次の表では、これらの手順で表示される値について説明します。  
  
|プロパティ|値|  
|--------------|-----------|  
|SQL Server|**\<SQL Server 名\>**|  
|シングル サインオン データベース|**\<SQL Server データベース名\>**|  
|シングル サインオン シークレット サーバー名|**\<シングル サインオン サーバーの名前\>**|  
|シングル サインオン管理者アカウント|ドメイン \ アカウント名|  
|シングル サインオン関連管理者アカウント|ドメイン \ アカウント名|  
|削除されたアプリケーション (監査エントリの数) の監査テーブルのサイズ|1,000 (既定値)|  
|削除されたユーザーのマッピング (監査エントリの数) の監査テーブルのサイズ|1,000 (既定値)|  
|外部資格情報参照 (監査エントリの数) の監査テーブルのサイズ|1,000 (既定値)|  
|チケットのタイムアウト (分)|2 (既定)<br /><br /> この値は、整数 from1 525,600 を通じて指定できます。|  
|資格情報キャッシュ タイムアウト (分)|60 (既定値)|  
|シングル サインオンの状態|有効/無効|  
|許可されたチケット|はい/いいえ (既定値)|  
|チケットを検証します。|[はい] (既定値)/no|  
  
## <a name="see-also"></a>参照  
 [SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md)   
 [SSO の使用](../core/using-sso.md)