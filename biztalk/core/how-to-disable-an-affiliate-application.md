---
title: 関連アプリケーションを無効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, applications
- managing [SSO applications], disabling
- applications [SSO], disabling
ms.assetid: febf1687-f0d0-4f87-b462-23535bbddf6d
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09efa7dd00f563b8b02469909d2105d443438e95
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-disable-an-affiliate-application"></a>関連アプリケーションを無効にする方法
MMC スナップインまたはコマンド ラインを使用して、指定した関連アプリケーションを無効にすることができます。  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a>MMC スナップインを使用して関連アプリケーションを無効にするには  
  
1.  **開始**  メニューのをクリックして **プログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  関連アプリケーションを右クリックし、をクリックし、 **を無効にする**です。  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a>コマンド ラインを使用して関連アプリケーションを無効にするには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、し、入力 **cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 **ssomanage – disableapp *\<アプリケーション名\>* * *、どこで\<*アプリケーション名*\>関連アプリケーションの名前を指定します。無効にします。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)