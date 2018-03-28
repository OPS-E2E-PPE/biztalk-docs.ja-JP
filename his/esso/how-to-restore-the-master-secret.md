---
title: マスター シークレットを復元する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b331c9c5-ca90-4a05-b3f6-59db88bf73dc
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5e640f2762ed9f9cc03a7795062c98a6aa76a59d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-restore-the-master-secret"></a>マスター シークレットを復元する方法
データの回復手順の一部として、既存のデータを再利用するマスター シークレットを復元する必要があります。 このタスクを実行するには、Windows 管理者であり、シングル サインオン (SSO) 管理者であるアカウントを使用して、マスタ シークレット サーバーにログオンする必要があります。  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレットを復元するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。  
  
2.  ENTSSO Microsoft 管理コンソール (MMC) スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**マスター シークレットの復元**です。  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a>コマンド ラインを使用してマスター シークレットを復元するには  
  
1.  **開始** メニューのをクリックして**プログラム**、クリックして**アクセサリ**です。 右クリック **コマンド プロンプト**, 、クリックして **実行付けて**します。  
  
2.  適切な管理者を選択し、クリックして **OK**します。  
  
3.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
4.  型`ssoconfig –restoresecret <restore file>`ここで、 *\<ファイルを復元 >*はマスター シークレットが格納されているファイルの名前とパス。  
  
## <a name="see-also"></a>参照  
 [マスター シークレットを生成する方法](../esso/how-to-generate-the-master-secret.md)   
 [マスター シークレットをバックアップする方法](../esso/how-to-back-up-the-master-secret.md)   
 [マスター シークレット サーバー](../esso/master-secret-server.md)   
 [マスター シークレットの管理](../esso/managing-the-master-secret.md)