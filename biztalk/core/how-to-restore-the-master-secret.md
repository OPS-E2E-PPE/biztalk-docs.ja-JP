---
title: "マスター シークレットを復元する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], restoring
- Master Secret server, restoring
- restoring, Master Secret server
ms.assetid: 68e133c5-4591-4d76-9a3b-c9564ff1aa60
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2550d8e1ea0ad45147b2f27daef7244f6c18770b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-restore-the-master-secret"></a>マスター シークレットを復元する方法
データ復元処理の一環として、既存のデータを再利用するためにマスター シークレットの復元が必要になる場合があります。 この作業を行うには、Windows 管理者であり SSO 管理者でもあるアカウントを使用してマスター シークレット サーバーにログオンする必要があります。  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレットを復元するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**シークレットの復元**です。  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a>コマンド ラインを使用してマスター シークレットを復元するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、クリックして**アクセサリ**です。 右クリック**コマンド プロンプト**、クリックして**として実行しています.**.  
  
2.  適切な管理者の場合を選択し、クリックして**OK**です。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssoconfig – restoresecret と入力\<ファイルを復元 >**ここで、 **\<ファイルを復元 >**はマスター シークレットが格納されているファイルの名前とパス。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)   
 [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)   
 [マスター シークレット サーバー](../core/master-secret-server.md)   
 [マスタ シークレットの管理](../core/managing-the-master-secret.md)