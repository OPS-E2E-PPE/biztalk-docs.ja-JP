---
title: マスター シークレットを復元する方法 |Microsoft Docs
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
ms.openlocfilehash: 04852571be9294ee62733bd78c884b407f2fb5b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384133"
---
# <a name="how-to-restore-the-master-secret"></a>マスター シークレットを復元する方法
データ回復の手順の一環として、既存のデータを再使用するマスター シークレットを復元する必要があります。 このタスクを実行するためには、Windows 管理者であり、SSO 管理者であるアカウントを使用してマスター シークレット サーバーにログオンする必要があります。  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレットを復元するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリックして**システム**、 をクリックし、**シークレットの復元**します。  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a>コマンドラインを使用してマスター シークレットを復元するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、順にクリックします**アクセサリ**します。 右クリックして**コマンド プロンプト**、 をクリックし、**として実行しています**。  
  
2.  適切な管理者を選択し、クリックして**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssoconfig – restoresecret と入力\<ファイル復元\>** ここで、 **\<ファイルを復元\>** マスター シークレットがファイルの名前とパスには格納されています。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)   
 [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)   
 [マスター シークレット サーバー](../core/master-secret-server.md)   
 [マスター シークレットの管理](../core/managing-the-master-secret.md)