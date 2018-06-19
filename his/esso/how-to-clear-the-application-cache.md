---
title: アプリケーション キャッシュをクリアする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a897791-d32f-46a4-8c5d-2b2161e92bd9
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 24954e8314bc94d4570eb57acbf1d4b03bebb65b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250942"
---
# <a name="how-to-clear-the-application-cache"></a>アプリケーション キャッシュをクリアする方法
MMC スナップインを使用して、または**purgecache** (すべての情報、関連アプリケーションに関連付けられている) の資格情報のキャッシュの内容を削除するコマンドのすべてのシングル サインオン (SSO) サーバー上で指定されたアプリケーション。  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a>MMC スナップインを使用してキャッシュをクリアするには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  クリックして **関連アプリケーション**します。  
  
4.  結果ウィンドウで 関連アプリケーションを右クリックし、をクリックして **クリア**します。  
  
### <a name="to-clear-the-cache-using-the-command-line"></a>コマンド ラインを使用してキャッシュをクリアするには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssomanage –purgecache <application name>`ここで、 \<*アプリケーション名*> 用のキャッシュを消去する関連アプリケーションの名前を指定します。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../esso/sso-affiliate-applications.md)   
 [関連アプリケーションの管理](../esso/managing-affiliate-applications.md)