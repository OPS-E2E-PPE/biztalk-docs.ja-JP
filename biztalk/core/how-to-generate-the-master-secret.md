---
title: マスター シークレットを生成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, generating
- managing [Master Secret server], generating
ms.assetid: 5512a8ee-bc5b-4fe4-90c7-41e3baaa723b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2104dae9d01ef56d4e0d99a2af887db8c68131e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337704"
---
# <a name="how-to-generate-the-master-secret"></a>マスター シークレットを生成する方法
このタスクを実行するために、マスタ シークレット サーバーで管理者権限が必要です。 さらに、マスター シークレット サーバーからこのタスクを実行する必要があります。  
  
 エンタープライズ シングル サインオンをインストールする最初のサーバーでは、マスター シークレット サーバーになります。  
  
> [!IMPORTANT]
>  SSO システムに 1 つだけのマスター シークレット サーバーがあります。  
> 
> [!NOTE]
>  エンタープライズ シングル サインオンがインストールされている場合の一部として、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成ウィザードの一部としてインストールでは、マスター シークレットが生成されます。 のみ、新しいマスター シークレットを生成する場合は、このタスクを実行する必要があります。  
  
### <a name="to-generate-the-master-secret-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレットを生成するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、 をクリックし、**シークレットの生成**します。  
  
### <a name="to-generate-the-master-secret-using-the-command-line"></a>コマンドラインを使用してマスター シークレットを生成するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssoconfig – generateSecret \<*バックアップ ファイル*\>** ここで、 \<*バックアップ ファイル*\>の名前を指定しますマスター シークレットを含むファイルです。  
  
     作成したファイルを保護するパスワードを入力するように促されます。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)   
 [マスター シークレット サーバー](../core/master-secret-server.md)   
 [マスター シークレットの管理](../core/managing-the-master-secret.md)