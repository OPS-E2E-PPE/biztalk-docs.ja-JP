---
title: アプリケーション キャッシュをクリアする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 184569a3eed693a7b699b2ad14cfb8461cc496e8
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25968640"
---
# <a name="how-to-clear-the-application-cache"></a>アプリケーション キャッシュをクリアする方法
MMC スナップインまたはコマンド ラインを使用して、すべてのシングル サインオン サーバーの指定したアプリケーションの、資格情報キャッシュの内容 (関連アプリケーションに関連付けられたすべての情報) を削除できます。  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a>MMC スナップインを使用してキャッシュをクリアするには  
  
1.  **開始**  メニューのをクリックして **すべてのプログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  クリックして **関連アプリケーション**します。  
  
4.  結果ウィンドウで 関連アプリケーションを右クリックし、をクリックして **クリア**します。  
  
### <a name="to-clear-the-cache-using-the-command-line"></a>コマンド ラインを使用してキャッシュをクリアするには  
  
1.  **開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 **ssomanage – purgecache *\<アプリケーション名\>* * *、どこで\<* アプリケーション名*\>関連アプリケーションの名前を指定します。キャッシュを消去します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)