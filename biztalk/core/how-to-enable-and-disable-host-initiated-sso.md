---
title: 側開始 SSO を有効にし、ホストを無効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host initiated SSO, disabling
- disabling, host initiated SSO
- enabling, host initiated SSO
- host initiated SSO, enabling
ms.assetid: a11d314a-6ff9-4d0a-89c3-c412541c2cec
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 312d5c295981bf7af5ec4ed45140fa6c915a7ae6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337966"
---
# <a name="how-to-enable-and-disable-host-initiated-sso"></a>側開始 SSO を有効にし、ホストを無効にする方法
既定ではホスト側開始シングル サインオン、シングル サインオン システムを有効にしないと、SSO 管理者によって有効にする必要があります。  
  
### <a name="to-enable-host-initiated-sso-using-the-mmc-snap-in"></a>側開始 SSO を MMC スナップインを使用してホストを有効にします。  
  
1.  **開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリックして**システム**、 をクリックし、**プロパティ**します。  
  
4.  をクリックして、**オプション**タブ。  
  
5.  選択、**有効にするホスト側開始 SSO**ボックスし、をクリックして**OK**します。  
  
### <a name="to-enable-host-initiated-sso-using-the-command-line"></a>側開始 SSO をコマンドラインを使用してホストを有効にします。  
  
1. **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2. **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4. 型**ssomanage-hisso を有効にする**します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
   SSO を無効にすると、SSO システム全体に適用され、ホスト側開始 SSO に関連するすべての操作がオフになります。  
  
#### <a name="to-disable-host-initiated-sso-using-the-mmc-snap-in"></a>側開始 SSO を MMC スナップインを使用してホストを無効にします。  
  
1.  **開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリックして**システム**、 をクリックし、**プロパティ**します。  
  
4.  をクリックして、**オプション**タブ。  
  
5.  クリア、**有効にするホスト側開始 SSO**ボックスし、をクリックして**OK**します。  
  
#### <a name="to-disable-host-initiated-sso-using-the-command-line"></a>側開始 SSO をコマンドラインを使用してホストを無効にします。  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssomanage-hisso を無効にする**に応じて。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ホスト側開始 SSO](../core/host-initiated-sso.md)