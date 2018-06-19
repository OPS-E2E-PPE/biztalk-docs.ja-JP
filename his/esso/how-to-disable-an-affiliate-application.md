---
title: 関連アプリケーションを無効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7df6e78-6d18-443d-82dc-4351c20a8c4e
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 6bae89d2a05ec34095e0fa2ac3feafc7b88b894e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250926"
---
# <a name="how-to-disable-an-affiliate-application"></a>関連アプリケーションを無効にする方法
MMC スナップインを使用して、または**disableapp**指定された関連アプリケーションを無効にするコマンド。  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a>MMC スナップインを使用して関連アプリケーションを無効にするには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  関連アプリケーションを右クリックし、をクリックし、 **を無効にする**です。  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a>コマンド ラインを使用して関連アプリケーションを無効にするには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssomanage –disableapp <application name>`ここで、 \<*アプリケーション名*> を無効にする関連アプリケーションの名前を指定します。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../esso/sso-affiliate-applications.md)   
 [関連アプリケーションを有効にする方法](../esso/how-to-enable-an-affiliate-application.md)   
 [ユーザー マッピングを管理します。](../esso/managing-user-mappings.md)   
 [関連アプリケーションの管理](../esso/managing-affiliate-applications.md)