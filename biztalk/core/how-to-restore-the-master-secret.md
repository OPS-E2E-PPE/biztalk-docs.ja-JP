---
title: マスター シークレットを復元する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], restoring
- Master Secret server, restoring
- restoring, Master Secret server
ms.assetid: 68e133c5-4591-4d76-9a3b-c9564ff1aa60
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9241c8d9c5f6e41f47199211d0215c16526951d6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25970912"
---
# <a name="how-to-restore-the-master-secret"></a>マスター シークレットを復元する方法
データ復元処理の一環として、既存のデータを再利用するためにマスター シークレットの復元が必要になる場合があります。 この作業を行うには、Windows 管理者であり SSO 管理者でもあるアカウントを使用してマスター シークレット サーバーにログオンする必要があります。  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレットを復元するには  
  
1.  **開始**  メニューのをクリックして **すべてのプログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  右クリック **システム**, 、クリックして **シークレットの復元**します。  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a>コマンド ラインを使用してマスター シークレットを復元するには  
  
1.  **開始**  メニューのをクリックして **すべてのプログラム**, 、 をクリックし、 **アクセサリ**します。 右クリック **コマンド プロンプト**, 、クリックして **実行付けて**します。  
  
2.  適切な管理者を選択し、クリックして **OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssoconfig – restoresecret と入力\<ファイルを復元\>** ここで、 **\<ファイルを復元\>** マスター シークレットがファイルの名前とパスには格納されています。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)   
 [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)   
 [マスター シークレット サーバー](../core/master-secret-server.md)   
 [マスター シークレットの管理](../core/managing-the-master-secret.md)