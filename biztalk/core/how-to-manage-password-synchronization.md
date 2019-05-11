---
title: パスワード同期を管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], managing
- managing [SSO], disabling features
- managing [SSO], enabling features
- Password Synchronization [SSO], SSOMANAGE command line utility
- SSO database, SSOMANAGE command line utility
- managing, Password Synchronization [SSO]
- SSO database, database settings
- SSOMANAGE command line utility
ms.assetid: 033e63f2-e5b0-4400-99c3-145679d9b84e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df4030becd9dfe86abfaa5745cb72e42c0a4b0c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384651"
---
# <a name="how-to-manage-password-synchronization"></a>パスワード同期を管理する方法
MMC スナップインまたは SSOMANAGE コマンド ライン ユーティリティを使用して有効または SSO の機能を無効にして、SSO データベースの現在の設定を表示します。  
  
### <a name="to-manage-features-or-display-settings-using-the-mmc-snap-in"></a>機能の管理または MMC スナップインを使用して設定を表示するには  
  
1.  適切な機能またはデータベースを右クリックします。  
  
2.  適切なメニュー項目をクリックします。  
  
### <a name="to-enable-sso-features-using-the-command-line"></a>コマンドラインを使用して SSO 機能を有効にするには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssomanage-有効にする**Enter キーを押します。  
  
### <a name="to-disable-sso-features-using-the-command-line"></a>コマンドラインを使用して SSO 機能を無効にするには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssomanage-を無効にする**Enter キーを押します。  
  
### <a name="to-display-current-database-settings-using-the-command-line"></a>コマンドラインを使用して現在のデータベース設定を表示するには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssomanage-displaydb** Enter キーを押します。  
  
## <a name="see-also"></a>参照  
 [パスワード同期](../core/password-synchronization2.md)