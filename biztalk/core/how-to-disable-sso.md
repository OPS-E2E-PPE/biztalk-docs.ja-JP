---
title: SSO を無効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, SSO
- SSO, disabling
- managing [SSO], disabling
ms.assetid: 0fe4f87a-d7c2-4af6-afee-1065bc4a5285
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c14f83d4130153f7066b542702007bf9f704387
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338080"
---
# <a name="how-to-disable-sso"></a>SSO を無効にする方法
MMC スナップインまたはコマンドラインを使用して、全体でシングル サインオン システムを無効にできます。  
  
 ありますすべてのシングル サインオン サーバーを無効にする、しばらく時間がかかるように、最新のグローバル情報を SSO データベースにポーリングします。  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-mmc-snap-in"></a>エンタープライズ シングル サインオン、MMC スナップインを使用して無効にするには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、 をクリックし、**を無効にする**します。  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-command-line"></a>エンタープライズ シングル サインオン、コマンドラインを使用して無効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – disablesso**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO を有効にする方法](../core/how-to-enable-sso.md)   
 [SSO の使用](../core/using-sso.md)