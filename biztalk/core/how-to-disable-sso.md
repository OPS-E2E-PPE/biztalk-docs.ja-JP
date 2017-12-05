---
title: "SSO を無効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disabling, SSO
- SSO, disabling
- managing [SSO], disabling
ms.assetid: 0fe4f87a-d7c2-4af6-afee-1065bc4a5285
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7096a9c77dda72bbf0aea3ec76423c759fa90df
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-disable-sso"></a>SSO を無効にする方法
MMC スナップインまたはコマンド ラインを使用して、シングル サインオン システムを全面的に無効にすることができます。  
  
 最新のグローバル情報を取得するために SSO データベースをポーリングするので、すべてのシングル サインオン サーバーが無効になるまでに、若干の遅延が発生します。  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-mmc-snap-in"></a>MMC スナップインでエンタープライズ シングル サインオンを無効にするには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**を無効にする**です。  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-command-line"></a>コマンド ラインでエンタープライズ シングル サインオンを無効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – disablesso**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO を有効にする方法](../core/how-to-enable-sso.md)   
 [SSO の使用](../core/using-sso.md)