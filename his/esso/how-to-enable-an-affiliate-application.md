---
title: 関連アプリケーションを有効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 051bc35f-55e6-4811-9559-b1bb66a570ce
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 53dcd9886bc808f84b112146971a6f9519c404e2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-enable-an-affiliate-application"></a>関連アプリケーションを有効にする方法
MMC スナップインを使用することができます、または**enableapp**コマンドを指定された関連アプリケーションを有効にします。  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a>MMC スナップインを使用して関連アプリケーションを有効にするには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  関連アプリケーションを右クリックし、をクリックし、 **を有効にする**です。  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a>コマンド ラインを使用して関連アプリケーションを有効にするには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssomanage –enableapp <application name>`ここで、 \<*アプリケーション名*> を有効にする関連アプリケーションの名前を指定します。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../esso/sso-affiliate-applications.md)   
 [関連アプリケーションを作成する方法](../esso/how-to-create-an-affiliate-application.md)   
 [ユーザー マッピングを管理します。](../esso/managing-user-mappings.md)   
 [関連アプリケーションの管理](../esso/managing-affiliate-applications.md)