---
title: "関連アプリケーションを有効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], enabling
- managing [SSO applications], enabling
- enabling, applications [SSO]
ms.assetid: 81c94e1b-cd3d-482e-9a78-9b1476af9e5f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca2e0d03b233ffdf6bc0db759133062928aa22ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-an-affiliate-application"></a>関連アプリケーションを有効にする方法
MMC スナップインまたはコマンド ラインを使用して、指定した関連アプリケーションを有効にすることができます。  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a>MMC スナップインを使用して関連アプリケーションを有効にするには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  関連アプリケーションを右クリックし、をクリックして**を有効にする**です。  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a>コマンド ラインを使用して関連アプリケーションを有効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – enableapp *\<アプリケーション名 >***ここで、 \<*アプリケーション名*> 関連アプリケーションの名前を指定します。有効にします。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションを作成する方法](../core/how-to-create-an-affiliate-application.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)