---
title: アプリケーション キャッシュをクリアする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- caching, applications
- managing [SSO applications], clearing cache
- applications [SSO], caching
ms.assetid: 6230b9a4-c7b8-47b4-854b-12853d9bf5b0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1a1405c3c4a024d7347e85be7abde432f693182
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387001"
---
# <a name="how-to-clear-the-application-cache"></a>アプリケーション キャッシュをクリアする方法
すべてのシングル サインオン サーバーの指定したアプリケーションの資格情報のキャッシュ (すべての情報、関連アプリケーションに関連付けられている) の内容を削除するのに MMC スナップインまたはコマンドラインを使用できます。  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a>MMC スナップインを使用してキャッシュをクリアするには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  クリックして**関連アプリケーション**します。  
  
4.  結果ウィンドウで、関連アプリケーションを右クリックし、をクリックして**クリア**します。  
  
### <a name="to-clear-the-cache-using-the-command-line"></a>コマンドラインを使用してキャッシュをクリアするには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型<strong>ssomanage – purgecache *\<アプリケーション名\></strong><em>ここで、 \<</em>アプリケーション名*\>名前を指定します関連アプリケーションのキャッシュをクリアすることが。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)