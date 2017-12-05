---
title: "側開始 SSO を有効にし、ホストを無効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host initiated SSO, disabling
- disabling, host initiated SSO
- enabling, host initiated SSO
- host initiated SSO, enabling
ms.assetid: a11d314a-6ff9-4d0a-89c3-c412541c2cec
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1e5783893bbc9091d0a5f1fb3f116b17413bc5d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-and-disable-host-initiated-sso"></a>側開始 SSO を有効にし、ホストを無効にする方法
既定では、ホスト側開始シングル サインオンはシングル サインオン システムで有効になっていないため、SSO 管理者が有効化する必要があります。  
  
### <a name="to-enable-host-initiated-sso-using-the-mmc-snap-in"></a>MMC スナップインを使用してホスト側開始 SSO を有効にするには  
  
1.  **開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**プロパティ**です。  
  
4.  クリックして、**オプション**タブです。  
  
5.  選択、**有効にするホスト側開始 SSO**ボックスし、をクリックして**OK**です。  
  
### <a name="to-enable-host-initiated-sso-using-the-command-line"></a>コマンド ラインを使用してホスト側開始 SSO を有効にするには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssomanage-hisso を有効にする**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
 SSO を無効にすると SSO システム全体に適用されるので、ホスト側開始 SSO に関連するすべての操作が無効になります。  
  
#### <a name="to-disable-host-initiated-sso-using-the-mmc-snap-in"></a>MMC スナップインを使用してホスト側開始 SSO を無効にするには  
  
1.  **開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**プロパティ**です。  
  
4.  クリックして、**オプション**タブです。  
  
5.  クリア、**有効にするホスト側開始 SSO**ボックスし、をクリックして**OK**です。  
  
#### <a name="to-disable-host-initiated-sso-using-the-command-line"></a>コマンド ラインを使用してホスト側開始 SSO を無効にするには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssomanage-hisso を無効にする**に応じて。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ホスト側開始 SSO](../core/host-initiated-sso.md)