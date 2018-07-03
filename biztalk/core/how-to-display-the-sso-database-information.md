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
ms.openlocfilehash: 8371ccae36fe66051178da5baa55360e9fcf8406
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010019"
---
# <a name="how-to-display-the-sso-database-information"></a>SSO データベース情報を表示する方法
SSO データベース情報は、MMC スナップインまたはコマンド ライン (ssomanage) ユーティリティを使用して表示できます。  
  
### <a name="to-display-the-sso-database-information-using-the-mmc-snap-in"></a>MMC スナップインを使用して SSO データベース情報を表示するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリックして**システム**、 をクリックし、**プロパティ**します。  
  
4.  タブをクリックし、**システム プロパティ**ダイアログ ボックスに SSO データベース情報を表示します。  
  
### <a name="to-display-the-sso-database-information-using-the-command-line"></a>コマンド ラインを使用して SSO データベース情報を表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – displaydb**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-display-the-sso-database-the-sso-server-is-connected-to-using-the-command-line"></a>コマンド ラインを使用して SSO サーバーの接続先 SSO データベースを表示するには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型**ssomanage – showdb**します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
   次の表では、上記の手順で返される値について説明します。  
  
|プロパティ|値|  
|--------------|-----------|  
|SQL Server|**\<SQL Server 名\>**|  
|シングル サインオン データベース|**\<SQL Server データベース名\>**|  
|シングル サインオン シークレット サーバー名|**\<シングル サインオン サーバーの名前\>**|  
|シングル サインオン管理者アカウント|ドメイン\アカウント名|  
|シングル サインオン関連管理者アカウント|ドメイン\アカウント名|  
|削除したアプリケーションの監査テーブルのサイズ (監査エントリの数)|1,000 (既定値)|  
|削除したユーザー マッピングの監査テーブルのサイズ (監査エントリの数)|1,000 (既定値)|  
|外部資格情報参照の監査テーブルのサイズ (監査エントリの数)|1,000 (既定値)|  
|チケットのタイムアウト (分)|2 (既定)<br /><br /> この値には、1 ～ 525,600 の整数値を指定できます。|  
|資格情報キャッシュ タイムアウト (分)|60 (既定値)|  
|シングル サインオンの状態|有効/無効|  
|[許可されたチケット]|Yes/no (既定値)|  
|[チケットの検証]|Yes (既定値)/no|  
  
## <a name="see-also"></a>参照  
 [SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md)   
 [SSO の使用](../core/using-sso.md)