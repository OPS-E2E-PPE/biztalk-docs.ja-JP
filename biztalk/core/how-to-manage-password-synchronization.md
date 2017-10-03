---
title: "パスワード同期を管理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2939fd0594c878e3a5f1416d0b1e871b78ba3858
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-password-synchronization"></a>パスワード同期を管理する方法
MMC スナップインまたは SSOMANAGE コマンド ライン ユーティリティを使用すると、SSO 機能を有効または無効にしたり、現在の SSO データベース設定を表示できます。  
  
### <a name="to-manage-features-or-display-settings-using-the-mmc-snap-in"></a>MMC スナップインを使用して機能の管理や設定の表示を行うには  
  
1.  対象の機能またはデータベースを右クリックします。  
  
2.  適切なメニュー項目をクリックします。  
  
### <a name="to-enable-sso-features-using-the-command-line"></a>コマンド ラインを使用して SSO 機能を有効にするには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssomanage-有効にする**Enter キーを押します。  
  
### <a name="to-disable-sso-features-using-the-command-line"></a>コマンド ラインを使用して SSO 機能を無効にするには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssomanage-無効**Enter キーを押します。  
  
### <a name="to-display-current-database-settings-using-the-command-line"></a>コマンド ラインを使用して現在のデータベース設定を表示するには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssomanage-displaydb** Enter キーを押します。  
  
## <a name="see-also"></a>参照  
 [パスワード同期](../core/password-synchronization2.md)